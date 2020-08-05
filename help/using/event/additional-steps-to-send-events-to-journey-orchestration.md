---
title: Aanvullende stappen om gebeurtenissen naar Journey Orchestration te verzenden
description: Meer informatie over extra stappen om gebeurtenissen naar Journey Orchestration te verzenden
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---



# Aanvullende stappen om gebeurtenissen te verzenden naar [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>Wanneer u een gebeurtenis maakt, wordt [!DNL Journey Orchestration] automatisch een id voor deze gebeurtenis gegenereerd. Het systeem dat de gebeurtenis duwt zou geen identiteitskaart moeten produceren, zou het moeten gebruiken beschikbaar in de voorproef van de lading. Zie [](../event/previewing-the-payload.md).

Als u gebeurtenissen wilt configureren die moeten worden verzonden naar **[!UICONTROL Streaming Ingestion APIs]** en gebruikt in [!DNL Journey Orchestration], moet u de volgende stappen uitvoeren:

1. Haal de inlaatURL op van de Adobe Experience Platform API&#39;s (zie [Streaming Ingestie-API&#39;s](https://docs.adobe.com/content/help/en/experience-platform/ingestion/streaming/overview.html)).
1. Kopieer de lading van de payload voorproef in het **[!UICONTROL Event]** menu. Zie [](../event/defining-the-payload-fields.md).

Vervolgens moet u het gegevenssysteem configureren dat gebeurtenissen naar Streaming Ingestie-API&#39;s stuurt met de door u gekopieerde payload:

1. Stel een POST-API-aanroep in naar de URL van de Streaming Ingestie-API&#39;s (een zogenaamde inlaat).
1. Gebruik de payload die u hebt gekopieerd vanuit [!DNL Journey Orchestration] de hoofdtekst (&quot;gegevenssectie&quot;) van de API-aanroep naar de API&#39;s voor streaming congestie. Zie hieronder voor een voorbeeld
1. Bepaal waar u alle variabelen in de lading wilt ophalen. Voorbeeld: als de gebeurtenis geacht wordt het adres over te brengen, zal de geplakte lading &quot;adres&quot;tonen: &quot;string&quot;. &quot;string&quot; moet worden vervangen door de variabele die automatisch de juiste waarde invult, de e-mail van de persoon waarnaar een bericht wordt verzonden. In de voorvertoning van de lading vullen we in de **[!UICONTROL Header]** sectie vele waarden automatisch die u uw werk vergemakkelijken.
1. Selecteer &#39;application/json&#39; als type body.
1. Geef uw IMS-organisatie-id in de koptekst door met behulp van de sleutel &quot;x-gw-ims-org-id&quot;. Gebruik voor de waarde uw IMS-organisatie-id (&quot;XXX@AdobeOrg&quot;).

Hier volgt een voorbeeld van een gebeurtenis Streaming ingestie-API&#39;s:

```
{
    "header": {
        "msgType": "xdmEntityCreate",
        "msgId": "c25585b9-252e-431d-b562-e73da70c04e7",
        "msgVersion": "1.0",
        "xactionId": "f5995abe-c49d-4848-9577-a7a4fc2996fb",
        "datasetId": "string - required if you want the data to land in a specific dataset - not mandatory",
        "imsOrgId": "XXX@AdobeOrg",
        "schemaRef": {
            "id": "XXX",
            "contentType": "application/vnd.adobe.xed-full+json;version=1"
        },
        "source": {
            "name": "Journeys"
        }
    },
    "body": {
        "xdmMeta": {
            "schemaRef": {
                "id": "XXX",
                "contentType": "application/vnd.adobe.xed-full+json;version=1"
            }
        },
        "xdmEntity": {
            "_instance_name": {
                "person": {
                    "firstName": "string",
                    "lastName": "string",
                    "gender": "string",
                    "birthYear": 10,
                    "emailAddress": "string"
                }
            },
            "identityMap": {
                "Email": [
                {
                    "id": "string"
                    }
                ]
            },
            "_id": "string",
            "timestamp": "2018-05-29T00:00:00.000Z",
            "_experience": {
                "campaign": {
                    "orchestration": {
                    "eventID": "XXX"
                    }
                }
            }
        }
    }
}
```

Als u de locatie waar u het onderdeel &quot;data&quot; wilt plakken gemakkelijker wilt kunnen identificeren, kunt u een JSON-visualisatiefunctie gebruiken, zoals [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

Raadpleeg deze [pagina](https://docs.adobe.com/content/help/en/experience-platform/ingestion/streaming/troubleshooting.html)voor informatie over het oplossen van problemen met de API&#39;s voor streaming.
