---
title: Beperkingen voor aangepaste acties
description: Meer informatie over beperkingen van aangepaste handelingen
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
source-wordcount: '125'
ht-degree: 5%

---


# Beperkingen voor aangepaste acties {#concept_lh2_df1_2gb}

Hier volgen enkele beperkingen ten aanzien van het gebruik van aangepaste handelingen:

* Er is geen verzendend volume bufferen/vloeiend maken.
* In het geval van een fout worden systematisch twee pogingen uitgevoerd. U kunt het aantal pogingen niet aanpassen volgens het ontvangen foutbericht.
* Met de ingebouwde **[!UICONTROL Reaction]** gebeurtenis kunt u reageren op acties die buiten de box vallen (zie [](../building-journeys/reaction-events.md)). Als u op een bericht wilt reageren dat via een douaneactie wordt verzonden, moet u een specifieke gebeurtenis vormen.
* De URL van de aangepaste handeling ondersteunt geen dynamische parameters.
* Alleen methoden voor het aanroepen van POSTEN en PUTTEN worden ondersteund.
* De naam van de queryparameter of -header mag niet beginnen met &quot;.&quot; of &quot;$&quot;.
* IP-adressen zijn niet toegestaan.
* Interne Adobe-adressen (.adobe.) zijn niet toegestaan.
