---
title: Gebeurtenissen op basis van regels
description: Meer informatie over op regels gebaseerde gebeurtenissen.
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 11%

---


# Gebeurtenissen op basis van regels{#simplified-events}

We hebben de manier vereenvoudigd waarop u Experience-gebeurtenissen instelt. We introduceren een nieuwe methode waarvoor geen eventID nodig is. Wanneer u de gebeurtenis instelt in Journey Orchestration, kunt u nu een op regels gebaseerde gebeurtenis definiëren.

Dit nieuwe type gebeurtenis genereert geen eventID. Gebruikend de eenvoudige uitdrukkingsredacteur, definieert u nu eenvoudig een regel die door het systeem zal worden gebruikt om de relevante gebeurtenissen te identificeren die uw reizen zullen teweegbrengen. Deze regel kan worden gebaseerd op elk veld dat beschikbaar is in de gebeurtenislading, bijvoorbeeld de locatie van het profiel of het aantal items dat is toegevoegd aan het winkelwagentje van het profiel.

Deze nieuwe methode is meestal transparant voor gebruikers. De enige wijziging is een nieuw veld in het scherm met gebeurtenisdefinities.

>[!CAUTION]
>
>Een afschilderingsregel wordt bepaald voor op regel-gebaseerde gebeurtenissen. Het beperkt het aantal gekwalificeerde gebeurtenissen dat een reis kan verwerken tot 400 k per minuut. Neem contact op met het contactpunt voor het alpha-programma voor meer informatie.

## Adobe Analytics-gegevens gebruiken{#analytics-data}

>[!NOTE]
>
>Deze sectie is alleen van toepassing op klanten die Adobe Analytics-gegevens moeten gebruiken.

U kunt alle Adobe Analytics-gedragsgebeurtenisgegevens die u al vastlegt en in het Platform stroomt, benutten om reizen te starten en ervaringen voor uw klanten te automatiseren.

Dit werkt alleen als u in Adobe Experience Platform de rapportsuite activeert die u wilt gebruiken:

1. Selecteer vervolgens in Adobe Experience Platform **[!UICONTROL Sources]** **[!UICONTROL Add data]** de sectie Adobe Analytics. De lijst met beschikbare Adobe Analytics-rapportsuites wordt weergegeven.

1. Kies de rapportsuite die u wilt inschakelen, klik **[!UICONTROL Next]** en klik **[!UICONTROL Finish]**.

1. Deel de id van de brongegevens met uw Alpha- programmapunt van contact.

Dit laat de bron van Analytics schakelaar voor die rapportreeks toe. Telkens wanneer de gegevens binnenkomen, worden ze omgezet in een Experience-gebeurtenis en verzonden naar Adobe Experience Platform.

![](../assets/alpha-event9.png)

Raadpleeg de [documentatie](https://docs.adobe.com/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html) en [zelfstudie](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)voor meer informatie over de Adobe Analytics-bronaansluiting.

## Het vormen van een op regel-gebaseerde gebeurtenis{#configuring-rule-based}

1. Klik in het linkermenu op het **[!UICONTROL Admin]** pictogram en klik vervolgens op **[!UICONTROL Events]**. De lijst met gebeurtenissen wordt weergegeven.

   ![](../assets/alpha-event1.png)

1. Klik op **[!UICONTROL Add]** om een nieuwe gebeurtenis te maken. Het deelvenster voor gebeurtenisconfiguratie wordt aan de rechterkant van het scherm geopend.

   ![](../assets/alpha-event2.png)

1. Voer de naam van de gebeurtenis in. U kunt ook een beschrijving toevoegen.

   ![](../assets/alpha-event3.png)

1. In the new **[!UICONTROL Event ID type]** field, select **[!UICONTROL Rule Based]**.

   ![](../assets/alpha-event4.png)

   >[!NOTE]
   >
   >Het **[!UICONTROL System Generated]** type is de bestaande methode die een eventID vereist. Zie [deze sectie](../event/about-events.md).

1. Definieer de **[!UICONTROL Schema]** lading en de lading **[!UICONTROL Fields]**. Zie [deze sectie](../event/defining-the-payload-fields.md).

   ![](../assets/alpha-event5.png)

   >[!NOTE]
   >
   >Wanneer u de optie selecteert, **[!UICONTROL System Generated type]** zijn alleen schema&#39;s beschikbaar die de mix van het type eventID hebben. Wanneer u het **[!UICONTROL Rule Based]** type selecteert, zijn alle schema&#39;s van de Gebeurtenis van de Ervaring beschikbaar.

1. Klik in het **[!UICONTROL Event ID condition]** veld. Gebruikend de eenvoudige uitdrukkingsredacteur, bepaal de voorwaarde die door het systeem zal worden gebruikt om de gebeurtenissen te identificeren die uw reis zullen teweegbrengen.

   ![](../assets/alpha-event6.png)

   In ons voorbeeld schreven we een voorwaarde op basis van de stad van het profiel. Dit betekent dat wanneer het systeem een gebeurtenis ontvangt die overeenkomt met deze voorwaarde (**[!UICONTROL City]** veld en **[!UICONTROL Paris]** waarde), deze wordt doorgegeven aan Journey Orchestration.

1. Definieer de **[!UICONTROL Namespace]** en **[!UICONTROL Key]**. Zie [De naamruimte](../event/selecting-the-namespace.md) selecteren en de [gebeurtenissleutel](../event/defining-the-event-key.md)definiëren.

   ![](../assets/alpha-event7.png)

De andere stappen voor gebeurtenisconfiguratie en het creëren van de reis blijven onveranderd.

De gebeurtenis is nu geconfigureerd en klaar om op een reis te worden neergezet, net als elke andere gebeurtenis. Telkens wanneer een gebeurtenis die de regel aanpast naar het systeem wordt verzonden, wordt het overgegaan tot Journey Orchestration om uw reizen teweeg te brengen.

## De wijze van de test voor op regel-gebaseerde gebeurtenissen{#test-rule-based}

De testmodus is ook beschikbaar voor reizen die een op regels gebaseerde gebeurtenis gebruiken.

Wanneer u een gebeurtenis activeert, kunt u in het configuratiescherm **Gebeurtenis** de gebeurtenisparameters definiëren die tijdens de test moeten worden doorgegeven. U kunt de voorwaarde van de gebeurtenis-identiteitskaart bekijken door het tooltip pictogram in de hoogste juiste hoek te klikken. Er is ook knopinfo beschikbaar naast elk veld dat deel uitmaakt van de regelevaluatie.

![](../assets/alpha-event8.png)

For more information on how to use the test mode, refer to [](../building-journeys/testing-the-journey.md).

