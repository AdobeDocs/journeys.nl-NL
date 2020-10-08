---
title: Datatypen
description: Meer informatie over gegevenstypen in geavanceerde expressies
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 3%

---


# Datatypen {#concept_gp3_rj5_dgb}

Technisch gesproken bevat een constante altijd een gegevenstype. In de letterlijke expressie geven we alleen de waarde op. Het gegevenstype kan worden afgeleid van de waarde (bijvoorbeeld tekenreeks, geheel getal, decimaal enz.). Voor specifieke gevallen, zoals datumtijd, gebruiken wij specifieke functies voor de vertegenwoordiging.

Hieronder wordt beschreven hoe expressies van gegevenstypen worden weergegeven:

<table>
    <thead>
        <tr>
        <td>Gegevenstype</td>
        <td>Beschrijving</td>
        <td>Letterlijke vertegenwoordiging</td>
        <td>Voorbeeld</td>
        </tr>
    </thead>
    <tbody>
    <tr>
        <td>string</td>
        <td><p>Algemene reeks tekens.</p><p>Het heeft geen specifieke grootte behalve impliciet die uit het milieu zoals de beschikbare hoeveelheid geheugen komt.</p><p>JSON-indeling: String</p><p>Serienummeringsindeling: UTF-8</p></td>
        <td><p>"&lt;value&gt;"</p><p>'&lt;value&gt;'</p></td>
        <td><p><pre>"hello world"</pre></p><p><pre>'hello world'</pre></p></td>
    </tr>
    <tr>
        <td>integer</td>
        <td><p>Gehele waarde van -2^63 tot 2^63-1.</p><p>JSON-indeling: Getal</p></td>
        <td>&lt;geheel getal&gt;</td>
        <td><p><pre>42</pre></p></td>
    </tr>
    <tr>
        <td>decimaal</td>
        <td><p>Decimaal getal.</p><p>Deze vertegenwoordigt een zwevende waarde:</p>
        <p>- grootste positieve eindige waarde van type dubbel, (2-2^-52)x2^1023</p>
        <p> - kleinste positieve normale waarde van type double, 2-1022</p>
        <p> - kleinste positieve niet-nulwaarde van type double, 2 p-1074</p><p>JSON-indeling: Getal</p><p>Serienummeringsindeling: gebruiken '.' als decimaalteken.</p></td>
        <td>&lt;geheel getal&gt;.&lt;geheel getal&gt;</td>
        <td><p><pre>3.14</pre></p></td>
    </tr>
    <tr>
        <td>boolean</td>
        <td><p>Booleaanse waarde, in kleine letters geschreven: true of false</p><p>JSON-indeling: Boolean</p></td>
        <td><p>true</p><p>false</p></td>
        <td><p><pre>true</pre></p></td>
    </tr>
    <tr>
        <td>dateTimeOnly</td>
        <td><p>Vertegenwoordigt een datumtijd zonder een tijdzone, die als jaar-maand-dag-uur-minuut-seconde-milliseconde wordt bekeken.</p><p>Er wordt geen tijdzone opgeslagen of weergegeven.</p><p>In plaats daarvan is het een beschrijving van de datum, zoals die voor verjaardagen wordt gebruikt, gecombineerd met de lokale tijd zoals die op een muurklok wordt gezien.</p><p>Het kan geen onmiddellijk op tijdlijn zonder extra informatie zoals een compensatie of tijdzone vertegenwoordigen.</p><p>Serienummeringsindeling: ISO-8601 extended offset date-time format.</p><p>Er wordt DateTimeFormatter gebruikt.</p><p>ISO_LOCAL_DATE_TIME om de waarde te deserialiseren en serialiseren.</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME">Meer informatie</a>.</td>
        <td><p>toDateTimeOnly("&lt;dateTimeOnly in ISO-8601-indeling&gt;")</p></td>
        <td></td>
    </tr>
    <tr>
        <td>dateTime</td>
        <td><p>Datumtijdconstante die ook rekening houdt met tijdzone.</p><p>Deze vertegenwoordigt een datum-tijd met een verschuiving van UTC. Het kan als onmiddellijk in tijd met de extra informatie van de compensatie worden bekeken. </p><p>Het is een manier om een specifiek "moment" te vertegenwoordigen op een bepaalde plaats in de wereld.</p><p>JSON-indeling: Tekenreeks.</p><p> Deze moet zijn ingekapseld in een toDateTime-functie.</p><p>
        Serienummeringsindeling: ISO-8601 extended offset date-time format.</p><p> Het gebruikt DateTimeFormatter.ISO_OFFSET_DATE_TIME om de waarde te deserialiseren en serialiseren.</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME">Meer informatie</a>. 
        <p>U kunt ook een geheel getal doorgeven dat een epochwaarde doorgeeft.</p> <a href="https://www.epochconverter.com/">Meer informatie</a>.</p>
        <p>De tijdzone kan door een compensatie of een code van de tijdzone worden gespecificeerd (voorbeeld: Europa/Parijs, Z - UTC).</p></td>
        <td><p>toDateTime("&lt;dateTime in ISO-8601-indeling&gt;")</p>
        <p>toDateTime(&lt;geheel-getalwaarde van een tijdperk in milliseconden&gt;)</p></td>
        <td><p><pre>toDateTime("1977-04-22T06:00:00Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123+02:00")</pre></p>
        <p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123-00:20")</pre></p><p><pre>toDateTime(1560762190189)</pre></p></td>
    </tr>
    <tr>
        <td>duur</td>
        <td><p>Het vertegenwoordigt een tijd-gebaseerde hoeveelheid tijd, zoals "34.5 seconden".</p><p> Het modelleert een hoeveelheid of een hoeveelheid tijd in milliseconden.</p><p>De ondersteunde tijdseenheden zijn: milliseconden, seconden, minuten, uren, dagen waarbij een dag gelijk is aan 24 uur.</p><p> Jaren en maanden worden niet ondersteund omdat het geen vaste tijd is.</p><p>JSON-indeling: Tekenreeks. Het moet in een toDuration functie worden ingekapseld.</p><p>Serienummeringsindeling: Als u een tijdzone-id wilt deserialiseren, wordt de java-functie java.time gebruikt.</p><p>Duration.parse: de aanvaarde formaten zijn gebaseerd op de ISO-8601-duurnotatie PnDTnHnMn.nS met dagen die precies 24 uur worden geacht.</p><a href="https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-">Meer informatie</a>.</td>
        <td><p>toDuration("&lt;duration in ISO-8601 format&gt;")</p><p>toDuration(&lt;duration in milliseconds&gt;)</p></td>
        <td><p><pre>toDuration("PT5S") // 5 seconden</pre></p>
        <p><pre>toDuration(500) // </pre></p>
        <p><pre>500ms</pre></p>
        <p><pre>toDuration("PT20.345S") </pre></p>
        <p><pre>— parseert als "20,345 seconden"</pre></p>
        <p><pre>toDuration("PT15M") </pre></p>
        <p><pre> — parseert als "15 minuten"</pre></p>
        <p><pre>(waarbij een minuut 60 seconden is)</pre></p>
        <p><pre>toDuration("PT10H") </pre></p>
        <p><pre>— parseert als "10 uur"</pre></p>
        <p><pre>(waarbij een uur 3600 seconden is)</pre></p>
        <p><pre>toDuration("P2D") </pre></p>
        <p><pre>— parseert als "2 dagen"</pre></p>
        <p><pre>(waarbij een dag </pre></p>
        <p><pre>24 uur of 86400 seconden)</pre></p>
        <p><pre>toDuration("P2DT3H4M") </pre></p>
        <p><pre>— parseren als</pre></p>
        <p><pre>"2 dagen, 3 uur en 4 minuten"</pre></p>
        <p><pre>toDuration("P-6H3M") </pre></p>
        <p><pre>— parseren als</pre></p>
        <p><pre>"-6 uur en +3 minuten"</pre></p>
        <p><pre>toDuration("-P6H3M") </pre></p>
        <p><pre>— parseren als</pre></p>
        <p><pre>"-6 uur en -3 minuten"</pre></p>
        <p><pre>toDuration("-P-6H+3M") </pre></p>
        <p><pre>— parseren als</pre></p>
        <p><pre>"+6 uur en -3 minuten"</pre></p></td>
    </tr>
    <tr>
        <td>list</td>
        <td>Door komma's gescheiden lijst met expressies waarbij vierkante haakjes als scheidingstekens worden gebruikt. Polymorfisme wordt niet ondersteund en daarom moeten alle uitdrukkingen in de lijst van hetzelfde type zijn.</td>
        <td>[&lt;expression&gt;, &lt;expression&gt;, ... ]</td>
        <td><p><pre>["value1","value2"]</pre></p><p><pre>[3,5]</pre></p><p><pre>[toDuration(500),toDuration(800)]</pre></p></td>
    </tr>
    </tbody>
</table>
