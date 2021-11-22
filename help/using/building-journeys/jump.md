---
product: adobe campaign
title: Van de ene journey naar de andere gaan
description: Van de ene journey naar de andere gaan
feature: Journeys
role: User
level: Intermediate
exl-id: 520376aa-2cb5-46d6-8f21-3e03544f5da1
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 3%

---

# Van de ene journey naar de andere gaan {#jump}

De **[!UICONTROL Jump]** door actie kunt u individuen van de ene reis naar de andere duwen. Met deze functie kunt u:

* vereenvoudigen het ontwerp van zeer complexe reizen door deze in verschillende te splitsen
* ritten bouwen op basis van gemeenschappelijke en herbruikbare reispatronen

Voeg eenvoudig een **[!UICONTROL Jump]** en selecteer een doelreis. Wanneer het individu de **[!UICONTROL Jump]** stap, wordt een interne gebeurtenis verzonden naar de eerste gebeurtenis van de doelreis. Als de **[!UICONTROL Jump]** de actie is succesvol , het individu blijft op reis . Het gedrag is vergelijkbaar met andere acties.

Tijdens de doelrit wordt de eerste gebeurtenis intern geactiveerd door de **[!UICONTROL Jump]** de activiteit zal de individuele doorstroming van de reis maken .

>[!NOTE]
>
>Raadpleeg ook de zelfstudievideo [hier](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/building-a-journey/jumping-to-another-journey.html)

## Levenscyclus

Laten we zeggen dat u een **[!UICONTROL Jump]** activiteit op reis A naar reis B. Reis A is de **oorspronkelijke reis** en reis B **doelreis**.
Hier volgen de verschillende stappen van het uitvoeringsproces:

**Reis A** wordt geactiveerd door een externe gebeurtenis:

1. Reis A ontvangt een externe gebeurtenis met betrekking tot een individu.
1. De persoon bereikt de **[!UICONTROL Jump]** stap.
1. Het individu wordt naar Journey B geduwd en gaat naar de volgende stappen in Reis A, na **[!UICONTROL Jump]** stap.

Bij reis B wordt het eerste evenement intern geactiveerd, via de **[!UICONTROL Jump]** activiteit van reis A:

1. Journey B ontving een intern evenement van Journey A.
1. Het individu begint te stromen in Journey B.

>[!NOTE]
>
>Reis B kan ook worden geactiveerd via een externe gebeurtenis.

## Best practices en beperkingen

### Authoring

* De **[!UICONTROL Jump]** activiteit is alleen beschikbaar bij reizen die een naamruimte gebruiken.
* U kunt alleen naar een reis springen die dezelfde naamruimte gebruikt als de oorspronkelijke reis.
* U kunt niet naar een reis springen die begint met een **Segmentkwalificatie** gebeurtenis.
* U kunt geen **[!UICONTROL Jump]** en **Segmentkwalificatie** tijdens dezelfde reis.
* U kunt maximaal **[!UICONTROL Jump]** activiteiten die u op reis nodig hebt. Na een **[!UICONTROL Jump]**, kunt u elke gewenste activiteit toevoegen.
* U kunt zo veel sprongniveaus hebben zoals nodig. Reis A springt bijvoorbeeld naar reis B, die naar reis C gaat enzovoort.
* De doelreis kan ook het aantal **[!UICONTROL Jump]** activiteiten indien nodig.
* Luspatronen worden niet ondersteund. Er is geen manier om twee of meer reizen aan elkaar te koppelen, wat een oneindige lus zou creëren. De **[!UICONTROL Jump]** Het scherm van de activiteitenconfiguratie verhindert u dit te doen.

### Uitvoering

* Wanneer de **[!UICONTROL Jump]** de activiteit wordt uitgevoerd, wordt de recentste versie van de doelreis teweeggebracht.
* Zoals gebruikelijk kan een uniek individu slechts eenmaal op dezelfde reis aanwezig zijn. Als het individu dat van de oorspronkelijke reis werd geduwd al op de doelreis zit, zal het individu dus niet de doelreis betreden. Er wordt geen fout gerapporteerd in de **[!UICONTROL Jump]** activiteit omdat dit een normaal gedrag is.

## De sprongactiviteit configureren

1. Ontwerp uw **oorspronkelijke reis**.

   ![](../assets/jump1.png)

1. Voeg bij elke stap van de reis een **[!UICONTROL Jump]** van de **[!UICONTROL ACTIONS]** categorie. Voeg een label en beschrijving toe.

   ![](../assets/jump2.png)

1. Klik in het dialoogvenster **Doelreis** veld.
De lijst toont alle reisversies die ontwerp, levend of in testwijze zijn. Reizen die een andere naamruimte gebruiken of die beginnen met een **Segmentkwalificatie** is niet beschikbaar. Doeltrajecten die een luspatroon zouden maken, worden ook uitgefilterd.

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >U kunt op de knop **Doelreis openen** aan de rechterkant om de doelreis in een nieuw tabblad te openen.

1. Selecteer de doelreis waarnaar u wilt springen.
De **Eerste gebeurtenis** veld wordt voorgevuld met de naam van de eerste gebeurtenis van de doelreis. Als uw doelreis meerdere gebeurtenissen bevat, **[!UICONTROL Jump]** is alleen toegestaan op de eerste gebeurtenis.

   ![](../assets/jump4.png)

1. De **Handelingsparameters** worden alle velden van de doelgebeurtenis weergegeven. Net als bij andere typen acties wijst u elk veld met velden uit de gebeurtenis van oorsprong of de gegevensbron toe. Deze informatie wordt tijdens runtime doorgegeven aan de doelroute.
1. Voeg de volgende activiteiten toe om uw oorspronkelijke reis te voltooien.

   ![](../assets/jump5.png)


   >[!NOTE]
   >
   >De identiteit van het individu wordt automatisch toegewezen. Deze informatie is niet zichtbaar in de interface.

Uw **[!UICONTROL Jump]** activiteit wordt gevormd. Zodra uw reis of in testwijze levend is, bereiken individuen die **[!UICONTROL Jump]** de stap zal worden gezet van naar de doelreis .

Wanneer een **[!UICONTROL Jump]** activiteit wordt gevormd in een reis, a **[!UICONTROL Jump]** het ingangspictogram wordt automatisch toegevoegd aan het begin van de doelreis. Dit helpt u identificeren dat de reis extern maar ook intern van kan teweegbrengen **[!UICONTROL Jump]** activiteit.

![](../assets/jump7.png)

## Problemen oplossen

Bij publicatie van de reis of in testmodus treden fouten op als:
* de beoogde reis is niet langer mogelijk
* de doelreis is een concept, een gesloten of een stilstand
* als de eerste gebeurtenis van de doelreis is gewijzigd en de mapping is verbroken

![](../assets/jump6.png)
