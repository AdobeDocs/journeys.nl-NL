---
product: adobe campaign
solution: Journey Orchestration
title: De databron configureren
description: Leer hoe te om de gegevensbron voor de reis eenvoudig te vormen gebruiksgeval
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 6%

---


# De databron configureren{#concept_ax3_bcy_w2b}

In ons gebruiksgeval, willen wij verpersoonlijkingsgegevens voor onze berichten gebruiken. We moeten ook controleren of de persoon een vrouw is. Deze informatie wordt opgeslagen in het gegevensbestand van het Profiel van de Klant in real time. De **technische gebruiker** moet controleren of deze velden zijn gedefinieerd in de ingebouwde Adobe Experience Platform-gegevensbron.

Raadpleeg [deze pagina](../datasource/about-data-sources.md)voor meer informatie over de configuratie van de gegevensbron.

1. Klik in het bovenste menu op het **[!UICONTROL Data Sources]** tabblad en selecteer de Adobe Experience Platform-gegevensbron voor de build-in.

   ![](../assets/journey23.png)

1. Controleer in de veldgroepen of de volgende velden zijn geselecteerd:

   * _person > name > firstName_
   * _person > name > lastName_
   * _persoon > geslacht_
   * _PersonalEmail > address_

1. Klik op **[!UICONTROL Save]**.

De gegevensbron is nu gevormd en klaar om in uw reis worden gebruikt.
