---
product: adobe campaign
title: Naamruimte selecteren
description: Leer hoe u de naamruimte kunt selecteren
feature: Journeys
role: User
level: Intermediate
exl-id: 976c6353-797e-40cc-bb90-5d82381bb903
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 4%

---

# Naamruimte selecteren {#concept_ckb_3qt_52b}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


Met de naamruimte kunt u het type sleutel definiëren waarmee de persoon wordt geïdentificeerd die aan de gebeurtenis is gekoppeld. De configuratie is optioneel. Het wordt vereist als u, in uw reizen, extra informatie wilt terugwinnen die uit het [ Real-time Profiel van de Klant ](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=nl) komt. De naamruimtedefinitie is niet nodig als u alleen gegevens gebruikt die afkomstig zijn van een systeem van derden via een aangepaste gegevensbron.

U kunt een van de vooraf gedefinieerde naamruimten gebruiken of een nieuwe naamruimte maken met de service Identiteitsnaamruimte. Verwijs naar deze [ pagina ](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=nl).

Als u een schema met een primaire identiteit selecteert, worden de velden **[!UICONTROL Key]** en **[!UICONTROL Namespace]** vooraf ingevuld. Als er geen bepaalde identiteit is, selecteren wij _identityMap > identiteitskaart_ als primaire sleutel. Dan moet u een namespace selecteren en de sleutel (onder het **[!UICONTROL Namespace]** gebied) zal worden vooraf ingevuld gebruikend _identityMap > identiteitskaart_.

Wanneer u velden selecteert, worden primaire identiteitsvelden gecodeerd.

![](../assets/primary-identity.png)


Selecteer een naamruimte in de vervolgkeuzelijst.

![](../assets/journey17.png)

Per reis is slechts één naamruimte toegestaan. Als u meerdere gebeurtenissen gebruikt op dezelfde reis, moeten ze dezelfde naamruimte gebruiken. Zie [deze pagina](../building-journeys/journey.md).
