# HELFER UND AUTOMATISIERUNGEN


Um das Pop-Up automatisiert zu öffnen, sind Helfer und Automatisierungen notwendig.
Da ich mit einem Zeitplan, zwei Popups öffne aber immer nur eines angezeigt werden kann, habe ich meine Pop-Ups mit einem `GELESEN-BUTTON` versehen und die Automatisierungen so angepasst, dass das zweite Pop-Up erst geöffnet wird, wenn das erste gelesen wurde.


## HELFER


Ich habe folgende Helfer für mein Müllerinnerungs-PopUp und Geburtstags-PopUp erstellt:


- HELFER ZEITPLAN:    schedule.zeitplan_popup
- HELFER BUTTON:    input_button.button_mullerinnerung
- HELFER BUTTON:    input_button.mullerinnerung_gelesen
- HELFER BUTTON:    input_button.button_geburtstag
- HELFER BUTTON:    input_button.geburtstag_gelesen
- HELFER SWITCH:    input_boolean.schalter_popup



### HELFER IM DETAIL

<br>
<details>

<summary>:arrow_down_small: HELFER IM DETAIL :arrow_down_small:</summary>

<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Helfer_Zeitplan.png" alt="Example" width="600"/>


<br>


<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Helfer_Button_Mullerinnerung.png" alt="Example" width="600"/>


<br>


<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Helfer_PopUp_Mullerinnerung_gelesen.png" alt="Example" width="600"/>


<br>


<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Helfer_Button_Geburtstag.png" alt="Example" width="600"/>


<br>


<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Helfer_PopUp_Geburtstag_gelesen.png" alt="Example" width="600"/>


<br>


<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Helfer_Schalter_PopUp.png" alt="Example" width="600"/>


<br>


</details>
<br>


## AUTOMATISIERUNGEN

Dies sind die Automatisierungen zu den Popups:


- Popup Müllerinnerung
- Button Müllerinnerung
- PopUp Müllerinnerung gelesen
- Popup Geburtstag
- Button Geburtstag
- PopUp Geburtstag gelesen



### AUTOMATISIERUNGEN IM DETAIL

<br>
<details>

<summary>:arrow_down_small: AUTOMATISIERUNGEN IM DETAIL :arrow_down_small:</summary>

```yaml
alias: Popup Müllerinnerung
description: ""
trigger:
  - platform: state
    entity_id:
      - schedule.zeitplan_popup
    from: "off"
    to: "on"
condition:
  - condition: template
    value_template: "{{ states.sensor.mullabholung_heute.state != 'Keine' }}"
action:
  - service: input_button.press
    data: {}
    target:
      entity_id: input_button.button_mullerinnerung
mode: single
```

<br>

```yaml
alias: Button Müllerinnerung
description: ""
trigger:
  - platform: state
    entity_id:
      - input_button.button_mullerinnerung
condition: []
action:
  - service: browser_mod.more_info
    data:
      entity: input_button.button_mullerinnerung
      large: false
      ignore_popup_card: false
      browser_id: SHB-PC_Vivaldi
  - service: input_boolean.turn_on
    target:
      entity_id: input_boolean.schalter_popup
    data: {}
mode: single
```

<br>

```yaml
alias: PopUp Müllerinnerung gelesen
description: ""
trigger:
  - platform: state
    entity_id:
      - input_button.mullerinnerung_gelesen
condition: []
action:
  - service: browser_mod.close_popup
    data:
      browser_id: SHB-PC_Vivaldi
  - service: input_boolean.turn_off
    target:
      entity_id: input_boolean.schalter_popup
    data: {}
mode: single
```

<br>

```yaml
alias: Popup Geburtstag
description: ""
trigger:
  - platform: state
    entity_id:
      - schedule.zeitplan_popup
    from: "off"
    to: "on"
    for:
      hours: 0
      minutes: 0
      seconds: 5
  - platform: state
    entity_id:
      - input_boolean.schalter_popup
    from: "on"
    to: "off"
condition:
  - condition: and
    conditions:
      - condition: state
        entity_id: input_boolean.schalter_popup
        state: "off"
      - condition: template
        value_template: "{{ states.sensor.geburtstag_heute.state != 'Niemand' }}"
action:
  - delay:
      hours: 0
      minutes: 0
      seconds: 1
      milliseconds: 0
  - service: input_button.press
    data: {}
    target:
      entity_id: input_button.button_geburtstag
mode: single
```

<br>

```yaml
alias: Button Geburtstag
description: ""
trigger:
  - platform: state
    entity_id:
      - input_button.button_geburtstag
condition: []
action:
  - service: browser_mod.more_info
    data:
      entity: input_button.button_geburtstag
      large: false
      ignore_popup_card: false
      browser_id: SHB-PC_Vivaldi
mode: single
```

<br>

```yaml
alias: Popup Geburtstag gelesen
description: ""
trigger:
  - platform: state
    entity_id:
      - input_button.geburtstag_gelesen
condition: []
action:
  - service: browser_mod.close_popup
    data:
      browser_id: SHB-PC_Vivaldi
mode: single
```


</details>
<br>


> NICHT VERGESSEN ALLE SENSOR-DATEN, ENTITÄTEN UND DIE BROWSER_ID ANZUPASSEN!