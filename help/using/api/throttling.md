---
product: adobe campaign
title: Werken met de beperkings-API
description: Meer informatie over de beperkings-API
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 76afe397-3e18-4e01-9b0b-c21705927ce2
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 91%

---

# Werken met de beperkings-API


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


De Throttling API helpt u om uw throttling configuraties tot stand te brengen, te vormen en te controleren om het aantal gebeurtenissen te beperken die per seconde worden verzonden.

>[!IMPORTANT]
>
>Momenteel is slechts één configuratie per organisatie toegestaan. Een configuratie moet worden gedefinieerd voor een productiesandbox (gegeven via x-sandbox-name in de headers).
>
>Een configuratie wordt toegepast op organisatieniveau.
>
>Wanneer de in de API ingestelde limiet is bereikt, worden verdere gebeurtenissen maximaal 6 uur in de wachtrij geplaatst. Deze waarde kan niet worden gewijzigd.

## Beschrijving van beperkings-API {#description}

| Methode | Pad | Beschrijving |
|---|---|---|
| [!DNL POST] | list/throttlingConfigs | Ontvang een lijst van de beperkingsconfiguraties |
| [!DNL POST] | /throttlingConfigs | Een beperkingsconfiguratie maken |
| [!DNL POST] | /throttlingConfigs/`{uid}`/deploy | Beperkingsconfiguratie implementeren |
| [!DNL POST] | /throttlingConfigs/`{uid}`/undeploy | Implementatie van een beperkingsconfiguratie ongedaan maken |
| [!DNL POST] | /throttlingConfigs/`{uid}`/canDeploy | Controleren of een beperkingsconfiguratie kan worden geïmplementeerd of niet |
| [!DNL PUT] | /throttlingConfigs/`{uid}` | Een beperkingsconfiguratie bijwerken |
| [!DNL GET] | /throttlingConfigs/`{uid}` | Een beperkingsconfiguratie ophalen |
| [!DNL DELETE] | /throttlingConfigs/`{uid}` | Een beperkingsconfiguratie verwijderen |

## Beperkingsconfiguratie {#configuration}

Dit is de structuur van een beperkingsconfiguratie. De attributen **name** en **description** zijn optioneel.

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

Bij het maken of bijwerken van een configuratie valideert het proces de gegeven configuratie en retourneert de validatiestatus die wordt geïdentificeerd door de unieke ID, ofwel:

```
"ok" or "error"
```

>[!IMPORTANT]
>
>De attributen **maxThroughput**, **urlPattern** en **methods** zijn verplicht.
>
>**maxThroughput**-waarde moet tussen 200 en 5000 liggen.

Bij het maken, verwijderen of implementeren van een beperkingsconfiguratie kunnen de volgende fouten optreden:

* **ERR_THROTTLING_CONFIG_100**: beperkingsconfig: `<mandatory attribute>` vereist
* **ERR_THROTTLING_CONFIG_101**: beperkingsconfig: maxThroughput is vereist en moet groter zijn dan of gelijk aan 200 en kleiner dan of gelijk aan 5000
* **ERR_THROTTLING_CONFIG_104**: beperkingsconfig: niet-welgevormd URL-patroon
* **ERR_THROTTLING_CONFIG_105**: beperkingsconfig: jokers zijn niet toegestaan in het hostgedeelte van het URL-patroon
* **ERR_THROTTLING_CONFIG_106**: beperkingsconfig: ongeldige payload
* **THROTTLING_CONFIG_DELETE_FORBIDDEN_ERROR: 1456**, &quot;Kan een geïmplementeerde beperkingsconfiguratie niet verwijderen. Implementatie ongedaan maken voordat deze wordt verwijderd&quot;
* **THROTTLING_CONFIG_DELETE_ERROR: 1457**, &quot;Kan beperkingsconfiguratie niet verwijderen: onverwachte fout&quot;
* **THROTTLING_CONFIG_DEPLOY_ERROR: 1458**, &quot;Kan beperkingsconfiguratie niet implementeren: onverwachte fout &quot;
* **THROTTLING_CONFIG_UNDEPLOY_ERROR: 1459**, &quot;Kan beperkingsconfig niet ongedaan maken: onverwachte fout&quot;
* **THROTTLING_CONFIG_GET_ERROR: 1460**, &quot;Kan geen beperkingsconfiguratie krijgen: onverwachte fout&quot;
* **THROTTLING_CONFIG_UPDATE_NOT_ACTIVE_ERROR: 1461**, &quot;Kan beperkingsconfiguratie niet bijwerken: runtime versie is niet actief&quot;
* **THROTTLING_CONFIG_UPDATE_ERROR: 1462**, &quot;Kan beperkingsconfiguratie niet bijwerken: onverwachte fout&quot;
* **THROTTLING_CONFIG_NON_PROD_SANDBOX_ERROR: 1463**, &quot;Operatie niet toegestaan op beperkingsconfig: non prod sandbox&quot;
* **THROTTLING_CONFIG_CREATE_ERROR: 1464**, &quot;Kan geen beperkingsconfiguratie maken: onverwachte fout&quot;
* **THROTTLING_CONFIG_CREATE_LIMIT_ERROR: 1465**, &quot;Kan geen beperkingsconfiguratie maken: slechts één configuratie toegestaan per org&quot;
* **THROTTLING_CONFIG_ALREADY_DEPLOYED_ERROR: 1466**, &quot;Kan beperkingsconfiguratie niet implementeren: reeds geïmplementeerd&quot;
* **THROTTLING_CONFIG_NOT_FOUND_ERROR: 1467**, &quot;beperkingsconfig niet gevonden&quot;
* **THROTTLING_CONFIG_NOT_DEPLOYED_ERROR: 1468**, &quot;Kan beperkingsconfiguratie niet verwijderen: nog niet geïmplementeerd&quot;

**Voorbeelden van fouten**

Als u probeert een configuratie te maken op een non-prod sandbox:

```
{
    "status": 400,
    "error": "{\"code\":1463,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Operation not allowed on throttling config: non prod sandbox\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:384\",\"schema\":\"throttlingConfigs$ui-tests\"}",
    "requestId": "5sgnAYXs8mpswwjAFEIaAU2faQYbtyHc"
}
```

Als deze sandbox niet bestaat:

```
{
    "status": 500,
    "error": "{\"code\":4000,\"family\":\"INTERNAL_ERROR\",\"message\":\"INTERNAL ERROR\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.common.exceptions.ApiErrorException:43\"}",
    "requestId": "04ZJ4e5ki4bYs3lfO17a7hovRGewjvdK"
}
```

Wanneer u probeert een andere configuratie te maken:

```
{
    "status": 400,
    "error": "{\"code\":1465,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Can't create throttling config: only one config allowed per org\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:108\",\"schema\":\"throttlingConfigs$prod\"}",
    "requestId": "A7ezT8JhOQT4WIAf1Fv7K2wCDA8281qM"
}
```

## Gebruiksscenario&#39;s {#uc}

Voor hulp bij het testen en configureren is [hier](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Throttling-API_postman-collection.json) een Postman-verzameling beschikbaar.

Deze Postman-verzameling is opgezet om de Postman Variabele verzameling te delen die is gegenereerd via __[Adobe I/O Console-integraties](https://console.adobe.io/integrations) > Uitproberen > Downloaden voor Postman__, wat een Postman-omgevingsbestand genereert met de geselecteerde integratiewaarden.

Eenmaal gedownload en geüpload naar Postman moet u drie variabelen toevoegen: `{JO_HOST}`,`{BASE_PATH}` en `{SANDBOX_NAME}`.
* `{JO_HOST}`: [!DNL Journey Orchestration] Gateway-URL
* `{BASE_PATH}`: ingangspunt voor de API. De waarde is &#39;/authoring&#39;
* `{SANDBOX_NAME}`: de header **x-sandbox-name** (bijvoorbeeld &#39;prod&#39;) die overeenkomt met de sandboxnaam waar de API-operaties zullen plaatsvinden. Zie het [sandboxoverzicht](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=nl) voor meer informatie.

In het volgende gedeelte vindt u de geordende lijst van Rest-API-aanroepen om het gebruiksscenario uit te voeren.

Gebruiksscenario nr. 1: **Nieuwe beperkingsconfiguratie maken en implementeren**

1. list
1. create
1. candeploy
1. deploy

Gebruiksscenario nr. 2: **Een beperkingsconfiguratie bijwerken en implementeren die nog niet is geïmplementeerd**

1. list
1. get
1. update
1. candeploy
1. deploy

Gebruiksscenario nr. 3: **Een geïmplementeerde beperkingsconfiguratie deïmplementeren en verwijderen**

1. list
1. undeploy
1. delete

Gebruiksscenario nr. 4: **Een geïmplementeerde beperkingsconfiguratie verwijderen**

In slechts één API-oproep kunt u de configuratie deïmplementeren en verwijderen met behulp van de parameter forceDelete.

1. list
1. delete, met parameter forceDelete

Gebruiksscenario nr. 5: **Een geïmplementeerde beperkingsconfiguratie bijwerken**

>[!NOTE]
>
>Het is niet nodig om de configuratie te deïmplementeren alvorens bij te werken

1. list
1. get
1. update

## Configuratie levenscyclus op runtimeniveau {#config}

Wanneer een configuratie ge-deïmplementeerd is, wordt deze gemarkeerd als inactief op runtimeniveau en worden lopende gebeurtenissen gedurende 24 uur verwerkt. Deze wordt dan verwijderd in de runtimeservice.

Nadat een configuratie is ge-deïmplementeerd, kunt u de configuratie bijwerken en opnieuw implementeren. Daardoor wordt een nieuwe runtimeconfiguratie gemaakt die in aanmerking wordt genomen bij de toekomstige uitvoering van acties.

Bij het bijwerken van een geïmplementeerde configuratie wordt onmiddellijk rekening gehouden met de nieuwe waarden. De onderliggende systeembronnen worden automatisch aangepast. Dit is optimaal in vergelijking met het deïmplementeren en dan opnieuw implementeren van de configuratie.

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

**Update - PUT**

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
