---
title: De geavanceerde expressie-editor gebruiken
description: Leer hoe u geavanceerde expressies kunt maken
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: benzaama
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%

---


# De geavanceerde expressie-editor gebruiken

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

    &quot;
    In( &quot;addToCart&quot;, #{ExperiencePlatformDataSource
    .ExperienceEventFieldGroup
    .ExperienceEvent
    .all(
    inLastDays(currentDataPackField.timestamp, 7 ))
    .productData
    .productInteraction})
    
    AndNot(In( &quot;completePurchase&quot;, #{ExperienceNot} PlatformDataSource
    .ExperienceEventFieldGroup
    
    
    
    
    
    
    .experienceEvent.all(inLastDays(currentDataPackField.timestamp, 7)).productData.productInteraction})&quot;

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

    &quot;
    @{GeofenceEntry
    .placeContext
    .POIinteraction
    .POIDetail
    .name} == &quot;Arlington&quot;
    &quot;

Uitleg: Dit is een strikte tekenreeksvergelijking (hoofdlettergevoelig), gelijk aan een query in de eenvoudige modus die wordt gebruikt `equal to` met `Is sensitive` ingeschakeld.

Dezelfde query met `Is sensitive` uncheck genereert de volgende expressie in de geavanceerde modus:

    &quot;
    equalIgnoreCase(@{GeofenceEntry
    .placeContext
    .POIinteraction
    .POIDetail
    .name}, &quot;Arlington&quot;)
    
    &quot;

**In handelingen**

De volgende uitdrukking staat u toe om identiteitskaart van CRM in een gebied van de actieverpersoonlijking te bepalen:

    &quot;
    substr(@{MobileAppLaunch
    ._myorganisation
    .identification
    .crmid}, 1,
    lastIndexOf(@{MobileAppLaunch
    ._myorganisation
    .identification
    .crmid}
    )
    
    
    &quot;

Uitleg: In dit voorbeeld worden accolades `substr` en `lastIndexOf` functies verwijderd die de CRM-id omsluiten die is doorgegeven met een gebeurtenis voor het starten van een mobiele app.

Bekijk [deze video](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/create-a-journey.html)voor meer informatie over het gebruik van de geavanceerde expressieeditor.
