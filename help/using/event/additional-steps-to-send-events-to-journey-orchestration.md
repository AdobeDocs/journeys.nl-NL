---
product: adobe campaign
title: Aanvullende stappen om gebeurtenissen naar Journey Orchestration te verzenden
description: Meer informatie over extra stappen om gebeurtenissen naar Journey Orchestration te verzenden
feature: Journeys
role: User
level: Intermediate
exl-id: 11e337c6-5e05-4898-9953-b6b821af8fd1
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 4%

---

# Aanvullende stappen om gebeurtenissen te verzenden naar [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>Wanneer u een gebeurtenis maakt, [!DNL Journey Orchestration] genereert automatisch een id voor deze gebeurtenis. Het systeem dat de gebeurtenis duwt zou geen identiteitskaart moeten produceren, zou het moeten gebruiken beschikbaar in de voorproef van de lading. Zie [deze pagina](../event/previewing-the-payload.md).

Om gebeurtenissen te vormen die moeten worden verzonden naar **[!UICONTROL Streaming Ingestion APIs]** en te gebruiken in [!DNL Journey Orchestration], moet u deze stappen volgen:

1. De inlaatURL ophalen van de Adobe Experience Platform API&#39;s (zie [Streaming-API&#39;s](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=nl)).
1. Kopieer de lading van de payload voorproef in **[!UICONTROL Event]** -menu. Zie [deze pagina](../event/defining-the-payload-fields.md).

Vervolgens moet u het gegevenssysteem configureren dat gebeurtenissen naar Streaming Ingestie-API&#39;s stuurt met de door u gekopieerde payload:

1. Stel een POST-API-aanroep in naar de URL van de Streaming Ingestie-API&#39;s (een zogenaamde inlaat).
1. De lading gebruiken die u hebt gekopieerd [!DNL Journey Orchestration] in de hoofdtekst (&quot;gegevenssectie&quot;) van de API-aanroep naar Streaming Ingestie-API&#39;s. Zie hieronder voor een voorbeeld
1. Bepaal waar u alle variabelen in de lading wilt ophalen. Voorbeeld: als de gebeurtenis geacht wordt het adres over te brengen, zal de geplakte lading &quot;adres&quot;tonen: &quot;string&quot;. &quot;string&quot; moet worden vervangen door de variabele die automatisch de juiste waarde invult, de e-mail van de persoon waarnaar een bericht wordt verzonden. Let op: in de voorvertoning van de lading, in de **[!UICONTROL Header]** in deze sectie worden veel waarden automatisch ingevuld die u nodig hebt om uw werk te vergemakkelijken.
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

U kunt een JSON-visualisatiefunctie gebruiken, zoals [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

Raadpleeg deze voor informatie over het oplossen van problemen met de API&#39;s voor streaming-insluiting [page](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html).
