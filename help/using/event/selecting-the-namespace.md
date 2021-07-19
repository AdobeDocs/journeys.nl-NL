---
product: adobe campaign
title: Naamruimte selecteren
description: Leer hoe u de naamruimte kunt selecteren
feature: Journeys
role: User
level: Intermediate
exl-id: 976c6353-797e-40cc-bb90-5d82381bb903
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 10%

---

# Naamruimte selecteren {#concept_ckb_3qt_52b}

Met de naamruimte kunt u het type sleutel definiëren waarmee de persoon wordt geïdentificeerd die aan de gebeurtenis is gekoppeld. De configuratie is optioneel. Het is vereist als u, in uw reizen, extra informatie wilt terugwinnen die uit [Real-time Profiel van de Klant ](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=nl) komt. De naamruimtedefinitie is niet nodig als u alleen gegevens gebruikt die afkomstig zijn van een systeem van derden via een aangepaste gegevensbron.

U kunt een van de vooraf gedefinieerde naamruimten gebruiken of een nieuwe naamruimte maken met de service Identiteitsnaamruimte. Zie deze [pagina](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=nl).

Als u een schema met een primaire identiteit selecteert, worden de velden **[!UICONTROL Key]** en **[!UICONTROL Namespace]** vooraf ingevuld. Als er geen identiteit wordt bepaald, selecteren wij _identityMap > id_ als primaire sleutel. Vervolgens moet u een naamruimte selecteren en wordt de sleutel vooraf ingevuld (onder het veld **[!UICONTROL Namespace]**) met _identityMap > id_.

Wanneer u velden selecteert, worden primaire identiteitsvelden gecodeerd.

![](../assets/primary-identity.png)


Selecteer een naamruimte in de vervolgkeuzelijst.

![](../assets/journey17.png)

Per reis is slechts één naamruimte toegestaan. Als u meerdere gebeurtenissen gebruikt op dezelfde reis, moeten ze dezelfde naamruimte gebruiken. Zie [deze pagina](../building-journeys/journey.md).
