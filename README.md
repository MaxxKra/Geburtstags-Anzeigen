# ALLES ÜBER GEBURTSTAGE IN HOME ASSISTANT

Das Anzeigen von Geburtstagen, ebenso wie Termine oder Ereignise in Home Assistant ist keine Hexerei und es gibt verschiedenste Möglichkeiten diese zu integrieren bzw. anzuzeigen. 
Hier sind alle Informationen über Integrationen und Karten welche ich in meinem Smarthome dafür verwende.


## INHALTSVERZEICHNIS:


1. [Verwendete Integrationen](/README.md#one-verwendete-integrationen)
2. [Anniversaries Integration](/README.md#two-anniversaries-integration)
3. [Google Kalender Integration](/README.md#three-google-kalender-integration)
4. [Template Geburtstag Heute](/README.md#four-template-geburtstag-heute)
5. [Template Gerburtstag Liste](/README.md#five-template-gerburtstag-liste)
6. [Template Geburtstag Texte](/README.md#six-template-geburtstag-texte)
7. [Dashboard Karten und Pop-Up Erinnerung](/README.md#seven-dashboard-karten-und-pop-up-erinnerung-arrow_down)


<br>

Beispiel:
![Beispiel](https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Dashboard_Ansicht.gif)
  
<br>


### <p align="center">Wenn du Interesse daran hast, mich, meinen Kanal oder meine kreative Arbeit zu unterstützen,<br>freue ich mich über jeglichen Support:
</p>
<p align="center">
  <a href="https://www.buymeacoffee.com/bastler">
    <img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Allgemein/buy_me_a_coffee_logo.png" alt="Buy Me A Coffee" width="150">
  </a>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="https://www.paypal.me/kramlmaxx">
    <img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Allgemein/paypal_donate_logo.png" alt="PayPal Donate" width="150">
  </a>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="https://www.amazon.de/hz/wishlist/ls/3FT7MNGRVOTM3?ref_=wl_share">
    <img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Allgemein/amazon_wishlist_logo.png" alt="Amazon Wishlist" width="150">
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
| Card Tools | HACS | https://github.com/thomasloven/lovelace-card-tools.git |
| Atomic Calendar Revive | HACS | https://github.com/totaldebug/atomic-calendar-revive.git |
| Layout Card | HCS |  https://github.com/thomasloven/lovelace-layout-card.git |
| Entities Card | Lovelace | Home Assistant Standard Karte |
| Expander Card | HACS | https://github.com/Alia5/lovelace-expander-card.git |


<br>


## :two: Anniversaries Integration:

Die erste Integration, welche ich zur Anzeige von unseren Geburtstagen incl. Alter und verbleibenden Tagen bis zum Ereignis verwendet habe, ist [Anniversaries](https://github.com/pinkywafer/Anniversaries.git)

Wie diese Integration zu installieren ist, sieh dir auf der Github Seite von @pinkywafer bzw. anhand meines Videos auf YouTube an.

**A big thank you to @pinkywafer for crafting this top-notch integration. With it, it's a breeze to display my anniversaries!**


Wie ich meine Termine angelegt habe, kannst du dir anhand der folgenden Beschreibungen und Codes ansehen.

### Termine über das UI

Termine sind bei dieser Integration über das UI, also das Userinterface, in Home Assistant unter Geräte&Dienste ganz leicht hinzuzufügen. Eine Schritt für Schritt - Anleitung kannst du dir im Dropdownmennü ansehen.
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


> [!IMPORTANT]
> Der Standardmäßig angelegte Google Kalender, sprich der Geburtstagskalender, übernimmt die Namen automatisch aus der Kontaktliste und lässt daher kein Hinzufügen manueller Termine und dadurch auch kein Eintragen von Notizen bzw. Beschreibungen zu. Da dies aber zur Berechnung des Alters dringend notwendig ist, habe ich den Standardkalender gelöscht und einen neuen mit dem Namen Geburtstag hinzugefügt.


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


<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Termin_1.png" alt="Example" width="350"/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Termin_2.png" alt="Example" width="350"/>


<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Eintrag_Geb_Heute.png" alt="Example" width="800"/>


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
  - trigger: time_pattern
    minutes: /15
  - trigger: homeassistant
    event: start
  - trigger: state
    entity_id:
      - input_button.trigger_update
action:
  - action: calendar.get_events
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

Um nun die Kalender Einträge in Home Assistant auszuwerten, habe ich mehrere Template Sensoren erstellt.

Das Zweite, ist ein Template um eine Liste zukünftiger Termine (Geburtstage Liste) aus dem Kalender zu suchen und ihn in einen Sensor mit Attributen umzuwandeln. Dieser Sensor hat folgende Werte:

Zustand:
- **Anzahl der Einträge der nächsten 60 Tage**
Attribute:
- **Name**
- **Datum**
- **Alter**
- **Notiz** (gesamt)
- **Hinweis** (Notiz ohne eventuelle Jahreszahl)
- **Geburtstag** (Anzahl Tage bis... bzw. Heute/Morgen)


<br>

### BEISPIELLISTE MIT 4 EINTRÄGEN


<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Eintrag_Geb_Liste.png" alt="Example" width="800"/>


<br>

Um diese Werte zu erhalten, ist dieses Template auch in Home Assistant einzutragen. Hier handelt es sich ebenso um eine "Auslöser-basierende-Template-Entitäten", dass bedeutet auch dieses Template wird durch einen Auslöser aktiviert.


Das Template für "Geburtstage Liste" ist in der Dropdown Sektion zum kopieren bereitgestellt:


<details>


### Template Geburtstage Liste

<summary>:arrow_down_small: Template Geburtstage Liste :arrow_down_small:</summary>

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
# **Template Geburtstage Liste**
#-----------------------------------------------------------
trigger:
  - trigger: time_pattern
    minutes: /15
  - trigger: homeassistant
    event: start
  - trigger: state
    entity_id:
      - input_button.trigger_update
action:
  - action: calendar.get_events
    target:
      entity_id: calendar.geburtstag
    data:
      duration:
        days: 60
    response_variable: my_bithday_events
sensor:
  - name: Geburtstage Liste
    unique_id: geburtstage_liste
    state: "{{ my_bithday_events['calendar.geburtstag'].events | count() }}"
    attributes:
      scheduled_events: >
        {%- set HEUER = now().year %}
        {%- set HEUTE = today_at() %}
        {%- set data = namespace(result=[]) %}
        {%- for event in my_bithday_events['calendar.geburtstag'].events %}
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


## :six: Template Geburtstag Texte 


Zur Darstellung auf dem Dashboard bzw. zur Definition von Texten für den Sprachassistenten habe ich zusätzliche Templates als **Geburtstags Texte** angelegt.


Diese Templates sind:


- **Geburtstags Termine Einzeln** (Zeigt den Namen des ersten Eintrags am jeweiligen Tag als Zustand an)
- **Geburtstags Alter Einzeln** (Zeigt das Alter des ersten Eintrags am jeweiligen Tag als Zustand an)
- **Geburtstag Heute Einzeln** (Zeigt den Namen des Ersten Eintrags als Zustand, sowie das Alter als Attribut an)
- **Geburtstags Text Zeile** (Stellt eine Textzeile aus Namen und Alter der Geburtstage am jeweiligen Tag zusammen)
- **Geburtstags Text Dashboard** (Stellt eine Liste der Namen und Alter der Geburtstage mit Sepertor zusammen)


> Bei allen Tempaltes gilt, dass das Alter nur angezeigt bzw. berechnet wird, wenn im Kalender bei Notiz eine Jahreszahl eingetragen wurde.

<br>

<details>


### Templates Geburtstag Texte

<summary>:arrow_down_small: Templates Geburtstag Texte :arrow_down_small:</summary>

```yaml
#-----------------------------------------------------------
# Geburtstags Kalender
#-----------------------------------------------------------

sensor:

#-----------------------------------------------------------
# Wer hat heute Geburtstag Einzeln | NAME
#-----------------------------------------------------------
- name: Geburtstags Termine Einzeln
  unique_id: geburtstags_termine_einzeln
  icon: mdi:calendar-month-outline
  state: >
    {% set KAL = states.calendar.geburtstag.state %}
    {% set NAME = states.calendar.geburtstag.attributes.message%}
    {%- if KAL == 'off' %}
    Heute keine Termine!
    {%- elif KAL == 'on' %}
    {{ NAME }}
    {% else %}
    FEHLER
    {%- endif %}    

#-----------------------------------------------------------
# Berechnung des Alters wenn Geburtsjahr als Notiz  Einzeln
#-----------------------------------------------------------
- name: Geburtstags Alter Einzeln
  unique_id: geburtstags_alter_einzeln
  icon: mdi:numeric-9-plus-circle-outline
  state: >
    {%- set KAL = states.calendar.geburtstag.state %}
    {%- set NOTIZ = states['calendar.geburtstag'].attributes.description %}
    {%- set HEUTE = now().year %}    
    {%- if KAL == 'on' and NOTIZ != "" %}
      {%- set ALTER = NOTIZ | regex_findall('(\d{4})') | first %}
      {%- if ALTER is defined %}
        {{ HEUTE - ALTER | int }}
      {%- else %}
        ??
      {%- endif %}
    {%- else %}
      ??
    {%- endif %}

#-----------------------------------------------------------
# Geburtstag Heute Einzeln| NAME + ALTER als Attribut
#-----------------------------------------------------------
- name: Geburtstag Heute Einzeln
  unique_id: geburtstag_heute_einzeln
  icon: mdi:calendar-month-outline
  state: >
    {% set KAL = states.calendar.geburtstag.state %}
    {% set NAME = states.calendar.geburtstag.attributes.message%}
    {%- if KAL == 'off' %}
    Niemand
    {%- elif KAL == 'on' %}
    {{ NAME }}
    {% else %}
    FEHLER
    {%- endif %}
  attributes:
    Alter: >
      {% set KAL = states.calendar.geburtstag.state %}
      {% set ALTER = states.sensor.geburtstags_alter.state %}
      {%- if KAL == 'off' %}
      UNBEKANNT
      {%- elif KAL == 'on' %}
      {{ ALTER }}
      {% else %}
      FEHLER
      {%- endif %}

#-----------------------------------------------------------
# Textzeile Geburtstag zusammengestellt (Sprachausgabe)
#-----------------------------------------------------------
- name: Geburtstags Text Zeile
  unique_id: geburtstags_text_zeile
  icon: mdi:calendar-month-outline
  state: >
    {%- set GEBLISTE = state_attr('sensor.geburtstag_heute','scheduled_events') %}
    {%- if GEBLISTE is defined and GEBLISTE|length == 1 %}
    {%- for E in GEBLISTE %}
    {{ E.Name }} hat heute Geburtstag und wird {{ E.Alter }} Jahre alt!
    {%- endfor %}
    {%- elif GEBLISTE is defined and GEBLISTE|length > 1 %}
    {%- for E in GEBLISTE %}
    {{ E.Name }}, Alter {{ E.Alter }} Jahre
      {%- if not loop.last %} und {%- endif %}
      {%- if loop.last %} haben heute Geburtstag!{%- endif %}
    {%- endfor %}
    {%- else %}
    Heute hat niemand Geburtstag!
    {%- endif %}  

#-----------------------------------------------------------
# Textliste Geburtstag für das Dashboard
#-----------------------------------------------------------
- name: Geburtstags Text Dashboard
  unique_id: geburtstags_text_dashboard
  icon: mdi:calendar-month-outline
  state: >
    {%- set TERMINE = states.sensor.geburtstag_heute.state %}
    {%- set GEBLISTE = state_attr('sensor.geburtstag_heute','scheduled_events') %}
    {%- if GEBLISTE is defined and GEBLISTE|length > 0%}
    {%- for E in GEBLISTE %}
    {{ E.Name }} | Alter: {{ E.Alter }}{%- if not loop.last %};{%- endif %}
    {%- endfor %}
    {%- else %}
    Heute keine Geburtstage!
    {%- endif %}

```

</details>

<br>


## :seven: Dashboard Karten und Pop-Up Erinnerung :arrow_down:

Um eine ansprechende Darstellung am Dashboard zu erhalten, habe ich mehrere Karten erstellt.
Die Aufteilung dieser Karten am dashboard erfolgt mittels Layout-Card.

<br>

### Aufteilung Layout-Card

<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Dashboard_Layout_Aufteilung_2.png" alt="Example" width="600"/>


<br>

Zur Vereinfachung der Codeerstellung für das Layout, habe ich mir in EXCEL einen Codegenerator erstellt. Dieser ist im Ordner Dateien zur Verwendung bereitgestellt.


Das verwendete Layout sieht im EXCEL Codegenerator so aus:


### Aufteilung Layout-Card

<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Dashboard_Layout_Aufteilung_3.png" alt="Example" width="600"/>

Die einzelnen Karten werden beim Einfügen am Dashboard in der jeweiligen `area` angezeigt:

<br>

<details>


### Der Code für das Layout ist hier zu Kopieren:

<summary>:arrow_down_small: Der Code für das Layout ist hier zu Kopieren: :arrow_down_small:</summary>

```yaml
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

```

</details>


<br>


### Um die Beschreibungen der einzelnen Karten zu sehen, folge den Links:


<br>

- [TITEL_1 KARTE](/Karten/TITEL_1.md)

<br>

- [TITEL_2 KARTE](/Karten/TITEL_2.md)

<br>

- [GEBURTSTAG HEUTE KARTE](/Karten/GEB-HEUTE.md)

<br>

- [ENTITY KARTE](/Karten/ENTITY_KARTE.md)

<br>

- [KALENDER KARTE KARTE](/Karten/KALENDER.md)

<br>

- [GEBURTSTAGE LISTE KARTE](/Karten/GEB-LISTE.md)

<br>

- [POPUP KARTE](/Karten/POPUP.md)

