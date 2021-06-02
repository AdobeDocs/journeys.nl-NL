---
product: adobe campaign
title: random
description: Meer informatie over de willekeurige functie
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: c47dc5f0-ea69-4814-863b-e0e483ba7770
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 7%

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
