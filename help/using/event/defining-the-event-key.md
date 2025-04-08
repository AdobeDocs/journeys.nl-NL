---
product: adobe campaign
title: Gebeurtenistoets definiëren
description: Leer hoe u de gebeurtenissleutel definieert
feature: Journeys
role: User
level: Intermediate
exl-id: 79bcf562-f971-42f1-a607-94a2510c4a07
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 2%

---

# Gebeurtenistoets definiëren {#concept_ond_hqt_52b}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


De sleutel is het veld of de combinatie van velden maakt deel uit van de ladingsgegevens van de gebeurtenis. Hierdoor kan het systeem de persoon identificeren die aan de gebeurtenis is gekoppeld. De sleutel kan bijvoorbeeld de Experience Cloud-id, een CRM-id of een e-mailadres zijn.

Als u van plan bent aan hefboomgegevens die in het gegevensbestand van het Profiel van de Klant in real time worden opgeslagen, moet u, als gebeurtenissleutel selecteren, informatie u als identiteit van een profiel in de [ Echte Dienst van het Profiel van de Klant ](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=nl) bepaalde.

Hierdoor kan het systeem de afstemming tussen de gebeurtenis en het profiel van het individu uitvoeren. Als u een schema met een primaire identiteit selecteert, worden de velden **[!UICONTROL Key]** en **[!UICONTROL Namespace]** vooraf ingevuld. Als er geen bepaalde identiteit is, selecteren wij _identityMap > identiteitskaart_ als primaire sleutel. Dan moet u een namespace selecteren en de sleutel (onder het **[!UICONTROL Namespace]** gebied) zal worden vooraf ingevuld gebruikend _identityMap > identiteitskaart_.

Wanneer u velden selecteert, worden primaire identiteitsvelden gecodeerd.

![](../assets/primary-identity.png)

Als u een andere sleutel, zoals een identiteitskaart van CRM of een e-mailadres moet gebruiken, moet u het manueel toevoegen:

1. Klik in het veld **[!UICONTROL Key]** of op het potloodpictogram.

   ![](../assets/journey16.png)

1. Selecteer het veld dat u als de sleutel hebt gekozen in de lijst met ladingsvelden. U kunt ook overschakelen naar de geavanceerde expressie-editor om complexere sleutels te maken (bijvoorbeeld een samenvoeging van twee velden met de gebeurtenissen). Zie hieronder, in deze sectie.

   ![](../assets/journey20.png)

Wanneer de gebeurtenis wordt ontvangen, zal de waarde van de sleutel het systeem toestaan om de persoon te identificeren verbonden aan de gebeurtenis. Verbonden aan een namespace (zie [ deze pagina ](../event/selecting-the-namespace.md)), kan de sleutel worden gebruikt om vragen op Adobe Experience Platform uit te voeren. Zie [ deze pagina ](../building-journeys/about-orchestration-activities.md).
De sleutel wordt ook gebruikt om te controleren of een persoon op reis is. Een persoon kan namelijk niet op twee verschillende plaatsen op dezelfde reis zijn. Als gevolg hiervan staat het systeem niet toe dat dezelfde sleutel, bijvoorbeeld de sleutel CRMID=3224, zich op verschillende plaatsen op dezelfde reis bevindt.

U hebt ook toegang tot de geavanceerde uitdrukkingsfuncties (**[!UICONTROL Advanced mode]**) als u extra manipulaties wilt uitvoeren. Met deze functies kunt u de waarden manipuleren die worden gebruikt voor het uitvoeren van specifieke query&#39;s, zoals het wijzigen van de opmaak, het uitvoeren van veldsamenvoegingen, waarbij alleen rekening wordt gehouden met een deel van een veld (bijvoorbeeld de eerste 10 tekens). Zie [deze pagina](../expression/expressionadvanced.md).
