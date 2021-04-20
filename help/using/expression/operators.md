---
product: adobe campaign
solution: Journey Orchestration
title: Operatoren
description: Informatie over operatoren in geavanceerde expressies
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 6%

---



# Operatoren {#concept_wd5_pj5_dgb}

Er zijn twee soorten operatoren: unaire operatoren en binaire operatoren. Er zijn linkerhand unaire operatoren en rechterhand unaire operatoren.

```
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

Hier volgt een lijst met ondersteunde operatoren:

## Logisch {#logical}

### en

```
<expression1> and <expression2>
```

Zowel &lt;expression1> als &lt;expression2> moeten booleaans zijn. Het resultaat is booleaans.

Voorbeeld:

```
3.14 > 2 and 3.15 < 1
```

### of



```
<expression1> or <expression2>
```

Zowel &lt;expression1> als &lt;expression2> moeten booleaans zijn. Het resultaat is booleaans.

Voorbeeld:

```
3.14 > 2 or 3.15 < 1
```

### niet



```
not <expression>
```

&lt;expression> moet Booleaans zijn. Het resultaat is booleaans.

Voorbeeld:

```
not 3.15 < 1
```

## Vergelijking {#comparison}

### is null



```
<expression> is null
```

Het resultaat is booleaans.

Null betekent dat de expressie geen geëvalueerde waarde heeft.

Voorbeeld:

```
@{BarBeacon.location} is null
```

### is niet null



```
<expression> is not null
```

Het resultaat is booleaans.

Null betekent dat de expressie geen geëvalueerde waarde heeft.

Voorbeeld:

```
@ is not null
```

### heeft null



```
<expression> has null
```

&lt;expression> moet een lijst zijn. Het resultaat is booleaans.

Nuttig om aan te geven dat een lijst minstens één null-waarde bevat.

Voorbeeld:

```
["foo", "bar", null] has null --  returns true.
```

```
["foo", "bar", ""] has null -- returns false because "" is not considered as null.
```

### ==



```
<expression1> == <expression2>
```

Zowel &lt;expression1> als &lt;expression2> moeten het zelfde gegevenstype hebben. Het resultaat is booleaans.

Voorbeeld:

```
3.14 == 42
```

```
"foo" == "bar"
```

### !=



```
<expression1> != <expression2>
```

Zowel &lt;expression1> als &lt;expression2> moeten het zelfde gegevenstype hebben. Het resultaat is booleaans.

Voorbeeld:

```
3.14 != 42
```

```
"foo" != "bar"
```

### >



```
<expression1> > <expression2>
```

Datetime kan met Datetime worden vergeleken.

Datetimeonly kan met Datetimeonly worden vergeleken.

Zowel geheel als decimaal kunnen met zowel geheel als decimaal worden vergeleken.

Elke andere combinatie is verboden.

Het resultaat is booleaans.

Voorbeeld:

```
3.14 > 42
```

### >=



```
<expression1> >= <expression2>
```

Datetime kan met Datetime worden vergeleken.

Datetimeonly kan met Datetimeonly worden vergeleken.

Zowel geheel als decimaal kunnen met zowel geheel als decimaal worden vergeleken.

Elke andere combinatie is verboden.

Het resultaat is booleaans.

Voorbeeld:

```
42 >= 3.14
```

### &lt;>



```
<expression1> < <expression2>
```

Datetime kan met Datetime worden vergeleken.

Datetimeonly kan met Datetimeonly worden vergeleken.

Zowel geheel als decimaal kunnen met zowel geheel als decimaal worden vergeleken.

Elke andere combinatie is verboden.

Het resultaat is booleaans.

Voorbeeld:

```
42 < 3.14
```

### &lt;>



```
<expression1> <= <expression2>
```

Datetime kan met Datetime worden vergeleken.

Datetimeonly kan met Datetimeonly worden vergeleken.

Zowel geheel als decimaal kunnen met zowel geheel als decimaal worden vergeleken.

Elke andere combinatie is verboden.

Het resultaat is booleaans.

Voorbeeld:

```
42 <= 3.14
```

## Rekenkundig {#arithmetic}

### +



```
<expression1> + <expression2>
```

Beide expressies moeten numeriek (geheel getal of decimaal) zijn.

Het resultaat is ook numeriek.

Voorbeeld:

```
1 + 2 -- returns 3
```

### -



```
<expression1> - <expression2>
```

Beide expressies moeten numeriek (geheel getal of decimaal) zijn.

Het resultaat is ook numeriek.

Voorbeeld:

```
2 - 1 -- returns 1
```

### /



```
<expression1> / <expression2>
```

Beide expressies moeten numeriek (geheel getal of decimaal) zijn.

Het resultaat is ook numeriek.

&lt;expression2> mag niet gelijk zijn aan 0 (retourneert 0).

Voorbeeld:

```
4 / 2 -- returns 2
```

### *



```
<expression1> * <expression2>
```

Beide expressies moeten numeriek (geheel getal of decimaal) zijn.

Het resultaat is ook numeriek.

Voorbeeld:

```
3 * 4 -- returns 12
```

### %



```
<expression1> % <expression2>
```

Beide expressies moeten numeriek (geheel getal of decimaal) zijn.

Het resultaat is ook numeriek.

Voorbeeld:

```
3 % 2 -- returns 1.
```

## Wiskundig {#math}

### is numeriek



```
<expression> is numeric
```

Het type van de uitdrukking is geheel of decimaal.

Voorbeeld:

```
@ is numeric
```

### is integer



```
<expression> is integer
```

Het type van de expressie is geheel getal.

Voorbeeld:

```
@ is integer
```

### is decimaal



```
<expression> is decimal
```

Het type van de expressie is decimaal.

Voorbeeld:

```
@ is decimal
```

## Tekenreeks {#string}

### +



```
<string> + <expression>
```

```
<expression> + <string>
```

Twee expressies worden samengevoegd.

Eén expressie moet een kettingtekenreeks zijn.

Voorbeeld:

```
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## Datum {#date}

### +



```
<expression + <duration>
```

Voeg een duur aan dateTime, een dateTimeOnly of een duur toe.

Voorbeeld:

```
toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M") -- returns 2011-12-03T15:30:30Z
```

```
toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M") -- returns 2011-12-03T15:30:30
```

```
now() + toDuration("PT1H") -- returns a dateTime (with UTC time zone) one hour later from current time
```

```
toDuration("PT1H") + toDuration("PT1H") -- returns  PT2H
```
