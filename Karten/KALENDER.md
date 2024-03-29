# KALENDER - KARTE


Die Kalender-Karte ist zur Übersicht aller Geburtstagstermine auf einem Kalender. 

<br>

Beispiel:
![Beispiel](https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Dashboard_Karte_Kalender.png)
  
<br>

Positioniert ist diese Karte am Dashboard, welches mit der Layout-Card erstellt wurde, auf `area: card2`.

<br>

Beispiel:
![Beispiel](https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Dashboard_Layout_Aufteilung.png)
  
<br>

Verwendet wurde für diese Karte die `custom:atomic-calendar-revive` sowie der Geburtstags-Kalender und der Anniversaries-Kalender. 


### CODE KALENDER KARTE


```yaml
type: custom:atomic-calendar-revive
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
  grid-area: Kal
card_mod:
  style: |
    ha-card {
      border: none;
      background: transparent;
      font-family: Arial Rounded MT;  
      color: var(--primary-color) !important;
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
```
