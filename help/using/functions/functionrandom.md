---
title: willekeurig
description: Meer informatie over de willekeurige functie
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 0%

---


# willekeurig {#random}

Hiermee genereert u een willekeurig getal tussen 0 en 1.

## Categorie

Math

## Functiesyntaxis

`random(<parameters>)`

## Handtekening en type geretourneerd

`random()`

Retourneert een decimaal.

## Voorbeeld

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

Uitleg: als de succesverhouding geen waarde/waarde null heeft, wordt de standaardwaarde toegepast en is deze een willekeurig getal tussen 0 en 1 * 100 (dat wil zeggen 0 tot 100).
