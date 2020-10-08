---
title: De databron configureren
description: Leer hoe te om de gegevensbron voor de reis eenvoudig te vormen gebruiksgeval
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 6%

---


# De databron configureren{#concept_ax3_bcy_w2b}

In ons gebruiksgeval, willen wij verpersoonlijkingsgegevens voor onze berichten gebruiken. We moeten ook controleren of de persoon een vrouw is. Deze informatie wordt opgeslagen in het gegevensbestand van het Profiel van de Klant in real time. De **technische gebruiker** moet controleren of deze velden zijn gedefinieerd in de ingebouwde Adobe Experience Platform-gegevensbron.

Voor extra informatie over gegevensbronconfiguratie, verwijs naar [](../datasource/about-data-sources.md).

1. Klik in het bovenste menu op het **[!UICONTROL Data Sources]** tabblad en selecteer de Adobe Experience Platform-gegevensbron voor de build-in.

   ![](../assets/journey23.png)

1. Controleer in de veldgroepen of de volgende velden zijn geselecteerd:

   * _person > name > firstName_
   * _person > name > lastName_
   * _persoon > geslacht_
   * _PersonalEmail > address_

1. Klik op **[!UICONTROL Save]**.

De gegevensbron is nu gevormd en klaar om in uw reis worden gebruikt.
