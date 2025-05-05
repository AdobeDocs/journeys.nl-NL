---
product: adobe campaign
title: Van de ene journey naar de andere gaan
description: Van de ene journey naar de andere gaan
feature: Journeys
role: User
level: Intermediate
exl-id: 520376aa-2cb5-46d6-8f21-3e03544f5da1
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '822'
ht-degree: 2%

---

# Van de ene journey naar de andere gaan {#jump}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._



Met de actieactiviteit **[!UICONTROL Jump]** kunt u personen van de ene reis naar de andere verplaatsen. Met deze functie kunt u:

* vereenvoudigen het ontwerp van zeer complexe reizen door deze in verschillende te splitsen
* ritten bouwen op basis van gemeenschappelijke en herbruikbare reispatronen

Voeg in de oorspronkelijke reis gewoon een **[!UICONTROL Jump]** activiteit toe en selecteer een doelreis. Wanneer het individu de **[!UICONTROL Jump]** stap ingaat, wordt een interne gebeurtenis verzonden naar de eerste gebeurtenis van de doelreis. Als de **[!UICONTROL Jump]** actie succesvol is, blijft het individu in de reis voortgaan. Het gedrag is vergelijkbaar met andere acties.

Tijdens de doelrit maakt de eerste gebeurtenis die intern door de **[!UICONTROL Jump]** -activiteit wordt geactiveerd, de individuele flow in de reis.

## Levenscyclus

Laten wij zeggen u a **[!UICONTROL Jump]** activiteit in een reis A aan reis B. Reis A is de **oorsprongstrij** en reis B, de **doelreis** toegevoegd.
Hier volgen de verschillende stappen van het uitvoeringsproces:

**Reis A** wordt teweeggebracht van een externe gebeurtenis:

1. Reis A ontvangt een externe gebeurtenis met betrekking tot een individu.
1. De persoon bereikt de **[!UICONTROL Jump]** -stap.
1. Het individu wordt naar Journey B geduwd en gaat naar de volgende stappen in Reis A, na de **[!UICONTROL Jump]** stap.

Bij reis B wordt de eerste gebeurtenis intern geactiveerd, via de **[!UICONTROL Jump]** -activiteit van reis A:

1. Journey B ontving een intern evenement van Journey A.
1. Het individu begint te stromen in Journey B.

>[!NOTE]
>
>Reis B kan ook worden geactiveerd via een externe gebeurtenis.

## Best practices en beperkingen

### Authoring

* De **[!UICONTROL Jump]** -activiteit is alleen beschikbaar voor reizen die een naamruimte gebruiken.
* U kunt alleen naar een reis springen die dezelfde naamruimte gebruikt als de oorspronkelijke reis.
* U kunt niet aan een reis springen die met de kwalificatiegebeurtenis van het a **Segment** begint.
* U kunt geen a **[!UICONTROL Jump]** activiteit en a **de kwalificatiegebeurtenis van het Segment** in de zelfde reis hebben.
* U kunt zoveel **[!UICONTROL Jump]** activiteiten opnemen als u nodig hebt voor een reis. Na een **[!UICONTROL Jump]** kunt u alle benodigde activiteiten toevoegen.
* U kunt zo veel sprongniveaus hebben zoals nodig. Reis A springt bijvoorbeeld naar reis B, die naar reis C gaat enzovoort.
* De doeltocht kan ook zoveel **[!UICONTROL Jump]** activiteiten omvatten als nodig is.
* Luspatronen worden niet ondersteund. Er is geen manier om twee of meer reizen aan elkaar te koppelen, wat een oneindige lus zou creëren. Het scherm van de **[!UICONTROL Jump]** activiteitenconfiguratie verhindert u dit te doen.

### Execution

* Wanneer de **[!UICONTROL Jump]** activiteit wordt uitgevoerd, wordt de recentste versie van de doelreis teweeggebracht.
* Zoals gebruikelijk kan een uniek individu slechts eenmaal op dezelfde reis aanwezig zijn. Als het individu dat van de oorspronkelijke reis werd geduwd al op de doelreis zit, zal het individu dus niet de doelreis betreden. Er wordt geen fout gerapporteerd over de **[!UICONTROL Jump]** -activiteit omdat dit een normaal gedrag is.

## De sprongactiviteit configureren

1. Ontwerp uw **originele reis**.

   ![](../assets/jump1.png)

1. Voeg bij elke stap van de rit een **[!UICONTROL Jump]** activiteit toe vanuit de categorie **[!UICONTROL ACTIONS]** . Voeg een label en beschrijving toe.

   ![](../assets/jump2.png)

1. Klik binnen het **reis van het Doel** gebied.
In de lijst worden alle reisversies weergegeven die concept, live of in de testmodus zijn. De reizen die een verschillende namespace gebruiken of die met de kwalificatiegebeurtenis van het a **Segment** beginnen zijn niet beschikbaar. Doeltrajecten die een luspatroon zouden maken, worden ook uitgefilterd.

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >U kunt het **Open doelreis** pictogram, op de rechterkant klikken, om de doelreis in een nieuw lusje te openen.

1. Selecteer de doelreis waarnaar u wilt springen.
Het **Eerste gebeurtenis** gebied wordt voorgevuld met de naam van de eerste gebeurtenis van de doelreis. Als uw doelreis meerdere gebeurtenissen bevat, is **[!UICONTROL Jump]** alleen toegestaan voor de eerste gebeurtenis.

   ![](../assets/jump4.png)

1. De **parameters van de Actie** sectie toont alle gebieden van de doelgebeurtenis. Net als bij andere typen acties wijst u elk veld met velden uit de gebeurtenis van oorsprong of de gegevensbron toe. Deze informatie wordt tijdens runtime doorgegeven aan de doelroute.
1. Voeg de volgende activiteiten toe om uw oorspronkelijke reis te voltooien.

   ![](../assets/jump5.png)


   >[!NOTE]
   >
   >De identiteit van het individu wordt automatisch toegewezen. Deze informatie is niet zichtbaar in de interface.

Uw **[!UICONTROL Jump]** activiteit wordt gevormd. Zodra uw reis of in testmodus actief is, worden personen die de stap **[!UICONTROL Jump]** bereiken, van de doelreis overgezet.

Wanneer een **[!UICONTROL Jump]** activiteit in een reis wordt gevormd, wordt een **[!UICONTROL Jump]** ingangspictogram automatisch toegevoegd aan het begin van de doelreis. Dit helpt u identificeren dat de reis extern maar ook intern van een **[!UICONTROL Jump]** activiteit kan worden teweeggebracht.

![](../assets/jump7.png)

## Problemen oplossen

Bij publicatie van de reis of in testmodus treden fouten op als:
* de beoogde reis is niet langer mogelijk
* de doelreis is een concept, een gesloten of een stilstand
* als de eerste gebeurtenis van de doelreis is gewijzigd en de mapping is verbroken

![](../assets/jump6.png)
