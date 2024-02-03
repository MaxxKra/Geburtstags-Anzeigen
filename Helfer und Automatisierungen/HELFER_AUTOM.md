# HELFER UND AUTOMATISIERUNGEN


Um das Pop-Up automatisiert zu öffnen, sind Helfer und Automatisierungen notwendig.
Diese habe ich hier für 1 oder 2 Pop-Up vorbereitet


# HELFER UND AUTOMATISIERUNGEN FÜR EIN POP-UP

<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/PopUp_einzeln.gif" alt="Example" width="600"/>


# HELFER UND AUTOMATISIERUNGEN FÜR ZWEI POP-UPS

<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/PopUp_mehrere.gif" alt="Example" width="600"/>


## Die Details findest du im Dropdown Menü:
<br>
<details>

<summary>:arrow_down_small: DETAILS ZWEI POPUPS :arrow_down_small:</summary>

<br>
<br>

Da ich mit einem Zeitplan, zwei Popups öffne aber immer nur eines angezeigt werden kann, habe ich meine Pop-Ups mit einem `GELESEN-BUTTON` versehen und die Automatisierungen so angepasst, dass das zweite Pop-Up erst geöffnet wird, wenn das erste gelesen wurde.

<br>
<br>

## HELFER

<br>
<br>

Ich habe folgende Helfer für mein Müllerinnerungs-PopUp und Geburtstags-PopUp erstellt:

<br>
<br>

- HELFER ZEITPLAN:    schedule.zeitplan_popup
- HELFER BUTTON:    input_button.button_mullerinnerung
- HELFER BUTTON:    input_button.button_geburtstag
- HELFER BUTTON:    input_button.popup_gelesen
- HELFER SWITCH:    input_boolean.schalter_popup

<br>
<br>

### HELFER SCHEDULE - ZEITPLAN POPUP
<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Helfer_Zeitplan.png" alt="Example" width="600"/>

<br>
<br>

### HELFER INPUT-BUTTON - MÜLLERINNERUNG
<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Helfer_Button_Mullerinnerung.png" alt="Example" width="600"/>

<br>
<br>

### HELFER INPUT-BUTTON - GEBURTSTAG
<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Helfer_Button_Geburtstag.png" alt="Example" width="600"/>

<br>
<br>

### HELFER INPUT-BUTTON - POPUP GELESEN
<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Helfer_PopUp_Geburtstag_gelesen.png" alt="Example" width="600"/>

<br>
<br>

### HELFER INPUT-BOOLEAN - SCHALTER POPUP
<img src="https://raw.githubusercontent.com/MaxxKra/README_images/master/Geburtstagskalender/Helfer_Schalter_PopUp.png" alt="Example" width="600"/>

<br>
<br>
<br>

## AUTOMATISIERUNGEN

<br>
<br>

Dies sind die Automatisierungen zu den Popups:

<br>
<br>

- Popup Müllerinnerung
- Popup Geburtstag
- PopUp gelesen

<br>
<br>

Um die Einrichtung der Automatisierungen für euch einfacher zu gestallten, habe ich für jede ein `blueprint` erstellt.
Die Import-Adressen dieser Blaupausen sind hier angeführt:

<br>
<br>

- Öffne das erste Pop-Up: https://gist.github.com/MaxxKra/835b3380ed912c0e66d81941636eedcc
- Öffne das zweite Pop-Up: https://gist.github.com/MaxxKra/f6cc2e344abfe43221631304bb93d9e2
- Schließe die Pop-Ups: https://gist.github.com/MaxxKra/7979490bd78565943564156999f4f299


Um diese Blaupausen einzufügen, gehe auf `EINSTELLUNGEN` / `AUTOMATISIERUNGEN & SZENEN` / `BLAUPAUSEN` und wähle rechts unten `BLAUPAUSE IMPORTIEREN`.

<br>
<br>

Kopiere dir die Adressen der Blaupausen und füge diese ein. Danach wähle `VORSCHAU` und dann `BLAUPAUSE IMPORTIEREN`.
Nun ist die Blaupause installiert und kann ausgewählt und mit Daten gefüllt werden.

<br>
<br>
<br>

> NICHT VERGESSEN ALLE SENSOR-DATEN, ENTITÄTEN UND DIE BROWSER_ID ANZUPASSEN!


</details>
<br>