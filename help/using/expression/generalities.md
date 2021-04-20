---
product: adobe campaign
solution: Journey Orchestration
title: Algemeen
description: Meer informatie over algemene geavanceerde expressies
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 2%

---


# Algemeen {#concept_rcy_qj5_dgb}

## Haakjes en expressieprioriteit{#section_edf_fks_bgb}

U kunt ronde haakjes gebruiken om een complexe expressie leesbaarder te maken. _(&lt;expression>)_ is het equivalent van  _&lt;expression>_. Het haakje kan ook worden gebruikt om de evaluatievolgorde en de associatie te bepalen.

De expressies worden van links naar rechts geëvalueerd. De associatie bij rekenkundige operatoren moet worden toegepast: vermenigvuldigingen en splitsingen hebben voorrang op toevoegingen en aftrekken. Om een bepaalde volgorde op te leggen, moet een haakje worden toegevoegd om de bewerkingen te begrenzen. Bijvoorbeeld:

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| Uitdrukking | Evaluatie |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39; heeft voorrang op &#39;+&#39;: 2 * 10 wordt geëvalueerd → 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>De haakjes wijzigen de prioriteit: (4 + 2) wordt geëvalueerd → 6</li><li> 6 * 10 → 60</li></ul> |

## Hoofdlettergevoeligheid{#section_lrb_xh5_dgb}

Hier volgen de verschillende regels voor hoofdlettergevoeligheid:

* Alle operatoren (en, enz.) moet in kleine letters worden geschreven. _`<expression1>`en`<expression2>`_ zijn bijvoorbeeld een geldige expressie, terwijl de expressie _`<expression1>`AND`<expression2>`_ dat niet is.
* Alle functienamen zijn hoofdlettergevoelig. _inSegment()_ is bijvoorbeeld geldig, terwijl de functie _INSEGMENT()_ dat niet is.
* Veldverwijzingen en constante waarden zijn hoofdlettergevoelig: zij zijn geen ingebouwde elementen van de taal (in tegenstelling tot exploitanten en functies), zij worden ontworpen door de eindgebruiker.

## Type geretourneerde expressie{#section_gyc_435_53b}

Afhankelijk van de context van het gebruik, kan de uitdrukkingsredacteur verschillende waarden terugkeren.

| Geavanceerd gebruik van expressieeditor | Type geretourneerde expressie verwacht |
|--- |--- |
| Voorwaarde (gegevensbronvoorwaarde, datumvoorwaarde) | boolean |
| Aangepaste timer | dateTimeOnly |
| Toewijzing van Action Parameters | Alle |
