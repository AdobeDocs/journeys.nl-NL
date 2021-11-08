---
product: adobe campaign
title: serializeList
description: Meer informatie over de functie serializeList
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 84912d38-32ee-4cfe-8cb4-bad12f9c52af
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 19%

---

# serializeList {#serializeList}

Hiermee wordt de lijst (elk type) in de eerste parameter omgezet in een tekenreeks. De tweede parameter vertegenwoordigt het te gebruiken scheidingsteken. De derde parameter is een booleaanse waarde die aangeeft of elk element van de expressie aanhalingstekens moet bevatten.

## Categorie

Lijst

## Functiesyntaxis

`serializeList(<parameters>)`

## Parameters

| Parameter | Type |
|-----------|------------------|
| Tekenreeks | Tekenreeks |
| Boolean | Boolean |
| DateTimeOnly | DateTimeOnly |
| Lijst | listString |
| Lijst | listBoolean |
| Lijst | listPoint |
| Lijst | listDecimal |
| Lijst | listDuration |
| Lijst | listDateTime |
| Lijst | listDateTimeOnly |
| Lijst | listDateOnly |

## Handtekening en type geretourneerd

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDateOnly>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

`serializeList(<listPoint>,<string>,<boolean>)`

Retourneer een tekenreeks.

## Voorbeeld

`serializeList(["Hello","World"], " ", false)`

Retourneert &quot;Hello World&quot;.

`serializeList(["Hello", "World"], ",", true)`

Retourneert &quot;&quot;Hello&quot;,&quot;World&quot;&quot;.
