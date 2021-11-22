---
product: adobe campaign
title: Gegevenscyclus gebeurtenis
description: Meer informatie over de gebeurtenisgegevenscyclus
feature: Journeys
role: User
level: Intermediate
exl-id: b362589a-32b0-4dbd-8ceb-a371e1e048ac
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 76%

---

# Datacyclus {#section_r1f_xqt_pgb}

Gebeurtenissen zijn POST-API-aanroepen. Gebeurtenissen worden via streamingopname-API’s verzonden naar het Adobe Experience-gegevensplatform. De URL-bestemming van gebeurtenissen die via API’s voor transactionele berichten worden verzonden, wordt een inlet genoemd. De payload van gebeurtenissen volgt de XDM-indeling.

De payload bevat informatie die voor streamingopname-API’s nodig is om te functioneren (in de kop) en de informatie die voor [!DNL Journey Orchestration] nodig is om te functioneren (de gebeurtenis-id, een deel van de payloadhoofdtekst) plus informatie die moet worden gebruikt tijdens journey’s (in de hoofdtekst, bijvoorbeeld het bedrag van een verlaten winkelwagen). Er zijn twee modi voor streamingopname, geverifieerd en niet-geverifieerd. Raadpleeg [deze koppeling](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html)voor meer informatie over streamingopname-API’s.

Na aankomst via streamingopname-API’s stromen de gebeurtenissen naar de interne service, de Pipeline genoemd, en vervolgens naar het Adobe Experience Platform. Als in het het gebeurtenisschema de markering voor real-timeklantprofielservice is ingeschakeld en een dataset-id eveneens de markering voor real-timeklantprofiel heeft, stroomt deze naar de real-timeklantprofielservice.

Voor door het systeem gegenereerde gebeurtenissen, filtert de Pipeline gebeurtenissen die een lading bevatten [!DNL Journey Orchestration] eventID&#39;s (zie het proces voor het maken van gebeurtenissen hieronder) verstrekt door [!DNL Journey Orchestration] en opgenomen in gebeurtenislading. Voor op regel-gebaseerde gebeurtenissen, identificeert het systeem de gebeurtenis gebruikend de eventID voorwaarde. Er wordt naar deze gebeurtenissen geluisterd door [!DNL Journey Orchestration] en de bijbehorende journey wordt geactiveerd.
