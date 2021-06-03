---
product: adobe campaign
title: Veldverwijzingen
description: Meer informatie over veldverwijzingen in geavanceerde expressies
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2f317306-9afd-4e9a-88b8-fc66102e1046
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 4%

---

# Veldverwijzingen {#concept_fkj_ll5_dgb}

Een veldverwijzing kan aan een gebeurtenis of een gebiedsgroep worden vastgemaakt. De enige betekenisvolle informatie is de naam van het veld en het pad ervan.

Als u speciale tekens in een veld gebruikt, moet u dubbele aanhalingstekens of eenvoudige aanhalingstekens gebruiken. Hier volgen de gevallen waarin noteringen nodig zijn:

* het veld begint met numerieke tekens
* het veld begint met het &quot;-&quot; teken
* het veld bevat iets anders dan: _a_-_z_, _A_-_Z_, _0_-_9_, _, _-_

Als uw veld bijvoorbeeld _3h_ is: _#{OpenWeather.windData.rain.&#39;3h&#39;} > 0_

```
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

In de expressie wordt naar gebeurtenisvelden verwezen met &quot;@&quot; en wordt naar gegevensbronvelden verwezen met &quot;#&quot;.

Een syntaxiskleur wordt gebruikt om (groene) gebeurtenisvelden visueel te onderscheiden van (blauwe) veldgroepen.

**Standaardwaarden voor veldverwijzingen**

Er kan een standaardwaarde aan een veldnaam worden gekoppeld. De syntaxis is als volgt:

```
// event field
@{<event name>.<XDM path to the field>, defaultValue: <default value expression>}
@{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: "example@adobe.com"}
// field group
#{<data source name>.<field group name>.<path to the field>, defaultValue: <default value expression>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address, defaultValue: "example@adobe.com"}
```

>[!NOTE]
>
>Het veldtype en de standaardwaarde moeten hetzelfde zijn. Bijvoorbeeld @{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue : 2} will be invalid because the default value is an integer whereas the expected value should be a string.

Voorbeelden:

```
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

**Referentie van een veld binnen verzamelingen**

Er wordt verwezen naar de elementen die in verzamelingen zijn gedefinieerd met behulp van de specifieke functies all, first en last. Raadpleeg [deze sectie](../expression/collection-management-functions.md) voor meer informatie.

Voorbeeld :

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

**Referentie van een veld dat is gedefinieerd in een kaart**

Om een element in een kaart terug te winnen, gebruiken wij de ingangsfunctie met een bepaalde sleutel. Deze wordt bijvoorbeeld gebruikt wanneer de sleutel van een gebeurtenis wordt gedefinieerd op basis van de geselecteerde naamruimte. Zie De naamruimte selecteren. Zie [deze pagina](../event/selecting-the-namespace.md) voor meer informatie.

```
@{MyEvent.identityMap.entry('Email').first().id}
```

In deze expressie krijgen we de vermelding voor de E-mailsleutel van het veld IdentityMap van een gebeurtenis. Het item &quot;Email&quot; is een verzameling, waaruit we de &quot;id&quot; in het eerste element gebruiken met &quot;first()&quot;. Zie [deze pagina](../expression/collection-management-functions.md) voor meer informatie.

**Parameterwaarden van een gegevensbron (dynamische waarden van gegevensbron)**

Als u een veld selecteert uit een externe gegevensbron waarvoor een parameter moet worden aangeroepen, wordt rechts een nieuw tabblad weergegeven waarin u deze parameter kunt opgeven. Zie [deze pagina](../expression/expressionadvanced.md).

Voor complexere gebruiksgevallen, als u de parameters van de gegevensbron in de belangrijkste uitdrukking wilt omvatten, kunt u hun waarden bepalen gebruikend het sleutelwoord _params_. Een parameter kan elke geldige expressie zijn, zelfs van een andere gegevensbron die ook een andere parameter bevat.

>[!NOTE]
>
>Wanneer u de parameterwaarden in de expressie definieert, verdwijnt de rechtertab.

Gebruik de volgende syntaxis:

```
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**: de exacte naam van de eerste parameter uit de gegevensbron.
* **`<params-1-value>`**: de waarde van de eerste parameter. Het kan elke geldige expressie zijn.

Voorbeeld:

```
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
