---
title: Naamruimte selecteren
description: Leer hoe u de naamruimte kunt selecteren
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
source-wordcount: '202'
ht-degree: 11%

---


# Naamruimte selecteren {#concept_ckb_3qt_52b}

Met de naamruimte kunt u het type sleutel definiëren waarmee de persoon wordt geïdentificeerd die aan de gebeurtenis is gekoppeld. De configuratie is optioneel. Dit is vereist als u tijdens uw reizen aanvullende informatie wilt ophalen die afkomstig is uit het [realtime klantprofiel](https://docs.adobe.com/content/help/nl-NL/experience-platform/profile/home.html). De naamruimtedefinitie is niet nodig als u alleen gegevens gebruikt die afkomstig zijn van een systeem van derden via een aangepaste gegevensbron.

U kunt een van de vooraf gedefinieerde naamruimten gebruiken of een nieuwe naamruimte maken met de service Identiteitsnaamruimte. Refer to this [page](https://docs.adobe.com/content/help/nl-NL/experience-platform/identity/home.html).

Als u een schema met een primaire identiteit selecteert, worden de **[!UICONTROL Key]** **[!UICONTROL Namespace]** velden en de velden vooraf ingevuld. Als er geen identiteit is gedefinieerd, selecteren we _identityMap > id_ als primaire sleutel. Vervolgens moet u een naamruimte selecteren en wordt de sleutel vooraf ingevuld (onder het **[!UICONTROL Namespace]** veld) met _identityMap > id_.

Wanneer u velden selecteert, worden primaire identiteitsvelden gecodeerd.

![](../assets/primary-identity.png)


Selecteer een naamruimte in de vervolgkeuzelijst.

![](../assets/journey17.png)

Per reis is slechts één naamruimte toegestaan. Als u meerdere gebeurtenissen gebruikt op dezelfde reis, moeten ze dezelfde naamruimte gebruiken. Zie [](../building-journeys/journey.md).
