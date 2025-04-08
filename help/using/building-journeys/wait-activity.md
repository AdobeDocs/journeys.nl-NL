---
product: adobe campaign
title: Wachtactiviteit
description: Meer informatie over wachtactiviteiten
feature: Journeys
role: User
level: Intermediate
exl-id: 819ff3c3-0e3e-4d86-b5d2-10c5b10d19e6
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 3%

---

# Wachtactiviteit{#section_rlm_nft_dgb}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._



Als u wilt wachten voordat u de volgende activiteit in het pad uitvoert, kunt u een **[!UICONTROL Wait]** activiteit gebruiken. Hiermee kunt u bepalen wanneer de volgende activiteit wordt uitgevoerd. Er zijn drie opties beschikbaar:

* [ Duur ](#duration)
* [ Douane ](#custom)
  <!--* [Email send time optimization](#email_send_time_optimization)-->

## Informatie over de activiteit Wachten{#about_wait}

Hier is hoe de wacht voorrang krijgt wanneer u verscheidene wacht parallel gebruikt. Als zij de zelfde tijdconfiguratie en een verschillende maar overlappende voorwaarde hebben, hierboven gepositioneerde wachttijd zal aan voorrang gegeven zijn. De eerste wachttijd is bijvoorbeeld &#39;een vrouw zijn&#39; en de tweede wachttijd is &#39;een VIP zijn&#39;. De eerste wachtbewerking krijgt prioriteit.

Houd er ook rekening mee dat als twee verschillende wachttijden parallel lopen, de eerste prioriteit krijgt, ongeacht de verticale positie. Bijvoorbeeld, als een 1 uur wacht boven is en een 30 minuut wacht onder is, na 30 minuten, zal het 30 minieme ogenblik worden verwerkt.

>[!NOTE]
>
>De maximale wachttijd is 30 dagen.
>
>In de testmodus kunt u met de parameter **[!UICONTROL Wait time in test]** de tijd definiëren waarop elke wachtactiviteit wordt uitgevoerd. De standaardtijd is 10 seconden. Zo krijgt u de testresultaten snel. Zie [ deze pagina ](../building-journeys/testing-the-journey.md)

## Wachten op duur{#duration}

Selecteer de duur van de wachttijd voordat de volgende activiteit wordt uitgevoerd.

![](../assets/journey55.png)

## Aangepast wachten{#custom}

Met deze optie kunt u een aangepaste datum definiëren, bijvoorbeeld 12 juli 2020 om 17.00 uur, met een geavanceerde expressie die is gebaseerd op een veld dat afkomstig is van een gebeurtenis of gegevensbron. U kunt hiermee geen aangepaste duur definiëren, bijvoorbeeld 7 dagen. De expressie in de expressie-editor moet een dateTimeOnly-indeling hebben. Zie [ deze pagina ](../expression/expressionadvanced.md). Voor meer informatie over dateTimeOnly formaat, zie [ deze pagina ](../expression/data-types.md).

>[!NOTE]
>
>U kunt een dateTimeOnly-expressie gebruiken of een functie gebruiken om om te zetten in een dateTimeOnly. Bijvoorbeeld: toDateTimeOnly (@{Event.offerOpened.activity.endTime}), het gebied in de gebeurtenis die van vorm 2016-08-12T09 :46: 06Z is.
>
>De **tijdzone** wordt verwacht in de eigenschappen van uw reis. Dientengevolge, is het niet mogelijk vandaag van de interface om bij volledige tijdstempel te richten ISO-8601 die tijd en tijdzone zoals 2016-08-12T09 :46: 06.982-05 mengen. Zie [deze pagina](../building-journeys/timezone-management.md).

![](../assets/journey57.png)

<!--## Email send time optimization{#email_send_time_optimization}

>[!CAUTION]
>
>The email send time optimization capability is only available to customers who use the [Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html).

This type of wait uses a score calculated in the Adobe Experience Platform. The score calculates the propensity to click or open an email in the future based on past behavior. Note that the algorithm calculating the score needs a certain amount of data to work. As a result, when it does not have enough data, the default wait time will apply. At publication time, you'll be notified that the default time applies.

>[!NOTE]
>
>The first event of your journey must have a namespace.
>
>This capability is only available after an **[!UICONTROL Email]** activity. You need to have Adobe Campaign Standard.

1. In the **[!UICONTROL Amount of time]** field, define the number of hours to consider to optimize email sending.
1. In the **[!UICONTROL Optimization type]** field, choose if the optimization should increase clicks or opens.
1. In the **[!UICONTROL Default time]** field, define the default time to wait if the predictive send time score is not available.

    >[!NOTE]
    >
    >Note that the send time score can be unavailable because there is not enough data to perform the calculation. In this case, you will be informed, at publication time, that the default time applies.

![](../assets/journey57bis.png)-->
