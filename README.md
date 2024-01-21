# ALLES ÜBER GEBURTSTAGE IN HOME ASSISTANT

Das Anzeigen von Geburtstagen, ebenso wie Termine oder Ereignise in Home Assistant ist keine Hexerei und es gibt verschiedenste Möglichkeiten diese zu integrieren bzw. anzuzeigen. 
Hier sind alle Informationen über Integrationen und Karten welche ich in meinem Smarthome dafür verwende.

Example:
![Example](https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstags-Dshboard.png)


## Verwendete Integrationen:

<!-- CODE ZUM KOPIEREN -->

| **HACS INTEGRATION** | **WO?** | **LINK** |
| --- | --- | --- |
| Google Kalender | Geräte und Dienste | Home Assistant Standard Integration |
| Anniversaries | HACS | https://github.com/pinkywafer/Anniversaries.git |
| Card Mod | HACS | https://github.com/thomasloven/lovelace-card-mod.git |
| Button Card | HACS |  https://github.com/custom-cards/button-card.git |
| Secondary Info | HACS | https://github.com/custom-cards/secondaryinfo-entity-row.git |
| Atomic Calendar Revive | HACS | https://github.com/totaldebug/atomic-calendar-revive.git |
| Layout Card | HCS |  https://github.com/thomasloven/lovelace-layout-card.git |


## Anniversaries Integration

Die erste Integration, welche ich zur Anzeige von unseren Geburtstagen incl. Alter und verbleibenden Tagen bis zum Ereignis verwendet habe, ist [Anniversaries](https://github.com/pinkywafer/Anniversaries.git)

Wie diese Integration zuinstallieren ist, sieh dir auf der Github Seite von @pinkywafer an.

**A big thank you to @pinkywafer for crafting this top-notch integration. With it, it's a breeze to display my anniversaries!**


Wie ich meine Termine angelegt habe, kannst du dir anhand der folgenden Beschreibungen und Codes ansehen.

### Termine über das UI

Termine sind bei dieser Integration über das UI als das Userinterface in Home Assistant unter Geräte&Dienste ganz leicht hinzuzufügen. Eine Schritt für Schritt - Anleitung kannst du dir im Dropdownmennü ansehen.
<details>

<summary>Termine erstellen über das UI</summary>


<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Anniversaries/HA_Int_1.png" alt="Example" width="300"/>

<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Anniversaries/HA_Int_2.png" alt="Example" width="800"/>

<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Anniversaries/HA_Int_3.png" alt="Example" width="600"/>

<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Anniversaries/HA_Int_4.png" alt="Example" width="600"/>

<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Anniversaries/HA_Int_5.png" alt="Example" width="800"/>

</details>


Eine andere Möglichkeit ist das Erstellen von Terminen in der `configuration.yaml`.
Für mich und meine Familienmitglieder habe ich das auf diese Art eingerichtet.

<details>

<summary>Termine erstellen in der configuration.yaml</summary>

```yaml
#-----------------------------------------------------------  
# Geburtstage Familie
#-----------------------------------------------------------
anniversaries:
  sensors:
  - name: Moni
    date: '1969-01-29'
    id_prefix: geburtstag_
    days_as_soon: 5
    unit_of_measurement: Tage
  - name: Michelle
    date: '2002-03-11'
    id_prefix: geburtstag_
    days_as_soon: 5
    unit_of_measurement: Tage
  - name: Maxx
    date: '1978-03-12'
    id_prefix: geburtstag_
    days_as_soon: 5
    unit_of_measurement: Tage
  - name: Natascha
    date: '2000-06-22'
    id_prefix: geburtstag_
    days_as_soon: 5
    unit_of_measurement: Tage

```

</details>

## Google Kalender Integration


## Template Alter berechnen




## Dshboard Karten

