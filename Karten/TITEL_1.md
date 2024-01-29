# TITEL 1 - KARTE


Die erste Titel-Karte ist die Darstellung einer Textzeile eines ausgewählten Geburtstags aus der Anniversaries-Integration.
In meinem Beispiel handelt es sich um den Geburtstag von Home Assistant.

<br>

Beispiel:
![Beispiel](https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Dashboard_Karte_Titel1.png)
  
<br>

Positioniert ist diese Karte am Dashboard, welches mit der Layout-Card erstellt wurde, auf `area: titel1`.

<br>

Beispiel:
![Beispiel](https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Dashboard_Layout_Aufteilung.png)
  
<br>

Verwendet wurde für diese Karte wieder die `custom:button-card` und diverse Template Sensoren. Als Tap-Action habe ich für mich den Schalter für das Dashboard-Vollbild eingetragen. Dies sollte bei Verwendung der Karte abgeändert werden.


### CODE TITEL 1 KARTE

```yaml
type: custom:button-card
aspect_ratio: 18/1
show_icon: false
name: |
  [[[
    // Konstanten definieren
    const CardTextColor = 'var(--primary-text-color)';
    const CardStateColor = 'var(--primary-color)';
    const geburtstagSensor = states['sensor.geburtstag_home_assistant'];
    const originalDateStr = geburtstagSensor.attributes.next_date;
    const originalDate = new Date(originalDateStr);
    const newDateFormat = `${originalDate.getDate().toString().padStart(2, '0')}.${(originalDate.getMonth() + 1).toString().padStart(2, '0')}.${originalDate.getFullYear()}`;
    const yearsAtAnniversary = geburtstagSensor.attributes.years_at_anniversary;
    const remainingDays = geburtstagSensor.state;
    const soonAnniversaryText = remainingDays <= 5 ? 'Nur noch' : 'Noch';
    const remainingDaysText = remainingDays === 1 ? 'Tag' : 'Tage';

    // Ergebnis zurückgeben
    return `<div style='display: flex;display: -webkit-flex;'>
                <span style='color: ${CardTextColor};'>
                  Der Geburtstag von &nbsp
                </span>  
                <span style='color: ${CardStateColor};'>  ${geburtstagSensor.attributes.friendly_name}&nbsp 
                </span>
                <span style='color: ${CardTextColor};'>
                ist am &nbsp 
                </span> 
                <span style='color: ${CardStateColor};'> ${newDateFormat}&nbsp 
                </span>
                <span style='color: ${CardTextColor};'> und es wird &nbsp 
                </span> 
                <span style='color: ${CardStateColor};'> ${yearsAtAnniversary}&nbsp 
                </span>
                <span style='color: ${CardTextColor};'> Jahre alt. ${soonAnniversaryText} &nbsp 
                </span> 
                <span style='color: ${CardStateColor};'> ${remainingDays}&nbsp 
                </span>
                <span style='color: ${CardTextColor};'> ${remainingDaysText} warten!
                </span>
            </div>`;
  ]]]
tap_action:
  action: call-service
  service: input_boolean.toggle
  service_data:
    entity_id: input_boolean.youtube_vollbild
styles:
  name:
    - font-size: 2em
    - font-family: Arial Rounded MT
  card:
    - background: transparent
    - border: none
view_layout:
  grid-area: titel1
```
