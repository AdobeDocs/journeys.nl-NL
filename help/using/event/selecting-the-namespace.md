---
product: adobe campaign
solution: Journey Orchestration
title: Naamruimte selecteren
description: Leer hoe u de naamruimte kunt selecteren
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 12%

---


# Naamruimte selecteren {#concept_ckb_3qt_52b}

Met de naamruimte kunt u het type sleutel definiëren waarmee de persoon wordt geïdentificeerd die aan de gebeurtenis is gekoppeld. De configuratie is optioneel. Dit is vereist als u tijdens uw reizen aanvullende informatie wilt ophalen die afkomstig is uit het [realtime klantprofiel](https://docs.adobe.com/content/help/nl-NL/experience-platform/profile/home.html). De naamruimtedefinitie is niet nodig als u alleen gegevens gebruikt die afkomstig zijn van een systeem van derden via een aangepaste gegevensbron.

U kunt een van de vooraf gedefinieerde naamruimten gebruiken of een nieuwe naamruimte maken met de service Identiteitsnaamruimte. Refer to this [page](https://docs.adobe.com/content/help/nl-NL/experience-platform/identity/home.html).

Als u een schema met een primaire identiteit selecteert, worden de **[!UICONTROL Key]** **[!UICONTROL Namespace]** velden en de velden vooraf ingevuld. Als er geen identiteit is gedefinieerd, selecteren we _identityMap > id_ als primaire sleutel. Vervolgens moet u een naamruimte selecteren en wordt de sleutel vooraf ingevuld (onder het **[!UICONTROL Namespace]** veld) met _identityMap > id_.

Wanneer u velden selecteert, worden primaire identiteitsvelden gecodeerd.

![](../assets/primary-identity.png)


Selecteer een naamruimte in de vervolgkeuzelijst.

![](../assets/journey17.png)

Per reis is slechts één naamruimte toegestaan. Als u meerdere gebeurtenissen gebruikt op dezelfde reis, moeten ze dezelfde naamruimte gebruiken. Zie [deze pagina](../building-journeys/journey.md).
