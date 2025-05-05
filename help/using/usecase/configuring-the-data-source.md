---
product: adobe campaign
title: De databron configureren
description: Leer hoe te om de gegevensbron voor de reis eenvoudig te vormen gebruiksgeval
feature: Journeys
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 4%

---

# De databron configureren{#concept_ax3_bcy_w2b}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


In ons gebruiksgeval, willen wij verpersoonlijkingsgegevens voor onze berichten gebruiken. We moeten ook controleren of de persoon een vrouw is. Deze informatie wordt opgeslagen in het gegevensbestand van het Profiel van de Klant in real time. De **technische gebruiker** moet controleren dat die gebieden in de ingebouwde gegevensbron van Adobe Experience Platform worden bepaald.

Voor extra informatie over gegevensbronconfiguratie, verwijs naar [ deze pagina ](../datasource/about-data-sources.md).

1. Selecteer **[!UICONTROL Admin]** in het menuvenster. Klik in de sectie **[!UICONTROL Data sources]** op **[!UICONTROL Manage]** .
1. Selecteer de ingebouwde Adobe Experience Platform-gegevensbron.

   ![](../assets/journey23.png)

1. Controleer in de veldgroepen of de volgende velden zijn geselecteerd:

   * _persoon > naam > firstName_
   * _persoon > naam > lastName_
   * _persoon > geslacht_
   * _PersonalEmail > adres_

1. Klik op **[!UICONTROL Save]**.

De gegevensbron is nu gevormd en klaar om in uw reis worden gebruikt.
