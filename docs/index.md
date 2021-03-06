# Einstellungsdetails

## Auf dem Client

Um die Einstellungen zu öffnen scanne den Code `scan2rest-settings`.

Hierzu kannst du selbst einen Code erstellen, der diese Zeichenkette repräsentiert, oder den Code hier benutzen:

![Scannen des Codes öffnet das Einstellungsmenü](scan2rest-settings.png)

## Parameterübergabe an den Server

Die Parameterübergabe des HTTP-Requests muss folgendem Format entprechen: 

- `<URL>?scanner=<scannerName>&code=<scannedValue>`


Das Format beinhaltet ein paar von `<` und `>` umschlossene Zeichenketten, die wie folgt zu verstehen sind; alle anderen Zeichen stehen für sich selbst und dürfen nicht ersätzt werden:

Zeichenkette | Bedeutung     | Beispiel
:----------- | :------------ | :------------
`<URL>`          | Die im Client konfigurierte URL des empfangenden Servers. | `http://my-web-url-example.de:12345/api/Scan2Rest`
`<scannerName>`  | Der Name des Scanners (ändert sich bei sukzessiven REST-Calls nie). | Beliebige alphanumerische Zeichenkette, zB. `Raum10`
`<scannedValue>` | Der gescannnte Wert (ändert sich in der Regel bei sukzessiven REST-Calls). | Beliebige Zeichenkette, zB. `42`

Eine valide URL kann zum Beispiel so aussehen:

- `http://my-web-url-example.de:12345/api/Scan2Rest?scanner=DerScannerInRaum3&code=42`

## HTTP-Response vom Server

Die vom Server zurückgeschickte HTTP-Response wird in JSON dargestellt und hat das folgende allgemeine Format.

```JSON
{
  "success": <responseBool>,
  "response": "<responseText>"
}

```

Das Format ist so zu verstehen:

Zeichenkette | Bedeutung
:----------- | :------------
`<responseBool>` | Entweder eine textuelle `1` falls erfolgreich (im Client als erfolgreich vermerkt), oder eine textuelle `0` falls nicht erfolgreich (im Client als Fehler vermerkt).
`<responseText>` | Eine Nachricht an den Client, die an den Benutzer weitergegeben werden soll.

Eine valide Response kann zum Beispiel so aussehen:


```JSON
{
  "success": 1,
  "response": "Material erfolgreich geprüft."
}

```


