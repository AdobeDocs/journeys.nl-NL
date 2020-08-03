---
title: De gebeurtenistoets definiëren
description: Leer hoe u de gebeurtenissleutel definieert
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
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 0%

---


# De gebeurtenistoets definiëren {#concept_ond_hqt_52b}

De sleutel is het veld of de combinatie van velden maakt deel uit van de ladingsgegevens van de gebeurtenis. Hierdoor kan het systeem de persoon identificeren die aan de gebeurtenis is gekoppeld. De sleutel kan bijvoorbeeld de Experience Cloud-id, een CRM-id of een e-mailadres zijn.

Als u gegevens wilt gebruiken die zijn opgeslagen in de realtime database van het klantprofiel, moet u, als de sleutel van de gebeurtenis, informatie selecteren die u als de identiteit van een profiel hebt gedefinieerd in de [realtime service](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html)voor klantprofiel.

Hierdoor kan het systeem de afstemming tussen de gebeurtenis en het profiel van het individu uitvoeren. Als u een schema met een primaire identiteit selecteert, worden de **[!UICONTROL Key]** **[!UICONTROL Namespace]** velden en de velden vooraf ingevuld. Als er geen identiteit is gedefinieerd, selecteren we _identityMap > id_ als primaire sleutel. Vervolgens moet u een naamruimte selecteren en wordt de sleutel vooraf ingevuld (onder het **[!UICONTROL Namespace]** veld) met _identityMap > id_.

Wanneer u velden selecteert, worden primaire identiteitsvelden gecodeerd.

![](../assets/primary-identity.png)

Als u een andere sleutel, zoals een identiteitskaart van CRM of een e-mailadres moet gebruiken, moet u het manueel toevoegen:

1. Klik in het **[!UICONTROL Key]** veld of op het potloodpictogram.

   ![](../assets/journey16.png)

1. Selecteer het veld dat u als de sleutel hebt gekozen in de lijst met ladingsvelden. U kunt ook overschakelen naar de geavanceerde expressie-editor om complexere sleutels te maken (bijvoorbeeld een samenvoeging van twee velden met de gebeurtenissen). Zie hieronder in deze sectie.

   ![](../assets/journey20.png)

Wanneer de gebeurtenis wordt ontvangen, zal de waarde van de sleutel het systeem toestaan om de persoon te identificeren verbonden aan de gebeurtenis. Gekoppeld aan een naamruimte (zie [](../event/selecting-the-namespace.md)), kan de sleutel worden gebruikt om query&#39;s uit te voeren op het Adobe Experience Platform. Zie [](../building-journeys/about-orchestration-activities.md).
De sleutel wordt ook gebruikt om te controleren of een persoon op reis is. Een persoon kan namelijk niet op twee verschillende plaatsen op dezelfde reis zijn. Als gevolg hiervan staat het systeem niet toe dat dezelfde sleutel, bijvoorbeeld de sleutel CRMID=3224, zich op verschillende plaatsen op dezelfde reis bevindt.

U hebt ook toegang tot de geavanceerde expressiefuncties (**[!UICONTROL Advanced mode]**) als u aanvullende bewerkingen wilt uitvoeren. Met deze functies kunt u de waarden manipuleren die worden gebruikt voor het uitvoeren van specifieke query&#39;s, zoals het wijzigen van de opmaak, het uitvoeren van veldsamenvoegingen, waarbij alleen rekening wordt gehouden met een deel van een veld (bijvoorbeeld de eerste 10 tekens). Zie [](../expression/expressionadvanced.md).
