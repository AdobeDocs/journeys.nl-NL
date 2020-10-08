---
title: Beschrijving van API voor uitlijnen
description: Meer informatie over de API voor aftiteling.
contentOwner: sauviat
products: journeys
audience: audiences
content-type: reference
topic-tags: journeys
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '1108'
ht-degree: 1%

---


# Werken met API voor uitlijnen

## Inleiding

[!DNL Journey Orchestration]API&#39;s ondersteunen 5000 gebeurtenissen/seconden, maar sommige externe systemen of API&#39;s kunnen geen equivalente doorvoer hebben. Daarom [!DNL Journey Orchestration] wordt er een speciale functie met de naam Capping API (Capping API) gebruikt om de snelheid die we opleggen aan externe systemen te controleren en te beperken.

Tijdens een gegevensbronconfiguratie, zult u een verbinding aan een systeem bepalen om extra informatie terug te winnen die in uw reizen, of voor een actiedefinitie zal worden gebruikt, zult u verbinding van een derdesysteem vormen om berichten of API vraag te verzenden. Telkens wanneer een API vraag door Journey wordt uitgevoerd, wordt het maximum dat API wordt gevraagd, komt de vraag door de API motor. Als er een bepaalde grens is, wordt de vraag verworpen en het externe systeem zal niet worden overbelast.

Meer over actie of datasource configuratie leren, zie [Ongeveer acties](https://docs.adobe.com/content/help/en/journeys/using/action-journeys/action.html) of [Ongeveer gegevensbronnen](https://docs.adobe.com/content/help/en/journeys/using/data-source-journeys/about-data-sources.html)


## Bronnen

>[!NOTE]
>
>De API voor [!DNL Journey Orchestration] uitlijnen wordt beschreven in een Swagger-bestand dat [hier](https://adobedocs.github.io/JourneyAPI/docs/)beschikbaar is.

Als u deze API met uw [!DNL Journey Orchestration] instantie wilt gebruiken, moet u de AdobeI/O-console gebruiken. U kunt beginnen door dit te volgen [Aan de slag met de Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) van de Ontwikkelaar van Adobe en dan de secties in deze pagina te gebruiken.

Om uw integratie te testen en voor te bereiden, is een inzameling van Postman beschikbaar [hier](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

## Verificatie

### API-toegang instellen

[!DNL Journey Orchestration] API-toegang wordt ingesteld via de onderstaande stappen. Elk van deze stappen wordt beschreven in de [Adobe I/O documentatie](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Om certificaten in Adobe I/O te beheren, zorg ervoor u de <b>beheerderrechten</b> van het Systeem op de organisatie of een [ontwikkelaarrekening](https://helpx.adobe.com/enterprise/using/manage-developers.html) in de Admin console hebt.

1. **Controleer of u een digitaal certificaat** hebt of maak er zo nodig een. De openbare en persoonlijke sleutels die van het certificaat worden voorzien zijn vereist in de volgende stappen.
1. **Creeer een nieuwe integratie aan[!DNL Journey Orchestration]Dienst** in Adobe I/O en vorm het. Toegang tot het productprofiel is vereist voor [!DNL Journey Orchestration] en Adobe Experience Platform. Uw referenties worden vervolgens gegenereerd (API-sleutel, clientgeheim...).
1. **Maak een JSON Web Token (JWT)** van de eerder gegenereerde referenties en onderteken deze met uw persoonlijke sleutel. De JWT codeert alle identiteits- en beveiligingsgegevens die Adobe nodig heeft om uw identiteit te verifiëren en u toegang tot de API te verlenen. Deze stap wordt beschreven in deze [sectie](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Uitwisseling uw JWT voor een Token** van de Toegang door een verzoek van de POST of via de Interface van de Console van de Ontwikkelaar. Dit toegangstoken moet worden gebruikt in elke header van uw API-aanvragen.

Om een veilige dienst-aan-dienst Adobe I/O API zitting tot stand te brengen, moet elk verzoek aan de dienst van de Adobe in de kopbal van de Vergunning de hieronder informatie omvatten.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANISATIE>**: Dit is uw persoonlijke ORGANIZATION ID, één ORGANIZATION ID wordt verstrekt door Adobe voor elk van uw instanties:

   * &lt;ORGANISATIE>: productie-instantie

   Raadpleeg de beheerder of uw technische contactpersoon voor Adobe om de waarde van uw ORGANISATIE-id op te vragen. U kunt het in Adobe I/O ook terugwinnen wanneer het creëren van een nieuwe integratie, in de vergunningslijst (zie de <a href="https://www.adobe.io/authentication.html">Adobe I/O documentatie</a>).

* **&lt;ACCESS_TOKEN>**: Uw persoonlijk toegangstoken, dat werd teruggewonnen toen het ruilen van uw JWT door een verzoek van de POST.

* **&lt;API_KEY>**: uw persoonlijke API-sleutel. Het wordt verstrekt in Adobe I/O na het creëren van een nieuwe integratie aan de [!DNL Journey Orchestration] Dienst.



## Beschrijving van API voor uitlijnen

Met de API voor uitsnijden kunt u uw configuraties voor uitlijnen maken, configureren en controleren.

| Methode | Pad | Beschrijving |
|---|---|---|
| [!DNL POST] | list/endConfigs | Krijg een lijst van de eindpunt die configuraties begrenzen |
| [!DNL POST] | /endConfigs | Creeer een eindpunt het bedekken configuratie |
| [!DNL POST] | /EndendConfigs/`{uid}`/distribueren | Implementeer een configuratie voor het afdekken van eindpunten |
| [!DNL POST] | /EndendConfigs/`{uid}`/undeploy | Maak een eindpunt onbruikbaar dat configuratie begrenst |
| [!DNL POST] | /EndindpuntConfigs/`{uid}`/canDeploy | Controle als een eindpunt het begrenzen configuratie kan worden opgesteld of niet |
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
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: ongeldige servicenaam `<!--<given value>-->`: moet &#39;dataSource&#39; of &#39;action&#39; zijn


De mogelijke waarschuwing is:

**ERR_ENDPOINTCONFIG_106**: configuratie beperken: max. HTTP-verbindingen niet gedefinieerd: geen beperking



## Gebruiksscenario&#39;s

In deze sectie, zult u de vijf belangrijkste gebruik-gevallen vinden die u kunt uitvoeren om uw het capteren configuratie binnen te beheren [!DNL Journey Orchestration].

Om u in uw het testen en configuratie te helpen, is een inzameling van Postman beschikbaar [hier](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

Deze Postman-verzameling is ingesteld om de Postman-variabele-verzameling te delen die via de integratie __[van de](https://console.adobe.io/integrations)Adobe I/O-console is gegenereerd > Uitproberen > Downloaden voor Postman__, waardoor een Postman-milieubestand met de geselecteerde integratiewaarden wordt gegenereerd.

Nadat u het bestand hebt gedownload en geüpload naar Postman, moet u drie variabelen toevoegen: `{JO_HOST}`,`{Base_Path}` en `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] Gateway-URL
* `{BASE_PATH}` : ingangspunt voor de API. De waarde is &#39;/authoring&#39;
* `{SANDBOX_NAME}` : de naam **van de header** x-sandbox (bijvoorbeeld &#39;prod&#39;) die overeenkomt met de naam van de sandbox waarin de API-bewerkingen worden uitgevoerd. Zie het [sandboxoverzicht](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html) voor meer informatie.

In de volgende sectie vindt u de lijst met gerangschikte aanroepen van de Rest-API om de use-case uit te voeren.

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

