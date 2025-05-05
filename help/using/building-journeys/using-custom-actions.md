---
product: adobe campaign
title: Aangepaste acties gebruiken
description: Meer informatie over activiteiten
feature: Journeys
role: User
level: Intermediate
exl-id: 9996d1eb-ddef-46dd-aaa9-c37fa9deb2f9
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 7%

---

# Aangepaste acties gebruiken {#section_f2c_hbg_nhb}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


De ruit van de activiteitenconfiguratie toont de URL configuratieparameters en de authentificatieparameters die voor de douaneactie worden gevormd. [Meer informatie](../action/about-custom-action-configuration.md).

## URL-configuratie

### Dynamisch pad

Als de URL een dynamisch pad bevat, geeft u het pad op in het veld **[!UICONTROL Path]** .

>[!NOTE]
>
>U kunt niet opstelling het statische deel van URL in de reis, maar in de globale configuratie van de douaneactie. [Meer informatie](../action/about-custom-action-configuration.md).

Als u velden en onbewerkte teksttekenreeksen wilt samenvoegen, gebruikt u de tekenreeksfuncties of het plusteken (+) in de geavanceerde expressie-editor. Plaats normale teksttekenreeksen tussen enkele aanhalingstekens (&#39;) of tussen dubbele aanhalingstekens (&#39;). [Meer informatie](../expression/expressionadvanced.md).

In deze tabel ziet u een voorbeeld van configuratie:

| Veld | Waarde |
| --- | --- |
| URL | `https://xxx.yyy.com:8080/somethingstatic/` |
| Pad | `The id of marketingCampaign + '/messages'` |

De samengevoegde URL heeft de volgende vorm:

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;campagne ID\>`/messages`

![](../assets/journey-custom-action-url.png)

### Kopteksten

In de sectie **[!UICONTROL URL Configuration]** worden de dynamische koptekstvelden weergegeven, maar niet de constante koptekstvelden. Dynamische headervelden zijn HTTP-headervelden waarvan de waarde is geconfigureerd als een variabele. [Meer informatie](../action/about-custom-action-configuration.md).

Geef zo nodig de waarde van dynamische koptekstvelden op:

1. Selecteer de aangepaste handeling tijdens de rit.
1. Klik in het configuratievenster op het potloodpictogram naast het koptekstveld in de sectie **[!UICONTROL URL Configuration]** .

   ![](../assets/journey-dynamicheaderfield.png)

1. Selecteer een veld en klik op **[!UICONTROL OK]** .

## Handelingsparameters

In de **[!UICONTROL Action parameters]** sectie, zult u de berichtparameters zien die als _worden bepaald &quot;Variabele&quot;_. Voor deze parameters kunt u bepalen waar u deze informatie wilt ophalen (bijvoorbeeld: gebeurtenissen, gegevensbronnen), waarden handmatig doorgeven of de geavanceerde expressie-editor voor geavanceerde gebruiksgevallen gebruiken. Gevallen van geavanceerd gebruik kunnen gegevensmanipulatie en ander functiegebruik zijn. [Meer informatie](../expression/expressionadvanced.md).

**Verwante onderwerpen**

[Een handeling configureren](../action/about-custom-action-configuration.md)
