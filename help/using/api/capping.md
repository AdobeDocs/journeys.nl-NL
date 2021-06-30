---
product: adobe campaign
title: Beschrijving van API voor uitlijnen
description: Meer informatie over de API voor aftiteling.
products: journeys
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: e42ef98b1d84d8311cf49967ec75ec9be6cc53f1
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 1%

---

# Werken met API voor uitlijnen

## Inleiding

[!DNL Journey Orchestration]API&#39;s ondersteunen 5000 gebeurtenissen/seconden, maar sommige externe systemen of API&#39;s kunnen geen equivalente doorvoer hebben. Daarom wordt [!DNL Journey Orchestration] geleverd met een speciale functie die Capping API wordt genoemd om de snelheid die we opleggen aan externe systemen te controleren en te beperken.

Tijdens een gegevensbronconfiguratie, zult u een verbinding aan een systeem bepalen om extra informatie terug te winnen die in uw reizen, of voor een actiedefinitie zal worden gebruikt, zult u verbinding van een derdesysteem vormen om berichten of API vraag te verzenden. Telkens wanneer een API vraag door Journey wordt uitgevoerd, wordt het maximum dat API wordt gevraagd, komt de vraag door de API motor. Als er een bepaalde grens is, wordt de vraag verworpen en het externe systeem zal niet worden overbelast.

Voor externe gegevensbronnen, wordt het maximumaantal vraag per seconde geplaatst aan 15. Als het aantal vraag 15 per seconde overschrijdt, worden de resterende vraag verworpen. U kunt deze limiet verhogen voor externe privégegevensbronnen. Contacteer Adobe aan whitelist het eindpunt. Dit is niet mogelijk voor openbare externe gegevensbronnen. Raadpleeg deze [pagina](../about/external-systems.md) voor meer informatie over beste praktijken en richtlijnen bij het integreren van externe systemen.

Meer over actie of datasource configuratie leren, zie [Ongeveer acties](https://experienceleague.adobe.com/docs/journeys/using/action-journeys/action.html) of [Ongeveer gegevensbronnen](https://experienceleague.adobe.com/docs/journeys/using/data-source-journeys/about-data-sources.html)

## Bronnen

>[!NOTE]
>
>De [!DNL Journey Orchestration] Capping-API wordt beschreven in een Swagger-bestand dat [hier](https://adobedocs.github.io/JourneyAPI/docs/) beschikbaar is.

Als u deze API met uw [!DNL Journey Orchestration]-exemplaar wilt gebruiken, moet u de AdobeI/O-console gebruiken. U kunt beginnen door dit [te volgen Begonnen met de Console van de Ontwikkelaar van Adobe](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) en dan de secties in deze pagina te gebruiken.

Om uw integratie te testen en voor te bereiden, is een inzameling van Postman beschikbaar [hier](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

## Verificatie

### API-toegang instellen

[!DNL Journey Orchestration] API-toegang wordt ingesteld via de onderstaande stappen. Elk van deze stappen wordt gedetailleerd in [Adobe I/O documentatie](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Als u certificaten in Adobe I/O wilt beheren, moet u <b>Systeembeheerder</b> rechten hebben op de organisatie of een [ontwikkelingsaccount](https://helpx.adobe.com/enterprise/using/manage-developers.html) in de beheerconsole.

1. **Controleer of u een digitaal certificaat** hebt of maak er zo nodig een. De openbare en persoonlijke sleutels die van het certificaat worden voorzien zijn vereist in de volgende stappen.
1. **Creeer een nieuwe integratie aan  [!DNL Journey Orchestration]** Onderhoud Adobe I/O en vorm het. De toegang tot het productprofiel is vereist voor [!DNL Journey Orchestration] en Adobe Experience Platform. Uw referenties worden vervolgens gegenereerd (API-sleutel, clientgeheim...).
1. **Maak een JSON Web Token (JWT)** van de eerder gegenereerde referenties en onderteken deze met uw persoonlijke sleutel. De JWT codeert alle identiteits- en beveiligingsgegevens die Adobe nodig heeft om uw identiteit te verifiëren en u toegang tot de API te verlenen. Deze stap wordt beschreven in deze [sectie](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Uitwisseling uw JWT voor een** Tokenon van de Toegang door een verzoek van de POST of via de Interface van de Console van de Ontwikkelaar. Dit toegangstoken moet worden gebruikt in elke header van uw API-aanvragen.

Om een veilige dienst-aan-dienst Adobe I/O API zitting tot stand te brengen, moet elk verzoek aan de dienst van de Adobe in de kopbal van de Vergunning de informatie hieronder omvatten.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**: Dit is uw persoonlijke ORGANIZATION ID, één ORGANIZATION ID wordt verstrekt door Adobe voor elk van uw instanties:

   * &lt;organization> : productie-instantie

   Raadpleeg de beheerder of uw technische contactpersoon voor Adobe om de waarde van uw ORGANISATIE-id op te vragen. U kunt het in Adobe I/O ook terugwinnen wanneer het creëren van een nieuwe integratie, in de vergunningslijst (zie <a href="https://www.adobe.io/authentication.html">Adobe I/O documentatie</a>).

* **&lt;access_token>**: Uw persoonlijk toegangstoken, dat werd teruggewonnen toen het ruilen van uw JWT door een verzoek van de POST.

* **&lt;api_key>**: uw persoonlijke API-sleutel. De service wordt geleverd in Adobe I/O na het maken van een nieuwe integratie in de service [!DNL Journey Orchestration].



## Beschrijving van API voor uitlijnen

Met de API voor uitsnijden kunt u uw configuraties voor uitlijnen maken, configureren en controleren.

| Methode | Pad | Beschrijving |
|---|---|---|
| [!DNL POST] | list/endConfigs | Krijg een lijst van de eindpunt die configuraties begrenzen |
| [!DNL POST] | /endConfigs | Creeer een eindpunt het bedekken configuratie |
| [!DNL POST] | /endConfigs/`{uid}`/opstellen | Implementeer een configuratie voor het afdekken van eindpunten |
| [!DNL POST] | /EndendConfigs/`{uid}`/undeploy | Maak een eindpunt onbruikbaar dat configuratie begrenst |
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
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: ongeldige servicenaam  `<!--<given value>-->`: moet &#39;dataSource&#39; of &#39;action&#39; zijn


De mogelijke waarschuwing is:

**ERR_ENDPOINTCONFIG_106**: configuratie beperken: max. HTTP-verbindingen niet gedefinieerd: geen beperking



## Gebruiksscenario&#39;s

In deze sectie, zult u de vijf belangrijkste gebruik-gevallen vinden die u kunt uitvoeren om uw het capteren configuratie in [!DNL Journey Orchestration] te beheren.

Om u in uw het testen en configuratie te helpen, is een inzameling van Postman beschikbaar [hier](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

Deze Postman-verzameling is ingesteld om de Postman-variabele-verzameling te delen die is gegenereerd via de integratie van __[Adobe I/O-console](https://console.adobe.io/integrations) > Uitproberen > Download for Postman__. Hiermee wordt een Postman-milieubestand gegenereerd met de geselecteerde integratiewaarden.

Nadat u het bestand hebt gedownload en geüpload naar Postman, moet u drie variabelen toevoegen: `{JO_HOST}`,`{Base_Path}` en `{SANDBOX_NAME}`.
* `{JO_HOST}` :  [!DNL Journey Orchestration] Gateway-URL
* `{BASE_PATH}` : ingangspunt voor de API. De waarde is &#39;/authoring&#39;
* `{SANDBOX_NAME}` : de header  **x-sandbox-name**  (bijvoorbeeld &#39;prod&#39;) die overeenkomt met de sandboxnaam waar de API-bewerkingen worden uitgevoerd. Zie het [overzicht van sandboxen](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html) voor meer informatie.

In de volgende sectie vindt u de lijst met gerangschikte aanroepen van de Rest-API om de use-case uit te voeren.

Gebruiksscenario n°1: **Een nieuwe configuratie voor plafonnering maken en implementeren**

1. list
1. maken
1. canimplementeren
1. inzetten

Gebruiksscenario n°2: **Een configuratie voor plafonnering bijwerken en implementeren die nog niet is geïmplementeerd**

1. list
1. get
1. update
1. canimplementeren
1. inzetten

Gebruiksscenario n°3: **Implementatie en verwijdering van een geïmplementeerde configuratie met begappingen ongedaan maken**

1. list
1. desimplementatie
1. delete

Gebruiksscenario n°4: **Verwijder een geïmplementeerde configuratie voor uitlijnen.**

In slechts één API vraag, kunt u de configuratie met het gebruik van de forceDelete parameter ongedaan maken en schrappen.
1. list
1. delete, met forceDelete-parameter

Gebruiksscenario n°5: **Werk een reeds geïmplementeerde configuratie voor plafonnering bij**

1. list
1. get
1. update
1. desimplementatie
1. canimplementeren
1. inzetten
