---
product: adobe campaign
title: Aan de slag met reis-API's
description: Meer informatie over reis-API's
products: journeys
feature: Journeys
role: User
level: Intermediate
source-git-commit: 137637a753ba44cc4f8e397b77c3fc076ec3de3f
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 1%

---

# Aan de slag met reis-API&#39;s

## Informatie over API&#39;s voor uitlijnen en draaien

Wanneer het vormen van een gegevensbron of een actie, vestigt u een verbinding aan een systeem om of extra informatie terug te winnen om in uw reizen te gebruiken of berichten of API vraag te verzenden.

Reis-API&#39;s ondersteunen maximaal 5000 gebeurtenissen per seconde, maar sommige externe systemen of API&#39;s hebben mogelijk geen equivalente doorvoer. Om overbelasting van deze systemen te voorkomen, kunt u de **Afbeelding** en **Throttling** API&#39;s om het aantal verzonden gebeurtenissen per seconde te beperken.

Telkens wanneer een API-aanroep door reizen wordt uitgevoerd, loopt deze door de API-engine. Als de limiet die in de API is ingesteld, wordt de aanroep afgewezen als u de API voor uitsnijden gebruikt, of zo snel mogelijk in de volgorde waarin deze is ontvangen als u de API voor rotatie gebruikt in de wachtrij en verwerkt.

Stel bijvoorbeeld dat u voor uw externe systeem een regel hebt gedefinieerd voor het bijsnijden of vertragen van 100 aanroepen per seconde. Uw systeem wordt opgeroepen door een aangepaste actie tijdens 10 verschillende reizen. Als één reis 200 vraag per seconde ontvangt, zal het de 100 beschikbare groeven gebruiken en zal verwerpen of de 100 resterende groeven in de rij plaatsen. Aangezien het maximumtarief is overschreden, zullen de overige 9 reizen geen slots meer hebben. Deze granulariteit helpt het externe systeem te beschermen tegen overbelasting en vastlopen.

>[!IMPORTANT]
>
>**Afdekregels** worden geconfigureerd op sandboxniveau voor een specifiek eindpunt (de URL wordt aangeroepen), maar globaal voor alle reizen van die sandbox.
>
>**Throtatieregels** alleen geconfigureerd zijn op productiestanddozen, voor een specifiek eindpunt maar globaal voor alle reizen over alle sandboxen. U kunt slechts één throttling configuratie per organisatie hebben.

Raadpleeg de volgende secties voor meer informatie over het werken met deze API&#39;s:

* [API voor uitlijnen](capping.md)
* [Throttling API](throttling.md)

Beide API&#39;s worden ook beschreven in een Swagger-bestand dat beschikbaar is [hier](https://adobedocs.github.io/JourneyAPI/docs/).

## Gegevensbronnen en aangepaste handelingscapaciteit {#capacity}

Voor **externe gegevensbronnen**, is het maximumaantal oproepen per seconde beperkt tot 15. Als deze limiet wordt overschreden, worden eventuele aanvullende aanroepen genegeerd of in een wachtrij geplaatst, afhankelijk van de gebruikte API. Het is mogelijk om deze grens voor privé externe gegevensbronnen te verhogen door Adobe te contacteren om het eindpunt in de lijst van gewenste personen op te nemen, maar dit is geen optie voor openbare externe gegevensbronnen. * [Leer hoe te om gegevensbronnen te vormen](../datasource/about-data-sources.md).

>[!NOTE]
>
>Als een gegevensbron een douaneauthentificatie met een verschillend eindpunt dan gebruikt voor de gegevensbron gebruikt, moet u Adobe contacteren om dat eindpunt in de lijst van gewenste personen ook te omvatten.

Voor **aangepaste handelingen**, moet u de capaciteit van uw externe API evalueren. Bijvoorbeeld, als Journey Optimizer 1000 vraag per seconde verzendt en uw systeem slechts 100 vraag per seconde kan steunen, moet u een het in kaart brengen of het gooien configuratie bepalen zodat uw systeem niet verzadigt. [Leer hoe u handelingen configureert](../action/action.md)

## API-toegang instellen {#api}

Deze API&#39;s gebruiken met uw [!DNL Journey Orchestration] -instantie, moet u de AdobeI/O-console gebruiken. [!DNL Journey Orchestration] API-toegang wordt ingesteld via de onderstaande stappen. Elk van deze stappen wordt beschreven in [Adobe I/O-documentatie](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Als u certificaten wilt beheren in Adobe I/O, moet u ervoor zorgen dat u beschikt over <b>Systeembeheerder</b> rechten van de organisatie of [ontwikkelaarsaccount](https://helpx.adobe.com/enterprise/using/manage-developers.html) in de beheerconsole.

1. **Controleer of u een digitaal certificaat hebt** of maak indien nodig een sjabloon. De openbare en persoonlijke sleutels die van het certificaat worden voorzien zijn vereist in de volgende stappen.
1. **Een nieuwe integratie maken voor [!DNL Journey Orchestration] Service** in Adobe I/O en configureren. Toegang tot het productprofiel is vereist voor [!DNL Journey Orchestration] en Adobe Experience Platform. Uw referenties worden vervolgens gegenereerd (API-sleutel, clientgeheim...).
1. **Een JSON-webtoken (JWT) maken** uit de eerder gegenereerde referenties en deze ondertekenen met uw persoonlijke sleutel. De JWT codeert alle identiteits- en beveiligingsgegevens die Adobe nodig heeft om uw identiteit te verifiëren en u toegang tot de API te verlenen. Deze stap wordt in deze [sectie](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Uitwisseling uw JWT voor een Token van de Toegang** via een POST-aanvraag of via de Developer Console Interface. Dit toegangstoken moet worden gebruikt in elke header van uw API-aanvragen.

Om een veilige service-to-service Adobe I/O API-sessie tot stand te brengen, moet elke aanvraag naar een Adobe-service de onderstaande informatie bevatten in de machtigingheader.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**: Dit is uw persoonlijke ORGANISATIE-id. Eén ORGANISATIE-id wordt door Adobe opgegeven voor elk van uw varianten. Raadpleeg de beheerder of uw technische contactpersoon voor Adobe om de waarde van uw ORGANISATIE-id op te vragen. U kunt het in Adobe I/O ook terugwinnen wanneer het creëren van een nieuwe integratie, in de vergunningslijst (zie <a href="https://www.adobe.io/authentication.html">Adobe I/O-documentatie</a>).

* **&lt;access_token>**: Uw persoonlijk toegangstoken, dat werd teruggewonnen toen het ruilen van uw JWT door een verzoek van de POST.

* **&lt;api_key>**: uw persoonlijke API-sleutel. Het wordt aangeboden in Adobe I/O nadat een nieuwe integratie is gecreëerd in [!DNL Journey Orchestration] Service.
