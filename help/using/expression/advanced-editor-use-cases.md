---
product: adobe campaign
title: De geavanceerde expressie-editor gebruiken
description: Geavanceerde expressies maken
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 724ae59e-d1b5-4de9-b140-d37064e22ac6
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 1%

---

# Geavanceerde expressievoorbeelden


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


De Geavanceerde uitdrukkingsredacteur kan worden gebruikt om voorwaarden tot stand te brengen om u toe te staan om gebruikers in uw reizen te filtreren. Met deze voorwaarden kunt u zich richten op gebruikers op tijd, datum, locatie, duur of acties zoals het kopen of verlaten van winkelwagentjes, zodat ze tijdens de reis opnieuw op de doelgroep kunnen worden geplaatst.

>[!NOTE]
>
>Gebeurtenissen beginnen met @, gegevensbronnen met #.

## Voorwaarden voor ervaringsgebeurtenissen opbouwen

De geavanceerde uitdrukkingsredacteur is verplicht om vragen op tijdreeksen zoals een lijst van aankopen of voorbij klikken op berichten uit te voeren. Dergelijke vragen kunnen niet worden uitgevoerd gebruikend de eenvoudige redacteur.

De ervaringsgebeurtenissen worden uit de Adobe Experience Platform opgehaald als een verzameling in omgekeerde chronologische volgorde, vandaar:

* De eerste functie retourneert de meest recente gebeurtenis
* last function retourneert de oudste functie.

Bijvoorbeeld, laten wij zeggen u klanten met een kartontroeping in de laatste 7 dagen wilt richten om een bericht te verzenden wanneer de klant dichtbij een opslag, met een aanbieding op punten komt die zij gewild hebben die in opslag zijn.

**u moet de volgende voorwaarden bouwen:**

Ten eerste doelklanten die in de online winkel hebben gebladerd maar de bestelling de laatste 7 dagen niet hebben voltooid.

<!--**This expression looks for a specified value in a string value:**

`In ("addToCart", #{field reference from experience event})`-->

**Deze uitdrukking zoekt alle gebeurtenissen voor deze gebruiker die in de laatste 7 dagen wordt gespecificeerd:**

Vervolgens worden alle addtocart-gebeurtenissen geselecteerd die niet zijn omgezet in een completePurchase.

>[!NOTE]
>
>Als u snel velden in de expressie wilt invoegen, dubbelklikt u op het veld in het linkerdeelvenster van de editor.

De opgegeven tijdstempel fungeert als datumtijdwaarde en de tweede als aantal dagen.

```json
        in( "addToCart", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
        and
        not(in( "completePurchase", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction}))
```

Deze expressie retourneert een Booleaanse waarde.

**nu bouwen een uitdrukking die controleert dat het product in voorraad** is

* In Inventory, zoekt deze uitdrukking naar kwantitatief gebied van een product en specificeert dat het groter zou moeten zijn dan 0.

`#{Inventory.fieldgroup3.quantity} > 0`

* Bij het recht, worden de noodzakelijke waarden gespecificeerd, hier, moeten wij de plaats van de opslag terugwinnen, die van de plaats van de gebeurtenis &quot;ArriveLumaStudio&quot;in kaart wordt gebracht:

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* En geef SKU op door de functie `first` te gebruiken om de meest recente interactie &quot;addToCart&quot; op te halen:

  ```json
      #{ExperiencePlatformDataSource
                      .ExperienceEventFieldGroup
                      .experienceevent
                      .first(
                      currentDataPackField
                      .productData
                      .productInteraction == "addToCart"
                      )
                      .SKU}
  ```

Vanaf dat punt kunt u een ander pad in uw reis toevoegen voor wanneer het product niet in voorraad is en meldingen verzenden met een serviceaanbieding. Vorm dienovereenkomstig berichten en gebruik verpersoonlijkingsgegevens om het berichtdoel te verbeteren.

## Voorbeelden van tekenreeksbewerkingen met de geavanceerde expressie-editor

**In voorwaarden**

Met deze voorwaarde worden alleen de geofence-gebeurtenissen opgehaald die worden geactiveerd in &quot;Arlington&quot;:

```json
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

Uitleg: dit is een strikte tekenreeksvergelijking (hoofdlettergevoelig), gelijk aan een query in de eenvoudige modus die `equal to` gebruikt met `Is sensitive` checked.

Dezelfde query met `Is sensitive` uncheck genereert de volgende expressie in de geavanceerde modus:

```json
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**in acties**

De volgende uitdrukking staat u toe om identiteitskaart van CRM in een gebied van de actieverpersoonlijking te bepalen:

```json
substr(
   @{MobileAppLaunch
   ._myorganization
   .identification
   .crmid},
   1, 
   lastIndexOf(
     @{MobileAppLaunch
     ._myorganization
     .identification
     .crmid},
     '}'
   )
)
```

Uitleg: in dit voorbeeld worden `substr` - en `lastIndexOf` -functies gebruikt om accolades te verwijderen die de CRM-id omsluiten die is doorgegeven met een mobiele startgebeurtenis van de app.

Voor meer op hoe te om de geavanceerde uitdrukkingsredacteur te gebruiken, let op [ deze video ](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/create-a-journey.html?lang=nl-NL).
