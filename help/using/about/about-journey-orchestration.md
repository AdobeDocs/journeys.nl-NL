---
title: Info over Journey Orchestration
description: Meer informatie over Journey Orchestration
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 0%

---


# Info [!DNL Journey Orchestration]{#concept_nd3_mqt_52b}

Stel in real-time implementatiefuncties samen voor het orkestgebruik, waarbij gebruik wordt gemaakt van contextuele gegevens die zijn opgeslagen in gebeurtenissen of gegevensbronnen.

[!DNL Journey Orchestration] is een toepassingsservice die met het Adobe Experience Platform is geïntegreerd.

![](../assets/journeydiagram.png)

[!DNL Journey Orchestration] staat organisatie in real time toe die door contextafhankelijke gegevens van gebeurtenissen, informatie van het Adobe Experience Platform, of gegevens van de diensten van derdeAPI wordt aangedreven. U kunt een douaneactie vormen als u een derdesysteem gebruikt om uw berichten te verzenden. Als je Adobe Campaign Standard hebt, kun je e-mails, pushberichten en SMS verzenden via de mogelijkheden [voor](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)Transactieberichten van Adobe Campaign Standard.

In het lusje van de gebeurtenisconfiguratie, vormt een **technische gebruiker** gebeurtenissen die in de reizen worden verwacht. De gegevens van binnenkomende gebeurtenissen worden genormaliseerd volgens het Adobe Experience Data Model (XDM). Gebeurtenissen komen van de Streaming Ingestie-API&#39;s voor geverifieerde en niet-geverifieerde gebeurtenissen (zoals Adobe Mobile SDK-gebeurtenissen).

In het lusje van de gegevensbronconfiguratie, vormt een **technische gebruiker** :

* De verschillende gebieden die van het Adobe Experience Platform in de reisontwerper voor voorwaardenbouw en verpersoonlijkingsdoeleinden worden blootgesteld.
* De extra bronnen van douanegegevens die u hefboomwerking in de reisontwerper. Aangepaste gegevensbronnen zijn verbindingen tussen systemen [!DNL Journey Orchestration] en services van derden via API. U kunt een systeem van de derde zoals een loyaliteitssysteem aansluiten. De derdediensten kunnen, bijvoorbeeld, een weer API zijn.

Met de reisontwerper, kan een **bedrijfsgebruiker** een ingangsgebeurtenis gemakkelijk slepen en laten vallen, voorwaarden toevoegen en de uit te voeren actie specificeren.

Vervolgens maakt u voorwaarden op basis van:

* tijd
* gegevens die afkomstig zijn van de gebeurtenislading
* informatie uit gegevensbronnen: Gegevensbron van gebruikersprofiel of aangepaste gegevensbronnen in realtime

U kunt de splitsingsvoorwaarde gebruiken om mensen in de reis in verschillende richtingen te sturen.

Gebruikend actieactiviteiten, kunt u een bericht via een derdesysteem dan verzenden. Als je Adobe Campaign Standard hebt, verzend je realtime persoonlijke SMS, pushberichten of e-mails.

Zoals [!DNL Journey Orchestration] in meerdere stappen gebeurt, kunt u geavanceerde scenario&#39;s maken. U kunt bijvoorbeeld na een eerste gebeurtenis en handeling andere gebeurtenissen slepen. Vervolgens kunt u een tweede handeling toevoegen, een wachtbewerking plaatsen om een tijd te wachten, een gesplitste voorwaarde toevoegen om mensen naar twee verschillende paden te duwen en vervolgens andere berichten verzenden.

>[!NOTE]
>
>Deze documentatie wordt regelmatig bijgewerkt om recente wijzigingen in het product te weerspiegelen. Sommige schermafbeeldingen kunnen echter enigszins afwijken van de interface van het product.
