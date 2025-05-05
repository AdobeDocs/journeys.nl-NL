---
product: adobe campaign
solution: Journey Orchestration
title: Een bericht verzenden met Campaign v7/v8
description: Een bericht verzenden met Campaign v7/v8
exl-id: 717a927a-4357-4058-a626-1b69f4bb46bc
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 5%

---

# Een bericht verzenden met Campaign v7/v8 {#campaign-classic-use-case}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


In dit geval worden alle stappen beschreven die nodig zijn om een e-mail te verzenden via de integratie met Adobe Campaign Classic v7 en Adobe Campaign v8.

We maken eerst een transactionele e-mailsjabloon in Campagne. In Journey Orchestration maken we dan het evenement, de actie en ontwerpen we de reis.

Raadpleeg de volgende pagina&#39;s voor meer informatie over de integratie van campagnes:

* [Campagne maken](../action/acc-action.md)
* [ Gebruikend de actie in een reis ](../building-journeys/using-adobe-campaign-classic.md).

**Adobe Campaign**

Voor deze integratie moet uw Campagne-instantie zijn ingericht. De eigenschap van het Overseinen van de Transactie moet worden gevormd.

1. Meld u aan bij de besturingsinstantie Campagne.

1. Onder **Beleid** > **Platform** > **Opsommingen**, selecteer het **type van Gebeurtenis** (eventType) opsomming. Maak een nieuw gebeurtenistype (&quot;reis-gebeurtenis&quot;, in ons voorbeeld). U moet de interne naam van het gebeurtenistype gebruiken wanneer u het JSON-bestand later schrijft.

   ![](../assets/accintegration-uc-1.png)

1. Maak de verbinding met de instantie los en maak opnieuw verbinding zodat het maken effectief is.

1. Onder **Centrum van het Bericht** > **Transactionele berichtmalplaatjes**, creeer een nieuw e-mailmalplaatje dat op het eerder gecreeerde gebeurtenistype wordt gebaseerd.

   ![](../assets/accintegration-uc-2.png)

1. Ontwerp uw sjabloon. In dit voorbeeld gebruiken we personalisatie op de voornaam en het ordernummer van het profiel. De voornaam staat in de Adobe Experience Platform-gegevensbron en het ordernummer is een veld uit onze Journey Orchestration-gebeurtenis. Gebruik de juiste veldnamen in Campagne.

   ![](../assets/accintegration-uc-3.png)

1. Publiceer uw transactiesjabloon.

   ![](../assets/accintegration-uc-4.png)

1. Nu moet u de JSON-payload schrijven die overeenkomt met de sjabloon.

```
{
     "channel": "email",
     "eventType": "journey-event",
     "email": "Email address",
     "ctx": {
          "firstName": "First name", "purchaseOrderNumber": "Purchase order number"
     }
}
```

* Voor het kanaal moet u &quot;email&quot; typen.
* Voor eventType gebruikt u de interne naam van het gebeurtenistype dat u eerder hebt gemaakt.
* Het e-mailadres is een variabele, dus u kunt elk label typen.
* Onder ctx, zijn de verpersoonlijkingsgebieden ook variabelen.

**Journey Orchestration**

1. Eerst moet u een gebeurtenis maken. Zorg ervoor dat u het veld &quot;purchaseOrderNumber&quot; opneemt.

   ![](../assets/accintegration-uc-5.png)

1. Vervolgens moet u in Journey Orchestration een actie maken die overeenkomt met uw campagnemjabloon. In het **type van Actie** drop-down, uitgezochte **Adobe Campaign Classic**.

   ![](../assets/accintegration-uc-6.png)

1. Klik het **gebied van de Lading** en kleef JSON eerder gecreeerd.

   ![](../assets/accintegration-uc-7.png)

1. Voor het e-mailadres en de twee verpersoonlijkingsgebieden, veranderings **Constante** aan **Variabele**.

   ![](../assets/accintegration-uc-8.png)

1. Maak nu een nieuwe reis en begin met de gebeurtenis die eerder is gemaakt.

   ![](../assets/accintegration-uc-9.png)

1. Voeg de handeling toe en wijs elk veld toe aan het juiste veld in Journey Orchestration.

   ![](../assets/accintegration-uc-10.png)

1. Voeg een **Eind** activiteit toe en test uw reis.

   ![](../assets/accintegration-uc-11.png)

1. U kunt nu uw reis publiceren.
