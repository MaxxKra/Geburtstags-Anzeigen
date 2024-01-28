# :wrench: README NOCH IN ARBEIT! :wrench:


# ALLES ÜBER GEBURTSTAGE IN HOME ASSISTANT

Das Anzeigen von Geburtstagen, ebenso wie Termine oder Ereignise in Home Assistant ist keine Hexerei und es gibt verschiedenste Möglichkeiten diese zu integrieren bzw. anzuzeigen. 
Hier sind alle Informationen über Integrationen und Karten welche ich in meinem Smarthome dafür verwende.

<br>

Beispiel:
![Beispiel](https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Dashboard_Ansicht.gif)
  
<br>

### <p align="center">Wenn du Interesse daran hast, mich, meinen Kanal oder meine kreative Arbeit zu unterstützen,<br>freue ich mich über jeglichen Support:
</p>
<p align="center">
  <a href="https://www.buymeacoffee.com/">
    <img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png" alt="Buy Me A Coffee">
  </a>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="https://www.paypal.me/kramlmaxx">
    <img src="https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif" alt="PayPal Donate">
  </a>
</p>

### <p align="center">Danke</p>

<br>

## :one: Verwendete Integrationen:

<!-- CODE ZUM KOPIEREN -->

| **INTEGRATION / Karten** | **WO?** | **LINK** |
| --- | --- | --- |
| Google Kalender | Geräte und Dienste | Home Assistant Standard Integration |
| Anniversaries | HACS | https://github.com/pinkywafer/Anniversaries.git |
| Card Mod | HACS | https://github.com/thomasloven/lovelace-card-mod.git |
| Button Card | HACS |  https://github.com/custom-cards/button-card.git |
| Secondary Info | HACS | https://github.com/custom-cards/secondaryinfo-entity-row.git |
| Atomic Calendar Revive | HACS | https://github.com/totaldebug/atomic-calendar-revive.git |
| Layout Card | HCS |  https://github.com/thomasloven/lovelace-layout-card.git |
| Markdown Card | Lovelace | Home Assistant Standard Karte |
| Expander Card | HACS | https://github.com/Alia5/lovelace-expander-card.git |


<br>


## :two: Anniversaries Integration:

Die erste Integration, welche ich zur Anzeige von unseren Geburtstagen incl. Alter und verbleibenden Tagen bis zum Ereignis verwendet habe, ist [Anniversaries](https://github.com/pinkywafer/Anniversaries.git)

Wie diese Integration zu installieren ist, sieh dir auf der Github Seite von @pinkywafer bzw. anhand meines Videos auf YouTube an.

**A big thank you to @pinkywafer for crafting this top-notch integration. With it, it's a breeze to display my anniversaries!**


Wie ich meine Termine angelegt habe, kannst du dir anhand der folgenden Beschreibungen und Codes ansehen.

### Termine über das UI

Termine sind bei dieser Integration über das UI als das Userinterface in Home Assistant unter Geräte&Dienste ganz leicht hinzuzufügen. Eine Schritt für Schritt - Anleitung kannst du dir im Dropdownmennü ansehen.
<details>

<summary>:arrow_down_small: Termine erstellen über das UI :arrow_down_small:</summary>


<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Anniversaries/HA_Int_1.png" alt="Example" width="300"/>

<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Anniversaries/HA_Int_2.png" alt="Example" width="800"/>

<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Anniversaries/HA_Int_3.png" alt="Example" width="600"/>

<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Anniversaries/HA_Int_4.png" alt="Example" width="600"/>

<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Anniversaries/HA_Int_5.png" alt="Example" width="800"/>

</details>


Eine andere Möglichkeit ist das Erstellen von Terminen in der `configuration.yaml`.
Für mich und meine Familienmitglieder habe ich das auf diese Art eingerichtet.

<details>


### Termine in der Configurtation.yaml

<summary>:arrow_down_small: Termine erstellen in der configuration.yaml :arrow_down_small:</summary>

```yaml
#-----------------------------------------------------------  
# Geburtstage Familie
#-----------------------------------------------------------
anniversaries:
  sensors:
  - name: Name 1
    date: '1978-03-12'
    id_prefix: geburtstag_
    days_as_soon: 5
    unit_of_measurement: Tage
    icon_normal: mdi:face-man
  - name: Name 2
    date: '1979-04-16'
    id_prefix: geburtstag_
    days_as_soon: 5
    unit_of_measurement: Tage
    icon_normal: mdi:face-woman
  - name: Name 3
    date: '2000-7-21'
    id_prefix: geburtstag_
    days_as_soon: 5
    unit_of_measurement: Tage
    icon_normal: mdi:face-woman-profile
  - name: Name 4
    date: '2005-12-12'
    id_prefix: geburtstag_
    days_as_soon: 5
    unit_of_measurement: Tage
    icon_normal: mdi:face-man-profile

```

</details>

<br>


## :three: Google Kalender Integration:

Die Integration des Google Kalenders ist zwar etwas aufwendiger aber auch für Neueinsteiger in Home Assistant mit der richtigen Anleitung durchführbar. In meinem Video auf Youtube kannst du dir das Schritt für Schritt ansehen.

Hier kommst du zur offiziellen Dokumentation der Google Integration: [GOOGLE INTEGRATION](https://www.home-assistant.io/integrations/google)


Um im späteren Verlauf das Alter mittels Termin-Eintrag zu berechnen, habe ich das Geburtsjahr als Notiz dem Termin beigefügt. In Home Assistant wird diese Notiz als Attribut `description:` angezeigt. Mit dem von mir erstellten Template, ist es auch kein Problem, wenn zusätzlich zu der 4 Stelligen Jahreszahl noch ein Text als Hinweis oder dergleichen in der Termin-Notiz eingetragen wird.


<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Geb_Termin_1.png" alt="Example" width="600"/>

<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Geb_Termin_2.png" alt="Example" width="600"/>

<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Geb_Termin_3.png" alt="Example" width="800"/>

<br>


## :four: Template Geburtstag Heute:

Um nun die Kalender Einträge in Home Assistant auszuwerten, habe ich mehrere Template Sensoren erstellt.

Das Erste, ist ein Template um einen aktuellen Termin (Geburtstag Heute) aus dem Kalender zu suchen und ihn in einen Sensor mit Attributen umzuwandeln. Dieser Sensor hat folgende Werte:

Zustand:
- **Anzahl der Einträge Heute**
Attribute:
- **Name**
- **Datum**
- **Alter**
- **Notiz** (gesamt)
- **Hinweis** (Notiz ohne eventuelle Jahreszahl)


<br>

### BEISPIELEINTRÄGE IM KALENDER


<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Termin_1.png" alt="Example" width="300"/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Termin_2.png" alt="Example" width="300"/>


<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Eintrag_Geb_Heute.png" alt="Example" width="600"/>


<br>

Um diese Werte zu erhalten, ist lediglich das Template in Home Assistant einzutragen. Hier handelt es sich um "Auslöser-basierende-Template-Entitäten", dass bedeutet dieses Template wird durch einen Auslöser aktiviert.

In Falle dieser Templates ist der Auslöser einmal ein Zeitinterval von 15 Minuten und zum Zweiten der Neustart von Home Assistant.

Wenn einer dieser Auslöser eintritt, wird aus dem Google Kalender eine Listen-Abfrage gestartet.

Der Sensor wird dann aus dieser Liste erstellt.

In meinem Fall sind Sensoren und Templates aus der `configuration.yaml` ausgelagert und in separaten Ordnern bzw. Dateien gespeichert. 

Das Template für "Geburtstag Heute" ist in der Dropdown Sektion zum kopieren bereitgestellt:


<details>


### Template Geburtstag Heute

<summary>:arrow_down_small: Template Geburtstag Heute :arrow_down_small:</summary>

```yaml
#
# **Beim Eintrag in configuration.yaml**
#
# template:
#   - trigger:
#
#     action:
#
#     sensor:
#
```

```yaml
#-----------------------------------------------------------  
# **Template Geburtstag Heute**
#-----------------------------------------------------------
trigger:
  - platform: time_pattern
    minutes: /15
  - platform: homeassistant
    event: start
  - platform: state
    entity_id:
      - input_button.trigger_update
action:
  - service: calendar.get_events
    target:
      entity_id: calendar.geburtstag
    data:
      start_date_time: "{{ today_at('00:00:01') }}"
      end_date_time: "{{ today_at('23:59:59') }}"
    response_variable: today_bithday_events
sensor:
  - name: Geburtstag Heute
    unique_id: geburtstag_heute
    state: "{{ today_bithday_events['calendar.geburtstag'].events | count() }}"
    attributes:
      scheduled_events: >
        {%- set HEUER = now().year %}
        {%- set HEUTE = today_at() %}
        {%- set data = namespace(result=[]) %}
        {%- for event in today_bithday_events['calendar.geburtstag'].events %}
          {%- if event.description is defined %}
            {%- set JAHR = event.description | regex_findall('(\d{4})') | first %}
          {%- endif %}
          {%- set START = strptime(event.start, '%Y-%m-%d') %}
          {%- set DATUM = START.strftime("%d.%m.%Y") %}
          {%- set GEBDAT = event.start | as_datetime | as_local %}
          {%- set TAGE = (GEBDAT - HEUTE).days %}
          {%- if TAGE == 0 %}
            {%- set INTAGEN = "Heute" %}
          {%- elif TAGE == 1 %}
            {%- set INTAGEN = "Morgen" %}
          {%- else %}
            {%- set INTAGEN = "in " + TAGE|string + " Tagen" %}
          {%- endif %}
          {%- set NAME = event.summary %}
          {%- if event.description is defined %}
            {%- set NOTIZ = event.description | default('') %}
          {%- else %}
            {%- set NOTIZ = '' %}
          {%- endif %}
          {%- set HINWEIS = NOTIZ | regex_replace('\d{4}', '') | trim %}
          {%- if JAHR is defined %}
            {%- set ALTER = HEUER - JAHR | int %}
          {%- else %}
            {%- set ALTER = "??" %}
          {%- endif %}
          
          {%- set event_dict = {
              'Datum': DATUM,
              'Name': NAME,
              'Notiz': NOTIZ,
              'Alter': ALTER,
              'Hinweis': HINWEIS,
              'Geburtstag': INTAGEN
            }
          %}
          
          {%- set data.result = data.result + [(event_dict)] %}
        {%- endfor %}
        {{ data.result }}
    icon: mdi:calendar

```

</details>

<br>


## :five: Template Gerburtstag Liste:


<br>


## :six: Dshboard Karten :arrow_down:

