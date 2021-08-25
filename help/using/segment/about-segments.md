---
product: adobe campaign
title: Informatie over Adobe Experience Platform-segmenten
description: Leer hoe u een Adobe Experience Platform-segment configureert
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
source-git-commit: e5c0db2e1f85ea72fd54f91e4a26cc287377fb0e
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 0%

---

# Informatie over Adobe Experience Platform-segmenten {#about-segments}

Als u [Adobe Experience Platform Segmentation Service](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html) gebruikt om uw segmenten te creëren, kunt u hen in [!DNL Journey Orchestration] hefboomwerking. Dankzij een toegewijde gebeurtenisactiviteit kunt u ervoor zorgen dat individuen op basis van Adobe Experience Platform-segmentingangen en -uitgangen een reis maken of vooruit gaan. Hierdoor kunt u ook complexe omstandigheden maken tijdens uw reizen met de eenvoudige of geavanceerde expressieeditor.

Laten we zeggen dat je een &quot;zilveren klant&quot;-segment hebt. Met deze activiteit, kunt u alle nieuwe zilveren klanten een reis maken en hen een reeks gepersonaliseerde berichten verzenden. U kunt ook eenvoudig voorwaarden bouwen die op dit segment worden gebaseerd.

Hier zijn de mogelijkheden [!DNL Journey Orchestration] u met segmenten aanbieden:

* Open de lijst met Adobe Experience Platform-segmenten. Zie [Een segment maken](../segment/creating-a-segment.md).
* Maak rechtstreeks segmenten in [!DNL Journey Orchestration] op dezelfde manier als u ze maakt met de Segmentatieservice. Zie [Een segment maken](../segment/creating-a-segment.md).
* Gebruik de eenvoudige of geavanceerde expressie-editor om segmenten in de reisomstandigheden te benutten. Zie [Segmenten gebruiken in condities](../segment/using-a-segment.md).
* Voeg een gebeurtenis **[!UICONTROL Segment qualification]** toe aan uw reis om naar de ingangen en de uitgang van profielen in de segmenten van Adobe Experience Platform te luisteren. Zie [Gebeurtenisactiviteiten](../building-journeys/segment-qualification-events.md).

## Evaluatiemethode in Journey Orchestration {#evaluation-method-in-journey-orchestration}

In Journey Orchestration wordt het publiek gegenereerd op basis van segmentdefinities aan de hand van een van de volgende evaluatiemethoden:

* Streaming segmentatie: de publiekslijst voor het segment wordt in real-time bijgewerkt terwijl nieuwe gegevens in het systeem stromen.
* De segmentatie van de partij - de publiekslijst voor het segment wordt bijgewerkt op een uurbasis, die op gegevens wordt gebaseerd die in het afgelopen uur zijn aangekomen.

De bepaling tussen partijsegmentatie en het stromen segmentatie wordt gemaakt door het systeem voor elke segmentdefinitie, die op de ingewikkeldheid en de kosten wordt gebaseerd om de segmentregel te evalueren.

U kunt de evaluatiemethode voor elk segment in **[!UICONTROL Evaluation method]** kolom van de segmentlijst bekijken.

Nadat u een segment hebt gedefinieerd, worden profielen toegevoegd aan het publiek wanneer deze in aanmerking komen.

Het ondersteunen van het publiek op basis van eerdere gegevens kan 24 uur in beslag nemen. Nadat het publiek is teruggevuld, wordt het publiek voortdurend bijgewerkt en is altijd klaar om zich te richten.