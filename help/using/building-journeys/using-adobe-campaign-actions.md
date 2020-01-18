---
title: Adobe Campagne-acties gebruiken
description: Meer informatie over Adobe Campagne-acties
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


# Adobe Campagne-acties gebruiken {#using_campaign_action}

Als u Adobe Campaign Standard hebt, zijn de volgende acties beschikbaar die buiten de doos vallen: **[!UICONTROL Email]**,**[!UICONTROL Push]** en **[!UICONTROL SMS]**.

>[!NOTE]
>
>Hiervoor moet u de ingebouwde actie configureren. Zie [](../action/working-with-adobe-campaign.md).

Voor elk van deze kanalen selecteert u een **sjabloon** voor Transactioneel Overseinen in Adobe Campagne Standard. Journey Orchestration is geen boodschap die een oplossing biedt. Voor de ingebouwde e-mail, sms en duw kanalen, vertrouwen wij op Transactieoverseinen om bericht uit te voeren die verzenden. Dit betekent dat als u een bepaalde berichtsjabloon wilt gebruiken voor uw reizen, u deze moet publiceren in Adobe Campagnestandaard. Raadpleeg deze [pagina](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html) voor meer informatie over het gebruik van deze functie.

![](../assets/journey59.png)

U kunt een gebeurtenis (die ook als Real-Time wordt bekend) of een malplaatje van het profieltransactie gebruiken.

>[!NOTE]
>
>Wanneer wij transactieberichten in real time (rtEvent) verzenden of wanneer wij berichten met een derdesysteem door een douaneactie leiden, wordt een specifieke opstelling vereist voor moeheid, zwarte lijst of unsubscription beheer. Als bijvoorbeeld een kenmerk &quot;blacklist&quot; of &quot;unsubscribe&quot; is opgeslagen in het Platform of in een systeem van derden, moet een voorwaarde worden toegevoegd vóór het bericht dat deze voorwaarde verzendt.

Als u een sjabloon selecteert, worden alle velden die in de berichtlading worden verwacht, weergegeven in het deelvenster Activiteitsconfiguratie onder **[!UICONTROL Address]**en**[!UICONTROL Personalization Data]**. U moet elk van deze gebieden met het gebied in kaart brengen u, of van de gebeurtenis of van de gegevensbron wilt gebruiken. U kunt de geavanceerde uitdrukkingsredacteur ook gebruiken om een waarde manueel over te gaan, gegevensmanipulatie op teruggewonnen informatie (bijvoorbeeld om een koord in hoofdletters om te zetten) uit te voeren of functies zoals &quot;als, toen, anders&quot;te gebruiken. Zie [](../expression/expressionadvanced.md).

![](../assets/journey60.png)

## E-mail en sms {#section_asc_51g_nhb}

Voor **[!UICONTROL Email]**en**[!UICONTROL SMS]**, zijn de parameters identiek.

>[!NOTE]
>
>Voor e-mail, als u een malplaatje van de profieltransactie gebruikt, wordt het unsubscription mechanisme behandeld uit-van-de-doos door de Norm van de Campagne. U voegt eenvoudig een **[!UICONTROL Unsubscription link]**inhoudsblok in het malplaatje toe ([leer meer](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)). Als u een op een gebeurtenis gebaseerde sjabloon (rtEvent) gebruikt, moet u in het bericht een koppeling toevoegen die de e-mail van de persoon in de URL-parameter doorgeeft en naar een bestemmingspagina zonder abonnement verwijst. U moet deze openingspagina maken en ervoor zorgen dat de beslissing van de persoon om het abonnement op te zeggen wordt overgebracht naar Adobe.

Eerst, moet u een transactioneel overseinensjabloon kiezen. Zie [](../building-journeys/about-action-activities.md).

Er zijn twee categorieën beschikbaar: **[!UICONTROL Address]**en**[!UICONTROL Personalization Data]**.

U kunt gemakkelijk bepalen waar te om de **[!UICONTROL Address]**of de**[!UICONTROL Personalization Data]** gebruikend de interface terug te winnen. U kunt door gebeurtenissen en beschikbare gebieden van de gegevensbron doorbladeren. U kunt de geavanceerde uitdrukkingsredacteur voor geavanceerdere gebruiksgevallen zoals het gebruiken van een gegevensbron ook gebruiken die de overgaan van parameters of het uitvoeren van manipulaties vereist. Zie [](../expression/expressionadvanced.md).

**[!UICONTROL Address]**

>[!NOTE]
>
>Deze categorie is alleen zichtbaar als u een transactiebericht voor een gebeurtenis selecteert. Voor profielberichten wordt het **[!UICONTROL Address]**veld automatisch door het systeem opgehaald uit de Adobe Campaign Standard.

Dit zijn de gebieden het systeem vereist om te weten waar te om het bericht te verzenden. Voor een e-mailsjabloon is dit het e-mailadres. Voor een SMS is het het mobiele telefoonnummer.

![](../assets/journey61.png)

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>U kunt geen inzameling in verpersoonlijkingsgegevens overgaan. Als de transactie-e-mail of SMS inzamelingen verwacht, zal het niet werken. Merk ook op dat de verpersoonlijkingsgegevens een verwacht formaat hebben (voorbeeld: tekenreeks, decimaal, enz.). U moet deze verwachte formaten zorgvuldig respecteren.

Dit zijn de velden die worden verwacht in het bericht Adobe Campagne Standard. Deze velden kunnen worden gebruikt om het bericht aan te passen, voorwaardelijke opmaak toe te passen of een specifieke berichtvariant te kiezen.

![](../assets/journey62.png)

## Push {#section_im3_hvf_nhb}

Voordat u de pushactiviteit kunt gebruiken, moet uw mobiele app samen met Campagnestandaard worden geconfigureerd voor het verzenden van pushberichten. Gebruik dit [artikel](https://helpx.adobe.com/campaign/kb/integrate-mobile-sdk.html) om de benodigde implementatiestappen voor mobiele apparaten uit te voeren.

Eerst moet u een mobiele app kiezen in de vervolgkeuzelijst en een transactiebericht. Zie [](../building-journeys/about-action-activities.md).

![](../assets/journey62bis.png)

Er zijn twee categorieën beschikbaar: **[!UICONTROL Target]**en**[!UICONTROL Personalization Data]**.

**[!UICONTROL Target]**

>[!NOTE]
>
>Deze categorie is alleen zichtbaar als u een gebeurtenisbericht selecteert. Voor profielberichten worden de **[!UICONTROL Target]**velden automatisch door het systeem opgehaald met behulp van de afstemming die wordt uitgevoerd door Adobe Campaign Standard.

In deze sectie moet u de **[!UICONTROL Push platform]**code definiëren. In de vervolgkeuzelijst kunt u**[!UICONTROL Apple Push Notification Server]** (iOS) of **[!UICONTROL Firebase Cloud Messaging]**(Android) selecteren. U kunt ook een specifiek veld selecteren in een gebeurtenis of gegevensbron, of een geavanceerde expressie definiëren.

U moet ook de **[!UICONTROL Registration Token]**code definiëren. De uitdrukking hangt van hoe af het teken in de gebeurtenislading of in andere informatie van het Orchestration van de Reis wordt bepaald. Het kan een eenvoudig veld of een complexere expressie zijn voor het geval het token bijvoorbeeld in een verzameling wordt gedefinieerd:

```
@{Event_push._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
```

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>U kunt geen inzameling in verpersoonlijkingsgegevens overgaan. Als de transactioneel duw inzamelingen verwacht, zal het niet werken. Merk ook op dat de verpersoonlijkingsgegevens een verwacht formaat hebben (voorbeeld: tekenreeks, decimaal, enz.). U moet deze verwachte formaten zorgvuldig respecteren.

Dit zijn de velden die worden verwacht door de transactiesjabloon die wordt gebruikt in het bericht Adobe Campagne Standard. Deze velden kunnen worden gebruikt om uw bericht aan te passen, voorwaardelijke opmaak toe te passen of een specifieke berichtvariant te kiezen.
