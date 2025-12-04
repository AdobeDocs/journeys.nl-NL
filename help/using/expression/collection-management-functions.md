---
product: adobe campaign
title: Functies voor het beheer van verzamelingen
description: Meer informatie over gegevenstypen in functies voor verzamelingsbeheer
feature: Journeys
role: Developer
level: Experienced
exl-id: e80b04fe-b2d3-4c1b-ba22-7e37a9ad1d57
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 0%

---

# Functies voor het beheer van verzamelingen {#collection-management-functions}

De uitdrukkingstaal introduceert ook een reeks functies aan vraaginzamelingen.

Deze functies worden hieronder uitgelegd. In de volgende voorbeelden gebruiken we de gebeurtenislading die een verzameling bevat:

```json
                { 
   "_experience":{ 
      "campaign":{ 
         "message":{ 
            "profile":{ 
               "pushNotificationTokens":[ 
                  { 
                     "token":"token_1",
                     "application":{ 
                        "_id":"APP1",
                        "name":"MarltonMobileApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_2",
                     "application":{ 
                        "_id":"APP2",
                        "name":"MarketplaceApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_3",
                     "application":{ 
                        "_id":"APP3",
                        "name":"VendorApp",
                        "version":"2.0"
                     }
                  }
               ]
            }
         }
      }
   },
   "timestamp":"1536160728"
}
```

**de functie &quot;allen (`<condition>`)&quot;**

De functie **[!UICONTROL all]** laat de definitie van een filter op een bepaalde inzameling toe door een booleaanse uitdrukking te gebruiken.

```json
<listExpression>.all(<condition>)
```

Zo kunt u onder alle gebruikers van de app de toepassingen ophalen met IOS 13 (Booleaanse expressie &quot;app used == IOS 13&quot;). Het resultaat van deze functie is de gefilterde lijst met items die overeenkomen met de booleaanse expressie (bijvoorbeeld: app-gebruiker 1, app-gebruiker 34, app-gebruiker 432).

Bij een Source Condition-activiteit van Data kunt u controleren of het resultaat van de functie **[!UICONTROL all]** null is of niet. U kunt deze **[!UICONTROL all]** functie ook combineren met andere functies, zoals **[!UICONTROL count]** . Voor meer informatie, zie [ de activiteit van de Voorwaarde van Source van Gegevens ](../building-journeys/condition-activity.md#data_source_condition).

**Voorbeeld 1:**

We willen controleren of een gebruiker een specifieke versie van een toepassing heeft geïnstalleerd. Hiervoor krijgen we alle pushberichttokens die zijn gekoppeld aan mobiele toepassingen waarvoor de versie 1.0 is. Vervolgens voeren we een voorwaarde uit met de functie **[!UICONTROL count]** om te controleren of de geretourneerde lijst met tokens ten minste één element bevat.

```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

Het resultaat is waar.

**Voorbeeld 2:**

Hier gebruiken we de functie **[!UICONTROL count]** om te controleren of er pushberichttokens in de verzameling aanwezig zijn.

```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
```

Het resultaat zal waar zijn.

<!--Alternatively, you can check if there is no token in the collection:

   ```json
   count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) == 0
   ```

The result will be false.

Here we use the count function in a condition to count the number of push notification tokens in the event.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token})`

The result is true.

Note that when the condition in the **all()** function is empty, the filter will return all the elements in the list. Hence, the expression above is equivalent to:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.application.name})`

In both cases, the result of the expression is **3**.

A query of experience events recorded on the Adobe Experience Platform may or may not include the current event that triggered the current Journey. This will depend on the relative processing time with which [!DNL Journey Orchestration] sees an event and started evaluating conditions, versus the time it takes for that event to be ingested into the Adobe Experience Platform. For example, when using the .all() syntax to query experience events from the Adobe Experience Platform, we recommend enforcing the exclusion of the current event (by requiring an
earlier timestamp) in order to only consider prior events.-->

>[!NOTE]
>
>Wanneer de het filtreren voorwaarde in **allen ()** functie leeg is, zal de filter alle elementen in de lijst terugkeren. **Nochtans, om het aantal elementen van een inzameling te tellen, wordt de alle functie niet vereist.**


```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

Het resultaat van de uitdrukking is **3**.

**Voorbeeld 3:**

Hier controleren we of een individu in de afgelopen 24 uur geen communicatie heeft ontvangen. Wij filtreren de inzameling van ervaringsgebeurtenissen die uit de datasource ExperiencePlatform worden teruggewonnen, gebruikend twee uitdrukkingen die op twee elementen van de inzameling worden gebaseerd. Met name wordt de tijdstempel van de gebeurtenis vergeleken met de dateTime die door de functie **[!UICONTROL nowWithDelta]** wordt geretourneerd.

```json
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

Het resultaat is waar als er geen ervaringsgebeurtenis is die aan beide voorwaarden voldoet.

**Voorbeeld 4:**

Hier willen we controleren of een persoon in de afgelopen 7 dagen minstens één keer een toepassing heeft gestart, bijvoorbeeld om een pushmelding te activeren waarin hij of zij wordt uitgenodigd een zelfstudie te starten.

```json
count(
 #{ExperiencePlatform.AnalyticsData.experienceevent.all(
 nowWithDelta(-7,"days") <= currentDataPackField.timestamp
 and currentDataPackField.application.firstLaunches.value > 0
)._id}) > 0
```

<!--**"All + Count" example 4:** here we use the count function in a boolean expression to see if there is push notification tokens in the collection.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) > 0`

The result will be:

`true`

Alternatively, you can check if there is NO token in the collection:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) =0`

The result will be:

`false`-->

>[!NOTE]
>
>**[!UICONTROL currentEventField]** is slechts beschikbaar wanneer het manipuleren van gebeurtenisinzamelingen en **currentDataPackField**
>bij het manipuleren van gegevensbronverzamelingen. Wanneer u verzamelingen verwerkt met **[!UICONTROL all]** , **[!UICONTROL first]** en **[!UICONTROL last]** , worden
>loop elk element van de inzameling één voor één. **[!UICONTROL currentEventField]** en **currentDataPackField**
>komt overeen met het element dat wordt herhaald.

**de functies &quot;eerst (`<condition>`)&quot;en &quot;laatste (`<condition>`)&quot;**

De functies **[!UICONTROL first]** en **[!UICONTROL last]** laten ook de definitie van een filter op de inzameling toe terwijl het terugkeren van het eerste/laatste element van de lijst die de filter ontmoet.

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**Voorbeeld 1:**

Deze expressie retourneert het eerste pushmeldingtoken dat is gekoppeld aan mobiele toepassingen waarvoor de versie 1.0 is.

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

Het resultaat is &quot;token_1&quot;.

**Voorbeeld 2:**

Deze expressie retourneert het laatste pushmeldingtoken dat is gekoppeld aan mobiele toepassingen waarvoor de versie 1.0 is.

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
```

Het resultaat is &quot;token_2&quot;.

>[!NOTE]
>
>De ervaringsgebeurtenissen worden uit de Adobe Experience Platform opgehaald als een verzameling in omgekeerde chronologische volgorde, vandaar:
>
>* De functie **[!UICONTROL first]** retourneert de meest recente gebeurtenis
>* **[!UICONTROL last]** functie retourneert de oudste functie.

**Voorbeeld 3:**

We controleren of de eerste (meest recente) Adobe Analytics-gebeurtenis met een waarde groter dan nul voor DMA-id een waarde gelijk aan 602 heeft.

```json
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**de functie &quot;bij (`<index>`)&quot;**

Met de functie **[!UICONTROL at]** kunt u naar een specifiek element in een verzameling verwijzen op basis van een index.
Index 0 is de eerste index van de verzameling.

_`<listExpression>`.at(`<index>`)_

**Voorbeeld:**

Deze expressie retourneert de tweede token voor pushmeldingen van de lijst.

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

Het resultaat is &quot;token_2&quot;.

**Andere voorbeelden**

```json
#{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent. all(currentDataPackField._aepgdcdevenablement2.purchase_event.receipt_nbr == "10-337-4016"). 
_aepgdcdevenablement2.purchase_event.productListItems. all(currentDataPackField.SKU == "AB17 1234 1775 19DT B4DR 8HDK 762").name}
```

```json
 #{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent.last(
currentDataPackField.eventType == "commerce.productListAdds").productListItems.last(currentDataPackField.priceTotal >= 150).name}
```
