# GEBURTSTAG HEUTE - KARTE


Die Geburtstag-Heute Karte ist zur Anzeige der/des aktuellen Geburtstage/s auf dem Dashboard. 

<br>

Beispiel:
![Beispiel](https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Dashboard_Karte_Geb-Heute.png)
  
<br>

Positioniert ist diese Karte am Dashboard, welches mit der Layout-Card erstellt wurde, auf `area: card1`.

<br>

Beispiel:
![Beispiel](https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Dashboard_Layout_Aufteilung.png)
  
<br>

Verwendet wurde für diese Karte die `custom:button-card` sowie der Geburtstags-Kalender und der Template Sensor `sensor.geburtstags_text_dashboard`. Das verwendete Icon ist im Ordner Dateien zum Download bzw. Kopieren. Nicht vergessen im Code der Karte den Speicherpfad des Bildes anzupassen!

<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/button_re_birthday.png" alt="Example" width="300"/>


### CODE GEBURTSTAG-HEUTE KARTE


```yaml
type: custom:button-card
entity: calendar.geburtstag
layout: icon_label
show_state: false
show_icon: false
show_name: true
show_label: true
show_entity_picture: true
entity_picture: /local/lovelace/icon/button_re_birthday.png
label: Geburtstag heute
name: |
  [[[
      const text = states['sensor.geburtstags_text_dashboard'].state;
      
      if (text && text.includes(';')) {
          const lines = text.split(';').map(line => line.trim());
          const formattedText = lines.join('<br>');
          return `<span style='color: var(--primary-color);'>${formattedText}&nbsp;</span>`;
      } else {
          return `<span style='color: var(--primary-color);'>${text}&nbsp;</span>`;
      }
  ]]]
styles:
  card:
    - background-color: transparent
    - border: none
    - border-radius: 0px
  name:
    - font-size: 1.3vw
    - font-family: Arial Rounded MT
    - white-space: unset
    - text-overflow: unset
    - word-break: break-word
    - margin-top: 2%
    - width: 100%
  label:
    - font-size: 1.2vw
    - font-family: Arial Rounded MT
    - align-self: middle
    - justify-self: start
    - margin-left: '-10%'
    - color: var(--primary-text-color)
  entity_picture:
    - size: 50%
    - margin-left: '-10px'
```