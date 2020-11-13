---
title: Operatoren
description: Informatie over operatoren in geavanceerde expressies
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: eec6203f63fa6d7ea706595ea866d2b330d284a8
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 4%

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

## Logisch

<table>
<thead>
<tr><th>Operator</th><th>Letterlijke uitdrukking</th><th>Voorbeeld</th></tr>
</thead>
<tbody>
<tr><td>en</td><td><p><pre>&lt;expression1&gt; en &lt;expression2&gt;</pre></p>Zowel &lt;expression1&gt; als &lt;expression2&gt; moeten booleaans zijn. Het resultaat is booleaans.</td><td><pre>3.14 &gt; 2 en 3.15 &lt; 1</pre></td></tr>
<tr><td>of</td><td><p><pre>&lt;expression1&gt; of &lt;expression2&gt;</pre></p><p>Zowel &lt;expression1&gt; als &lt;expression2&gt; moeten booleaans zijn.</p><p> Het resultaat is booleaans.</p></td><td><p><pre>3.14 &gt; 2 of 3.15 &lt; 1</pre></p></td></tr>
<tr><td>niet</td><td><p><pre>niet &lt;expression&gt;</pre></p><p>&lt;expression&gt; moet Boolean zijn.</p><p> Het resultaat is booleaans.</p></td><td><pre>niet 3,15 &lt; 1</pre></td></tr>
</tbody>
</table>

## Vergelijking

<table>
<thead>
<tr><th>Operator</th><th>Letterlijke uitdrukking </th><th>Voorbeeld</th></tr>
</thead>
<tbody><tr><td>is null</td><td><p><pre>&lt;expression&gt; is null</pre></p><p>Het resultaat is booleaans.</p><p>Null betekent dat de expressie geen geëvalueerde waarde heeft.</p></td><td><pre>@{BarBeacon.location} is null</pre></td></tr>
<tr><td>is niet null</td><td><p><pre>&lt;expression&gt; is niet null</pre></p><p>Het resultaat is booleaans.</p><p>Null betekent dat de expressie geen geëvalueerde waarde heeft.</p></td><td><pre>@ is niet null</pre></td></tr>
<tr><td>heeft null</td><td><p><pre>&lt;expression&gt; heeft null</pre>&lt;expression&gt; moet een lijst zijn.</p><p>Het resultaat is booleaans.</p><p>Nuttig om aan te geven dat een lijst minstens één null-waarde bevat.</p></td><td><p><pre>["foo", "bar", null] heeft null</pre></p>retourneert true<p><pre>["foo", "bar", ""] heeft null</pre></p> retourneert false omdat "" niet als null wordt beschouwd.</td></tr>
<tr><td>==</td><td><p><pre>&lt;expression1&gt; == &lt;expression2&gt;</pre></p><p>Zowel &lt;expression1&gt; als &lt;expression2&gt; moeten het zelfde gegevenstype hebben.</p><p> Het resultaat is booleaans.</p></td><td><pre>3.14 == 42</pre><br /><pre>"foo" == "bar"</pre></td></tr>
<tr><td>!=</td><td><p><pre>&lt;expression1&gt; != &lt;expression2&gt;</pre></p><p> Zowel &lt;expression1&gt; als &lt;expression2&gt; moeten het zelfde gegevenstype hebben.</p><p> Het resultaat is booleaans.</p></td><td><pre>3.14 != 42</pre><br /><pre>"foo" != "bar"</pre></td></tr>
<tr><td>&gt;</td><td><p><pre>&lt;expression1&gt; &gt; &lt;expression2&gt;</pre></p><p>Datetime kan met Datetime worden vergeleken.</p><p>Datetimeonly kan met Datetimeonly worden vergeleken.</p><p>Zowel geheel als decimaal kunnen met zowel geheel als decimaal worden vergeleken.</p><p>Elke andere combinatie is verboden.</p><p>Het resultaat is booleaans.</p></td><td><pre>3.14 &gt; 42</pre></td></tr>
<tr><td>&gt;=</td><td><p><pre>&lt;expression1&gt; &gt;= &lt;expression2&gt;</pre></p><p>Datetime kan met Datetime worden vergeleken.</p><p>Datetimeonly kan met Datetimeonly worden vergeleken.</p><p>Zowel geheel als decimaal kunnen met zowel geheel als decimaal worden vergeleken.</p><p>Elke andere combinatie is verboden.</p><p>Het resultaat is booleaans.</p></td><td><pre>42 &gt;= 3.14</pre></td></tr>
<tr><td>&lt;</td><td><p><pre>&lt;expression1&gt; &lt; &lt;expression2&gt;</pre></p><p>Datetime kan met Datetime worden vergeleken.</p><p>Datetimeonly kan met Datetimeonly worden vergeleken.</p><p>Zowel geheel als decimaal kunnen met zowel geheel als decimaal worden vergeleken.</p><p>Elke andere combinatie is verboden.</p><p>Het resultaat is booleaans.</p></td><td><pre>42 &lt; 3.14</pre></td></tr>
<tr><td>&lt;=</td><td><p><pre>&lt;expression1&gt; &lt;= &lt;expression2&gt;</pre></p><p>Datetime kan met Datetime worden vergeleken.</p><p>Datetimeonly kan met Datetimeonly worden vergeleken.</p><p>Zowel geheel als decimaal kunnen met zowel geheel als decimaal worden vergeleken.</p><p>Elke andere combinatie is verboden.</p><p>Het resultaat is booleaans.</p></td><td><pre>42 &lt;= 3.14</pre></td></tr>
</tbody>
</table>

## Rekenkundig

<table>
<thead>
<tr><th>Operator</th><th>Letterlijke uitdrukking </th><th>Voorbeeld</th></tr>
</thead>
<tbody><tr><td>+</td><td><p><pre>&lt;expression1&gt; + &lt;expression2&gt;</pre></p><p>Beide expressies moeten numeriek (geheel getal of decimaal) zijn. </p><p>Het resultaat is ook numeriek.</p></td><td><p><p><pre>1 + 2</pre></p></p><br /><p>Retourneert 3</p></td></tr>
<tr><td>-</td><td><p><pre>&lt;expression1&gt; - &lt;expression2&gt;</pre></p><p> Beide expressies moeten numeriek (geheel getal of decimaal) zijn.</p><p> Het resultaat is ook numeriek.</p></td><td><p><pre>2 - 1</pre></p>Retourneert 1</td></tr>
<tr><td>/</td><td><p><pre>&lt;expression1&gt; / &lt;expression2&gt;</pre></p><p>Beide expressies moeten numeriek (geheel getal of decimaal) zijn. </p><p>Het resultaat is ook numeriek.</p><p>&lt;expression2&gt; mag niet gelijk zijn aan 0 (retourneert 0).</p></td><td><p><pre>4 / 2</pre></p>Retourneert 2</td></tr>
<tr><td>*</td><td><p><pre>&lt;expression1&gt; * &lt;expression2&gt;</pre></p><p> Beide expressies moeten numeriek (geheel getal of decimaal) zijn. </p><p>Het resultaat is ook numeriek.</p></td><td><p><pre>3 * 4</pre></p>Retourneert 12</td></tr>
<tr><td>%</td><td><p><pre>&lt;expression1&gt; % &lt;expression2&gt;</pre></p><p>Beide expressies moeten numeriek (geheel getal of decimaal) zijn.</p><p> Het resultaat is ook numeriek.</p></td><td><p><pre>3 % 2</pre></p>Retourneert 1.</td></tr>
</tbody>
</table>

## Wiskundig

<table>
<thead>
<tr><th>Operator</th><th>Letterlijke uitdrukking</th><th>Voorbeeld</th></tr>
</thead>
<tbody><tr><td>is numeriek</td><td><p><pre>&lt;expression&gt; is numeriek</pre></p><p>Het type van de uitdrukking is geheel of decimaal.</p></td><td><pre>@ is numeriek</pre></td></tr>
<tr><td>is integer</td><td><p><pre>&lt;expression&gt; is integer</pre></p><p>Het type van de expressie is geheel getal.</p></td><td><pre>@ is geheel getal</pre></td></tr>
<tr><td>is decimaal</td><td><p><pre>&lt;expression&gt; is decimal</pre></p><p>Het type van de expressie is decimaal.</p></td><td><pre>@ is decimaal</pre></td></tr>
</tbody>
</table>

## Tekenreeks

<table>
<thead>
<tr><th>Operator</th><th>Letterlijke uitdrukking </th><th>Voorbeeld</th></tr>
</thead>
<tbody><tr><td>+</td><td><p><pre>&lt;string&gt; + &lt;expression&gt;</pre></p><p><pre>&lt;expression&gt; + &lt;string&gt;</pre></p><p>Twee expressies worden samengevoegd. </p><p>Eén expressie moet een kettingtekenreeks zijn.</p></td><td><p><pre>"de huidige tijd is " + (now())</pre></p> Retourneert "de huidige tijd is 2019-09-23T09:30:06.693Z"<p><pre>(now() + " is de huidige tijd"</pre></p>Retourneert "2019-09-23T09:30:06.693Z is de huidige tijd"<p><pre>"a" + "b" + "c" + 1234</pre></p> Retourneert "abc1234".</td></tr>
</tbody>
</table>

## Datum

<table>
<thead>
<tr><th>Operator</th><th>Letterlijke uitdrukking </th><th>Voorbeeld</th></tr>
</thead>
<tbody>
<tr><td>+</td><td><p><pre>&lt;expression + &lt;duration&gt;</pre></p><p>Voeg een duur aan dateTime, een dateTimeOnly of een duur toe.</p></td><td><p><pre>toDateTime("2011-12-03T15:15:30Z")</pre></p><p><pre> + toDuration("PT15M")</pre></p><p>Retourneert 2011-12-03T15:30:30Z</p><p><pre>toDateTimeOnly("2011-12-03T15:15:30")</pre></p><p><pre> + toDuration("PT15M")</pre></p>Retourneert 2011-12-03T15:30:30<p><pre>now() + toDuration("PT1H")</pre></p><p>Retourneert een uur later een dateTime (met UTC-tijdzone) vanaf de huidige tijd</p><p><pre>toDuration("PT1H") + toDuration("PT1H")</pre></p><p>Retourneert PT2H</p></td></tr>
</tbody>
</table>