---
product: adobe campaign
solution: Journey Orchestration
title: Naamruimte selecteren
description: Leer hoe u de naamruimte kunt selecteren
feature: Reizen
role: Zakelijke praktiserer
level: Intermediair
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 12%

---


# Naamruimte selecteren {#concept_ckb_3qt_52b}

Met de naamruimte kunt u het type sleutel definiëren waarmee de persoon wordt geïdentificeerd die aan de gebeurtenis is gekoppeld. De configuratie is optioneel. Het is vereist als u, in uw reizen, extra informatie wilt terugwinnen die uit [Real-time Profiel van de Klant ](https://docs.adobe.com/content/help/nl-NL/experience-platform/profile/home.html) komt. De naamruimtedefinitie is niet nodig als u alleen gegevens gebruikt die afkomstig zijn van een systeem van derden via een aangepaste gegevensbron.

U kunt een van de vooraf gedefinieerde naamruimten gebruiken of een nieuwe naamruimte maken met de service Identiteitsnaamruimte. Zie deze [pagina](https://docs.adobe.com/content/help/nl-NL/experience-platform/identity/home.html).

Als u een schema met een primaire identiteit selecteert, worden de velden **[!UICONTROL Key]** en **[!UICONTROL Namespace]** vooraf ingevuld. Als er geen identiteit wordt bepaald, selecteren wij _identityMap > id_ als primaire sleutel. Vervolgens moet u een naamruimte selecteren en wordt de sleutel vooraf ingevuld (onder het veld **[!UICONTROL Namespace]**) met _identityMap > id_.

Wanneer u velden selecteert, worden primaire identiteitsvelden gecodeerd.

![](../assets/primary-identity.png)


Selecteer een naamruimte in de vervolgkeuzelijst.

![](../assets/journey17.png)

Per reis is slechts één naamruimte toegestaan. Als u meerdere gebeurtenissen gebruikt op dezelfde reis, moeten ze dezelfde naamruimte gebruiken. Zie [deze pagina](../building-journeys/journey.md).
