# workadventure des LV


## verwendete Programme

- aktueller(!) [Tiled editor](https://www.mapeditor.org/) software
- Texure Packer (zum packen der Spritesheets) (abgeschaut beim [c3CERT](https://github.com/c3CERT/rc3-cert))
- Grafikprogramme der Wahl. z.b. [Krita](https://krita.org)

## Basiseinstellungen
- Orientierung: Orthogonal
- Kachelebenenformat: CSV
- Kachel-Zeichenreihenfolge: Rechts Runter
- Kartengröße_ Festgelegt (dann aber beliebig)
- Tilegröße 32x32 Pixel

## Besondere Ebenentypen
- floorLayer: In dieser Ebene wird die Spielfigur dargestellt. Das ist der einzige Layer vom Typ Objectlayer.
- Start Layer: Startpunkt zum Betreten der Karte
	- Layer-Eigenschaft: "startLayer" (Typ bool)
	- Name des Layers kann als Paramter übergeben werden und so unterschiedliche Startpunkte realisiert werden.
	- Wenn mehrere Kacheln im Start Layer enthalten sind wird der Punkt zufällig gewählt an dem die Spielfigur erscheint
	- Benutze am besten das Tile "START" aus mapUtilities
- Exit Layer: Ausgänge zu anderen Karten
	- Layer-Eigenschaft: "exitUrl" (Typ string)
	- als relative URL: anderemap.json
	- als mit Ziel-Layer: anderemap.json#startpunkt
	- auf anderem Server: /_//mapserver/anderemap#startpunkt (Achtung, Rückweg)
	- Benutze am besten das Tile "EXIT" aus mapUtilities
- Kollisionen: Eigentlich benötigt man dazu keine eigene Ebene, aber um es übresichtlich zu halten ist das auf jeden Fall empfohlen
        - Benutze am besten das Tile "BLOCK" aus mapUtilities
	- Eigenschaft "collide" (Typ bool) muss für diese Kachel (!) gesetzt sein
	- Am besten unter den Boden platzieren, dann ist die Ebene nicht sichtbar
- Jitsi-Räume:
	- Layer-Eigenschaft "jitsiRoom" (Typ string) plus Raumname im String
	- Hebt Beschränkung auf 4 Teilnehmende im Annäherungschat auf
	- Jitsi-Raum kann auch ohne Workadventure betreten werden
	- Jitsi-Bereich kann unzusammenhängend sein (Verbindung zwischen entfernten Bereichen)
        - Benutze am besten das Tile "MISC" aus mapUtilities
- URL Layer: Öffnet externe Webseiten in einem "Popup"
        - Layer-Eigenschaft "openWebsite" (Typ string) plus URL im String
	- Die URL muss eine vollständige, absolute Adresse sein
	- Nur https:// funktioniert (aus Sicherheitsgründen)
	- Die Zielseite muss das Einnbetten zulassen
	- Jede URL benötigt ihren eigenen Layer
        - Benutze am besten das Tile "URL" aus mapUtilities






