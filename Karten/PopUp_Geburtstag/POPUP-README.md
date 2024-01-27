# Das Geburtstags-PupUp


Um am Dashboard zu einem bestimmten Zeitpunkt über einen aktuellen Geburtstag informiert zu werden, habe ich ein PopUp erstellt.

Dieses PopUp wird mittels Zeitplan (kann aber auch jeder andere Auslöser sein) aktiviert, und zeigt den Namen und das Alter auf einer Torte.

<br>

Beispiel:
![Beispiel](https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/PopUp_Gebrtstag.gif)
  
<br>

Benutz habe ich dazu:
- custom:popup-card (installiert mit Browser Mod 2)
- input_button.button_geburtstag (Helfer Taste)
- input_button.geburtstag_gelesen (Helfer Taste)
- custom:button-card (HACS Frontend Integration)
- sensor.geburtstags_termine (Angelegter Template Sensor)
- sensor.geburtstags_alter (Angelegter Template Sensor)
- Bild der Torte
<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Torte.png" alt="Example" width="3200"/>


<br>

Der Code für das PopUp kann hier kopiert werden.
Nicht vergessen ihn anzupassen!

```yaml
type: custom:popup-card
title: Geburtstag Heute
entity: input_button.button_geburtstag
dismissable: false
size: normal
style: |-
  --popup-max-width: 1000px;
  --popup-min-width: 600px;
  --mdc-theme-surface: rgba(15,10,10,0.7);
  --popup-border-radius: 0px;
  --border: 4px solid red;
card:
  type: picture-elements
  image: /local/images/birthday/Torte.png
  elements:
    - type: custom:button-card
      entity: sensor.geburtstags_termine
      show_state: true
      show_icon: false
      show_name: false
      styles:
        state:
          - color: var(--primary-color)
          - text-shadow: 1px 1px 2px black, 0 0 10px , 0 0 5px black
          - font-family: Arial Black
          - font-size: 2.5em
          - word-wrap: break-word
        card:
          - background: transparent
          - border: none
          - transform: matrix(1, -0.005, 0.3, 1, 0, 0)
      style:
        top: 45%
        left: 50%
        width: 70%
    - type: custom:button-card
      entity: sensor.geburtstags_alter
      show_state: true
      show_icon: false
      show_name: false
      state:
        - value: UNBEKANNT
          styles:
            state:
              - font-size: 0px
      styles:
        state:
          - color: purple
          - text-shadow: 1px 1px 2px black, 0 0 10px , 0 0 5px black
          - font-family: Goudy Stout
          - font-size: 7em
        card:
          - background: transparent
          - border: none
          - transform: matrix(1, -0.005, 0.3, 1, 0, 0)
      style:
        top: 60%
        left: 50%
        width: 70%
  card_mod:
    style: |
      ha-card {
        background: transparent;
        border: none
      }
right_button_action:
  service: input_button.press
  data:
    entity_id: input_button.geburtstag_gelesen
right_button: GELESEN
card_mod:
  style:
    ha-dialog$: |
      div.mdc-dialog__scrim {
        backdrop-filter: blur(15px) !important;
        -webkit-backdrop-filter: blur(15px) !important;
        background-color: rgba(15,10,10,0.7) !important;
        border-radius: 0px;
      }
    ha-dialog: |
      .content {
        border: 4px solid purple !important;
      }
```