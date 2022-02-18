---
product: adobe campaign
solution: Journey Orchestration
title: Een bericht verzenden met Campaign v7/v8
description: Een bericht verzenden met Campaign v7/v8
source-git-commit: 2195ee3863b38ead504eb6785ceb3c37735fade9
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 6%

---

# Een bericht verzenden met Campaign v7/v8 {#campaign-classic-use-case}

In dit geval worden alle stappen beschreven die nodig zijn om een e-mail te verzenden via de integratie met Adobe Campaign Classic v7 en Adobe Campaign v8.

We maken eerst een transactionele e-mailsjabloon in Campagne. Dan, in Journey Orchestration, zullen wij de gebeurtenis, actie en ontwerp de reis creëren.

Raadpleeg de volgende pagina&#39;s voor meer informatie over de integratie van campagnes:

* [Campagne maken](../action/acc-action.md)
* [De handeling op een reis gebruiken](../building-journeys/using-adobe-campaign-classic.md).

**Adobe Campaign**

Voor deze integratie moet uw Campagne-instantie zijn ingericht. De eigenschap van het Overseinen van de Transactie moet worden gevormd.

1. Meld u aan bij de besturingsinstantie Campagne.

1. Onder **Beheer** > **Platform** > **Opsommingen**, selecteert u de **Het type Event** (eventType) opsomming. Maak een nieuw gebeurtenistype (&quot;reis-gebeurtenis&quot;, in ons voorbeeld). U moet de interne naam van het gebeurtenistype gebruiken wanneer u het JSON-bestand later schrijft.

   ![](../assets/accintegration-uc-1.png)

1. Maak de verbinding met de instantie los en maak opnieuw verbinding zodat het maken effectief is.

1. Onder **Berichtencentrum** > **Transactieberichtsjablonen**, maakt u een nieuwe e-mailsjabloon op basis van het eerder gemaakte gebeurtenistype.

   ![](../assets/accintegration-uc-2.png)

1. Ontwerp uw sjabloon. In dit voorbeeld gebruiken we personalisatie op de voornaam en het ordernummer van het profiel. De voornaam staat in de Adobe Experience Platform-gegevensbron en het ordernummer is een veld van onze Journey Orchestration-gebeurtenis. Gebruik de juiste veldnamen in Campagne.

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

1. Vervolgens moet u in Journey Orchestration een actie maken die overeenkomt met uw campagnemalplaatje. In de **Type handeling** vervolgkeuzelijst, selecteert u **Adobe Campaign Classic**.

   ![](../assets/accintegration-uc-6.png)

1. Klik op de knop **Payloadveld** en plakt de eerder gemaakte JSON.

   ![](../assets/accintegration-uc-7.png)

1. Voor het e-mailadres en de twee velden voor personalisatie wijzigt u **Constante** tot **Variabele**.

   ![](../assets/accintegration-uc-8.png)

1. Maak nu een nieuwe reis en begin met de gebeurtenis die eerder is gemaakt.

   ![](../assets/accintegration-uc-9.png)

1. Voeg de handeling toe en wijs elk veld toe aan het juiste veld in Journey Orchestration.

   ![](../assets/accintegration-uc-10.png)

1. Een **Einde** en test je reis.

   ![](../assets/accintegration-uc-11.png)

1. U kunt nu uw reis publiceren.
