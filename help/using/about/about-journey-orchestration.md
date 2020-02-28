---
title: Informatie over Journey Orchestration
description: Meer informatie over Journey Orchestration
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 891216a489b79fe4b168ecdb6120f5d9f3e107d0

---


# Informatie over Journey Orchestration{#concept_nd3_mqt_52b}

Stel in real-time implementatiefuncties samen voor het orkestgebruik, waarbij gebruik wordt gemaakt van contextuele gegevens die zijn opgeslagen in gebeurtenissen of gegevensbronnen.

Reisorchestratie is een toepassingsservice die is geïntegreerd met het Experience Platform.

![](../assets/journeydiagram.png)

De Orchestratie van de reis staat in real time orchestratie toe die door contextafhankelijke gegevens van gebeurtenissen, informatie van het Platform van de Ervaring van Adobe, of gegevens van de diensten van derdeAPI wordt aangedreven. U kunt een douaneactie vormen als u een derdesysteem gebruikt om uw berichten te verzenden. Als u Adobe Campagne Standard hebt, kunt u e-mails, pushmeldingen en SMS verzenden met de mogelijkheden [voor](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)Transactieberichten van Adobe Campagne Standard.

In het lusje van de gebeurtenisconfiguratie, vormt een **technische gebruiker** gebeurtenissen die in de reizen worden verwacht. De gegevens van binnenkomende gebeurtenissen worden genormaliseerd volgens het Adobe Experience Data Model (XDM). Gebeurtenissen zijn afkomstig van de Streaming Ingestie-API&#39;s voor geverifieerde en niet-geverifieerde gebeurtenissen (zoals Adobe Mobile SDK-gebeurtenissen).

In het lusje van de gegevensbronconfiguratie, vormt een **technische gebruiker** :

* De verschillende velden die beschikbaar zijn via het Adobe Experience Platform in de reisontwerper voor het maken en personaliseren van voorwaarden.
* De extra bronnen van douanegegevens die u hefboomwerking in de reisontwerper. Aangepaste gegevensbronnen zijn verbindingen tussen de Journey Orchestration en systemen of services van derden via API. U kunt een systeem van de derde zoals een loyaliteitssysteem aansluiten. De derdediensten kunnen, bijvoorbeeld, een weer API zijn.

Met de reisontwerper, kan een **bedrijfsgebruiker** een ingangsgebeurtenis gemakkelijk slepen en laten vallen, voorwaarden toevoegen en de uit te voeren actie specificeren.

Vervolgens maakt u voorwaarden op basis van:

* tijd
* gegevens die afkomstig zijn van de gebeurtenislading
* informatie uit gegevensbronnen: Gegevensbron van gebruikersprofiel of aangepaste gegevensbronnen in realtime

U kunt de splitsingsvoorwaarde gebruiken om mensen in de reis in verschillende richtingen te sturen.

Gebruikend actieactiviteiten, kunt u een bericht via een derdesysteem dan verzenden. Als u Adobe Campagne Standard hebt, verzendt u realtime gepersonaliseerde SMS-, push-berichten of e-mailberichten.

Aangezien de Orchestratie van de Reis veelvoudige stappen is, kunt u geavanceerde scenario&#39;s tot stand brengen. U kunt bijvoorbeeld na een eerste gebeurtenis en handeling andere gebeurtenissen slepen. Vervolgens kunt u een tweede handeling toevoegen, een wachtbewerking plaatsen om een tijd te wachten, een gesplitste voorwaarde toevoegen om mensen naar twee verschillende paden te duwen en vervolgens andere berichten verzenden.

>[!NOTE]
>
>Deze documentatie wordt regelmatig bijgewerkt om recente wijzigingen in het product te weerspiegelen. Sommige schermafbeeldingen kunnen echter enigszins afwijken van de interface van het product.
