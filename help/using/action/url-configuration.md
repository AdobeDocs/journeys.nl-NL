---
product: adobe campaign
title: URL-configuratie
description: Meer informatie over URL-configuratie
feature: Journeys
role: User
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
source-git-commit: e71d641888caa9385d078d9c85e073b5f1ed743f
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 5%

---

# URL-configuratie {#concept_gbg_1f1_2gb}

Wanneer het vormen van een douaneactie, moet u de volgende **[!UICONTROL URL Configuration]** parameters bepalen:

![](../assets/journeyurlconfiguration.png)

1. Geef in het veld **[!UICONTROL URL]** de URL van de externe service op:

   * Als de URL statisch is, voert u de URL in dit veld in.

   * Als de URL een dynamisch pad bevat, voert u alleen het statische gedeelte van de URL in, dat wil zeggen het schema, de host, de poort en eventueel een statisch gedeelte van het pad.

      Voorbeeld: `https://xxx.yyy.com:8080/somethingstatic/`

      U geeft het dynamische pad van de URL op wanneer u de aangepaste handeling aan een rit toevoegt. [Meer informatie](../building-journeys/using-custom-actions.md).
   >[!NOTE]
   >
   >Om veiligheidsredenen raden we u ten zeerste aan het HTTPS-schema te gebruiken voor de URL. Wij staan niet het gebruik van Adobe adressen toe die niet openbaar en het gebruik van IP adressen zijn.

1. Selecteer de vraag **[!UICONTROL Method]**: kan **[!UICONTROL POST]** of **[!UICONTROL PUT]** zijn.
1. Definieer in de sectie **[!UICONTROL Headers]** de HTTP-headers van het aanvraagbericht dat naar de externe service moet worden verzonden:
   1. Als u een headerveld wilt toevoegen, klikt u op **[!UICONTROL Add a header field]**.
   1. Voer de sleutel van het headerveld in.
   1. Als u een dynamische waarde voor het sleutelwaardepaar wilt instellen, selecteert u **[!UICONTROL Variable]**. Anders selecteert u **[!UICONTROL Constant]**.

      Voor een tijdstempel kunt u bijvoorbeeld een dynamische waarde instellen.

   1. Als u **[!UICONTROL Constant]** hebt geselecteerd, voert u de constante waarde in.

      Als u **[!UICONTROL Variable]** hebt geselecteerd, dan zult u deze variabele wanneer het toevoegen van de douaneactie aan een reis specificeren. [Meer informatie](../building-journeys/using-custom-actions.md).

      ![](../assets/journeyurlconfiguration2.png)

   1. Als u een koptekstveld wilt verwijderen, wijst u naar het koptekstveld en klikt u op het pictogram **[!UICONTROL Delete]**.
   De koptekstvelden **[!UICONTROL Content-Type]** en **[!UICONTROL Charset]** zijn standaard ingesteld. U kunt deze velden niet wijzigen of verwijderen.

   Nadat u de douaneactie aan een reis hebt toegevoegd, kunt u nog kopbalgebieden aan het toevoegen als de reis in ontwerpstatus is. Als u niet wilt dat de reis door configuratieveranderingen wordt beïnvloed, dupliceer de douaneactie en voeg de kopbalgebieden aan de nieuwe douaneactie toe.

   >[!NOTE]
   >
   >Kopteksten worden gevalideerd volgens veldparseringsregels. [Meer informatie](https://tools.ietf.org/html/rfc7230#section-3.2.4).
