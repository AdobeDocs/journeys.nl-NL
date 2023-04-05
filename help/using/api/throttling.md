---
product: adobe campaign
title: Werken met de Throttling-API
description: Meer informatie over de Throttling API
products: journeys
feature: Journeys
role: User
level: Intermediate
source-git-commit: fa493cf1e856378e4d79a6932c30cebf5e11e028
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 1%

---

# Werken met de Throttling-API

De Throttling API helpt u om uw throttling configuraties tot stand te brengen, te vormen en te controleren.

>[!IMPORTANT]
>
>Er is momenteel slechts één configuratie toegestaan per organisatie. Er moet een configuratie worden gedefinieerd in een productiesandbox (opgegeven via de naam x-sandbox in de koppen).
>
>Een configuratie wordt toegepast op organisatieniveau.
>
>Wanneer de limiet die is ingesteld in de API is bereikt, worden nog meer gebeurtenissen in de wachtrij geplaatst voor maximaal 6 uur. Deze waarde kan niet worden gewijzigd.

## Beschrijving van de Throttende API {#description}

| Methode | Pad | Beschrijving |
|---|---|---|
| [!DNL POST] | list/throttlingConfigs | Krijg een lijst van de throttling configuraties |
| [!DNL POST] | /throttlingConfigs | Een configuratie voor vertragen maken |
| [!DNL POST] | /throttlingConfigs/`{uid}`/implementatie | Implementeer een configuratie voor het vertragen |
| [!DNL POST] | /throttlingConfigs/`{uid}`/uninstall | Implementatie van een vertragingsconfiguratie ongedaan maken |
| [!DNL POST] | /throttlingConfigs/`{uid}`/canDeploy | Controleren of een throttling-configuratie kan worden geïmplementeerd |
| [!DNL PUT] | /throttlingConfigs/`{uid}` | Een throttingconfiguratie bijwerken |
| [!DNL GET] | /throttlingConfigs/`{uid}` | Een configuratie voor vertragen ophalen |
| [!DNL DELETE] | /throttlingConfigs/`{uid}` | Een configuratie met vertraagde verwerking verwijderen |

## Throtting-configuratie {#configuration}

Hier is de structuur van een throttling configuratie. **name** en **beschrijving** kenmerken zijn optioneel.

```
{
    "name": "<given name - free text>",
    "description": "<given description - free text>"
    "urlPattern": "<endpoint URL - wildcards are allowed>",
    "methods": [ "<HTTP method such as GET, POST, PUT>" ],
    "maxThroughput": <max call throughput>
}
```

Voorbeeld:

```
{
  "name": "throttling-config-external",
  "description": "example of throttling config for an external endpoint",
  "urlPattern": "https://api.example.org/data/2.5/*",
  "methods": ["POST", "PUT"],
  "maxThroughput": 4000
}
```

## Fouten

Wanneer het creëren van of het bijwerken van een configuratie, bevestigt het proces de bepaalde configuratie en keert de bevestigingsstatus terug die door zijn Unieke identiteitskaart wordt geïdentificeerd, of:

```
"ok" or "error"
```

>[!IMPORTANT]
>
>De kenmerken **maxThroughput**, **urlPattern** en **methoden** zijn verplicht.
>
>**maxThroughput** waarde moet tussen 200 en 5000 liggen.

Wanneer het creëren van, het schrappen van of het opstellen van throttling configuratie, kunnen de volgende fouten voorkomen:

* **ERR_THROTTLING_CONFIG_100**: throttling config: `<mandatory attribute>` vereist
* **ERR_THROTTLING_CONFIG_101**: throttling config: maxThroughput is vereist en moet groter zijn dan of gelijk zijn aan 200 en kleiner dan of gelijk aan 5000
* **ERR_THROTTLING_CONFIG_104**: throttling config: onjuist geformuleerd url-patroon
* **ERR_THROTTLING_CONFIG_105**: throttling config: jokertekens niet toegestaan in het hostgedeelte van het url-patroon
* **ERR_THROTTLING_CONFIG_106**: throttling config: ongeldige payload
* **THROTTLING_CONFIG_DELETE_FORBIDDEN_ERROR: 1456**, &quot;Kan geen opgesteld throttling config schrappen. Implementatie ongedaan maken voordat deze wordt verwijderd&quot;
* **THROTTLING_CONFIG_DELETE_ERROR: 1457**, &quot;Kan vertraging config niet verwijderen: onverwachte fout&quot;
* **THROTTLING_CONFIG_DEPLOY_ERROR: 1458**, &quot;Kan geen throttling config opstellen: onverwachte fout&quot;
* **THROTTLING_CONFIG_UNDEPLOY_ERROR: 1459**, &quot;Kan throttling config niet ongedaan maken: onverwachte fout&quot;
* **THROTTLING_CONFIG_GET_ERROR: 1460**, &quot;Kan vertragingsconfig niet krijgen: onverwachte fout&quot;
* **THROTTLING_CONFIG_UPDATE_NOT_ACTIVE_ERROR: 1461**, &quot;Kan vertraging config niet bijwerken: runtimeversie is niet actief.&quot;
* **THROTTLING_CONFIG_UPDATE_ERROR: 1462**, &quot;Kan vertraging config niet bijwerken: onverwachte fout&quot;
* **THROTTLING_CONFIG_NON_PROD_SANDBOX_ERROR: 1463**, &quot;Bewerking niet toegestaan op throttling config: niet-prod sandbox&quot;
* **THROTTLING_CONFIG_CREATE_ERROR: 1464**, &quot;Kan geen throttling config tot stand brengen: onverwachte fout&quot;
* **THROTTLING_CONFIG_CREATE_LIMIT_ERROR: 1465**, &quot;Kan geen throttling config tot stand brengen: slechts één config toegestaan per org&quot;
* **THROTTLING_CONFIG_ALREADY_DEPLOYED_ERROR: 1466**, &quot;Kan geen throttling config opstellen: reeds geïmplementeerd&quot;
* **THROTTLING_CONFIG_NOT_FOUND_ERROR: 1467**, &quot;throttling config not found&quot;
* **THROTTLING_CONFIG_NOT_DEPLOYED_ERROR: 1468**, &quot;Kan throttling config niet ongedaan maken: nog niet geïmplementeerd&quot;

**Voorbeelden van fouten**

Bij het maken van een config in een niet-prod-sandbox:

```
{
    "status": 400,
    "error": "{\"code\":1463,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Operation not allowed on throttling config: non prod sandbox\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:384\",\"schema\":\"throttlingConfigs$ui-tests\"}",
    "requestId": "5sgnAYXs8mpswwjAFEIaAU2faQYbtyHc"
}
```

Indien het opgegeven vakje niet bestaat:

```
{
    "status": 500,
    "error": "{\"code\":4000,\"family\":\"INTERNAL_ERROR\",\"message\":\"INTERNAL ERROR\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.common.exceptions.ApiErrorException:43\"}",
    "requestId": "04ZJ4e5ki4bYs3lfO17a7hovRGewjvdK"
}
```

Wanneer het proberen om een andere config te creëren:

```
{
    "status": 400,
    "error": "{\"code\":1465,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Can't create throttling config: only one config allowed per org\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:108\",\"schema\":\"throttlingConfigs$prod\"}",
    "requestId": "A7ezT8JhOQT4WIAf1Fv7K2wCDA8281qM"
}
```

## Gebruiksscenario&#39;s {#uc}

Om u in uw test en configuratie te helpen, is een inzameling van Postman beschikbaar [hier](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Throttling-API_postman-collection.json).

Deze Postman-verzameling is ingesteld om de Postman Variable-collectie te delen die is gegenereerd via __[Integraties van Adobe I/O Console](https://console.adobe.io/integrations) > Uitproberen > Downloaden voor Postman__, waarmee een Postman Environment-bestand met de geselecteerde integratiewaarden wordt gegenereerd.

Nadat u het bestand hebt gedownload en geüpload naar Postman, moet u drie variabelen toevoegen: `{JO_HOST}`,`{BASE_PATH}` en `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] Gateway-URL
* `{BASE_PATH}` : ingangspunt voor de API. De waarde is &#39;/authoring&#39;
* `{SANDBOX_NAME}` : de koptekst **x-sandbox-name** (bijvoorbeeld &#39;prod&#39;) die overeenkomt met de naam van de sandbox waarin de API-bewerkingen worden uitgevoerd. Zie de [sandboxen, overzicht](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html) voor meer informatie .

In de volgende sectie vindt u de lijst met gerangschikte aanroepen van de Rest-API om de use-case uit te voeren.

Gebruiksscenario n°1: **Het creëren en de plaatsing van een nieuwe throttling configuratie**

1. list
1. maken
1. canimplementeren
1. inzetten

Gebruiksscenario n°2: **Update en stel een throttling configuratie op nog niet opgesteld**

1. list
1. get
1. update
1. canimplementeren
1. inzetten

Gebruiksscenario n°3: **Implementeer en verwijder een geïmplementeerde throttingconfiguratie**

1. list
1. desimplementatie
1. delete

Gebruiksscenario n°4: **Een geïmplementeerde vertragingsconfiguratie verwijderen**

In slechts één API vraag, kunt u de configuratie met het gebruik van de forceDelete parameter ongedaan maken en schrappen.

1. list
1. delete, met forceDelete-parameter

Gebruiksscenario n°5: **Een reeds geïmplementeerde configuratie voor vertragen bijwerken**

>[!NOTE]
>
>Het is niet vereist om de configuratie ongedaan te maken alvorens bij te werken

1. list
1. get
1. update

## Levenscyclus van configuratie op runtimeniveau {#config}

Wanneer een configuratie wordt gedecodeerd, wordt het duidelijk als inactief op runtime niveau en hangende gebeurtenissen worden verwerkt tijdens 24 uur. Deze wordt vervolgens verwijderd in de runtimeservice.

Nadat een configuratie is gedesgroepeerd, is het mogelijk om de configuratie bij te werken en opnieuw op te stellen. Hierdoor wordt een nieuwe runtimeconfiguratie gemaakt die in overweging zal worden genomen bij de uitvoering van de volgende acties.

Bij het bijwerken van een configuratie die al is geïmplementeerd, wordt onmiddellijk rekening gehouden met de nieuwe waarden. De onderliggende systeembronnen worden automatisch aangepast. Dit is optimaal in vergelijking met undeploy dan herstelt de configuratie.

## Voorbeelden van reacties {#responses}

**Maken - POST**

```
{
    "canDeploy": {
        "validationStatus": "ok"
    },
    "createdElement": {
        "name": "throttling-config-external",
        "description": "example of throttling config for an external endpoint",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "PUT",
            "POST"
        ],
        "maxThroughput": 4000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T10:48:16.099647Z"
        },
        "state": "created",
        "authoringFormatVersion": "1.0"
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "created"
}
```

**Bijwerken - PUT**

```
{
    "updatedElement": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "updated",
    "canDeploy": {
        "validationStatus": "ok"
    }
}
```

**Lezen (na update) - GET**

```
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    }
}
```

**Lezen (na implementatie) - GET**

```
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "authoringFormatVersion": "1.0",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "version": "1.0",
        "state": "deployed",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z",
            "lastDeployedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastDeployedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastDeployedAt": "2023-03-22T11:46:07.532648Z"
        },
        "hasBeenDeployed": true
    }
}
```
