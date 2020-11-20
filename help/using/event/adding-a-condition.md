---
product: adobe campaign
solution: Journey Orchestration
title: Voorwaarde toevoegen
description: Leer hoe u een voorwaarde toevoegt
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 4%

---



# Voorwaarde toevoegen {#concept_rbg_gqt_52b}

Met de gebeurtenisvoorwaarde kan het systeem de verwerking van gebeurtenissen filteren. Als de voorwaarde waar is, wordt de gebeurtenis verwerkt. Als de voorwaarde niet waar is, wordt de gebeurtenis genegeerd.

De voorwaarde voor gebeurtenissen kan alleen worden gebaseerd op gegevens die worden doorgegeven in de gebeurtenislading. De voorwaarde die op gebeurtenisniveau is gedefinieerd, kan niet op het canvas worden gewijzigd door een markeerteken. Het doel is deze voorwaarde te verharden wanneer deze gebeurtenis wordt gebruikt. Als je bijvoorbeeld nooit wilt dat marketers gebeurtenissen voor het verlaten van winkelwagentjes gebruiken als de waarde van het winkelwagentje te klein is, kun je een voorwaarde maken voor het gebeurtenisveld &#39;waarde van winkelwagentje&#39; en een waarde van meer dan 100 dollar opleggen.

U kunt de eenvoudige uitdrukkingsredacteur of de geavanceerde uitdrukkingsredacteur aan opstellingsvoorwaarden op gebeurtenissen gebruiken. Zie [deze pagina](../expression/expressionadvanced.md).

U kunt bijvoorbeeld een voorwaarde definiëren om alleen de gebeurtenissen van een specifiek gebeurtenistype te verwerken en de andere typen te negeren. Of als uw gebeurtenis een winkelwagentje is en de lading het waardegebied van het wagentje omvat, kunt u een gebeurtenisvoorwaarde bepalen om de gebeurtenissen te verwerken slechts als de kartwaarde groter is dan 100 dollars.

![](../assets/journey78.png)
