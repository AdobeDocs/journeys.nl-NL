---
product: adobe campaign
solution: Journey Orchestration
title: Informatie over Journey Orchestration
description: Meer informatie over Journey Orchestration
translation-type: ht
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: ht
source-wordcount: '390'
ht-degree: 100%

---


# Informatie over [!DNL Journey Orchestration]{#concept_nd3_mqt_52b}

Stel real-timegebruiksscenario’s voor orkestratie samen aan de hand van contextuele data die zijn opgeslagen in gebeurtenissen of databronnen.

[!DNL Journey Orchestration] is een applicatieservice die met het Adobe Experience Platform is geïntegreerd.

![](../assets/journeydiagram.png)

Met [!DNL Journey Orchestration] is real-timeorkestratie mogelijk aan de hand van contextuele data van gebeurtenissen, informatie van het Adobe Experience Platform of data van externe API-services. U kunt een aangepaste actie configureren als u een extern systeem gebruikt om uw berichten te verzenden. Als u Adobe Campaign Standard hebt, kunt u e-mails, pushberichten en sms-berichten verzenden met de [functies voor transactionele berichten](https://docs.adobe.com/content/help/nl-NL/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html) van Adobe Campaign Standard.

Op het tabblad voor gebeurtenisconfiguratie worden door een **technische gebruiker** gebeurtenissen geconfigureerd die tijdens de journey’s worden verwacht. De data van binnenkomende gebeurtenissen worden genormaliseerd volgens het Adobe Experience Data Model (XDM). Gebeurtenissen zijn afkomstig van de streamingopname-API’s voor geverifieerde en niet-geverifieerde gebeurtenissen (zoals Adobe Mobile SDK-gebeurtenissen).

Op het tabblad voor databronconfiguratie configureert een **technische gebruiker** het volgende:

* De verschillende zichtbare velden van het Adobe Experience Platform in de journeyontwerper voor het samenstellen van voorwaarden en personalisatie.
* De aanvullende aangepaste databronnen die u gebruikt in de journeyontwerper. Aangepaste databronnen zijn verbindingen tussen [!DNL Journey Orchestration] en externe systemen of services via API. U kunt verbinding maken met een extern systeem zoals een loyaliteitschema. Een externe service is bijvoorbeeld een weer-API.

Met de journeyontwerper kan een **zakelijke gebruiker** gemakkelijk een eerste gebeurtenis slepen en neerzetten, voorwaarden toevoegen en de uit te voeren actie opgeven.

Vervolgens maakt u voorwaarden op basis van:

* tijd
* data uit de gebeurtenispayload
* informatie uit databronnen: een realtime klantprofieldatabron of aangepaste databronnen

U kunt de splitsingsvoorwaarde gebruiken om mensen in de journey in verschillende richtingen te sturen.

Met actieactiviteiten kunt u vervolgens een bericht sturen via een extern systeem. Als u Adobe Campaign Standard hebt, kunt u gepersonaliseerde pushberichten, sms-berichten of e-mails verzenden in realtime.

Aangezien [!DNL Journey Orchestration] meerdere stappen omvat, kunt u geavanceerde scenario’s maken. U kunt bijvoorbeeld na een eerste gebeurtenis en actie andere gebeurtenissen slepen. Vervolgens kunt u een tweede actie toevoegen, een wachtactiviteit plaatsen om enige tijd te wachten, een gesplitste voorwaarde toevoegen om mensen naar twee verschillende paden te sturen en vervolgens verschillende berichten aan hen verzenden.

>[!NOTE]
>
>Deze documentatie wordt regelmatig aangepast aan recente wijzigingen in het product. Sommige screenshots kunnen echter iets afwijken van de interface van het product.
