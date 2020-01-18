---
title: Veldverwijzingen
description: Meer informatie over veldverwijzingen in geavanceerde expressies
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8be9cd1803ab2f7093934424c36fcd7407a4a20a

---



# Veldverwijzingen {#concept_fkj_ll5_dgb}

Een veldverwijzing kan aan een gebeurtenis of een gebiedsgroep worden vastgemaakt. De enige betekenisvolle informatie is de naam van het veld en het pad ervan.

Als u speciale tekens in een veld gebruikt, moet u dubbele aanhalingstekens of eenvoudige aanhalingstekens gebruiken. Hier volgen de gevallen waarin noteringen nodig zijn:

* het veld begint met numerieke tekens
* het veld begint met het &quot;-&quot; teken
* het veld bevat iets anders dan: _a_-_z_, _A_-_Z_, _0____-9, _,_

Als uw veld bijvoorbeeld _3u_ is: _#{OpenWeather.weerData.rain.&#39;3h&#39;} > 0_

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
>Het veldtype en de standaardwaarde moeten hetzelfde zijn. Bijvoorbeeld @{LobbyBeacon.endUserIDs._experience.ease.id, defaultValue: {2} is ongeldig omdat de standaardwaarde een geheel getal is en de verwachte waarde een tekenreeks.

**Referentie van een veld binnen verzamelingen**

Er wordt verwezen naar de elementen die in verzamelingen zijn gedefinieerd met behulp van de specifieke functies all, first en last. Zie voor meer informatie [](../expression/collection-management-functions.md).

Voorbeeld:

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

**Verwijzing van een gebied dat in een kaart** wordt bepaald om een element in een kaart terug te winnen, gebruiken wij de ingangsfunctie met een bepaalde sleutel. Deze wordt bijvoorbeeld gebruikt wanneer de sleutel van een gebeurtenis wordt gedefinieerd op basis van de geselecteerde naamruimte. Zie De naamruimte selecteren. Zie voor meer informatie [](../event/selecting-the-namespace.md).

```
@{MyEvent.identityMap.entry('Email').first().id}
```

In deze expressie krijgen we de vermelding voor de E-mailsleutel van het veld IdentityMap van een gebeurtenis. Het item &quot;Email&quot; is een verzameling, waaruit we de &quot;id&quot; in het eerste element gebruiken met &quot;first()&quot;. Zie voor meer informatie [](../expression/collection-management-functions.md).

**Parameterwaarden van een gegevensbron (dynamische waarden van gegevensbron)**

Als u een veld selecteert uit een externe gegevensbron waarvoor een parameter moet worden aangeroepen, wordt rechts een nieuw tabblad weergegeven waarin u deze parameter kunt opgeven. Zie [](../expression/expressionadvanced.md).

Als u de parameters van de gegevensbron in de hoofdexpressie wilt opnemen voor complexere gebruiksgevallen, kunt u de waarden van deze parameters definiëren met behulp van de _trefwoordparams_. Een parameter kan elke geldige expressie zijn, zelfs van een andere gegevensbron die ook een andere parameter bevat.

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
