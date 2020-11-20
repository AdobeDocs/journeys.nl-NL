---
product: adobe campaign
solution: Journey Orchestration
title: URL-configuratie
description: Meer informatie over URL-configuratie
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 9%

---


# URL-configuratie {#concept_gbg_1f1_2gb}

Wanneer het vormen van een douaneactie, moet u de volgende **[!UICONTROL URL Configuration]** parameters bepalen:

![](../assets/journeyurlconfiguration.png)

1. Add the **[!UICONTROL URL]** of the external service.

   >[!NOTE]
   >
   >We raden u uit beveiligingsoverwegingen sterk aan om HTTPS te gebruiken. Wij staan niet het gebruik van Adobe adressen toe die niet openbaar en het gebruik van IP adressen zijn.

1. Selecteer de vraag **[!UICONTROL Method]**: het kan of **[!UICONTROL POST]** of **[!UICONTROL PUT]**.
1. Klik in de **[!UICONTROL Headers]** sectie **[!UICONTROL Add a header field]** om een nieuw sleutel-/waardepaar te definiëren. Ze komen overeen met de HTTP-headers van de aanvraag die aan de externe service is gedaan. Als u sleutel-/waardeparen wilt verwijderen, plaatst u de cursor in het **[!UICONTROL Headers]** veld en klikt u op het **[!UICONTROL Delete]** pictogram.

   **[!UICONTROL Content-Type]** en **[!UICONTROL Charset]** worden standaard ingesteld en kunnen niet worden verwijderd of overschreven.

   >[!NOTE]
   >
   >Kopteksten worden gevalideerd volgens de volgende [parseringsregels](https://tools.ietf.org/html/rfc7230#section-3.2.4).
