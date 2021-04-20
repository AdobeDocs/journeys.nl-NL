---
product: adobe campaign
solution: Journey Orchestration
title: Voorwaarde toevoegen
description: Leer hoe u een voorwaarde toevoegt
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 4%

---



# Voorwaarde toevoegen {#concept_rbg_gqt_52b}

Voor door het systeem gegenereerde gebeurtenissen kunt u een gebeurtenisvoorwaarde definiëren waarmee het systeem de verwerking van gebeurtenissen kan filteren. Als de voorwaarde waar is, wordt de gebeurtenis verwerkt. Als de voorwaarde niet waar is, wordt de gebeurtenis genegeerd.

De voorwaarde voor gebeurtenissen kan alleen worden gebaseerd op gegevens die worden doorgegeven in de gebeurtenislading. De voorwaarde die op gebeurtenisniveau is gedefinieerd, kan niet op het canvas worden gewijzigd door een markeerteken. Het doel is deze voorwaarde te verharden wanneer deze gebeurtenis wordt gebruikt. Als je bijvoorbeeld nooit wilt dat marketers gebeurtenissen voor het verlaten van winkelwagentjes gebruiken als de waarde van het winkelwagentje te klein is, kun je een voorwaarde maken voor het gebeurtenisveld &#39;waarde van winkelwagentje&#39; en een waarde van meer dan 100 dollar opleggen.

U kunt de eenvoudige uitdrukkingsredacteur of de geavanceerde uitdrukkingsredacteur aan opstellingsvoorwaarden op gebeurtenissen gebruiken. Zie [deze pagina](../expression/expressionadvanced.md).

U kunt bijvoorbeeld een voorwaarde definiëren om alleen de gebeurtenissen van een specifiek gebeurtenistype te verwerken en de andere typen te negeren. Of als uw gebeurtenis een winkelwagentje is en de lading het waardegebied van het wagentje omvat, kunt u een gebeurtenisvoorwaarde bepalen om de gebeurtenissen te verwerken slechts als de kartwaarde groter is dan 100 dollars.

![](../assets/journey78.png)
