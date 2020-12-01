---
product: adobe campaign
solution: Journey Orchestration
title: Gegevenscyclus gebeurtenis
description: Meer informatie over de gebeurtenisgegevenscyclus
translation-type: tm+mt
source-git-commit: b3ed5d305ddd1c86814373fc923390dc50a80c7e
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 78%

---


# Gegevenscyclus {#section_r1f_xqt_pgb}

Gebeurtenissen zijn POST-API-aanroepen. Gebeurtenissen worden via streamingopname-API’s verzonden naar het Adobe Experience-gegevensplatform. De URL-bestemming van gebeurtenissen die via API’s voor transactionele berichten worden verzonden, wordt een inlet genoemd. De payload van gebeurtenissen volgt de XDM-indeling.

De payload bevat informatie die voor streamingopname-API’s nodig is om te functioneren (in de kop) en de informatie die voor [!DNL Journey Orchestration] nodig is om te functioneren (de gebeurtenis-id, een deel van de payloadhoofdtekst) plus informatie die moet worden gebruikt tijdens journey’s (in de hoofdtekst, bijvoorbeeld het bedrag van een verlaten winkelwagen). Er zijn twee modi voor streamingopname, geverifieerd en niet-geverifieerd. Raadpleeg [deze koppeling](https://docs.adobe.com/content/help/nl-NL/experience-platform/xdm/api/getting-started.html)voor meer informatie over streamingopname-API’s.

Na aankomst via streamingopname-API’s stromen de gebeurtenissen naar de interne service, de Pipeline genoemd, en vervolgens naar het Adobe Experience Platform. Als in het het gebeurtenisschema de markering voor real-timeklantprofielservice is ingeschakeld en een dataset-id eveneens de markering voor real-timeklantprofiel heeft, stroomt deze naar de real-timeklantprofielservice.

For system-generated events, the Pipeline filters events which have a payload containing [!DNL Journey Orchestration] eventIDs (see the event creation process below) provided by [!DNL Journey Orchestration] and contained in event payload. Voor op regel-gebaseerde gebeurtenissen, identificeert het systeem de gebeurtenis gebruikend de eventID voorwaarde. Er wordt naar deze gebeurtenissen geluisterd door [!DNL Journey Orchestration] en de bijbehorende journey wordt geactiveerd.
