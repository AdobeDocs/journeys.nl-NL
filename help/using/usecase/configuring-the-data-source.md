---
product: adobe campaign
title: De databron configureren
description: Leer hoe te om de gegevensbron voor de reis eenvoudig te vormen gebruiksgeval
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 7%

---

# De databron configureren{#concept_ax3_bcy_w2b}

In ons gebruiksgeval, willen wij verpersoonlijkingsgegevens voor onze berichten gebruiken. We moeten ook controleren of de persoon een vrouw is. Deze informatie wordt opgeslagen in het gegevensbestand van het Profiel van de Klant in real time. De **technische gebruiker** moet controleren of deze velden zijn gedefinieerd in de ingebouwde Adobe Experience Platform-gegevensbron.

Voor extra informatie over gegevensbronconfiguratie, verwijs naar [deze pagina](../datasource/about-data-sources.md).

1. Klik in het bovenste menu op het tabblad **[!UICONTROL Data Sources]** en selecteer de Adobe Experience Platform-gegevensbron voor de build-in.

   ![](../assets/journey23.png)

1. Controleer in de veldgroepen of de volgende velden zijn geselecteerd:

   * _person > name > firstName_
   * _person > name > lastName_
   * _persoon > geslacht_
   * _PersonalEmail > address_

1. Klik op **[!UICONTROL Save]**.

De gegevensbron is nu gevormd en klaar om in uw reis worden gebruikt.
