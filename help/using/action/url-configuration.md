---
product: adobe campaign
title: URL-configuratie
description: Meer informatie over URL-configuratie
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 10%

---

# URL-configuratie {#concept_gbg_1f1_2gb}

Wanneer het vormen van een douaneactie, moet u de volgende **[!UICONTROL URL Configuration]** parameters bepalen:

![](../assets/journeyurlconfiguration.png)

1. Voeg de **[!UICONTROL URL]** van de externe service toe.

   >[!NOTE]
   >
   >We raden u uit beveiligingsoverwegingen sterk aan om HTTPS te gebruiken. Wij staan niet het gebruik van Adobe adressen toe die niet openbaar en het gebruik van IP adressen zijn.

1. Selecteer de vraag **[!UICONTROL Method]**: kan **[!UICONTROL POST]** of **[!UICONTROL PUT]** zijn.
1. Klik in de sectie **[!UICONTROL Headers]** op **[!UICONTROL Add a header field]** om een nieuw sleutel-/waardepaar te definiëren. Ze komen overeen met de HTTP-headers van de aanvraag die aan de externe service is gedaan. Als u sleutel-/waardeparen wilt verwijderen, plaatst u de cursor in het veld **[!UICONTROL Headers]** en klikt u op het pictogram **[!UICONTROL Delete]**.

   **[!UICONTROL Content-Type]** en  **[!UICONTROL Charset]** worden standaard ingesteld en kunnen niet worden verwijderd of overschreven.

   >[!NOTE]
   >
   >Kopteksten worden gevalideerd volgens de volgende [parseringsregels](https://tools.ietf.org/html/rfc7230#section-3.2.4).
