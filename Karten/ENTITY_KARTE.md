# ENTITY - KARTE


Die Entity-Karte zeigt Geburtstage aus dem Anniversaries-Kalender. In diesm Fall sind es 4 Termine welche in der `configuration.yaml` eingetragen wurden.


- sensor.geburtstag_name_1
- sensor.geburtstag_name_2
- sensor.geburtstag_name_3
- sensor.geburtstag_name_4

Diese Sensoren bzw. dessen Namen müssen unbedingt angepasst werden.


Um auch die Attribute dieser Sensoren anzuzeigen, wurde die `custom:secondaryinfo-entity-row` aus HACS verwendet.

<br>

Beispiel:
![Beispiel](https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Dashboard_Karte_Entity.png)
  
<br>

Positioniert ist diese Karte am Dashboard, welches mit der Layout-Card erstellt wurde, auf `area: card5`.

<br>

Beispiel:
![Beispiel](https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Dashboard_Layout_Aufteilung.png)
  
<br>

Verwendet wurde für diese Karte die `entities` Karte sowie `custom:secondaryinfo-entity-row`.


### CODE ENTITY KARTE

```yaml
type: entities
title: Geburtstags Infos
entities:
  - entity: sensor.geburtstag_name_1
    type: custom:secondaryinfo-entity-row
    secondary_info: >-
      Alter:<b style='color:var(--primary-color)'> [[
      sensor.geburtstag_name_1.attributes.years_at_anniversary ]]</b>
  - entity: sensor.geburtstag_name_2
    type: custom:secondaryinfo-entity-row
    secondary_info: >-
      Alter:<b style='color:var(--primary-color)'> [[
      sensor.geburtstag_name_2.attributes.years_at_anniversary ]]</b>
  - entity: sensor.geburtstag_name_3
    type: custom:secondaryinfo-entity-row
    secondary_info: >-
      Alter:<b style='color:var(--primary-color)'> [[
      sensor.geburtstag_name_3.attributes.years_at_anniversary ]]</b>
  - entity: sensor.geburtstag_name_4
    type: custom:secondaryinfo-entity-row
    secondary_info: >-
      Alter:<b style='color:var(--primary-color)'> [[
      sensor.geburtstag_name_4.attributes.years_at_anniversary ]]</b>
state_color: true
view_layout:
  grid-area: card5
card_mod:
  style: |
    ha-card {
      border: none;
      background: transparent;
      font-family: Arial Rounded MT;
      margin-top: 6px
    }
```
