---
product: adobe campaign
solution: Journey Orchestration
title: Segmentactiviteit lezen
description: Meer informatie over de activiteit Leessegment.
translation-type: tm+mt
source-git-commit: 6ebedad2cb8e78b4dd953bc7a2993cebbeefabcc
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 4%

---


# Segmentactiviteit lezen {#segment-trigger-activity}

## Informatie over de activiteit Leessegment {#about-segment-trigger-actvitiy}

>[!NOTE]
>
>Als er op het canvas tijdens de publicatie of tijdens de activering van de testmodus een Adobe Campaign Standard-actie buiten de doos aanwezig is, wordt de rit vertraagd bij 13 ingangen per seconde. Anders zal de reis worden vertraagd bij 1000 gebeurtenissen per seconde.

Met de activiteit Leessegment kunt u alle personen die tot een Adobe Experience Platform-segment behoren een reis laten maken. Het starten van een journey kan één keer, of op regelmatige basis plaatsvinden.

Laten we zeggen dat je een Gold-klantensegment hebt op Adobe Experience Platform. Met de activiteit van het Leessegment, kunt u alle individuen van het Gouden klantensegment een reis maken en hen tot geïndividualiseerde reizen maken die alle reisfunctionaliteit gebruiken: voorwaarden, timers, gebeurtenissen, handelingen.

>[!NOTE]
>
>U kunt geen sprong en een **Gelezen segment** activiteit in de zelfde reis hebben. U kunt niet naar een reis springen die met een **Read segment** gebeurtenis begint.

## De activiteit {#configuring-segment-trigger-activity} configureren

>[!NOTE]
>
>Vanwege de vertraging bij de segmentuitvoer is het niet mogelijk om een op segmenten gebaseerde reis binnen een kortere periode dan 1 uur te activeren.

1. Ontvouw de **[!UICONTROL Orchestration]** categorie en laat vallen een **[!UICONTROL Read Segment]** activiteit in uw canvas.

   De activiteit moet als eerste stap van een reis worden geplaatst.

1. Voeg een **[!UICONTROL Label]** aan de activiteit (facultatief) toe.

1. Kies in het veld **[!UICONTROL Segment]** het Adobe Experience Platform-segment dat de rit moet ingaan en klik vervolgens op **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >U kunt de kolommen in de lijst aanpassen en sorteren.

   ![](../assets/segment-trigger-segment-selection.png)

   Zodra het segment wordt toegevoegd, staat **[!UICONTROL Copy]** knoop u toe om zijn naam en identiteitskaart te kopiëren:

   `{"name":"Gold customers,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-trigger-copy.png)

1. Kies in het veld **[!UICONTROL Namespace]** de naamruimte die u wilt gebruiken om de personen te identificeren. Raadpleeg [deze sectie](../event/selecting-the-namespace.md) voor meer informatie over naamruimten.

   >[!NOTE]
   >
   >Personen die behoren tot een segment dat niet de geselecteerde identiteit (naamruimte) onder hun verschillende identiteiten heeft, kunnen de reis niet betreden.

1. Met de **[!UICONTROL Read Segment]**-activiteit kunt u opgeven op welk tijdstip het segment de reis moet betreden. Om dit te doen, klik **[!UICONTROL Edit journey schedule]** verbinding om tot de eigenschappen van de reis toegang te hebben, dan vorm **[!UICONTROL Scheduler type]** gebied.

   ![](../assets/segment-trigger-schedule.png)

   Standaard komen segmenten **[!UICONTROL As soon as possible]** op de reis. Dit betekent 1 uur na publicatie van de reis. Als u wilt dat het segment de reis op een specifieke datum/tijd of op een terugkomende basis ingaat, selecteer de gewenste waarde van de lijst.

   >[!NOTE]
   >
   >De sectie **[!UICONTROL Schedule]** is alleen beschikbaar wanneer een activiteit **[!UICONTROL Read Segment]** op het canvas is neergezet.

   ![](../assets/segment-trigger-properties.png)

## De reis testen en publiceren {#testing-publishing}

Met de **[!UICONTROL Read Segment]**-activiteit kunt u de reis testen op een uniform profiel of op 100 willekeurig gekozen testprofielen uit de profielen die voor het segment in aanmerking komen.

Hiervoor activeert u de testmodus en selecteert u de gewenste optie in het linkerdeelvenster.

![](../assets/segment-trigger-test-modes.png)

U kunt de testwijze dan vormen en in werking stellen zoals gebruikelijk. Gedetailleerde stappen voor het testen van een reis worden beschreven in [deze sectie](../building-journeys/testing-the-journey.md).

Wanneer de test is uitgevoerd, kunt u met de knop **[!UICONTROL Show logs]** de testresultaten weergeven volgens de geselecteerde testoptie:

* **[!UICONTROL Single profile at a time]**: de teststammen bevatten dezelfde informatie als wanneer de monitaire testmodus wordt gebruikt. Raadpleeg [deze sectie](../building-journeys/testing-the-journey.md#viewing_logs) voor meer informatie

* **[!UICONTROL Up to 100 profiles at once]**: Aan de hand van de testlogboeken kunt u de voortgang van de segmentexport vanuit Adobe Experience Platform volgen, evenals de individuele voortgang van alle personen die de reis hebben betreden.

   Houd er rekening mee dat u door het testen van de reis met maximaal 100 profielen tegelijk de voortgang van de individuele personen op de reis niet kunt bijhouden met behulp van de visuele stroom.

   ![](../assets/read-segment-log.png)

Zodra de tests succesvol zijn, kunt u uw reis publiceren (zie [Publicerend de reis](../building-journeys/publishing-the-journey.md)). Personen die tot het segment behoren, komen de reis binnen op de datum/tijd die in de sectie **[!UICONTROL Scheduler]** in de eigendommen van de reis is vermeld.

>[!NOTE]
>
>Wanneer het doen van een nieuwe versie van een op segment-gebaseerde reis die niet terugkomt (die zo spoedig mogelijk begint of &quot;eens&quot;), zullen alle individuen die eerder de reis inging niet zijn nieuwe versie ingaan wanneer u het zult publiceren. Als u hen wilt toestaan om opnieuw binnen te komen, zou u de reis moeten dupliceren.
