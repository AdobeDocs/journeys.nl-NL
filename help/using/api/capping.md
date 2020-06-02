---
title: Beschrijving van API voor uitlijnen
description: Meer informatie over de API voor aftiteling.
contentOwner: sauviat
products: journeys
audience: audiences
content-type: reference
topic-tags: journeys
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9f28bdc0e74359ff9f8d84961769b84973ae3f39
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 0%

---


# Werken met API voor uitlijnen

## Inleiding

De API&#39;s van de Journey Orchestration ondersteunen 5000 gebeurtenissen/seconden, maar sommige externe systemen of API&#39;s kunnen geen equivalente doorvoer hebben. Dat is waarom de Orchestratie van de Reis met een specifieke eigenschap komt genoemd Capping API om het tarief te controleren en te beperken dat wij aan externe systemen opleggen.

Tijdens een gegevensbronconfiguratie, zult u een verbinding aan een systeem bepalen om extra informatie terug te winnen die in uw reizen, of voor een actiedefinitie zal worden gebruikt, zult u verbinding van een derdesysteem vormen om berichten of API vraag te verzenden. Telkens wanneer een API vraag door Journey wordt uitgevoerd, wordt het maximum dat API wordt gevraagd, komt de vraag door de API motor. Als er een bepaalde grens is, wordt de vraag verworpen en het externe systeem zal niet worden overbelast.

Meer over actie of datasource configuratie leren, zie [Ongeveer acties](https://docs.adobe.com/content/help/en/journeys/using/action-journeys/action.html) of [Ongeveer gegevensbronnen](https://docs.adobe.com/content/help/en/journeys/using/data-source-journeys/about-data-sources.html)


## Bronnen

De API voor het uitlijnen van reisorchestratie wordt beschreven in een Swagger-bestand dat [hier](https://adobedocs.github.io/JourneyAPI/docs/)beschikbaar is.

Als u deze API met uw instantie van de Journey Orchestration wilt gebruiken, moet u de AdobeIO-console gebruiken. U begint met het volgen van deze [Aan de slag met Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) en gebruikt vervolgens de secties op deze pagina.

Om uw integratie te testen en voor te bereiden, is een inzameling van Postman beschikbaar [hier](https://github.com/AdobeDocs/JourneyAPI/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

## Verificatie

### API-toegang instellen

De toegang tot de API voor reisorganisatie wordt ingesteld via de onderstaande stappen. Elk van deze stappen wordt beschreven in de documentatie [van](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)Adobe IO.

>[!CAUTION]
>
>Als u certificaten wilt beheren in Adobe IO, moet u ervoor zorgen dat u <b>Systeembeheerdersrechten</b> hebt voor de organisatie of een <a href="https://helpx.adobe.com/enterprise/using/manage-developers.html">ontwikkelaarsaccount</a> in de beheerconsole.

1. **Controleer of u een digitaal certificaat** hebt of maak er zo nodig een. De openbare en persoonlijke sleutels die van het certificaat worden voorzien zijn vereist in de volgende stappen.
1. **Maak een nieuwe integratie met de Journey Orchestration Service** in Adobe IO en configureer deze. Toegang tot het productprofiel is vereist voor Journey Orchestration and Adobe Experience Platform. Uw referenties worden vervolgens gegenereerd (API-sleutel, clientgeheim...).
1. **Maak een JSON Web Token (JWT)** van de eerder gegenereerde referenties en onderteken deze met uw persoonlijke sleutel. De JWT codeert alle identiteits- en beveiligingsgegevens die Adobe nodig heeft om uw identiteit te verifiëren en u toegang te verlenen tot de API. Deze stap wordt beschreven in deze [sectie](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Uitwisseling uw JWT voor een Token** van de Toegang door een POST- verzoek of via de Interface van de Console van de Ontwikkelaar. Dit toegangstoken moet worden gebruikt in elke header van uw API-aanvragen.

Om een beveiligde service-to-service Adobe I/O API-sessie tot stand te brengen, moet elke aanvraag naar een Adobe-service de onderstaande informatie bevatten in de machtigingheader.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANISATIE>**: Dit is uw persoonlijke ORGANIZATION-id. Adobe levert één ORGANIZATION-id voor elk van uw varianten:

   * &lt;ORGANISATIE>: productie-instantie
   Raadpleeg de beheerder of uw technische contactpersoon van Adobe voor informatie over de waarde van uw organisatie-id. U kunt de software ook ophalen in de Adobe I/O-lijst wanneer u een nieuwe integratie maakt, in de lijst met licenties (zie de <a href="https://www.adobe.io/authentication.html">Adobe IO-documentatie</a>).

* **&lt;ACCESS_TOKEN>**: Uw persoonlijke toegangstoken, die werd teruggewonnen toen het ruilen van uw JWT door een POST- verzoek.

* **&lt;API_KEY>**: uw persoonlijke API-sleutel. Deze wordt geleverd in Adobe I/O nadat u een nieuwe integratie hebt gemaakt in de Journey Orchestration Service.



## Beschrijving van API voor uitlijnen

Met de API voor uitsnijden kunt u uw configuraties voor uitlijnen maken, configureren en controleren.

| Methode | Pad | Beschrijving |
|---|---|---|
| POST | list/endConfigs | Krijg een lijst van de eindpunt die configuraties begrenzen |
| POST | /endConfigs | Creeer een eindpunt het bedekken configuratie |
| POST | /EndendConfigs/{uid}/opstellen | Implementeer een configuratie voor het afdekken van eindpunten |
| POST | /EndendConfigs/{uid}/undeploy | Maak een eindpunt onbruikbaar dat configuratie begrenst |
| POST | /endConfigs/{uid}/canDeploy | Controle als een eindpunt het begrenzen configuratie kan worden opgesteld of niet |
| PUT | /endConfigs/{uid} | Een configuratie voor het afdekken van eindpunten bijwerken |
| GET | /endConfigs/{uid} | Retrireer een eindpunt dat configuratie begrenst |
| VERWIJDEREN | /endConfigs/{uid} | Een configuratie voor het toewijzen van een hoekpunt verwijderen |

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
            "maxHttpConnections": <max connections count to the endpoint>
            "rating": {          
                "maxCallsCount": <max calls to be performed in the period defined by period/timeUnit>,
                "periodInMs": <integer value greater than 0>
            }
        },
        ...
    }
}
```

### Voorbeeld:

```
`{
  "url": "https://api.example.org/data/2.5/*",
  "methods": [
    "GET"
  ],
  "services": {
    "dataSource": {
      "maxHttpConnections": 30000,
      "rating": {
        "maxCallsCount": 5000,
        "periodInMs": 1000
      }
    }
  },
  "orgId": "<IMS Org Id>"
}
```


## Waarschuwing en fouten

Wanneer een **canDeploy** methode wordt geroepen, bevestigt het proces de configuratie en keert de bevestigingsstatus terug die door zijn Unieke identiteitskaart wordt geïdentificeerd, of:

```
"ok" or "error"
```

De mogelijke fouten zijn:

* **ERR_ENDPOINTCONFIG_100**: configuratie beperken: ontbrekende of ongeldige URL
* **ERR_ENDPOINTCONFIG_101**: configuratie beperken: misvormde url
* **ERR_ENDPOINTCONFIG_102**: configuratie beperken: onjuist gevormde URL: jokerteken in URL niet toegestaan in host:poort
* **ERR_ENDPOINTCONFIG_103**: configuratie beperken: ontbrekende HTTP-methoden
* **ERR_ENDPOINTCONFIG_104**: configuratie beperken: geen callrating gedefinieerd
* **ERR_ENDPOINTCONFIG_107**: configuratie beperken: ongeldige maximum vraagtelling (maxCallsCount)
* **ERR_ENDPOINTCONFIG_108**: configuratie beperken: ongeldige maximum vraagtelling (periodInMS)
* **ERR_ENDPOINTCONFIG_111**: configuratie beperken: kan eindpunt config niet tot stand brengen: ongeldige payload
* **ERR_ENDPOINTCONFIG_112**: configuratie beperken: kan eindpunt config niet tot stand brengen: JSON-payload verwacht
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: ongeldige servicenaam <!--<given value>-->: moet &#39;dataSource&#39; of &#39;action&#39; zijn


De mogelijke waarschuwing is:

**ERR_ENDPOINTCONFIG_106**: configuratie beperken: max. HTTP-verbindingen niet gedefinieerd: geen beperking



## Gebruiksscenario&#39;s

In deze sectie, zult u de vijf belangrijkste gebruik-gevallen vinden die u kunt uitvoeren om uw het in kaart brengen configuratie in de Orchestratie van de Reis te beheren.

Om u in uw het testen en configuratie te helpen, is een inzameling van Postman beschikbaar [hier](https://github.com/AdobeDocs/JourneyAPI/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

Deze Postman-verzameling is ingesteld om de Postman-variabele-verzameling te delen die via de integratie __[> Uitproberen > Download voor Postman](https://console.adobe.io/integrations)van__ Adobe I/O Console is gegenereerd. Hiermee wordt een Postman-milieubestand met de geselecteerde integratiewaarden gegenereerd.

Nadat u de gegevens hebt gedownload en geüpload naar Postman, moet u twee variabelen toevoegen: `{JO_HOST}` en `{Base_Path}`.
* `{JO_HOST}` : Reisorchestratie Gateway-URL
* `{BASE_PATH}` : ingangspunt voor de API. De waarde is &#39;/authoring&#39;



Gebruiksscenario n°1: **Het creëren en de plaatsing van een nieuwe het maximum configuratie**

1. list
1. maken
1. canimplementeren
1. inzetten

Gebruiksscenario n°2: **Een configuratie voor uitlijnen bijwerken en implementeren die nog niet is geïmplementeerd**

1. list
1. get
1. update
1. canimplementeren
1. inzetten

Gebruiksscenario n°3: **Implementeer en verwijder een geïmplementeerde configuratie voor plafonnering**

1. list
1. desimplementatie
1. delete

Gebruiksscenario n°4: **Verwijder een configuratie voor geïmplementeerde uiteinden.**

In slechts één API vraag, kunt u de configuratie met het gebruik van de forceDelete parameter ongedaan maken en schrappen.
1. list
1. delete, met forceDelete-parameter

Gebruiksscenario n°5: **Een reeds geïmplementeerde configuratie voor plafonnering bijwerken**

1. list
1. get
1. update
1. desimplementatie
1. canimplementeren
1. inzetten
