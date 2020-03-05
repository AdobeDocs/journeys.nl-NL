---
title: 'Externe gegevensbronnen '
description: 'Leer hoe te om externe gegevensbronnen te vormen '
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
source-git-commit: a0db4d65218861b71d35f83ccf2d15e25a1597e8

---



# Externe gegevensbronnen {#concept_t2s_kqt_52b}

De externe gegevensbronnen staan u toe om een verbinding aan derdesystemen te bepalen, bijvoorbeeld als u een hotel boekend systeem gebruikt om te controleren of de persoon een ruimte heeft geregistreerd. In tegenstelling tot de ingebouwde gegevensbron van het Platform van de Ervaring, kunt u zo vele externe gegevensbronnen tot stand brengen aangezien u nodig hebt.

REST APIs die POST gebruiken of KRIJGT en terugkerend JSON wordt gesteund. API-sleutel, basis- en aangepaste verificatiemodi worden ondersteund.

Neem het voorbeeld van de weer API dienst die ik wil gebruiken om het gedrag van mijn reis aan te passen volgens weergegevens in real time.

Hier zijn twee voorbeelden van de API vraag:

* _https://api.adobeweather.org/weather?city=London,uk&amp;appid=1234_
* _https://api.adobeweather.org/weather?lat=35&amp;lon=139&amp;appid=1234_

De oproep bestaat uit een hoofdURL (_https://api.adobeweather.org/weather_), twee parameterreeksen (&quot;city&quot; voor de stad en &quot;lat/long&quot; voor de lengte- en breedtegraad) en de API-sleutel (appid).

Hier zijn de belangrijkste stappen om een nieuwe externe gegevensbron tot stand te brengen en te vormen:

1. Van de lijst van gegevensbronnen, klik **[!UICONTROL Add]** om een nieuwe externe gegevensbron tot stand te brengen.

   ![](../assets/journey25.png)

   Dit opent de ruit van de gegevensbronconfiguratie op de rechterkant van het scherm.

   ![](../assets/journey26.png)

1. Ga een naam voor uw gegevensbron in.

   >[!NOTE]
   >
   >Gebruik geen spaties of speciale tekens. Gebruik niet meer dan 30 tekens.

1. Voeg een beschrijving aan uw gegevensbron toe. Deze stap is facultatief.
1. Voeg URL van de externe dienst toe. In ons voorbeeld: _https://api.adobeweather.org/weather_.

   >[!CAUTION]
   >
   >Wij adviseren sterk gebruikend HTTPS voor veiligheidsoverwegingen. Merk ook op dat wij niet het gebruik van de adressen van Adobe toestaan die niet openbaar beschikbaar en het gebruik van IP adressen zijn.

   ![](../assets/journey27.png)

1. Vorm de authentificatie afhankelijk van de externe de dienstconfiguratie: **[!UICONTROL No authentication]**, **[!UICONTROL Basic]**, **[!UICONTROL Custom]** of **[!UICONTROL API key]**. Voor meer informatie over de wijze van de douaneauthentificatie, zie [](../datasource/external-data-sources.md#section_wjp_nl5_nhb). In ons voorbeeld kiezen wij:


   * **[!UICONTROL Type]**: &quot;API-sleutel&quot;
   * **[!UICONTROL Value]**: &quot;1234&quot; (dit is de waarde van onze API-sleutel)
   * **[!UICONTROL Name]**: &quot;appid&quot; (dit is de API-sleutelparameternaam)
   * **[!UICONTROL Location]**: &quot;De parameter van de vraag&quot; (de API sleutel wordt gevestigd in URL)
   ![](../assets/journey28.png)

1. Voeg een nieuwe gebiedsgroep voor elke API parameter toe die door te klikken wordt geplaatst **[!UICONTROL Add a New Field Group]**. Gebruik geen spaties of speciale tekens in de naam van de veldgroep. In ons voorbeeld, moeten wij twee gebiedsgroepen tot stand brengen, voor elke parameterreeks (stad en lang/lat).

Voor de &quot;long/lat&quot;parameterreeks, creëren wij een gebiedsgroep met de volgende informatie:

* **[!UICONTROL Used in]**: toont het aantal ritten die een gebiedsgroep gebruiken. U kunt het **[!UICONTROL View journeys]** pictogram klikken om de lijst van reizen te tonen gebruikend deze gebiedsgroep.
* **[!UICONTROL Method]**: selecteer de POST of KRIJG methode. In ons geval, selecteren wij de GET methode.
* **[!UICONTROL Cache duration]**: in ons geval willen wij dat het weer tien minuten in beslag wordt genomen .
* **[!UICONTROL Response Payload]**: klik binnen het **[!UICONTROL Payload]** gebied en deeg een voorbeeld van de nuttige lading die door de vraag is teruggekeerd. Bijvoorbeeld, gebruikten wij een lading die op een weer API website wordt gevonden. Verifieer dat de gebiedstypes correct zijn. Telkens als API wordt geroepen, zal het systeem alle gebieden terugwinnen inbegrepen in het ladingsvoorbeeld. Merk op dat u kunt klikken op **[!UICONTROL Paste a new payload]** als u de momenteel overgegaane nuttige lading wilt veranderen.
* **[!UICONTROL Dynamic Values]**: ga de verschillende parameters in die door een coma worden gescheiden, &quot;lang, lat&quot;in ons voorbeeld. Aangezien de parameterwaarden van de uitvoeringscontext afhangen, zullen zij in de reizen worden bepaald. Zie [](../expression/expressionadvanced.md).
* **[!UICONTROL Sent Payload]**: dit veld staat niet in ons voorbeeld . Het is slechts beschikbaar als u de POST methode selecteert. Plak de lading die naar het derdesysteem zal worden verzonden.

In het geval van een GET vraag die parameter(s) vereist, voert u de parameter(s) in het **[!UICONTROL Parameters]** veld in en worden deze aan het einde van de oproep automatisch toegevoegd. In het geval van een POST vraag, moet u:

* maak een lijst van de parameters die bij vraagtijd op het **[!UICONTROL Parameter]** gebied (in het voorbeeld hieronder) moeten worden overgegaan: &quot;identificator&quot;).
* specificeer hen ook met de nauwkeurige zelfde syntaxis in het lichaam van de verzonden nuttige lading. Om dit te doen, moet u toevoegen: &quot;param&quot;: &quot;naam van uw parameter&quot; (in het onderstaande voorbeeld: &quot;identificator&quot;). Volg de syntaxis hieronder:

   ```
   {"id":{"param":"identifier"}}
   ```

![](../assets/journey29.png)

Klik **[!UICONTROL Save]**.

De gegevensbron wordt nu gevormd en klaar om in uw reizen, bijvoorbeeld in uw voorwaarden te worden gebruikt of een e-mail te personaliseren. Als de temperatuur boven 30°C ligt, kunt u beslissen een specifieke communicatie te verzenden.

## Aangepaste verificatiemodus{#section_wjp_nl5_nhb}

Deze authentificatiewijze wordt gebruikt voor complexe authentificatie, die vaak wordt gebruikt om API te roepen die protocollen zoals OAuth2 verpakt, om een toegangsteken terug te winnen dat in het echte HTTP- verzoek om de actie moet worden ingespoten.

Wanneer u de douaneauthentificatie vormt, kunt u op de hieronder knoop klikken om te controleren of wordt de nuttige lading van de douaneauthentificatie correct gevormd.

![](../assets/journey29-bis.png)

Als de test succesvol is, wordt de knoop groen.

![](../assets/journey29-ter.png)

Met deze authentificatie, is de actieuitvoering een proces in twee stappen:

1. Oproepen het eindpunt om het toegangsteken te produceren.
1. Oproepen REST API door op de juiste manier het toegangsteken te injecteren.

Deze authentificatie heeft twee delen.

De definitie van het eindpunt dat moet worden geroepen om het toegangsteken te produceren:

* eindpunt: URL aan gebruik om het eindpunt te produceren
* methode van het HTTP- verzoek op het eindpunt (KRIJG of POST)
* koppen: sleutel/waardeparen die als kopballen in deze vraag moeten worden geïnjecteerd indien nodig
* lichaam: beschrijft het lichaam van de vraag als de methode POST is. Wij steunen een beperkte lichaamsstructuur, die in bodyParams (zeer belangrijke/waardeparen) wordt bepaald. BodyType beschrijft het formaat en het coderen van het lichaam in de vraag:
   * &quot;formulier&quot;: betekenend dat het inhoudstype application/x-www-vorm-urlencoded (charset UTF-8) zal zijn en de sleutel/waardeparen zullen in series worden vervaardigd zoals is: key1=value1&amp;key2=value2&amp;...
   * &quot;json&quot;: betekenend dat het inhoudstype application/json (charset UTF-8) zal zijn en de belangrijkste waardeparen zullen in series worden vervaardigd als json voorwerp zoals is: _{&quot;key1&quot;: &quot;value1&quot;, &quot;key2&quot;: &quot;value2&quot;, ...}_

De definitie van de manier het toegangsteken in het HTTP- verzoek van de actie moet worden ingespoten:

* autorisatieType: bepaalt hoe het geproduceerde toegangsteken in de vraag van HTTP naar de actie moet worden ingespoten. De mogelijke waarden zijn:

   * drager: wijst erop dat het toegangsteken in de kopbal van de Vergunning moet worden ingespoten, zoals: _Vergunning: Drager &lt;toegangsteken>_
   * koptekst: wijst erop dat het toegangsteken als kopbal moet worden ingespoten, de kopbalnaam die door het bezit wordt bepaald tokenTarget. Bijvoorbeeld, als tokenTarget myHeader is, zal het toegangsteken als header worden geïnjecteerd als: _myHeader: &lt;toegangstoken>_
   * queryParam: wijst erop dat het toegangsteken als queryParam moet worden ingespoten, de naam van het vraagparam die door het bezit wordt bepaald tokenTarget. Bijvoorbeeld, als tokenTarget myQueryParam is, zal URL van de actievraag zijn: _&lt;url>?myQueryParam=&lt;access token>_

* tokenInResponse: wijst erop hoe te om het toegangsteken uit de authentificatievraag te halen. Dit bezit kan zijn:
   * &quot;antwoord&quot;: wijst erop dat de reactie van HTTP het toegangsteken is
   * een selecteur in een zoon (veronderstellend dat de reactie een zoon is, steunen wij geen andere formaten zoals XML). Het formaat van deze selecteur is _json://&lt;path aan het toegangsteken bezit>_. Bijvoorbeeld, als de reactie van de vraag is: _{&quot;access_token&quot;: &quot;theToken&quot;, &quot;timestamp&quot;: 12323445656}_, zal tokenInResponse zijn: _json: //access_token_

Het formaat van deze authentificatie is:

```
{
    "type": "customAuthorization",
    "authorizationType": "<value in 'bearer', 'header' or 'queryParam'>",
    (optional, mandatory if authorizationType is 'header' or 'queryParam') "tokenTarget": "<name of the header or queryParam if the authorizationType is 'header' or 'queryParam'>",
    "endpoint": "<URL of the authentication endpoint>",
    "method": "<HTTP method to call the authentication endpoint, in 'GET' or 'POST'>",
    (optional) "headers": {
        "<header name>": "<header value>",
        ...
    },
    (optional, mandatory if method is 'POST') "body": {
        "bodyType": "<'form'or 'json'>,
        "bodyParams": {
            "param1": value1,
            ...

        }
    },
    "tokenInResponse": "<'response' or json selector in format 'json://<field path to access token>'"
}
```
