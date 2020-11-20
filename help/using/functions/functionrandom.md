---
product: adobe campaign
solution: Journey Orchestration
title: random
description: Meer informatie over de willekeurige functie
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 5%

---


# random {#random}

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
