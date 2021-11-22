---
product: adobe campaign
title: Adobe Experience Platform-segmenten
description: Leer hoe u een Adobe Experience Platform-segment configureert
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
source-git-commit: e5c0db2e1f85ea72fd54f91e4a26cc287377fb0e
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 2%

---

# Adobe Experience Platform-segmenten {#about-segments}

Als u de [Adobe Experience Platform Segmentation Service](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html) om uw segmenten te maken, kunt u deze benutten in [!DNL Journey Orchestration]. Dankzij een toegewijde gebeurtenisactiviteit kunt u ervoor zorgen dat individuen op basis van Adobe Experience Platform-segmentingangen en -uitgangen een reis maken of vooruit gaan. Hierdoor kunt u ook complexe omstandigheden maken tijdens uw reizen met de eenvoudige of geavanceerde expressieeditor.

Laten we zeggen dat je een &quot;zilveren klant&quot;-segment hebt. Met deze activiteit, kunt u alle nieuwe zilveren klanten een reis maken en hen een reeks gepersonaliseerde berichten verzenden. U kunt ook eenvoudig voorwaarden bouwen die op dit segment worden gebaseerd.

Hier zijn de mogelijkheden [!DNL Journey Orchestration] bieden u segmenten aan:

* Open de lijst met Adobe Experience Platform-segmenten. Zie [Een segment maken](../segment/creating-a-segment.md).
* Segmenten rechtstreeks maken in [!DNL Journey Orchestration] op dezelfde manier creeert u hen gebruikend de Dienst van de Segmentatie. Zie [Een segment maken](../segment/creating-a-segment.md).
* Gebruik de eenvoudige of geavanceerde expressie-editor om segmenten in de reisomstandigheden te benutten. Zie [Segmenten in omstandigheden gebruiken](../segment/using-a-segment.md).
* Voeg een **[!UICONTROL Segment qualification]** om te luisteren naar de toegang tot en het vertrek van profielen in Adobe Experience Platform-segmenten. Zie [Gebeurtenisactiviteiten](../building-journeys/segment-qualification-events.md).

## Evaluatiemethode in Journey Orchestration {#evaluation-method-in-journey-orchestration}

In Journey Orchestration wordt het publiek gegenereerd op basis van segmentdefinities aan de hand van een van de volgende evaluatiemethoden:

* Streaming segmentatie: de publiekslijst voor het segment wordt in real-time bijgewerkt terwijl nieuwe gegevens in het systeem stromen.
* De segmentatie van de partij - de publiekslijst voor het segment wordt bijgewerkt op een uurbasis, die op gegevens wordt gebaseerd die in het afgelopen uur zijn aangekomen.

De bepaling tussen partijsegmentatie en het stromen segmentatie wordt gemaakt door het systeem voor elke segmentdefinitie, die op de ingewikkeldheid en de kosten wordt gebaseerd om de segmentregel te evalueren.

U kunt de evaluatiemethode voor elk segment in bekijken **[!UICONTROL Evaluation method]** kolom van de segmentlijst.

Nadat u een segment hebt gedefinieerd, worden profielen toegevoegd aan het publiek wanneer deze in aanmerking komen.

Het ondersteunen van het publiek op basis van eerdere gegevens kan 24 uur in beslag nemen. Nadat het publiek is teruggevuld, wordt het publiek voortdurend bijgewerkt en is altijd klaar om zich te richten.