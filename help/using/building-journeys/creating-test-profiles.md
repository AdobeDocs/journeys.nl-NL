---
product: adobe campaign
title: Een testprofiel maken
description: Meer informatie over het maken van testprofielen
exl-id: f1be46a8-04b9-4f40-b18e-9099099d2e1c
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 3%

---

# Testprofielen maken {#create-test-profiles}

Testprofielen zijn vereist wanneer de testmodus op een reis wordt gebruikt. Raadpleeg voor meer informatie over het gebruik van de testmodus [deze sectie](../building-journeys/testing-the-journey.md).

Er zijn verschillende manieren om een testprofiel te maken in Adobe Experience Platform. In deze documentatie richten wij ons op twee methodes: uploaden naar een [csv-bestand](../building-journeys/creating-test-profiles.md#create-test-profiles-csv) en gebruiken [API-aanroepen](../building-journeys/creating-test-profiles.md#create-test-profiles-api). U kunt een jsdossier in een dataset ook uploaden, verwijs naar [Documentatie over gegevensinname](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html#add-data-to-dataset).

Met deze importmethoden kunt u ook profielkenmerken bijwerken. Op deze manier kunt u een bestaand profiel omzetten in een testprofiel. Gebruik gewoon een vergelijkbaar bestand- of API-aanroep en neem alleen het veld ‘testProfile’ op met de waarde ‘true’.

Het maken van een testprofiel lijkt op het maken van gewone profielen in Adobe Experience Platform. Raadpleeg voor meer informatie de [Documentatie van het profiel van de klant in realtime](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=nl).

## Vereisten{#test-profile-prerequisites}

Om profielen te kunnen tot stand brengen, moet u eerst een schema en een dataset in Adobe Experience Platform tot stand brengen.

Eerst moet u **een schema maken**. Voer de volgende stappen uit:

1. Klik in Adobe Experience Platform op **[!UICONTROL Schemas]**in het linkermenu.
   ![](../assets/test-profiles-0.png)
1. Klikken **[!UICONTROL Create schema]** selecteert u in de rechterbovenhoek een schematype, bijvoorbeeld **[!UICONTROL XDM Individual Profile]**.
   ![](../assets/test-profiles-1.png)
1. Kies een naam voor het schema.
1. In de **[!UICONTROL Mixins]** sectie, klikt u op **[!UICONTROL Add]**.
   ![](../assets/test-profiles-1-bis.png)
1. Selecteer de juiste combinaties. Zorg ervoor dat u de **[!UICONTROL Profile test details]** mixin. Klik op **[!UICONTROL Add mixin]**.
   ![](../assets/test-profiles-1-ter.png)
De lijst van mengen wordt getoond op het scherm van het schemaoverzicht.

   ![](../assets/test-profiles-2.png)
1. Klik in de lijst met velden op het veld dat u als primaire identiteit wilt definiëren.
   ![](../assets/test-profiles-3.png)
1. In de **[!UICONTROL Field properties]** in het rechterdeelvenster, controleert u de **[!UICONTROL Identity]** en **[!UICONTROL Primary Identity]** en selecteert u een naamruimte. Als u wilt dat de primaire identiteit een e-mailadres is, kiest u de optie **[!UICONTROL Email]** naamruimte. Klik op **[!UICONTROL Apply]**.
   ![](../assets/test-profiles-4.png)
1. Selecteer het schema en schakel het **[!UICONTROL Profile]** in de **[!UICONTROL Schema properties]**.
   ![](../assets/test-profiles-5.png)
1. Klik op **[!UICONTROL Save]**.

>[!NOTE]
>
>Raadpleeg voor meer informatie over het maken van schema&#39;s de [XDM-documentatie](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#prerequisites).

Vervolgens moet u **Maak de dataset** waarin de profielen worden geïmporteerd. Voer de volgende stappen uit:

1. Klik in Adobe Experience Platform op **[!UICONTROL Datasets]** klikt u in het linkermenu op **[!UICONTROL Create dataset]**.
   ![](../assets/test-profiles-6.png)
1. Kies **[!UICONTROL Create dataset from schema]**.
   ![](../assets/test-profiles-7.png)
1. Selecteer het eerder gemaakte schema en klik op **[!UICONTROL Next]**.
   ![](../assets/test-profiles-8.png)
1. Kies een naam en klik op **[!UICONTROL Finish]**.
   ![](../assets/test-profiles-9.png)
1. De optie **[!UICONTROL Profile]** optie.
   ![](../assets/test-profiles-10.png)

>[!NOTE]
>
> Voor meer informatie over de verwezenlijking van dataset, verwijs naar [Documentatie Catalog Service](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html#getting-started).

## Een testprofiel maken met een CSV-bestand{#create-test-profiles-csv}

In Adobe Experience Platform kunt u profielen maken door een CSV-bestand met de verschillende profielvelden te uploaden naar uw gegevensset. Dit is de eenvoudigste methode.

1. Maak een eenvoudig CSV-bestand met behulp van een spreadsheetsoftware.
1. Voeg één kolom toe voor elk nodig veld. Voeg het primaire identiteitsveld (&quot;personID&quot; in het bovenstaande voorbeeld) en het veld &quot;testProfile&quot; toe op &quot;true&quot;.
   ![](../assets/test-profiles-11.png)
1. Voeg één regel per profiel toe en vul de waarden voor elk veld in.
   ![](../assets/test-profiles-12.png)
1. Sla het werkblad op als een CSV-bestand. Controleer of komma&#39;s als scheidingstekens worden gebruikt.
1. Klik in Adobe Experience Platform op **[!UICONTROL Workflows]**in het linkermenu.
   ![](../assets/test-profiles-14.png)
1. Kies **[!UICONTROL Map CSV to XDM schema]** en klik vervolgens op **[!UICONTROL Launch]**.
   ![](../assets/test-profiles-16.png)
1. Selecteer de dataset u de profielen in wilt invoeren. Klik op **[!UICONTROL Next]**.
   ![](../assets/test-profiles-17.png)
1. Klikken **[!UICONTROL Choose files]** en selecteert u het CSV-bestand. Wanneer het bestand is geüpload, klikt u op **[!UICONTROL Next]**.
   ![](../assets/test-profiles-18.png)
1. Wijs de bronCSV gebieden aan de schemagebieden toe, dan klik **[!UICONTROL Finish]**.
   ![](../assets/test-profiles-19.png)
1. Het importeren van de gegevens begint. De status verandert van **[!UICONTROL Processing]** tot **[!UICONTROL Success]**. Klikken **[!UICONTROL Preview data set]**, in de rechterbovenhoek.
   ![](../assets/test-profiles-20.png)
1. Controleer of de testprofielen correct zijn toegevoegd.
   ![](../assets/test-profiles-21.png)

Uw testprofielen worden toegevoegd en kunnen nu worden gebruikt bij het testen van een reis. Zie [deze sectie](../building-journeys/testing-the-journey.md).
>[!NOTE]
>
> Raadpleeg voor meer informatie over CSV-import de [Documentatie over gegevensinname](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html#tutorials).

## Testprofielen maken met behulp van API-aanroepen{#create-test-profiles-api}

U kunt testprofielen ook maken via API-aanroepen. Zie deze [pagina](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html).

U moet een profielschema gebruiken dat de &quot;de testdetails van het Profiel&quot;mengen bevat. De markering testProfile maakt deel uit van deze mix.

Wanneer u een profiel maakt, moet u de waarde doorgeven: testProfile = true.

U kunt een bestaand profiel ook bijwerken en de markering testProfile wijzigen in &quot;true&quot;.

Hier volgt een voorbeeld van een API-aanroep om een testprofiel te maken:

```
curl -X POST \
'https://dcs.adobedc.net/collection/xxxxxxxxxxxxxx' \
-H 'Cache-Control: no-cache' \
-H 'Content-Type: application/json' \
-H 'Postman-Token: xxxxx' \
-H 'cache-control: no-cache' \
-H 'x-api-key: xxxxx' \
-H 'x-gw-ims-org-id: xxxxx' \
-d '{
"header": {
"msgType": "xdmEntityCreate",
"msgId": "xxxxx",
"msgVersion": "xxxxx",
"xactionid":"xxxxx",
"datasetId": "xxxxx",
"imsOrgId": "xxxxx",
"source": {
"name": "Postman"
},
"schemaRef": {
"id": "https://example.adobe.com/mobile/schemas/xxxxx",
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"body": {
"xdmMeta": {
"schemaRef": {
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"xdmEntity": {
"_id": "xxxxx",
"_mobile":{
"ECID": "xxxxx"
},
"testProfile":true
}
}
}'
```
