---
title: URL-configuratie
description: Meer informatie over URL-configuratie
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 0%

---


# URL-configuratie {#concept_gbg_1f1_2gb}

Wanneer het vormen van een douaneactie, moet u de volgende **[!UICONTROL URL Configuration]** parameters bepalen:

![](../assets/journeyurlconfiguration.png)

1. Voeg de **[!UICONTROL URL]** externe service toe.

   >[!NOTE]
   >
   >We raden u ten zeerste aan HTTPS te gebruiken om beveiligingsredenen. Wij staan niet het gebruik van Adobe adressen toe die niet openbaar en het gebruik van IP adressen zijn.

1. Selecteer de vraag **[!UICONTROL Method]**: het kan of **[!UICONTROL POST]** of **[!UICONTROL PUT]**.
1. Klik in de **[!UICONTROL Headers]** sectie **[!UICONTROL Add a header field]** om een nieuw sleutel-/waardepaar te definiëren. Ze komen overeen met de HTTP-headers van de aanvraag die aan de externe service is gedaan. Als u sleutel-/waardeparen wilt verwijderen, plaatst u de cursor in het **[!UICONTROL Headers]** veld en klikt u op het **[!UICONTROL Delete]** pictogram.

   **[!UICONTROL Content-Type]** en **[!UICONTROL Charset]** worden standaard ingesteld en kunnen niet worden verwijderd of overschreven.

   >[!NOTE]
   >
   >Kopteksten worden gevalideerd volgens de volgende [parseringsregels](https://tools.ietf.org/html/rfc7230#section-3.2.4).
