---
product: adobe campaign
solution: Journey Orchestration
title: De geavanceerde expressie-editor gebruiken
description: Geavanceerde expressies maken
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 2%

---


# Geavanceerde expressievoorbeelden

De Geavanceerde uitdrukkingsredacteur kan worden gebruikt om voorwaarden tot stand te brengen om u toe te staan om gebruikers in uw reizen te filtreren. Met deze voorwaarden kunt u zich richten op gebruikers op tijd, datum, locatie, duur of acties zoals het kopen of verlaten van winkelwagentjes, zodat ze tijdens de reis opnieuw op de doelgroep kunnen worden geplaatst.

>[!NOTE]
>
>Gebeurtenissen beginnen met @, gegevensbronnen met #.

## Voorwaarden voor ervaringsgebeurtenissen opbouwen

De geavanceerde uitdrukkingsredacteur is verplicht om vragen op tijdreeksen zoals een lijst van aankopen of voorbij klikken op berichten uit te voeren. Dergelijke vragen kunnen niet worden uitgevoerd gebruikend de eenvoudige redacteur.

De ervaringsgebeurtenissen worden uit de Adobe Experience Platform opgehaald als een verzameling in omgekeerde chronologische volgorde, vandaar:

* De eerste functie retourneert de meest recente gebeurtenis
* last function retourneert de oudste functie.

Bijvoorbeeld, laten wij zeggen u klanten met een kartontroeping in de laatste 7 dagen wilt richten om een bericht te verzenden wanneer de klant dichtbij een opslag, met een aanbieding op punten komt die hij wilde die in opslag zijn.

**U moet de volgende voorwaarden bouwen:**

Ten eerste doelklanten die in de online winkel hebben gebladerd maar de bestelling de laatste 7 dagen niet hebben voltooid.

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**Deze expressie zoekt naar alle gebeurtenissen voor deze gebruiker die in de laatste 7 dagen zijn opgegeven:**

Vervolgens worden alle addtocart-gebeurtenissen geselecteerd die niet zijn omgezet in een completePurchase.

>[!NOTE]
>
>Als u snel velden in de expressie wilt invoegen, dubbelklikt u op het veld in het linkerdeelvenster van de editor.

De opgegeven tijdstempel fungeert als datumtijdwaarde en de tweede als aantal dagen.

```
        In( “addToCart”, #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
        And
        Not(In( “completePurchase”, #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
```

Deze expressie retourneert een Booleaanse waarde.

**Laten we nu een expressie maken die controleert of het product in voorraad is**

* In Inventory, zoekt deze uitdrukking naar kwantitatief gebied van een product en specificeert dat het groter zou moeten zijn dan 0.

`#{Inventory.fieldgroup3.quantity} > 0`

* Rechts, worden de noodzakelijke waarden gespecificeerd, hier, moeten wij de plaats van de opslag terugwinnen, die van de plaats van de gebeurtenis &quot;ArriveLumaStudio&quot;in kaart wordt gebracht:

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* En specificeer SKU, gebruikend de functie `first` om de meest recente &quot;addToCart&quot;interactie terug te winnen:

   ```
       #{ExperiencePlatformDataSource
                       .ExperienceEventFieldGroup
                       .experienceevent
                       .first(
                       currentDataPackField
                       .productData
                       .productInteraction == “addToCart”
                       )
                       .SKU}
   ```

Vanaf dat punt kunt u een ander pad in uw reis toevoegen voor wanneer het product niet in voorraad is en meldingen verzenden met een serviceaanbieding. Vorm dienovereenkomstig berichten en gebruik verpersoonlijkingsgegevens om het berichtdoel te verbeteren.

## Voorbeelden van tekenreeksbewerkingen met de geavanceerde expressie-editor

**In omstandigheden**

Met deze voorwaarde worden alleen de geofence-gebeurtenissen opgehaald die worden geactiveerd in &quot;Arlington&quot;:

```
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

Uitleg: Dit is een strikte tekenreeksvergelijking (hoofdlettergevoelig), gelijk aan een query in de eenvoudige modus die `equal to` gebruikt terwijl `Is sensitive` ingeschakeld is.

Dezelfde query met `Is sensitive` uitgeschakeld genereert de volgende expressie in de geavanceerde modus:

```
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**In handelingen**

De volgende uitdrukking staat u toe om identiteitskaart van CRM in een gebied van de actieverpersoonlijking te bepalen:

```
    substr(@{MobileAppLaunch
            ._myorganization
            .identification
            .crmid}, 1, 
            lastIndexOf(@{MobileAppLaunch
                        ._myorganization
                        .identification
                        .crmid}
                         }
                         ))
```

Uitleg: In dit voorbeeld worden `substr`- en `lastIndexOf`-functies gebruikt om accolades te verwijderen die de CRM-id omsluiten die is doorgegeven met een startgebeurtenis voor een mobiele app.

Voor meer op hoe te om de geavanceerde uitdrukkingsredacteur te gebruiken, bekijk [deze video](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/create-a-journey.html).
