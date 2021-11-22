---
product: adobe campaign
title: De databron configureren
description: Leer hoe te om de gegevensbron voor de reis eenvoudig te vormen gebruiksgeval
feature: Journeys
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 6%

---

# De databron configureren{#concept_ax3_bcy_w2b}

In ons gebruiksgeval, willen wij verpersoonlijkingsgegevens voor onze berichten gebruiken. We moeten ook controleren of de persoon een vrouw is. Deze informatie wordt opgeslagen in het gegevensbestand van het Profiel van de Klant in real time. De **technisch gebruiker** moet controleren of deze velden zijn gedefinieerd in de ingebouwde Adobe Experience Platform-gegevensbron.

Voor extra informatie over gegevensbronconfiguratie, verwijs naar [deze pagina](../datasource/about-data-sources.md).

1. Selecteer in het menuvenster de optie **[!UICONTROL Admin]**. In de **[!UICONTROL Data sources]** sectie, klikt u op **[!UICONTROL Manage]**.
1. Selecteer de ingebouwde Adobe Experience Platform-gegevensbron.

   ![](../assets/journey23.png)

1. Controleer in de veldgroepen of de volgende velden zijn geselecteerd:

   * _person > name > firstName_
   * _person > name > lastName_
   * _persoon > geslacht_
   * _PersonalEmail > address_

1. Klik op **[!UICONTROL Save]**.

De gegevensbron is nu gevormd en klaar om in uw reis worden gebruikt.
