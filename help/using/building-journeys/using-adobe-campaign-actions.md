---
product: adobe campaign
title: Adobe Campaign-acties gebruiken
description: Meer informatie over Adobe Campaign-acties
feature: Journeys
role: User
level: Intermediate
exl-id: b2e5c333-d0d8-4fe1-a6b8-5f2e6b3624a4
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 5%

---

# Adobe Campaign Standard gebruiken {#using_campaign_action}

Als u Adobe Campaign Standard hebt, zijn de volgende buiten-de-box actieactiviteiten beschikbaar: **[!UICONTROL Email]**, **[!UICONTROL Push]** en **[!UICONTROL SMS]**.

>[!NOTE]
>
>Hiervoor moet u de ingebouwde actie configureren. Zie [deze pagina](../action/working-with-adobe-campaign.md).

Voor elk van deze kanalen selecteert u een Adobe Campaign Standard Transaction Messaging **template**. Sterker nog, [!DNL Journey Orchestration] is geen bericht verzendend oplossing. Voor de ingebouwde e-mail, sms en duw kanalen, vertrouwen wij op Transactieoverseinen om bericht uit te voeren die verzenden. Het betekent dat als u een bepaald berichtmalplaatje in uw reizen wilt gebruiken, u het in Adobe Campaign Standard moet publiceren. Zie [deze pagina](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=nl) voor meer informatie over het gebruik van deze functie.

>[!NOTE]
>
>Het transactiemelding van de Campaign Standard en zijn bijbehorende gebeurtenis moeten worden gepubliceerd om in Journey Orchestration te worden gebruikt. Als de gebeurtenis wordt gepubliceerd maar het bericht niet is, zal het niet in de interface van Journey Orchestration zichtbaar zijn. Als het bericht wordt gepubliceerd maar zijn bijbehorende gebeurtenis is niet, zal het in de interface van Journey Orchestration zichtbaar zijn maar het zal niet bruikbaar zijn.

![](../assets/journey59.png)

U kunt een gebeurtenis (die ook als Real-Time wordt bekend) of een malplaatje van het profieltransactie gebruiken.

>[!NOTE]
>
>Wanneer wij transactieberichten in real time (rtEvent) verzenden of wanneer wij berichten met een derdesysteem dankzij een douaneactie leiden, wordt een specifieke opstelling vereist voor moeheid, lijst van gewezen personen of unsubscription beheer. Als bijvoorbeeld een kenmerk &quot;unsubscribe&quot; in de Adobe Experience Platform of in een systeem van derden wordt opgeslagen, moet een voorwaarde worden toegevoegd vóór het bericht dat deze voorwaarde verzendt.

Wanneer u een sjabloon selecteert, worden alle velden die in de berichtlading worden verwacht, weergegeven in het deelvenster voor activiteitenconfiguratie onder **[!UICONTROL Address]** en **[!UICONTROL Personalization Data]**. U moet elk van deze gebieden met het gebied in kaart brengen u, of van de gebeurtenis of van de gegevensbron wilt gebruiken. U kunt de geavanceerde uitdrukkingsredacteur ook gebruiken om een waarde manueel over te gaan, gegevensmanipulatie op teruggewonnen informatie (bijvoorbeeld om een koord in hoofdletters om te zetten) uit te voeren of functies zoals &quot;als, toen, anders&quot;te gebruiken. Zie [deze pagina](../expression/expressionadvanced.md).

![](../assets/journey60.png)

## E-mail en sms {#section_asc_51g_nhb}

Voor **[!UICONTROL Email]** en **[!UICONTROL SMS]**, zijn de parameters identiek.

>[!NOTE]
>
>Voor e-mail, als u een malplaatje van de profieltransactie gebruikt, wordt het unsubscription mechanisme behandeld uit-van-de-doos door Campaign Standard. U voegt eenvoudig een **[!UICONTROL Unsubscription link]** inhoudsblok in de sjabloon ([Meer informatie](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=nl)). Als u een op een gebeurtenis gebaseerde sjabloon (rtEvent) gebruikt, moet u in het bericht een koppeling toevoegen die de e-mail van de persoon in de URL-parameter doorgeeft en naar een bestemmingspagina zonder abonnement verwijst. U moet deze landingspagina maken en ervoor zorgen dat de beslissing van de persoon om het abonnement op te zeggen wordt doorgegeven aan Adobe.

Eerst, moet u een transactioneel overseinensjabloon kiezen. Zie [deze pagina](../building-journeys/about-action-activities.md).

Er zijn twee categorieën beschikbaar: **[!UICONTROL Address]** en **[!UICONTROL Personalization Data]**.

U kunt gemakkelijk bepalen waar te om terug te winnen **[!UICONTROL Address]** of de **[!UICONTROL Personalization Data]** het gebruiken van de interface. U kunt door gebeurtenissen en beschikbare gebieden van de gegevensbron doorbladeren. U kunt de geavanceerde uitdrukkingsredacteur voor geavanceerdere gebruiksgevallen zoals het gebruiken van een gegevensbron ook gebruiken die de overgaan van parameters of het uitvoeren van manipulaties vereist. Zie [deze pagina](../expression/expressionadvanced.md).

**[!UICONTROL Address]**

>[!NOTE]
>
>Deze categorie is alleen zichtbaar als u een transactiebericht voor een gebeurtenis selecteert. Voor &quot;profiel&quot;-berichten wordt **[!UICONTROL Address]** wordt automatisch door het systeem opgehaald uit Adobe Campaign Standard.

Dit zijn de gebieden het systeem vereist om te weten waar te om het bericht te verzenden. Voor een e-mailsjabloon is dit het e-mailadres. Voor een SMS is het het mobiele telefoonnummer.

![](../assets/journey61.png)

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>U kunt geen inzameling in verpersoonlijkingsgegevens overgaan. Als de transactie-e-mail of SMS inzamelingen verwacht, zal het niet werken. Merk ook op dat de verpersoonlijkingsgegevens een verwacht formaat hebben (voorbeeld: tekenreeks, decimaal, enz.). U moet deze verwachte formaten zorgvuldig respecteren.

Dit zijn de velden die worden verwacht door het Adobe Campaign Standard-bericht. Deze velden kunnen worden gebruikt om het bericht aan te passen, voorwaardelijke opmaak toe te passen of een specifieke berichtvariant te kiezen.

![](../assets/journey62.png)

## Push {#section_im3_hvf_nhb}

Voordat u de pushactiviteit kunt gebruiken, moet uw mobiele app samen met Campaign Standard worden geconfigureerd om pushmeldingen te verzenden. Gebruik deze [artikel](https://helpx.adobe.com/nl/campaign/kb/integrate-mobile-sdk.html) de nodige stappen voor de implementatie van mobiele apparatuur te ondernemen.

Eerst moet u een mobiele app kiezen in de vervolgkeuzelijst en een transactiebericht. Zie [deze pagina](../building-journeys/about-action-activities.md).

![](../assets/journey62bis.png)

Er zijn twee categorieën beschikbaar: **[!UICONTROL Target]** en **[!UICONTROL Personalization Data]**.

**[!UICONTROL Target]**

>[!NOTE]
>
>Deze categorie is alleen zichtbaar als u een gebeurtenisbericht selecteert. Voor profielberichten, **[!UICONTROL Target]** velden worden automatisch door het systeem opgehaald met behulp van de afstemming die door Adobe Campaign Standard wordt uitgevoerd.

In deze sectie moet u de opdracht **[!UICONTROL Push platform]**. In de vervolgkeuzelijst kunt u **[!UICONTROL Apple Push Notification Server]** (iOS) of **[!UICONTROL Firebase Cloud Messaging]** (Android). U kunt ook een specifiek veld selecteren in een gebeurtenis of gegevensbron, of een geavanceerde expressie definiëren.

U moet ook de **[!UICONTROL Registration Token]**. De expressie hangt af van de manier waarop het token is gedefinieerd in de gebeurtenislading of in andere [!DNL Journey Orchestration] informatie. Het kan een eenvoudig veld of een complexere expressie zijn voor het geval het token bijvoorbeeld in een verzameling wordt gedefinieerd:

```
@{Event_push._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
```

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>U kunt geen inzameling in verpersoonlijkingsgegevens overgaan. Als de transactioneel duw inzamelingen verwacht, zal het niet werken. Merk ook op dat de verpersoonlijkingsgegevens een verwacht formaat hebben (voorbeeld: tekenreeks, decimaal, enz.). U moet deze verwachte formaten zorgvuldig respecteren.

Dit zijn de velden die worden verwacht door de transactiesjabloon die wordt gebruikt in je Adobe Campaign Standard-bericht. Deze velden kunnen worden gebruikt om uw bericht aan te passen, voorwaardelijke opmaak toe te passen of een specifieke berichtvariant te kiezen.
