---
product: adobe campaign
title: Datatypen
description: Meer informatie over gegevenstypen in geavanceerde expressies
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 343f61b8-2315-4971-8b2b-6aa815bd9ced
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 5%

---

# Datatypen {#concept_gp3_rj5_dgb}

Technisch gesproken bevat een constante altijd een gegevenstype. In de letterlijke expressie geven we alleen de waarde op. Het gegevenstype kan worden afgeleid van de waarde (bijvoorbeeld tekenreeks, geheel getal, decimaal enz.). Voor specifieke gevallen, zoals datumtijd, gebruiken wij specifieke functies voor de vertegenwoordiging.

In de onderstaande secties vindt u informatie over de verschillende expressies van gegevenstypen en hoe deze worden weergegeven.

## string {#string}

**Beschrijving**

Algemene reeks tekens. Het heeft geen specifieke grootte behalve impliciet die uit het milieu zoals de beschikbare hoeveelheid geheugen komt.

JSON-indeling: String

Serienummeringsindeling: UTF-8

**Letterlijke representatie**

```json
"<value>"
```

```json
'<value>'
```

**Voorbeeld**

```json
"hello world"
```

```json
'hello world'
```

## integer {#integer}

**Beschrijving**

Gehele waarde van -2^63 tot 2^63-1.

JSON-indeling: Getal

**Letterlijke representatie**

```json
<integer value>
```

**Voorbeeld**

```json
42
```

## decimaal {#decimal}

**Beschrijving**

Decimaal getal. Deze vertegenwoordigt een zwevende waarde:

* grootste positieve eindige waarde van type dubbel, (2-2^-52)x2^1023
* kleinst positieve normale waarde van type double, 2-1022
* kleinst positieve, niet-nul waarde van type double, 2 p-1074

JSON-indeling: Getal

Serienummeringsindeling: gebruiken &#39;.&#39; als decimaalteken.

**Letterlijke representatie**

```json
<integer value>.<integer value>
```

**Voorbeeld**

```json
3.14
```

## boolean {#boolean}

**Beschrijving**

Booleaanse waarde, in kleine letters geschreven: true of false

JSON-indeling: Boolean

**Letterlijke representatie**

```json
true
```

```json
false
```

**Voorbeeld**

```json
true
```

## dateOnly {#date-only}

**Beschrijving**

Vertegenwoordigt een datum slechts zonder een tijdzone, die als jaar-maand-dag wordt bekeken.

Het is een beschrijving van de datum, zoals die voor verjaardagen wordt gebruikt.

JSON-indeling: Tekenreeks.

Indeling is: YYYY-MM-DD (ISO-8601), bijvoorbeeld: &quot;2021-03-11&quot;.

Deze kan worden ingekapseld in een toDateOnly-functie.

Het gebruikt DateTimeFormatter ISO_LOCAL_DATE_TIME om de waarde te deserialiseren en in series te vervaardigen. [Meer informatie](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6)

**Letterlijke representatie**

```json
date("<dateOnly in ISO-8601 format>")  
```

**Voorbeeld**

```json
date("2021-02-19")
```

## dateTimeOnly {#date-time-only}

**Beschrijving**

Vertegenwoordigt een datumtijd zonder een tijdzone, die als jaar-maand-dag-uur-minuut-seconde-milliseconde wordt bekeken.

JSON-indeling: Tekenreeks.

Er wordt geen tijdzone opgeslagen of weergegeven. In plaats daarvan is het een beschrijving van de datum, zoals die voor verjaardagen wordt gebruikt, gecombineerd met de lokale tijd zoals die op een muurklok wordt gezien.

Het kan geen onmiddellijk op tijdlijn zonder extra informatie zoals een compensatie of tijdzone vertegenwoordigen.

Het kan in een toDateTimeOnly functie worden ingekapseld.

Serienummeringsindeling: ISO-8601 extended offset date-time format.

Het gebruikt DateTimeFormatter ISO_LOCAL_DATE_TIME om de waarde te deserialiseren en in series te vervaardigen. [Meer informatie](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**Letterlijke representatie**

```json
date("<dateTimeOnly in ISO-8601 format>")  
```

**Voorbeelden**

```json
date("2021-02-19T00.00.000")
date("2021-02-19T00.00")
```

## dateTime {#date-time}

**Beschrijving**

Datumtijdconstante die ook rekening houdt met tijdzone. Deze vertegenwoordigt een datum-tijd met een verschuiving van UTC.

Het kan als onmiddellijk in tijd met de extra informatie van de compensatie worden bekeken. Het is een manier om een specifiek &quot;moment&quot; te vertegenwoordigen op een bepaalde plaats in de wereld.

JSON-indeling: Tekenreeks.

Het kan in een toDateTime functie worden ingekapseld.

Serienummeringsindeling: ISO-8601 extended offset date-time format.

Het gebruikt DateTimeFormatter ISO_OFFSET_DATE_TIME om de waarde te deserialiseren en serialiseren. [Meer informatie](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

U kunt ook een geheel getal doorgeven dat een epochwaarde doorgeeft. [Meer informatie](https://www.epochconverter.com)

De tijdzone kan door een compensatie of een code van de tijdzone worden gespecificeerd (voorbeeld: Europa/Parijs, Z - UTC).

**Letterlijke representatie**

```json
toDateTime("<dateTime in ISO-8601 format>")
```

```json
date("<dateTime in ISO-8601 format>")
```

```json
toDateTime(<integer value of an epoch in milliseconds>)
```

**Voorbeelden**

```json
date("2021-02-19T00.00.000Z")
```

```json
toDateTime("1977-04-22T06:00:00Z")
```

```json
toDateTime("2011-12-03T15:15:30Z")
```

```json
toDateTime("2011-12-03T15:15:30.123Z")
```

```json
toDateTime("2011-12-03T15:15:30.123+02:00")
```

```json
toDateTime("2011-12-03T15:15:30.123-00:20")
```

```json
toDateTime(1560762190189)
```

## duur {#duration}

**Beschrijving**

Het vertegenwoordigt een tijd-gebaseerde hoeveelheid tijd, zoals &quot;34.5 seconden&quot;. Het modelleert een hoeveelheid of een hoeveelheid tijd in milliseconden.

De ondersteunde tijdseenheden zijn: milliseconden, seconden, minuten, uren, dagen waarbij een dag gelijk is aan 24 uur. Jaren en maanden worden niet ondersteund omdat het geen vaste tijd is.

JSON-indeling: Tekenreeks.

Het moet in een toDuration functie worden ingekapseld.

Serienummeringsindeling: Als u een tijdzone-id wilt deserialiseren, wordt de java-functie java.time gebruikt.

Duration.parse: de aanvaarde formaten zijn gebaseerd op de ISO-8601-duurnotatie PnDTnHnMn.nS met dagen die precies 24 uur worden geacht. [Meer informatie](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**Letterlijke representatie**

```json
toDuration("<duration in ISO-8601 format>")
```

```json
toDuration(<duration in milliseconds>)
```

**Voorbeeld**

```json
toDuration("PT5S") -- parses as 5 seconds
```

```json
toDuration(500) -- parses as 500ms
```

```json
toDuration("PT20.345S") -- parses as "20.345 seconds"
```

```json
toDuration("PT15M") -- parses as "15 minutes" (where a minute is 60 seconds)
```

```json
toDuration("PT10H")  -- parses as "10 hours" (where an hour is 3600 seconds)
```

```json
toDuration("P2D") -- parses as "2 days" (where a day is 24 hours or 86400 seconds)
```

```json
toDuration("P2DT3H4M") -- parses as "2 days, 3 hours and 4 minutes"
```

```json
toDuration("P-6H3M") -- parses as "-6 hours and +3 minutes"
```

```json
toDuration("-P6H3M") -- parses as "-6 hours and -3 minutes"
```

```json
toDuration("-P-6H+3M") -- parses as "+6 hours and -3 minutes"
```

## list {#list}

**Beschrijving**

Door komma&#39;s gescheiden lijst met expressies waarbij vierkante haakjes als scheidingstekens worden gebruikt.

Polymorfisme wordt niet ondersteund en daarom moeten alle uitdrukkingen in de lijst van hetzelfde type zijn.

**Letterlijke representatie**

```json
[<expression>, <expression>, ... ]
```

**Voorbeeld**

```json
["value1","value2"]
```

```json
[3,5]
```

```json
[toDuration(500),toDuration(800)]
```
