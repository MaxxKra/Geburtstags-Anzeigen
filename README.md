# :wrench: README NOCH IN ARBEIT! :wrench:


# ALLES ÜBER GEBURTSTAGE IN HOME ASSISTANT

Das Anzeigen von Geburtstagen, ebenso wie Termine oder Ereignise in Home Assistant ist keine Hexerei und es gibt verschiedenste Möglichkeiten diese zu integrieren bzw. anzuzeigen. 
Hier sind alle Informationen über Integrationen und Karten welche ich in meinem Smarthome dafür verwende.

<br>

Beispiel:
![Beispiel](https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Dashboard_Ansicht.gif)
  
<br>

### <p align="center">Wenn du Interesse daran hast, mich, meinen Kanal oder meine kreative Arbeit zu unterstützen,<br>
freue ich mich über jeglichen Support:
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

## :three: Google Kalender Integration:

Die Integration des Google Kalenders ist zwar etwas aufwendiger aber auch für Neueinsteiger in Home Assistant mit der richtigen Anleitung durchführbar. In meinem Video auf Youtube kannst du dir das Schritt für Schritt ansehen.

Hier kommst du zur offiziellen Dokumentation der Google Integration: [GOOGLE INTEGRATION](https://www.home-assistant.io/integrations/google)


Um im späteren Verlauf das Alter mittels Termin-Eintrag zu berechnen, habe ich das Geburtsjahr als Notiz dem Termin beigefügt. In Home Assistant wird diese Notiz als Attribut `description:` angezeigt.

<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Geb_Termin_1.png" alt="Example" width="600"/>

<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Geb_Termin_2.png" alt="Example" width="600"/>

<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Geb_Termin_3.png" alt="Example" width="800"/>

## :four: Template Alter berechnen:




## :five: Template Gerburtstage-Liste:




## :six: Dshboard Karten :arrow_down:

