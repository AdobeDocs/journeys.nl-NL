---
title: Beperkingen voor aangepaste handelingen
description: Meer informatie over beperkingen van aangepaste handelingen
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# Beperkingen voor aangepaste handelingen {#concept_lh2_df1_2gb}

Hier volgen enkele beperkingen ten aanzien van het gebruik van aangepaste handelingen:

* Er is geen plafond of verzendend volume bufferen/vloeiend maken.
* In het geval van een fout worden systematisch twee pogingen uitgevoerd. U kunt het aantal pogingen niet aanpassen volgens het ontvangen foutbericht.
* De ingebouwde **[!UICONTROL Reaction]**gebeurtenis staat u toe om op uit-van-de-doos acties te reageren (zie[](../building-journeys/event-activities.md). Als u op een bericht wilt reageren dat via een douaneactie wordt verzonden, moet u een specifieke gebeurtenis vormen.
* De URL van de aangepaste handeling ondersteunt geen dynamische parameters.
* Alleen POST- en PUT-callmethoden worden ondersteund.
* De naam van de queryparameter of -header mag niet beginnen met &quot;.&quot; of &quot;$&quot;.
* IP-adressen zijn niet toegestaan.
* Interne Adobe-adressen (.adobe.) zijn niet toegestaan.
