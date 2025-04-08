---
product: adobe campaign
title: Algemeen
description: Meer informatie over algemene geavanceerde expressies
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ba474219-7c9e-4f93-8e9c-16c317131614
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 1%

---

# Algemeen {#concept_rcy_qj5_dgb}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


## Haakjes en prioriteit van expressie{#section_edf_fks_bgb}

U kunt ronde haakjes gebruiken om een complexe expressie leesbaarder te maken. _(&lt;expression>)_ is het equivalent van _&lt;expression>_. Het haakje kan ook worden gebruikt om de evaluatievolgorde en de associatie te bepalen.

De expressies worden van links naar rechts geëvalueerd. De associatie bij rekenkundige operatoren moet worden toegepast: vermenigvuldigingen en verdelingen hebben voorrang op toevoegingen en aftrekken. Om een bepaalde volgorde op te leggen, moet een haakje worden toegevoegd om de bewerkingen te begrenzen. Bijvoorbeeld:

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| Uitdrukking | Evaluatie |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39; heeft prioriteit boven &#39;+&#39;: 2 * 10 wordt geëvalueerd → 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>De haakjes wijzigen de prioriteit: (4 + 2) wordt geëvalueerd → 6</li><li> 6 * 10 → 60</li></ul> |

## Hoofdlettergevoeligheid{#section_lrb_xh5_dgb}

Hier volgen de verschillende regels voor hoofdlettergevoeligheid:

* Alle operatoren (en, enz.) moeten in kleine letters worden geschreven. _`<expression1>`en`<expression2>`_ zijn bijvoorbeeld een geldige expressie, maar de expressie _`<expression1>`AND`<expression2>`_ niet.
* Alle functienamen zijn hoofdlettergevoelig. Bijvoorbeeld, _inSegment ()_ is geldig terwijl de functie _INSEGMENT ()_ niet is.
* Veldverwijzingen en constante waarden zijn hoofdlettergevoelig: het zijn geen ingebouwde elementen van de taal (in tegenstelling tot operatoren en functies), maar worden ontworpen door de eindgebruiker.

## Type geretourneerde expressie{#section_gyc_435_53b}

Afhankelijk van de context van het gebruik, kan de uitdrukkingsredacteur verschillende waarden terugkeren.

| Geavanceerd gebruik van expressieeditor | Type geretourneerde expressie verwacht |
|--- |--- |
| Voorwaarde (gegevensbronvoorwaarde, datumvoorwaarde) | boolean |
| Aangepaste timer | dateTimeOnly |
| Toewijzing van Action Parameters | Alle |
