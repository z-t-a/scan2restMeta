# Einstellungsdetails

## Auf dem Client

Um die Einstellungen zu öffnen scanne den Code `scan2rest-settings`.

Hierzu kannst du selbst einen Code erstellen, der diese Zeichenkette repräsentiert, oder den Code hier benutzen:

![Scannen des Codes öffnet das Einstellungsmenü](scan2rest-settings.png)

## Parameterübergabe an den Server

Die Parameterübergabe des HTTP-Requests muss folgendem Format entprechen: 

- `URL/<variable>=<value>/...`


Das Format beinhaltet ein paar von `<` und `>` umschlossene Zeichenketten, die wie folgt zu verstehen sind; alle anderen Zeichen stehen für sich selbst und dürfen nicht ersätzt werden:

Zeichenkette | Bedeutung
------------ | -------------
`<URL>` | Die im Client konfigurierte Server-URL.
`<variable>` | Der erste Parametername in der REST-URL; ändert sich bei sukzessiven REST-Calls nie.
`<value>` | Der erste Parameterwert in der REST-URL; ändert sich in der Regel bei sukzessiven REST-Calls.

