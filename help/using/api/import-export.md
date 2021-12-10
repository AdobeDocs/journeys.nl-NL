---
product: adobe campaign
title: Export API-beschrijving importeren
description: Meer informatie over de import-API voor exporteren.
products: journeys
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '1123'
ht-degree: 1%

---


# Werken met API voor exporteren

Exporteer een reisversie en alle bijbehorende objecten (transport, gebeurtenissen, gegevensbronnen, veldgroepen, aangepaste handelingen) met één API-aanroep. De resulterende exportlading kan worden gebruikt om de reis in een andere milieu (instantie of zandbak) gemakkelijk in te voeren.
Met deze functie kunt u uw reizen in meerdere exemplaren of voor meerdere workflows voor testomgevingen beheren.


## Bronnen

De API voor exporteren en importeren van Journey Orchestration wordt beschreven in een wagerbestand dat beschikbaar is [hier](https://adobedocs.github.io/JourneyAPI/docs/).

Als u deze API met uw Journey Orchestration-instantie wilt gebruiken, moet u de AdobeI/O-console gebruiken. U kunt beginnen door dit te volgen [Aan de slag met Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) en gebruikt u vervolgens de secties op deze pagina.

Om uw integratie te testen en voor te bereiden, is een verzameling Postman beschikbaar [hier](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json).


## Exporteren en importeren, stroom

We raden u aan deze stappen te volgen om uw reizen te exporteren en te importeren in verschillende omgevingen:

1. Maak en parameter een reis in uw beginomgeving. [Meer informatie hier](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/about-journey-building/journey.html)
1. Controleer of de reisversie geen fout bevat. [Meer informatie hier](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/testing-the-journey.html)
1. Bellen **/lijst/reizen** API om de reis van UID en UID van uw recentste reisversie terug te winnen. Indien nodig, kunt u roepen **/trajecten/`{uid}`/last** om de UID van uw meest recente reisversie te vinden.
1. Roep de **export** API met de parameters van uw beginomgeving (orgID en sandboxName).
1. Open de geretourneerde lading en controleer vervolgens de volgende items:
   * Als uw geëxporteerde transport **specifieke referenties**, moet u deze geloofsbrieven met die vervangen die aan het nieuwe milieu beantwoorden.
   * Als uw geëxporteerde transport **gebeurtenissen** dat **XDM-schema**, moet u de verwijzing van schemaidentiteitskaart met schemaidentiteitskaart van het nieuwe milieu in de xdmEntiteitsknoop manueel bijwerken als IDs waarden verschillend zijn. Deze update moet voor elke gebeurtenis worden uitgevoerd. [Meer informatie hier](https://experienceleague.adobe.com/docs/journeys/using/events-journeys/experience-event-schema.html)
   * Als uw reis e-mail, sms of duw acties bevat, kunt u de malplaatjenaam of de naam moeten bijwerken mobileApp als de naam in het doelmilieu van verschillend is dan die in uw beginmilieu.
1. Roep de **Importeren** API met de parameters van uw doelomgeving (orgID en sandboxName). Let erop dat u de import-API zo vaak kunt aanroepen als u wilt. De UUID en de naam van elk voorwerp in de reis worden geproduceerd telkens als u de invoer API roept.
1. Nadat u de Reis hebt geïmporteerd, kunt u deze publiceren in de Journey Orchestration-toepassing. Meer informatie [hier](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/publishing-the-journey.html)


## Verificatie

### API-toegang instellen

Journey Orchestration API-toegang wordt ingesteld via de onderstaande stappen. Elk van deze stappen wordt beschreven in [Adobe I/O-documentatie](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Als u certificaten wilt beheren in Adobe I/O, moet u ervoor zorgen dat u beschikt over <b>Systeembeheerder</b> rechten van de organisatie of [ontwikkelaarsaccount](https://helpx.adobe.com/enterprise/using/manage-developers.html) in de beheerconsole.

1. **Controleer of u een digitaal certificaat hebt** of maak indien nodig een sjabloon. De openbare en persoonlijke sleutels die van het certificaat worden voorzien zijn vereist in de volgende stappen.
1. **Een nieuwe integratie maken voor [!DNL Journey Orchestration] Service** in Adobe I/O en configureren. Toegang tot het productprofiel is vereist voor Journey Orchestration en Adobe Experience Platform. Uw referenties worden vervolgens gegenereerd (API-sleutel, clientgeheim...).
1. **Een JSON-webtoken (JWT) maken** uit de eerder gegenereerde referenties en deze ondertekenen met uw persoonlijke sleutel. De JWT codeert alle identiteits- en beveiligingsgegevens die Adobe nodig heeft om uw identiteit te verifiëren en u toegang tot de API te verlenen. Deze stap wordt in deze [sectie](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Uitwisseling uw JWT voor een Token van de Toegang** via een POST-aanvraag of via de Developer Console Interface. Dit toegangstoken moet worden gebruikt in elke header van uw API-aanvragen.

Om een veilige service-to-service Adobe I/O API-sessie tot stand te brengen, moet elke aanvraag naar een Adobe-service de onderstaande informatie bevatten in de machtigingheader.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**: Dit is uw persoonlijke ORGANIZATION ID, één ORGANIZATION ID wordt verstrekt door Adobe voor elk van uw instanties:

   * &lt;organization> : productie-instantie
   Raadpleeg de beheerder of uw technische contactpersoon voor Adobe om de waarde van uw ORGANISATIE-id op te vragen. U kunt het in Adobe I/O ook terugwinnen wanneer het creëren van een nieuwe integratie, in de vergunningslijst (zie [Adobe I/O-documentatie](https://www.adobe.io/authentication.html)).

* **&lt;access_token>**: Uw persoonlijk toegangstoken, dat werd teruggewonnen toen het ruilen van uw JWT door een verzoek van de POST.

* **&lt;api_key>**: uw persoonlijke API-sleutel. Het wordt aangeboden in Adobe I/O nadat een nieuwe integratie is gecreëerd in [!DNL Journey Orchestration] Service.



## Beschrijving van API voor exporteren

Met deze API kunt u een reisversie exporteren die wordt geïdentificeerd door de bijbehorende UID en alle gerelateerde objecten (transport, gebeurtenissen, gegevensbronnen, veldgroepen, aangepaste handelingen) door de uid.
De resulterende lading kan worden gebruikt om de reisversie in een andere milieu (zandbak of instantie) in te voeren.

| Methode | Pad | Beschrijving |
|---|---|---|
| `[POST]` | /tripVersions/import | De inhoud van een reisversie importeren die het resultaat is van de export van een reisversie |
| `[GET]` | /tripVersions/`{uid}`/export | Een reisversie exporteren |
| `[GET]` | /trajecten/`{uid}`/last | De nieuwste reisversie voor een reis |
| `[POST]` | /lijst/reizen | Hier worden de metagegevens van de reizen en de reisversies vermeld |


### Exportkenmerken en -geleiders

* De reis moet geldig zijn vóór de uitvoer.

* De geloofsbrieven worden niet uitgevoerd en placeholder (d.w.z. INSERT_SECRET_HERE) wordt opgenomen in de antwoordlading.
Na de de uitvoervraag, moet u de nieuwe geloofsbrieven (die aan het doelmilieu beantwoorden) manueel opnemen alvorens de lading in het doelmilieu in te voeren.

* De volgende objecten worden geëxporteerd, maar worden nooit geïmporteerd in de doelomgeving. Dit zijn systeemmiddelen die automatisch door Journey Orchestration worden beheerd. U hoeft &quot;INSERT_SECRET_HERE&quot; niet te vervangen.
   * **DataProviders**: &quot;Adobe Campaign Standard Data Provider&quot; (acsDataProvider) en &quot;Experience Platform&quot; (acppsDataProvider)
   * **Veldgroepen** (dataEntities): &quot;ProfileFieldGroup&quot; (acppsDataPack)



### Importkenmerken

* Tijdens het importeren worden de reisobjecten gemaakt met een nieuwe UID en een nieuwe naam om ervoor te zorgen dat de doelomgeving (instantie of sandbox) uniek is.

* Als de importpayload geheime plaatsaanduidingen bevat, wordt een fout gegenereerd. U moet de referentie-informatie vervangen voordat de POST belt om de reis te importeren.

## Waarschuwing en fouten

De mogelijke fouten zijn:

* At **exporttijd**, indien de reisversie niet geldig is: fout 500

* At **importtijd**, als de lading na wijzigingen niet geldig is of als de geloofsbrieven niet duidelijk in de lading worden bepaald: fout 400

* Als na de importstap de XDM-schema-id voor uw gebeurtenissen niet geldig is in de doelomgeving, wordt een fout weergegeven in de Journey Orchestration-toepassing. In dat geval kan de reis niet worden gepubliceerd.