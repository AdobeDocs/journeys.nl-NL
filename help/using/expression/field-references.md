---
product: adobe campaign
title: Veldverwijzingen
description: Meer informatie over veldverwijzingen in geavanceerde expressies
feature: Journeys
role: Developer
level: Experienced
exl-id: 2f317306-9afd-4e9a-88b8-fc66102e1046
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 10%

---

# Veldverwijzingen {#concept_fkj_ll5_dgb}


>[!CAUTION]
>
>**Op zoek naar Adobe Journey Optimizer**? Klik [hier](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar verouderde materialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over toegang tot Journey Orchestration of Journey Optimizer._


Een veldverwijzing kan aan een gebeurtenis of een gebiedsgroep worden vastgemaakt. De enige relevante informatie is de naam van het veld en het pad ervan.

Als u speciale tekens in een veld gebruikt, moet u dubbele aanhalingstekens of eenvoudige aanhalingstekens gebruiken. Hier volgen de gevallen waarin noteringen nodig zijn:

* het veld begint met numerieke tekens
* het veld begint met het &quot;-&quot; teken
* het gebied bevat om het even wat buiten: _a_ - _z_, _A_ - _Z_, _0_ - _9_, _, _-_

Bijvoorbeeld als uw gebied _3h_ is: _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

```json
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

In de expressie wordt naar gebeurtenisvelden verwezen met &quot;@&quot; en wordt naar gegevensbronvelden verwezen met &quot;#&quot;.

Een syntaxiskleur wordt gebruikt om (groene) gebeurtenisvelden visueel te onderscheiden van (blauwe) veldgroepen.

## Standaardwaarden voor veldverwijzingen {#default-value}

Er kan een standaardwaarde aan een veldnaam worden gekoppeld. De syntaxis is als volgt:

```json
// event field
@{<event name>.<XDM path to the field>, defaultValue: <default value expression>}
@{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: "example@adobe.com"}
// field group
#{<data source name>.<field group name>.<path to the field>, defaultValue: <default value expression>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address, defaultValue: "example@adobe.com"}
```

>[!NOTE]
>
>Het veldtype en de standaardwaarde moeten hetzelfde zijn. Bijvoorbeeld @{LobbyBeacon.endUserIDs._experience.ease.id, defaultValue : 2} is ongeldig omdat de standaardwaarde een geheel getal is, terwijl de verwachte waarde een tekenreeks moet zijn.

Voorbeelden:

```json
// for an event 'OrderEvent' having the following payload:
{
    "orderId": "12345"
}
 
expression example:
- @{OrderEvent.orderId}                                    -> "12345"
- @{OrderEvent.producdId, defaultValue : "not specified" } -> "not specified" // default value, productId is not a field present in the payload
- @{OrderEvent.productId}                                  -> null
 
 
// for an entity 'Profile' on datasource 'ACP' having fields person/lastName, with fetched data such as:
{
    "person": {
        "lastName":"Snow"
    },
    "emails": [
        { "email":"john.snow@winterfell.westeros" },
        { "email":"snow@thewall.westeros" }
    ]
}
 
expression examples:
- #{ACP.Profile.person.lastName}                 -> "Snow"
- #{ACP.Profile.emails.at(1).email}              -> "snow@thewall.westeros"
- #{ACP.Profile.person.age, defaultValue : -1}   -> -1 // default value, age is not a field present in the payload
- #{ACP.Profile.person.age}                      -> null
```

U kunt elke gewenste expressie toevoegen als standaardwaarde. De enige beperking is dat de expressie het verwachte gegevenstype moet retourneren. Wanneer u een functie gebruikt, moet u de functie inkapselen met ().

```
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.any.time, defaultValue : (now())} 
== date("2022-02-10T00:00:00Z")
```

## Verwijzing naar een veld in verzamelingen

Er wordt verwezen naar de elementen die in verzamelingen zijn gedefinieerd, met behulp van de specifieke functies `all` , `first` en `last` . Raadpleeg [deze sectie](../expression/collection-management-functions.md) voor meer informatie.

Voorbeeld:

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

## Verwijzing naar een veld dat is gedefinieerd in een kaart

### `entry` functie

Om een element in een kaart terug te winnen, gebruiken wij de ingangsfunctie met een bepaalde sleutel. Deze wordt bijvoorbeeld gebruikt wanneer de sleutel van een gebeurtenis wordt gedefinieerd op basis van de geselecteerde naamruimte. Zie De naamruimte selecteren. Voor meer informatie, zie [ deze pagina ](../event/selecting-the-namespace.md).

```json
@{MyEvent.identityMap.entry('Email').first().id}
```

In deze expressie krijgen we de vermelding voor de E-mailsleutel van het veld IdentityMap van een gebeurtenis. Het item &#39;Email&#39; is een verzameling, waaruit we de &#39;id&#39; in het eerste element gebruiken met &#39;first()&#39;. Voor meer informatie, zie [ deze pagina ](../expression/collection-management-functions.md).

### `firstEntryKey` functie

Gebruik de functie `firstEntryKey` om de eerste entry-toets van een kaart op te halen.

In dit voorbeeld wordt getoond hoe u het eerste e-mailadres van de abonnees van een specifieke lijst ophaalt:

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-email').subscribers.firstEntryKey()}
```

In dit voorbeeld heeft de abonnementenlijst de naam `daily-email` . E-mailadressen worden gedefinieerd als sleutels in de `subscribers` -kaart, die is gekoppeld aan de abonnementenlijstkaart.

### `keys` functie

Gebruik de functie `keys` om alle toetsen van een kaart op te halen.

In dit voorbeeld wordt getoond hoe u voor een specifiek profiel alle e-mailadressen kunt ophalen die zijn gekoppeld aan de abonnees van een specifieke lijst:

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-mail').subscribers.keys()
```

## Parameterwaarden van een gegevensbron (dynamische waarden van gegevensbron)

Als u een veld selecteert uit een externe gegevensbron waarvoor een parameter moet worden aangeroepen, wordt rechts een nieuw tabblad weergegeven waarin u deze parameter kunt opgeven. Zie [deze pagina](../expression/expressionadvanced.md).

Voor complexere gebruiksgevallen, als u de parameters van de gegevensbron in de belangrijkste uitdrukking wilt omvatten, kunt u hun waarden bepalen gebruikend de sleutelwoord _params_. Een parameter kan elke geldige expressie zijn, zelfs van een andere gegevensbron die ook een andere parameter bevat.

>[!NOTE]
>
>Wanneer u de parameterwaarden in de expressie definieert, verdwijnt de rechtertab.

Gebruik de volgende syntaxis:

```json
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**: de exacte naam van de eerste parameter uit de gegevensbron.
* **`<params-1-value>`** : de waarde van de eerste parameter. Het kan elke geldige expressie zijn.

Voorbeeld:

```json
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
