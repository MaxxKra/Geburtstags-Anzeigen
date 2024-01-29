# TITEL 2 - KARTE


Die zweite Titel-Karte ist die Darstellung einer Textzeile der aktuellen Geburtstage aus dem Geburtstags Kalender
Diese Textzeile ist als Laufschrift eingerichtet und wird über eine `Bedingungs-Karte` nur angezeigt, wenn tatsächlich am heutigen Tag Geburtstage im Kalender eingetragen sind.

<br>

Beispiel:
![Beispiel](https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Dashboard_Karte_Titel2.gif)
  
<br>

Positioniert ist diese Karte am Dashboard, welches mit der Layout-Card erstellt wurde, auf `area: titel2`.

<br>

Beispiel:
![Beispiel](https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Dashboard_Layout_Aufteilung.png)
  
<br>

Verwendet wurde für diese Karte wieder die `custom:button-card` und die `conditional` Bedingungs Karte. 


### CODE TITEL 2 KARTE

```yaml
type: conditional
conditions:
  - condition: numeric_state
    entity: sensor.geburtstag_heute
    above: 0
card:
  type: custom:button-card
  entity: sensor.mein_dashboard_datum
  aspect_ratio: 20/1
  show_icon: false
  name: |
    [[[return `<div style='display: flex;display: -webkit-flex;'>
       <marquee>
       <span style='color: var(--primary-color);'>
       ${states['sensor.geburtstags_text_zeile'].state}&nbsp
       </span>
       </marquee>`]]]
  styles:
    name:
      - font-size: 2em
      - font-family: Arial Rounded MT
    card:
      - background: transparent
      - border: none
      - pointer-events: none
view_layout:
  grid-area: titel2
```
