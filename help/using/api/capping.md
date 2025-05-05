---
product: adobe campaign
title: Beschrijving van API voor uitlijnen
description: Meer informatie over de API voor aftiteling.
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 27%

---


# Werken met de API voor uitsnijden {#work}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


Met de API voor uitsnijden kunt u uw configuraties voor uitlijnen maken, configureren en controleren.

## Beschrijving van API voor uitlijnen

| Methode | Pad | Beschrijving |
|---|---|---|
| [!DNL POST] | list/endConfigs | Krijg een lijst van de eindpunt die configuraties begrenzen |
| [!DNL POST] | /endConfigs | Creeer een eindpunt het bedekken configuratie |
| [!DNL POST] | /endConfigs/`{uid}`/opstellen | Implementeer een configuratie voor het afdekken van eindpunten |
| [!DNL POST] | /endConfigs/`{uid}`/undeploy | Maak een eindpunt onbruikbaar dat configuratie begrenst |
| [!DNL POST] | /endConfigs/`{uid}`/canDeploy | Controle als een eindpunt het begrenzen configuratie kan worden opgesteld of niet |
| [!DNL PUT] | /endConfigs/`{uid}` | Een configuratie voor het afdekken van eindpunten bijwerken |
| [!DNL GET] | /endConfigs/`{uid}` | Retrireer een eindpunt dat configuratie begrenst |
| [!DNL DELETE] | /endConfigs/`{uid}` | Een configuratie voor een uitlijningselement verwijderen |

Wanneer een configuratie wordt gecreeerd of bijgewerkt, automatisch wordt een controle uitgevoerd om de syntaxis en de integriteit van de lading te waarborgen.
Als sommige problemen voorkomen, keert de verrichting waarschuwing of fouten terug om u te helpen de configuratie verbeteren.

## Eindpuntconfiguratie

Hier is de basisstructuur van een eindpuntconfiguratie:

```
{
    "url": "<endpoint URL>",  //wildcards are allowed in the endpoint URL
    "methods": [ "<HTTP method such as GET, POST, >, ...],
    "services": {
        "<service name>": { . //must be "action" or "dataSource" 
            "maxHttpConnections": <max connections count to the endpoint (optional)>
            "rating": {          
                "maxCallsCount": <max calls to be performed in the period defined by period/timeUnit>,
                "periodInMs": <integer value greater than 0>
            }
        },
        ...
    }
}
```

>[!IMPORTANT]
>
>De **maxHttpConnections** parameter is facultatief. Zo kunt u het aantal verbindingen beperken dat Journey Optimizer opent voor het externe systeem.
>
>De maximale waarde die kan worden ingesteld, is 400. Als niets wordt gespecificeerd, dan kan het systeem tot veelvoudige duizenden verbindingen afhankelijk van het dynamische schrapen van het systeem openen.

### Voorbeeld:

```
`{
  "url": "https://api.example.org/data/2.5/*",
  "methods": [
    "GET"
  ],
  "services": {
    "dataSource": {
      "maxHttpConnections": 50,
      "rating": {
        "maxCallsCount": 500,
        "periodInMs": 1000
      }
    }
  },
  "orgId": "<IMS Org Id>"
}
```

## Waarschuwing en fouten

Wanneer a **canDeploy** methode wordt geroepen, bevestigt het proces de configuratie en keert de bevestigingsstatus terug die door zijn Unieke identiteitskaart wordt geïdentificeerd, of:

```
"ok" or "error"
```

De mogelijke fouten zijn:

* **ERR_ENDPOINTCONFIG_100**: het in kaart brengen van config: ontbrekende of ongeldige URL
* **ERR_ENDPOINTCONFIG_101**: het in kaart brengen van config: misvormde url
* **ERR_ENDPOINTCONFIG_102**: het in kaart brengen config: misvormde url: vervangingsklank in url niet toegestaan in gastheer:haven
* **ERR_ENDPOINTCONFIG_103**: het in kaart brengen van config: ontbrekende methodes van HTTP
* **ERR_ENDPOINTCONFIG_104**: het in kaart brengen van config: geen bepaalde vraagclassificatie
* **ERR_ENDPOINTCONFIG_107**: het in kaart brengen van config: ongeldige maximum vraagtelling (maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**: het maximum config: ongeldige maximum vraagtelling (periodInMS)
* **ERR_ENDPOINTCONFIG_111**: het in kaart brengen van config: kan geen eindpunt config tot stand brengen: ongeldige lading
* **ERR_ENDPOINTCONFIG_112**: het begrenzen config: kan geen eindpunt config tot stand brengen: het verwachten van een nuttige lading JSON
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: ongeldige de dienstnaam `<!--<given value>-->`: moet &quot;dataSource&quot;of &quot;actie&quot;zijn

De mogelijke waarschuwing is:

**ERR_ENDPOINTCONFIG_106**: het in kaart brengen van config: maximum de verbindingen van HTTP niet bepaald: geen beperking door gebrek

## Gebruiksscenario&#39;s

In deze sectie vindt u de vijf hoofdgevallen voor het gebruik die u kunt uitvoeren om uw configuratie voor plafonds te beheren in [!DNL Journey Orchestration] .

Voor hulp bij het testen en configureren is [hier](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json) een Postman-verzameling beschikbaar.

Deze Postman-verzameling is opgezet om de Postman Variabele verzameling te delen die is gegenereerd via __[Adobe I/O Console-integraties](https://console.adobe.io/integrations) > Uitproberen > Downloaden voor Postman__, wat een Postman-omgevingsbestand genereert met de geselecteerde integratiewaarden.

Eenmaal gedownload en geüpload naar Postman moet u drie variabelen toevoegen: `{JO_HOST}`,`{BASE_PATH}` en `{SANDBOX_NAME}`.
* `{JO_HOST}`: [!DNL Journey Orchestration] Gateway-URL
* `{BASE_PATH}`: ingangspunt voor de API. De waarde is &#39;/authoring&#39;
* `{SANDBOX_NAME}`: de header **x-sandbox-name** (bijvoorbeeld &#39;prod&#39;) die overeenkomt met de sandboxnaam waar de API-operaties zullen plaatsvinden. Zie het [sandboxoverzicht](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=nl) voor meer informatie.

In het volgende gedeelte vindt u de geordende lijst van Rest-API-aanroepen om het gebruiksscenario uit te voeren.

Gebruik-Geval n°1: **creatie en plaatsing van een nieuwe het capteren configuratie**

1. list
1. create
1. candeploy
1. deploy

Gebruik-Geval n°2: **Update en stel een het maximum configuratie op die nog niet wordt opgesteld**

1. list
1. get
1. update
1. candeploy
1. deploy

Gebruik-Geval n°3: **stelt en schrapt een opgestelde het begrenzen configuratie** onbruikbaar

1. list
1. undeploy
1. delete

Gebruik-Geval n°4: **schrap een opgestelde het capteren configuratie.**

In slechts één API-oproep kunt u de configuratie deïmplementeren en verwijderen met behulp van de parameter forceDelete.
1. list
1. delete, met parameter forceDelete

Gebruik-Geval n°5: **werk een het maximum configuratie reeds in werking gesteld** bij

1. list
1. get
1. update
1. undeploy
1. candeploy
1. deploy
