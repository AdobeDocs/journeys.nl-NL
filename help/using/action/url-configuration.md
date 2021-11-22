---
product: adobe campaign
title: URL-configuratie
description: Meer informatie over URL-configuratie
feature: Journeys
role: User
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
source-git-commit: 2a93bce42ea9f1f21d70c68da3dbc36844dafd1b
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 4%

---

# URL-configuratie {#concept_gbg_1f1_2gb}

Wanneer het vormen van een douaneactie, moet u het volgende bepalen **[!UICONTROL URL Configuration]** parameters:

![](../assets/journeyurlconfiguration.png)

1. In de **[!UICONTROL URL]** -veld, geeft u de URL van de externe service op:

   * Als de URL statisch is, voert u de URL in dit veld in.

   * Als de URL een dynamisch pad bevat, voert u alleen het statische gedeelte van de URL in, dat wil zeggen het schema, de host, de poort en eventueel een statisch gedeelte van het pad.

      Voorbeeld: `https://xxx.yyy.com/somethingstatic/`

      U geeft het dynamische pad van de URL op wanneer u de aangepaste handeling aan een rit toevoegt. [Meer informatie](../building-journeys/using-custom-actions.md).
   >[!NOTE]
   >
   >Om veiligheidsredenen raden we u ten zeerste aan het HTTPS-schema te gebruiken voor de URL. Wij staan niet het gebruik van Adobe adressen toe die niet openbaar en het gebruik van IP adressen zijn.
   >
   >Alleen de standaardpoorten zijn toegestaan bij het definiëren van een aangepaste handeling: 80 voor http en 443 voor https.

1. Selecteer de vraag **[!UICONTROL Method]**: het kan **[!UICONTROL POST]** of **[!UICONTROL PUT]**.
1. In de **[!UICONTROL Headers]** in, definieert u de HTTP-headers van het aanvraagbericht dat naar de externe service moet worden verzonden:
   1. Als u een koptekstveld wilt toevoegen, klikt u op **[!UICONTROL Add a header field]**.
   1. Voer de sleutel van het headerveld in.
   1. Als u een dynamische waarde voor het sleutelwaardepaar wilt instellen, selecteert u **[!UICONTROL Variable]**. Anders selecteert u **[!UICONTROL Constant]**.

      Voor een tijdstempel kunt u bijvoorbeeld een dynamische waarde instellen.

   1. Als u **[!UICONTROL Constant]** Voer vervolgens de constante waarde in.

      Als u **[!UICONTROL Variable]**, dan zult u deze variabele specificeren wanneer het toevoegen van de douaneactie aan een reis. [Meer informatie](../building-journeys/using-custom-actions.md).

      ![](../assets/journeyurlconfiguration2.png)

   1. Als u een koptekstveld wilt verwijderen, wijst u naar het koptekstveld en klikt u op de knop **[!UICONTROL Delete]** pictogram.
   De **[!UICONTROL Content-Type]** en **[!UICONTROL Charset]** koptekstvelden worden standaard ingesteld. U kunt deze velden niet wijzigen of verwijderen.

   Nadat u de douaneactie aan een reis hebt toegevoegd, kunt u nog kopbalgebieden aan het toevoegen als de reis in ontwerpstatus is. Als u niet wilt dat de reis door configuratieveranderingen wordt beïnvloed, dupliceer de douaneactie en voeg de kopbalgebieden aan de nieuwe douaneactie toe.

   >[!NOTE]
   >
   >Kopteksten worden gevalideerd volgens veldparseringsregels. [Meer informatie](https://tools.ietf.org/html/rfc7230#section-3.2.4).
