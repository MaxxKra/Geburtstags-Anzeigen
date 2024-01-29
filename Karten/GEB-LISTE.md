# GEBURTSTAGS LISTE - KARTE


Die Geburtstags-Liste-Karte zeigt im der normalen Ansicht aktuelle Geburtstage an.
Da es sich um die `custom:expander-card` handelt, hat man die Möglichkeit eine Dropdown-Liste zu öffnen. Auf dieser werden alle Termine des `sensor.geburtstage_liste` angezeigt. 


<br>

Beispiel:
![Beispiel](https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Dashboard_Karte_Geb-Liste.png)
  
<br>

Positioniert ist diese Karte am Dashboard, welches mit der Layout-Card erstellt wurde, auf `area: card3`.

<br>

Beispiel:
![Beispiel](https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Dashboard_Layout_Aufteilung.png)
  
<br>

Verwendet wurde für diese Karte die `custom:expander-card` Karte sowie `custom:button-card`.


Die `custom:expander-card` hat, was unbedingt zu erwähnen ist, ein Problem wenn eine Titel-Karte eingetragen wird. Dieses Problem zeigt sich aber nur bei der Erstellung der Karte, indem zwischen Visuellem und YAML Editor umgeschaltet wird. 


### CODE GEBURTSTAGS LISTE KARTE

```yaml
type: custom:expander-card
gap: 0.1em
padding: 2em
clear: true
title: Expander
overlay-margin: 4em
child-padding: 0.1em
button-background: var(--primary-color)
cards:
  - type: custom:button-card
    layout: name_state
    show_icon: null
    name: |
      [[[
          const alterprefix = 'Alter';
          const events = states['sensor.geburtstage_liste'].attributes.scheduled_events;
          let result = `<span style='font-size: 1.2em; color: var(--primary-color);'>
          <b>Es sind ${states['sensor.geburtstage_liste'].state} Geburtstage in den <br>nächsten 2 Monaten</b></span><br><br>`;

          for (const e of events) {
              const formattedText = `
                  ${e.Datum}: <span style='color: var(--primary-color); font-size: 1.2em;'>${e.Name}&nbsp;</span><br>
                  Geburtstag: ${e.Geburtstag}<br>
                  ${alterprefix}: ${e.Alter}<br>
                  Hinweis: ${e.Hinweis}<br><br>
              `.trim();

              result += `<span style='color: var(--secondary-color);'>${formattedText}&nbsp;</span>`;
          }

          return result;
      ]]]
    styles:
      name:
        - color: white
        - font-family: Arial Rounded MT
        - font-size: 1em
        - text-align: start
        - justify-self: start
      card:
        - background: transparent
        - border: none
title-card:
  type: custom:button-card
  name: |
    [[[
        const alterprefix = 'Alter';
        const events = states['sensor.geburtstag_heute'].attributes.scheduled_events;
        let result = `<span style='font-size: 1.2em; color: var(--primary-color);'>
        <b>Es sind ${states['sensor.geburtstage_liste'].state} Geburtstage <br>in den nächsten 2 Monaten</b>
        </span><br><br><b>Geburtstag Heute:</b><br><br>`;
        
        for (let i = 0; i < events.length; i++) {
            const e = events[i];
            const formattedText = `
                <span style='color: var(--primary-color); font-size: 1.2em;'>${e.Name}&nbsp;</span><br>
                ${alterprefix}: ${e.Alter}<br>
            `.trim();

            result += `<span style='color: var(--secondary-color);'>${formattedText}&nbsp;</span>`;
            
            if (i < events.length - 1) {
                // Nur ein <br> für alle außer dem letzten Eintrag
                result += '<br>';
            }
        }

        return result;
    ]]]
  styles:
    name:
      - color: white
      - font-family: Arial Rounded MT
      - font-size: 1em
      - text-align: start
      - justify-self: start
    card:
      - background: transparent
      - border: none
view_layout:
  grid-area: card3
title-card-button-overlay: true
expanded: false
```