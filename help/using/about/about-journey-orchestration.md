---
product: adobe campaign
title: Informatie over Journey Orchestration
description: Meer informatie over Journey Orchestration
feature: Journeys
role: User
level: Beginner
exl-id: 430bac3a-06da-45a8-af90-1dcd1504d532
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '426'
ht-degree: 100%

---

# Informatie over [!DNL Journey Orchestration]{#concept_nd3_mqt_52b}


>[!CAUTION]
>
>**Op zoek naar Adobe Journey Optimizer**? Klik [hier](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar verouderde materialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over toegang tot Journey Orchestration of Journey Optimizer._


Stel real-timegebruiksscenario’s voor orkestratie samen aan de hand van contextuele data die zijn opgeslagen in gebeurtenissen of databronnen.

[!DNL Journey Orchestration] is een applicatieservice die met het Adobe Experience Platform is geïntegreerd.

Met [!DNL Journey Orchestration] is real-timeorkestratie mogelijk aan de hand van contextuele data van gebeurtenissen, informatie van het Adobe Experience Platform of data van externe API-services. U kunt een aangepaste actie configureren als u een extern systeem gebruikt om uw berichten te verzenden. Als u Adobe Campaign Standard hebt, kunt u e-mails, pushberichten en sms-berichten verzenden met de [functies voor transactionele berichten](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=nl) van Adobe Campaign Standard.

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
