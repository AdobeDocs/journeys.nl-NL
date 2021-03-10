---
product: adobe campaign
solution: Journey Orchestration
title: Van de ene journey naar de andere gaan
description: Van de ene journey naar de andere gaan
feature: Reizen
role: Zakelijke praktiserer
level: Intermediair
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 3%

---


# Van de ene journey naar de andere gaan {#jump}

Met de actie **[!UICONTROL Jump]** kunt u personen van de ene reis naar de andere verplaatsen. Met deze functie kunt u:

* vereenvoudigen het ontwerp van zeer complexe reizen door deze in verschillende te splitsen
* ritten bouwen op basis van gemeenschappelijke en herbruikbare reispatronen

Voeg in de oorspronkelijke reis gewoon een **[!UICONTROL Jump]** activiteit toe en selecteer een doelreis. Wanneer het individu de stap **[!UICONTROL Jump]** ingaat, wordt een interne gebeurtenis verzonden naar de eerste gebeurtenis van de doelreis. Als de actie **[!UICONTROL Jump]** succesvol is, blijft het individu in de reis voortgaan. Het gedrag is vergelijkbaar met andere acties.

In de doelreis zal de eerste gebeurtenis die intern door de **[!UICONTROL Jump]** activiteit wordt teweeggebracht de individuele stroom in de reis maken.

>[!NOTE]
>
>Raadpleeg ook de videozelfstudie [hier](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/building-a-journey/jumping-to-another-journey.html)

## Levenscyclus

Laten we zeggen dat u een **[!UICONTROL Jump]** activiteit in een reis A aan reis B hebt toegevoegd. Reis A is de **oorspronkelijke reis** en reis B, de **doelreis**.
Hier volgen de verschillende stappen van het uitvoeringsproces:

**Reis** geactiveerd door een externe gebeurtenis:

1. Reis A ontvangt een externe gebeurtenis met betrekking tot een individu.
1. De persoon bereikt de stap **[!UICONTROL Jump]**.
1. Het individu wordt geduwd aan Reis B, en gaat naar de volgende stappen in Reis A, na de **[!UICONTROL Jump]** stap.

In reis B wordt het eerste evenement intern geactiveerd via de **[!UICONTROL Jump]** activiteit van reis A:

1. Journey B ontving een intern evenement van Journey A.
1. Het individu begint te stromen in Journey B.

>[!NOTE]
>
>Reis B kan ook worden geactiveerd via een externe gebeurtenis.

## Best practices en beperkingen

### Authoring

* De **[!UICONTROL Jump]** activiteit is slechts beschikbaar in reizen die een namespace gebruiken.
* U kunt alleen naar een reis springen die dezelfde naamruimte gebruikt als de oorspronkelijke reis.
* U kunt niet naar een reis springen die met een **segmentkwalificatie** gebeurtenis begint.
* U kunt geen **[!UICONTROL Jump]** activiteit en een **gebeurtenis van de segmentkwalificatie** in de zelfde reis hebben.
* U kunt zo veel **[!UICONTROL Jump]** activiteiten omvatten aangezien u in een reis nodig hebt. Na een **[!UICONTROL Jump]** kunt u elke gewenste activiteit toevoegen.
* U kunt zo veel sprongniveaus hebben zoals nodig. Reis A springt bijvoorbeeld naar reis B, die naar reis C gaat enzovoort.
* De doelreis kan ook zoveel **[!UICONTROL Jump]** activiteiten omvatten als nodig.
* Luspatronen worden niet ondersteund. Er is geen manier om twee of meer reizen aan elkaar te koppelen, wat een oneindige lus zou creëren. Het **[!UICONTROL Jump]** scherm van de activiteitenconfiguratie verhindert u dit te doen.

### Execution

* Wanneer de **[!UICONTROL Jump]** activiteit wordt uitgevoerd, wordt de recentste versie van de doelreis teweeggebracht.
* Zoals gebruikelijk kan een uniek individu slechts eenmaal op dezelfde reis aanwezig zijn. Als het individu dat van de oorspronkelijke reis werd geduwd al op de doelreis zit, zal het individu dus niet de doelreis betreden. Er wordt geen fout gerapporteerd bij de activiteit **[!UICONTROL Jump]** omdat dit een normaal gedrag is.

## De sprongactiviteit configureren

1. Ontwerp uw **oorspronkelijke reis**.

   ![](../assets/jump1.png)

1. Voeg bij elke stap van de rit een **[!UICONTROL Jump]** activiteit toe uit de categorie **[!UICONTROL ACTIONS]**. Voeg een label en beschrijving toe.

   ![](../assets/jump2.png)

1. Klik in het veld **Doel**.
De lijst toont alle reisversies die ontwerp, levend of in testwijze zijn. De reizen die een verschillende namespace gebruiken of die met een **gebeurtenis van het Segment** beginnen zijn niet beschikbaar. Doeltrajecten die een luspatroon zouden maken, worden ook uitgefilterd.

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >U kunt op het pictogram **Doelreis openen** aan de rechterkant klikken om de doelreis in een nieuw lusje te openen.

1. Selecteer de doelreis waarnaar u wilt springen.
Het veld **Eerste gebeurtenis** wordt voorgevuld met de naam van de eerste gebeurtenis van de doelreis. Als uw doelreis veelvoudige gebeurtenissen omvat, is **[!UICONTROL Jump]** slechts toegestaan op de eerste gebeurtenis.

   ![](../assets/jump4.png)

1. In de sectie **Handelingsparameters** worden alle velden van de doelgebeurtenis weergegeven. Net als bij andere typen acties wijst u elk veld met velden uit de gebeurtenis van oorsprong of de gegevensbron toe. Deze informatie wordt tijdens runtime doorgegeven aan de doelroute.
1. Voeg de volgende activiteiten toe om uw oorspronkelijke reis te voltooien.

   ![](../assets/jump5.png)


   >[!NOTE]
   >
   >De identiteit van het individu wordt automatisch toegewezen. Deze informatie is niet zichtbaar in de interface.

Uw **[!UICONTROL Jump]** activiteit wordt gevormd. Zodra uw reis of in testwijze levend is, zullen de individuen die de **[!UICONTROL Jump]** stap bereiken van aan de doelreis worden geduwd.

Wanneer een **[!UICONTROL Jump]** activiteit in een reis wordt gevormd, wordt een **[!UICONTROL Jump]** ingangspictogram automatisch toegevoegd aan het begin van de doelreis. Dit helpt u identificeren dat de reis extern maar ook intern van een **[!UICONTROL Jump]** activiteit kan worden teweeggebracht.

![](../assets/jump7.png)

## Problemen oplossen

Bij publicatie van de reis of in testmodus treden fouten op als:
* de beoogde reis is niet langer mogelijk
* de doelreis is een concept, een gesloten of een stilstand
* als de eerste gebeurtenis van de doelreis is gewijzigd en de mapping is verbroken

![](../assets/jump6.png)
