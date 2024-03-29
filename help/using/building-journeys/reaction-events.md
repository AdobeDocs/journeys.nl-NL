---
product: adobe campaign
title: Gebeurtenissen van Reacties
description: Meer informatie over reacties
feature: Journeys
role: User
level: Intermediate
exl-id: 2f2a2905-1521-48d9-b593-9b31238282a5
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 2%

---

# Reactiegebeurtenissen {#section_dhx_gss_dgb}

De ingebouwde **[!UICONTROL Reactions]** gebeurtenis. Met deze activiteit kunt u reageren op volggegevens met betrekking tot een bericht dat is verzonden met e-mail, SMS of push-activiteiten binnen dezelfde reis. Deze informatie is afkomstig van transactiemeldingen in Adobe Campaign Standard. We leggen deze informatie in real time vast op het moment dat ze met de Adobe Experience Platform wordt gedeeld. Voor pushberichten kunt u reageren op geklikte, verzonden of mislukte berichten. Voor SMS-berichten kunt u reageren op verzonden of mislukte berichten. Voor e-mailberichten kunt u reageren op geklikte, verzonden, geopende of mislukte berichten.

U kunt dit mechanisme ook gebruiken om een actie uit te voeren wanneer er geen reactie op uw berichten is. Hiertoe maakt u een tweede pad parallel aan de reactieactiviteit en voegt u een wachtactiviteit toe. Als er geen reactie optreedt tijdens de periode die is gedefinieerd in de wachtdienst, wordt het tweede pad gekozen. U kunt bijvoorbeeld een vervolgbericht verzenden.

Let op: u kunt alleen reactieactiviteiten op het canvas gebruiken als er al eerder een e-mail-, push- of SMS-activiteit is.

Zie [Informatie over actieactiviteiten](../building-journeys/about-action-activities.md).

![](../assets/journey45.png)

Hier volgen de verschillende stappen voor het configureren van reactiegebeurtenissen:

1. Voeg een **[!UICONTROL Label]** op de reactie. Deze stap is optioneel.
1. Selecteer in de vervolgkeuzelijst de activiteit waarop u wilt reageren. U kunt alle handelingen selecteren die zich in de vorige stappen van het pad bevinden.
1. Afhankelijk van de actie die u hebt geselecteerd (een e-mail, SMS of een pushmelding), kiest u waarop u wilt reageren.
1. U kunt een time-out voor de gebeurtenis (tussen 40 seconden en 30 dagen) en een time-outpad definiëren. Hierdoor wordt een tweede pad gemaakt voor personen die niet binnen de gedefinieerde tijdsduur hebben gereageerd. Bij het testen van een traject waarbij een reactiegebeurtenis wordt gebruikt, de testmodus **[!UICONTROL Wait time]** standaard en minimumwaarde is 40 seconden. Zie [deze sectie](../building-journeys/testing-the-journey.md).

>[!NOTE]
>
>Reactiegebeurtenissen werken met Adobe Campaign Standard, ongeacht of ze zijn geïmplementeerd op AWS- of Azure-servers.
>
>Reactiegebeurtenissen kunnen geen e-mail-, SMS- of pushacties bijhouden die op een andere reis plaatsvinden.
>
>Gebeurtenissen van Reaction volgen klikt op koppelingen van het type &quot;bijgehouden&quot; (zie deze [page](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/links.html#about-tracked-urls)). Er wordt geen rekening gehouden met abonnements- en spiegelpaginakoppelingen.

>[!IMPORTANT]
>
>E-mailclients zoals Gmail staan het blokkeren van afbeeldingen toe. E-mails die worden geopend, worden bijgehouden met een afbeelding van 0 pixels die in de e-mail is opgenomen. Als afbeeldingen worden geblokkeerd, wordt er geen rekening gehouden met het openen van e-mail.
