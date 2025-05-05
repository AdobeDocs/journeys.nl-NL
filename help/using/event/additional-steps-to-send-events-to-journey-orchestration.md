---
product: adobe campaign
title: Aanvullende stappen om gebeurtenissen naar Journey Orchestration te verzenden
description: Meer informatie over extra stappen om gebeurtenissen naar Journey Orchestration te verzenden
feature: Journeys
role: User
level: Intermediate
exl-id: 11e337c6-5e05-4898-9953-b6b821af8fd1
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 2%

---

# Aanvullende stappen voor het verzenden van gebeurtenissen naar [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}



>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


>[!NOTE]
>
>Wanneer u een gebeurtenis maakt, genereert [!DNL Journey Orchestration] automatisch een id voor deze gebeurtenis. Het systeem dat de gebeurtenis duwt zou geen identiteitskaart moeten produceren, zou het moeten gebruiken beschikbaar in de voorproef van de lading. Zie [deze pagina](../event/previewing-the-payload.md).

Voer de volgende stappen uit om gebeurtenissen te configureren die naar **[!UICONTROL Streaming Ingestion APIs]** moeten worden verzonden en die in [!DNL Journey Orchestration] moeten worden gebruikt:

1. Krijg inlaat URL van Adobe Experience Platform APIs (zie [ Streaming Ingestie APIs ](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=nl)).
1. Kopieer de lading van de ladingsvoorproef in het **[!UICONTROL Event]** menu. Zie [deze pagina](../event/defining-the-payload-fields.md).

Vervolgens moet u het gegevenssysteem configureren dat gebeurtenissen naar Streaming Ingestie-API&#39;s stuurt met de door u gekopieerde payload:

1. Stel een POST API-aanroep in naar de URL van de Streaming Ingestie-API&#39;s (een zogenaamde inlaat).
1. Gebruik de payload die u hebt gekopieerd vanuit [!DNL Journey Orchestration] in de hoofdtekst (&quot;gegevenssectie&quot;) van de API-aanroep naar de API&#39;s voor streaming congestie. Zie hieronder voor een voorbeeld
1. Bepaal waar u alle variabelen in de lading wilt ophalen. Voorbeeld: als de gebeurtenis het adres moet overbrengen, wordt bij de geplakte payload &quot;address&quot;: &quot;string&quot; weergegeven. &quot;string&quot; moet worden vervangen door de variabele die automatisch de juiste waarde invult, de e-mail van de persoon waarnaar een bericht wordt verzonden. In de voorvertoning van de payload vullen we in de sectie **[!UICONTROL Header]** veel waarden die u nodig hebt om uw werk te vergemakkelijken.
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

Om de identificatie van de plaats te vergemakkelijken waar te om het &quot;gegevens&quot;deel te kleven, kunt u een JSON visualization hulpmiddel zoals [ https://jsonformatter.curiousconcept.com ](https://jsonformatter.curiousconcept.com) gebruiken

Om het stromen Ingestie APIs problemen op te lossen, verwijs naar deze [ pagina ](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html?lang=nl-NL).
