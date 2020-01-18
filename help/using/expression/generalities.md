---
title: Algemeen
description: Meer informatie over algemene geavanceerde expressies
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 239efa9592b011c70e2fc331df8f33820301253d

---


# Algemeen {#concept_rcy_qj5_dgb}

## Haakjes en prioriteit van expressie{#section_edf_fks_bgb}

U kunt ronde haakjes gebruiken om een complexe expressie leesbaarder te maken. _(&lt;expression>)_ is het equivalent van _&lt;expression>_. Het haakje kan ook worden gebruikt om de evaluatievolgorde en de associatie te bepalen.

De expressies worden van links naar rechts geëvalueerd. De associatie bij rekenkundige operatoren moet worden toegepast: vermenigvuldigingen en splitsingen hebben voorrang op toevoegingen en aftrekken. Om een bepaalde volgorde op te leggen, moet een haakje worden toegevoegd om de bewerkingen te begrenzen. Bijvoorbeeld:

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| Uitdrukking | Evaluatie |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39; heeft voorrang op &#39;+&#39;: 2 * 10 wordt geëvalueerd → 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>De haakjes wijzigen de prioriteit: (4 + 2) wordt geëvalueerd → 6</li><li> 6 * 10 → 60</li></ul> |

## Hoofdlettergevoeligheid{#section_lrb_xh5_dgb}

Hier volgen de verschillende regels voor hoofdlettergevoeligheid:

* Alle operatoren (en, enz.) moet in kleine letters worden geschreven. Bijvoorbeeld, _`<expression1>`en`<expression2>`_is een geldige uitdrukking terwijl de uitdrukking_`<expression1>` EN `<expression2>`_ niet is.
* Alle functienamen zijn hoofdlettergevoelig. Zo is _getBestSendTime()_ geldig, terwijl de functie _GETBESTSENDTIME()_ dat niet is.
* Veldverwijzingen en constante waarden zijn hoofdlettergevoelig: zij zijn geen ingebouwde elementen van de taal (in tegenstelling tot exploitanten en functies), zij worden ontworpen door de eindgebruiker.

## Type geretourneerde expressie{#section_gyc_435_53b}

Afhankelijk van de context van het gebruik, kan de uitdrukkingsredacteur verschillende waarden terugkeren.

| Geavanceerd gebruik van expressieeditor | Type geretourneerde expressie verwacht |
|--- |--- |
| Voorwaarde (gegevensbronvoorwaarde, datumvoorwaarde) | boolean |
| Aangepaste timer | dateTimeOnly |
| Aangepaste tijdzone | timeZone of tekenreeks (bijvoorbeeld Europe/Paris) |
| Toewijzing van Action Parameters | Alle |
