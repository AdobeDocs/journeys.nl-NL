---
product: adobe campaign
title: Informatie over Adobe Experience Platform-segmenten
description: Leer hoe u een Adobe Experience Platform-segment configureert
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 0%

---

# Informatie over Adobe Experience Platform-segmenten {#about-segments}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


Als u de [ Dienst van de Segmentatie van Adobe Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=nl-NL) gebruikt om uw segmenten tot stand te brengen, kunt u hefboomwerking hen in [!DNL Journey Orchestration]. Dankzij een toegewijde gebeurtenisactiviteit kunt u ervoor zorgen dat individuen op basis van Adobe Experience Platform-segmentingangen en -uitgangen een reis maken of vooruit gaan. Hierdoor kunt u ook complexe omstandigheden maken tijdens uw reizen met behulp van de eenvoudige of geavanceerde expressieeditor.

Laten we zeggen dat je een &quot;zilveren klant&quot;-segment hebt. Met deze activiteit, kunt u alle nieuwe zilveren klanten een reis maken en hen een reeks gepersonaliseerde berichten verzenden. U kunt ook eenvoudig voorwaarden bouwen die op dit segment worden gebaseerd.

Hier volgen de mogelijkheden die [!DNL Journey Orchestration] u biedt met segmenten:

* Open de lijst met Adobe Experience Platform-segmenten. Zie [ Creërend een segment ](../segment/creating-a-segment.md).
* Maak rechtstreeks segmenten in [!DNL Journey Orchestration] op dezelfde manier als u ze maakt met de Segmentatieservice. Zie [ Creërend een segment ](../segment/creating-a-segment.md).
* Gebruik de eenvoudige of geavanceerde expressie-editor om segmenten in de reisomstandigheden te benutten. Zie [ Gebruikend segmenten in voorwaarden ](../segment/using-a-segment.md).
* Voeg een **[!UICONTROL Segment qualification]** -gebeurtenis toe aan uw reis om te luisteren naar de items en uitgangen van profielen in Adobe Experience Platform-segmenten. Zie [ de activiteiten van Gebeurtenissen ](../building-journeys/segment-qualification-events.md).

## Evaluatiemethode in Journey Orchestration {#evaluation-method-in-journey-orchestration}

In Journey Orchestration wordt het publiek op basis van segmentdefinities op basis van een van de volgende evaluatiemethoden gegenereerd:

* Streaming segmentatie: de publiekslijst voor het segment wordt in real-time bijgewerkt terwijl nieuwe gegevens in het systeem stromen.
* De segmentatie van de partij - de publiekslijst voor het segment wordt bijgewerkt op een uurbasis, die op gegevens wordt gebaseerd die in het afgelopen uur zijn aangekomen.

De bepaling tussen partijsegmentatie en het stromen segmentatie wordt gemaakt door het systeem voor elke segmentdefinitie, die op de ingewikkeldheid en de kosten wordt gebaseerd om de segmentregel te evalueren.

U kunt de evaluatiemethode voor elk segment in de **[!UICONTROL Evaluation method]** kolom van de segmentlijst bekijken.

Nadat u een segment hebt gedefinieerd, worden profielen toegevoegd aan het publiek wanneer deze in aanmerking komen.

Het ondersteunen van het publiek op basis van eerdere gegevens kan 24 uur in beslag nemen. Nadat het publiek is teruggevuld, wordt het publiek voortdurend bijgewerkt en is altijd klaar om zich te richten.