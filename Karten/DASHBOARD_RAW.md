# DASHBOARD RAW-KONFIGURATIONS EDITOR CODE


Hier ist der gesamte Code incl. Kiosk-Mode und dem Layout meines Geburtstags-Dashboards zum Kopieren.

Für den Kiosk-Mode habe ich mir einen Helfer Taster Namens `input_boolean.youtube_vollbild` angelegt.
Dieser ist im Titel (Header) als Tap-Action hinterlegt und schaltet die Seitenleiste sowie die Titelleiste aus und versetzt damit das Dashboard in den Vollbild-Modus.



```yaml
kiosk_mode:
  entity_settings:
    - entity:
        input_boolean.youtube_vollbild: 'on'
      hide_sidebar: true
      hide_header: true
views:
  - title: Geburtstag
    path: geburtstag
    animated_background: aqua
    icon: mdi:cake-layered
    theme: Caule Black Green Glass
    type: custom:grid-layout
    layout:
      grid-template-columns: 6% 20% 6% 17% 17% 2% 30% 2%
      grid-template-rows: auto
      align-items: start
      grid-template-areas: |
        "head head head head head head head head"   
        "titel1 titel1 titel1 titel1 titel1 titel1 titel1 titel1" 
        "titel2 titel2 titel2 titel2 titel2 titel2 titel2 titel2"   
        "card1 card1 card1 card2 card2 card8 card3 card9"   
        "card4 card5 card6 card2 card2 card8 card3 card9"   
        "card7 card7 card7 card2 card2 card8 card3 card9"
    badges: []
    cards:
      - type: custom:button-card
        name: Unser Geburtstags - Dashboard
        aspect_ratio: 24/1
        tap_action:
          action: call-service
          service: input_boolean.toggle
          service_data:
            entity_id: input_boolean.youtube_vollbild
        styles:
          card:
            - background: transparent
            - border: none
            - padding: '-1em'
          name:
            - font-size: 2.2em
            - color: var(--primary-color)
            - font-family: Arial Rounded MT
        view_layout:
          grid-area: head
      - type: custom:button-card
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
        tap_action: none
        styles:
          name:
            - font-size: 2em
            - font-family: Arial Rounded MT
          card:
            - background: transparent
            - border: none
        view_layout:
          grid-area: titel1
      - type: entities
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
      - type: custom:atomic-calendar-revive
        name: Unsere Kalender
        enableModeChange: true
        entities:
          - entity: calendar.geburtstag
            icon: mdi:cake-variant-outline
            color: '#ec6288'
          - entity: calendar.anniversaries
            type: icon
            icon: mdi:home-heart
            color: '#e6bc47'
        firstDayOfWeek: 1
        maxDaysToShow: 60
        refreshInterval: 60
        showDate: true
        showCurrentEventLine: true
        sortByStartTime: true
        dimFinishedEvents: false
        showLastCalendarWeek: true
        disableCalEventLink: true
        disableCalLink: true
        showNoEventsForToday: false
        showProgressBar: true
        showWeekDay: true
        showWeekNumber: true
        disableEventLink: true
        disableLocationLink: true
        showEventIcon: true
        showFullDayProgress: true
        showHiddenText: true
        dateColor: '#f1d7a6'
        timeColor: rgb(119,221,119)
        eventTitleColor: '#cc5500'
        locationLinkColor: rgb(253, 253, 150)
        locationIconColor: rgb(253, 253, 150)
        dayWrapperLineColor: rgba(253, 253, 150, .35)
        descColor: '#f1d7a6'
        eventCalNameColor: '#f1d7a6'
        calGridColor: rgba(253, 253, 150, 0.15)
        calEventBackgroundColor: rgb(194, 59, 0.15)
        calEventSatColor: rgba(12, 56, 100, 0.25)
        calEventSunColor: rgba(12, 56, 100, 0.25)
        calActiveEventBackgroundColor: rgba(128, 206, 225, 0.3)
        defaultCalColor: '#f1d7a6'
        calDayColor: '#f1d7a6'
        nameColor: '#f1d7a6'
        calWeekDayColor: '#f1d7a6'
        calDateColor: '#f1d7a6'
        cardHeight: 100%
        calShowDescription: true
        defaultMode: Calendar
        showDeclined: true
        showLocation: true
        showLoader: true
        hideDuplicates: true
        disableCalLocationLink: true
        compactMode: false
        showMultiDayEventParts: true
        showMultiDay: true
        allDayBottom: true
        offsetHeaderDate: true
        hideFinishedEvents: true
        showCalendarName: false
        showDatePerEvent: false
        showTimeRemaining: false
        hoursOnSameLine: false
        showMonth: true
        titleLength: 0
        startDaysAhead: 0
        sortBy: start
        noEventText: Keine Termine
        noEventsForNextDaysText: Keine Termine in den nächsten Tagen
        hiddenEventText: Termine sind versteckt
        untilText: Bis
        view_layout:
          grid-area: card2
        card_mod:
          style: |
            ha-card {
              border: none;
              background: transparent;
              font-family: Arial Rounded MT;  
              color: white !important;
            }
            .calDay {
              font-size: 1.2vw !important;
              color: var(--primary-color) !important;
              height: 3vw !important;
              max-width: 80px !important;
            }
            .calIcon {
              --mdc-icon-size: 15px !important;
            }
            thead th.cal {
              font-size: 1.2vw !important; !important;
              height: 3vw !important;
            }
      - type: custom:button-card
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
        view_layout:
          grid-area: card1
      - type: custom:expander-card
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
      - type: conditional
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
title: Geburtstag
```