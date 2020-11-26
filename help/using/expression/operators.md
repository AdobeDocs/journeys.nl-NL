---
product: adobe campaign
solution: Journey Orchestration
title: Operatoren
description: Informatie over operatoren in geavanceerde expressies
translation-type: tm+mt
source-git-commit: 20498e89eb9c95dd19a11e42150a0bbf67024f67
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 5%

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

## Logisch  {#logical}

### en

**Letterlijke expressie**

```<expression1> and <expression2>```

Zowel &lt;expression1> als &lt;expression2> moeten booleaans zijn. Het resultaat is booleaans.

**Voorbeeld**

```3.14 > 2 and 3.15 < 1```

### of

**Letterlijke expressie**

```<expression1> or <expression2>```

Zowel &lt;expression1> als &lt;expression2> moeten booleaans zijn. Het resultaat is booleaans.

**Voorbeeld**

```3.14 > 2 or 3.15 < 1```

### niet

**Letterlijke expressie**

```not <expression>```

&lt;expression> moet Boolean zijn. Het resultaat is booleaans.

**Voorbeeld**

```not 3.15 < 1```

## Vergelijking {#comparison}

### is null

**Letterlijke expressie**

```<expression> is null```

Het resultaat is booleaans.

Null betekent dat de expressie geen geëvalueerde waarde heeft.

**Voorbeeld**

```@{BarBeacon.location} is null```

### is niet null

**Letterlijke expressie**

```<expression> is not null```

Het resultaat is booleaans.

Null betekent dat de expressie geen geëvalueerde waarde heeft.

**Voorbeeld**

```@ is not null```

### heeft null

**Letterlijke expressie**

```<expression> has null```

&lt;expression> moet een lijst zijn. Het resultaat is booleaans.

Nuttig om aan te geven dat een lijst minstens één null-waarde bevat.

**Voorbeeld**

```["foo", "bar", null] has null``` retourneert true.

```["foo", "bar", ""] has null``` retourneert false omdat &quot;&quot; niet als null wordt beschouwd.

### ==

**Letterlijke expressie**

```<expression1> == <expression2>```

Zowel &lt;expression1> als &lt;expression2> moeten het zelfde gegevenstype hebben. Het resultaat is booleaans.

**Voorbeeld**

```3.14 == 42```

```"foo" == "bar"```

### !=

**Letterlijke expressie**

```<expression1> != <expression2>```

Zowel &lt;expression1> als &lt;expression2> moeten het zelfde gegevenstype hebben. Het resultaat is booleaans.

**Voorbeeld**

```3.14 != 42```

```"foo" != "bar"```

### >

**Letterlijke expressie**

```<expression1> > <expression2>```

Datetime kan met Datetime worden vergeleken.

Datetimeonly kan met Datetimeonly worden vergeleken.

Zowel geheel als decimaal kunnen met zowel geheel als decimaal worden vergeleken.

Elke andere combinatie is verboden.

Het resultaat is booleaans.

**Voorbeeld**

```3.14 > 42```

### >=

**Letterlijke expressie**

```<expression1> >= <expression2>```

Datetime kan met Datetime worden vergeleken.

Datetimeonly kan met Datetimeonly worden vergeleken.

Zowel geheel als decimaal kunnen met zowel geheel als decimaal worden vergeleken.

Elke andere combinatie is verboden.

Het resultaat is booleaans.

**Voorbeeld**

```42 >= 3.14```

### &lt;

**Letterlijke expressie**

```<expression1> < <expression2>```

Datetime kan met Datetime worden vergeleken.

Datetimeonly kan met Datetimeonly worden vergeleken.

Zowel geheel als decimaal kunnen met zowel geheel als decimaal worden vergeleken.

Elke andere combinatie is verboden.

Het resultaat is booleaans.

**Voorbeeld**

```42 < 3.14```

### &lt;=

**Letterlijke expressie**

```<expression1> <= <expression2>```

Datetime kan met Datetime worden vergeleken.

Datetimeonly kan met Datetimeonly worden vergeleken.

Zowel geheel als decimaal kunnen met zowel geheel als decimaal worden vergeleken.

Elke andere combinatie is verboden.

Het resultaat is booleaans.

**Voorbeeld**

```42 <= 3.14```

## Rekenkundig {#arithmetic}

### +

**Letterlijke expressie**

```<expression1> + <expression2>```

Beide expressies moeten numeriek (geheel getal of decimaal) zijn.

Het resultaat is ook numeriek.

**Voorbeeld**

```1 + 2``` retourneert 3

### -

**Letterlijke expressie**

```<expression1> - <expression2>```

Beide expressies moeten numeriek (geheel getal of decimaal) zijn.

Het resultaat is ook numeriek.

**Voorbeeld**

```2 - 1``` retourneert 1

### /

**Letterlijke expressie**

```<expression1> / <expression2>```

Beide expressies moeten numeriek (geheel getal of decimaal) zijn.

Het resultaat is ook numeriek.

&lt;expression2> mag niet gelijk zijn aan 0 (retourneert 0).

**Voorbeeld**

```4 / 2``` retourneert 2

### *

**Letterlijke expressie**

```<expression1> * <expression2>```

Beide expressies moeten numeriek (geheel getal of decimaal) zijn.

Het resultaat is ook numeriek.

**Voorbeeld**

```3 * 4``` retourneert 12

### %

**Letterlijke expressie**

```<expression1> % <expression2>```

Beide expressies moeten numeriek (geheel getal of decimaal) zijn.

Het resultaat is ook numeriek.

**Voorbeeld**

```3 % 2``` retourneert 1.

## Wiskundig {#math}

### is numeriek

**Letterlijke expressie**

```<expression> is numeric```

Het type van de uitdrukking is geheel of decimaal.

**Voorbeeld**

```@ is numeric```

### is integer

**Letterlijke expressie**

```<expression> is integer```

Het type van de expressie is geheel getal.

**Voorbeeld**

```@ is integer```

### is decimaal

**Letterlijke expressie**

```<expression> is decimal```

Het type van de expressie is decimaal.

**Voorbeeld**

```@ is decimal```

## Tekenreeks {#string}

### +

**Letterlijke expressie**

```<string> + <expression>```

```<expression> + <string>```

Twee expressies worden samengevoegd.

Eén expressie moet een kettingtekenreeks zijn.

**Voorbeeld**

```"the current time is " + (now())``` retourneert &quot;de huidige tijd is 2019-09-23T09:30:06.693Z&quot;

```(now()) + " is the current time"``` retourneert &quot;2019-09-23T09:30:06.693Z is de huidige tijd&quot;

```"a" + "b" + "c" + 1234``` retourneert &quot;abc1234&quot;.

## Datum {#date}

### +

**Letterlijke expressie**

```<expression + <duration>```

Voeg een duur aan dateTime, een dateTimeOnly of een duur toe.

**Voorbeeld**

```toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M")``` retourneert 2011-12-03T15:30:30Z

```toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M")``` retourneert 2011-12-03T15:30:30

```now() + toDuration("PT1H")``` retourneert een uur later een dateTime (met UTC-tijdzone) vanaf de huidige tijd

```toDuration("PT1H") + toDuration("PT1H")``` retourneert PT2H
