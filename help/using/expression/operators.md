---
product: adobe campaign
title: Operatoren
description: Informatie over operatoren in geavanceerde expressies
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: fd86b6ab-76cf-4b35-9e87-f441e914f20b
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 5%

---

# Operatoren {#concept_wd5_pj5_dgb}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


Er zijn twee soorten exploitanten: unaire exploitanten en binaire exploitanten. Er zijn linkerhand unaire operatoren en rechterhand unaire operatoren.

```json
    // left-hand unary operators
    <operator> <operand> // operand is an expression
    not (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example@adobe.com")

    // right-hand unary operators
    <operand> <operator> // operand is an expression
    @{LobbyBeacon.endUserIDs._experience.emailid.id} is not null

    // binary operators
    <operand1> <operator> <operand2>
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example1@adobe.com") or
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example2@adobe.com")
```

## Belangrijke opmerkingen{#important-notes}

* Wanneer het gebruiken van een vermenigvuldiging (`*`), moeten beide verrichtingsgebieden het zelfde type, of geheel of decimaal hebben. Voorbeeld:
   * het volgende voorbeeld is correct: `3.0 * 4.0`
   * `3 * 4.0` leidt tot een fout

## Logisch  {#logical}

### en

```json
<expression1> and <expression2>
```

Zowel &lt;expression1> als &lt;expression2> moeten booleaans zijn. Het resultaat is booleaans.

Voorbeeld:

```json
3.14 > 2 and 3.15 < 1
```

### of



```json
<expression1> or <expression2>
```

Zowel &lt;expression1> als &lt;expression2> moeten booleaans zijn. Het resultaat is booleaans.

Voorbeeld:

```json
3.14 > 2 or 3.15 < 1
```

### niet



```json
not <expression>
```

&lt;expression> moet Boolean zijn. Het resultaat is booleaans.

Voorbeeld:

```json
not 3.15 < 1
```

## Vergelijking {#comparison}

### is null



```json
<expression> is null
```

Het resultaat is booleaans.

Null betekent dat de expressie geen geëvalueerde waarde heeft.

Voorbeeld:

```json
@{BarBeacon.location} is null
```

### is niet null



```json
<expression> is not null
```

Het resultaat is booleaans.

Null betekent dat de expressie geen geëvalueerde waarde heeft.

Voorbeeld:

```json
@ is not null
```

### heeft null



```json
<expression> has null
```

&lt;expression> moet een lijst zijn. Het resultaat is booleaans.

Nuttig om aan te geven dat een lijst minstens één null-waarde bevat.

Voorbeeld:

```json
["foo", "bar", null] has null --  returns true.
```

```json
["foo", "bar", ""] has null -- returns false because "" is not considered as null.
```

### ==



```json
<expression1> == <expression2>
```

Zowel &lt;expression1> als &lt;expression2> moeten het zelfde gegevenstype hebben. Het resultaat is booleaans.

Voorbeeld:

```json
3.14 == 42
```

```json
"foo" == "bar"
```

### !=



```json
<expression1> != <expression2>
```

Zowel &lt;expression1> als &lt;expression2> moeten het zelfde gegevenstype hebben. Het resultaat is booleaans.

Voorbeeld:

```json
3.14 != 42
```

```json
"foo" != "bar"
```

### >



```json
<expression1> > <expression2>
```

Datetime kan met Datetime worden vergeleken.

Datetimeonly kan met Datetimeonly worden vergeleken.

Zowel geheel als decimaal kunnen met zowel geheel als decimaal worden vergeleken.

Elke andere combinatie is verboden.

Het resultaat is booleaans.

Voorbeeld:

```json
3.14 > 42
```

### >=



```json
<expression1> >= <expression2>
```

Datetime kan met Datetime worden vergeleken.

Datetimeonly kan met Datetimeonly worden vergeleken.

Zowel geheel als decimaal kunnen met zowel geheel als decimaal worden vergeleken.

Elke andere combinatie is verboden.

Het resultaat is booleaans.

Voorbeeld:

```json
42 >= 3.14
```

### &lt;



```json
<expression1> < <expression2>
```

Datetime kan met Datetime worden vergeleken.

Datetimeonly kan met Datetimeonly worden vergeleken.

Zowel geheel als decimaal kunnen met zowel geheel als decimaal worden vergeleken.

Elke andere combinatie is verboden.

Het resultaat is booleaans.

Voorbeeld:

```json
42 < 3.14
```

### &lt;=



```json
<expression1> <= <expression2>
```

Datetime kan met Datetime worden vergeleken.

Datetimeonly kan met Datetimeonly worden vergeleken.

Zowel geheel als decimaal kunnen met zowel geheel als decimaal worden vergeleken.

Elke andere combinatie is verboden.

Het resultaat is booleaans.

Voorbeeld:

```json
42 <= 3.14
```

## Rekenkundig {#arithmetic}

### +



```json
<expression1> + <expression2>
```

Beide expressies moeten numeriek (geheel getal of decimaal) zijn.

Het resultaat is ook numeriek.

Voorbeeld:

```json
1 + 2 -- returns 3
```

### -



```json
<expression1> - <expression2>
```

Beide expressies moeten numeriek (geheel getal of decimaal) zijn.

Het resultaat is ook numeriek.

Voorbeeld:

```json
2 - 1 -- returns 1
```

### /



```json
<expression1> / <expression2>
```

Beide expressies moeten numeriek (geheel getal of decimaal) zijn.

Het resultaat is ook numeriek.

&lt;expression2> mag niet gelijk zijn aan 0 (retourneert 0).

Voorbeeld:

```json
4 / 2 -- returns 2
```

### *



```json
<expression1> * <expression2>
```

Beide expressies moeten numeriek (geheel getal of decimaal) zijn.

Het resultaat is ook numeriek.

Voorbeeld:

```json
3 * 4 -- returns 12
```

### %



```json
<expression1> % <expression2>
```

Beide expressies moeten numeriek (geheel getal of decimaal) zijn.

Het resultaat is ook numeriek.

Voorbeeld:

```json
3 % 2 -- returns 1.
```

## Math {#math}

### is numeriek



```json
<expression> is numeric
```

Het type van de uitdrukking is geheel of decimaal.

Voorbeeld:

```json
@ is numeric
```

### is integer



```json
<expression> is integer
```

Het type van de expressie is geheel getal.

Voorbeeld:

```json
@ is integer
```

### is decimaal



```json
<expression> is decimal
```

Het type van de expressie is decimaal.

Voorbeeld:

```json
@ is decimal
```

## String {#string}

### +



```json
<string> + <expression>
```

```json
<expression> + <string>
```

Twee expressies worden samengevoegd.

Eén expressie moet een kettingtekenreeks zijn.

Voorbeeld:

```json
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```json
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```json
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## Datum {#date}

### +



```json
<expression> + <duration>
```

Voeg een duur aan dateTime, een dateTimeOnly of een duur toe.

Voorbeeld:

```json
toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M") -- returns 2011-12-03T15:30:30Z
```

```json
toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M") -- returns 2011-12-03T15:30:30
```

```json
now() + toDuration("PT1H") -- returns a dateTime (with UTC time zone) one hour later from current time
```

```json
toDuration("PT1H") + toDuration("PT1H") -- returns  PT2H
```
