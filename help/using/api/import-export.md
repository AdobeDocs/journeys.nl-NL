---
product: adobe campaign
title: Export API-beschrijving importeren
description: Meer informatie over de import-API voor exporteren.
products: journeys
source-git-commit: 8f409fe6e37a3b80527d9a5514b066e539dcd9f3
workflow-type: tm+mt
source-wordcount: '1119'
ht-degree: 19%

---


# Werken met API voor exporteren

Exporteer een reisversie en alle bijbehorende objecten (transport, gebeurtenissen, gegevensbronnen, veldgroepen, aangepaste handelingen) met één API-aanroep. De resulterende exportlading kan worden gebruikt om de reis in een andere milieu (instantie of zandbak) gemakkelijk in te voeren.
Met deze functie kunt u uw reizen in meerdere exemplaren of voor meerdere workflows voor testomgevingen beheren.


## Bronnen

De API voor het exporteren en importeren van Journeys Orchestration wordt beschreven in een wagerbestand [hier](https://adobedocs.github.io/JourneyAPI/docs/).

Als u deze API met uw Journey Orchestration-instantie wilt gebruiken, moet u de AdobeI/O-console gebruiken. U kunt beginnen door dit te volgen [Aan de slag met Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) en gebruikt u vervolgens de secties op deze pagina.

Voor het testen en voorbereiden van uw integratie is een Postman-collectie beschikbaar [hier](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json).


## Exporteren en importeren

We raden u aan deze stappen te volgen om uw reizen te exporteren en te importeren in verschillende omgevingen:

1. Maak en parameter een reis in uw beginomgeving. [Meer informatie hier](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/about-journey-building/journey.html?lang=nl-NL)
1. Controleer of de reisversie geen fout bevat. [Meer informatie hier](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/testing-the-journey.html?lang=nl-NL)
1. Bellen **/lijst/reizen** API om de reis van UID en UID van uw recentste reisversie terug te winnen. Indien nodig, kunt u roepen **/trajecten/`{uid}`/last** om de UID van uw meest recente reisversie te vinden.
1. Roep de **export** API met de parameters van uw beginomgeving (orgID en sandboxName).
1. Open de geretourneerde lading en controleer vervolgens de volgende items:
   * Als uw geëxporteerde transport **specifieke referenties**, moet u deze geloofsbrieven met die vervangen die aan het nieuwe milieu beantwoorden.
   * Als uw geëxporteerde transport **gebeurtenissen** dat een **XDM-schema**, moet u de verwijzing van schemaidentiteitskaart met schemaidentiteitskaart van het nieuwe milieu in de xdmEntiteitsknoop manueel bijwerken als IDs waarden verschillend zijn. Deze update moet voor elke gebeurtenis worden uitgevoerd. [Meer informatie hier](https://experienceleague.adobe.com/docs/journeys/using/events-journeys/experience-event-schema.html?lang=nl-NL)
   * Als uw reis e-mail, sms of duw acties bevat, kunt u de malplaatjenaam of de naam moeten bijwerken mobileApp als de naam in het doelmilieu van verschillend is dan die in uw beginmilieu.
1. Roep de **Importeren** API met de parameters van uw doelomgeving (orgID en sandboxName). Let erop dat u de import-API zo vaak kunt aanroepen als u wilt. De UUID en de naam van elk voorwerp in de reis worden geproduceerd telkens als u de invoer API roept.
1. Nadat u de Reis hebt geïmporteerd, kunt u deze publiceren in de toepassing Journey Orchestration. Meer informatie [hier](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/publishing-the-journey.html?lang=nl-NL)


## Authentificatie

### API-toegang instellen

API-toegang voor Journeys Orchestration wordt ingesteld via de onderstaande stappen. Elk van deze stappen is gedetailleerd beschreven in de [Adobe I/O-documentatie](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Om certificaten te beheren in Adobe I/O hebt u <b>systeembeheerders</b>rechten nodig voor de organisatie of een [ontwikkelaarsaccount](https://helpx.adobe.com/nl/enterprise/using/manage-developers.html) in de Admin-console.

1. **Controleer of u een digitaal certificaat hebt**, of maak er zo nodig een. De bij het certificaat geleverde openbare en privésleutels zijn nodig bij de volgende stappen.
1. **Maak een nieuwe integratie met [!DNL Journey Orchestration] Service** in Adobe I/O en configureer deze. Toegang tot het productprofiel is vereist voor Journey Orchestration en Adobe Experience Platform. Uw referenties worden dan gegenereerd (API-sleutel, klantgeheim...).

>[!CAUTION]
>
>De JWT-methode voor het genereren van toegangstokens is afgekeurd. Alle nieuwe integraties moeten worden gecreëerd met de [OAuth Server-aan-Server authentificatiemethode](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html?lang=nl-NL#select-oauth-server-to-server). De Adobe adviseert ook dat u uw bestaande integraties aan de methode OAuth migreert.
>
>Lees de volgende belangrijke documentatie:
>[Migratiehandleiding voor uw toepassingen van JWT naar OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/),
>[Implementatiehandleiding voor nieuwe en oude toepassingen met OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/),
>[Voordelen om de server-aan-server van OAuth methode van geloofsbrieven te gebruiken](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/#why-oauth-server-to-server-credentials)


Om een veilige Adobe I/O API-sessie tussen services tot stand te brengen moet elk verzoek aan een Adobe-service de onderstaande informatie bevatten in de autorisatieheader.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZATION>**: dit is uw persoonlijke ORGANISATIE-ID. Adobe verstrekt één ORGANISATIE-ID voor elk van uw instanties :

   * &lt;organization> : de productie-instantie

  Voor het verkrijgen van uw ORGANISATIE-ID-waarde raadpleegt u uw beheerder of uw technische contactpersoon bij Adobe. U kunt hem ook ophalen in Adobe I/O wanneer u een nieuwe integratie maakt, in de licentielijst (zie de [Adobe I/O-documentatie](https://www.adobe.io/authentication.html)).

* **&lt;access_token>**: Uw persoonlijke toegangstoken

* **&lt;API_KEY>**: uw persoonlijke API-sleutel. Deze wordt geleverd in Adobe I/O na het maken van een nieuwe integratie met [!DNL Journey Orchestration] Service.



## Beschrijving van API voor exporteren

Met deze API kunt u een reisversie exporteren die wordt geïdentificeerd door de bijbehorende UID en alle gerelateerde objecten (transport, gebeurtenissen, gegevensbronnen, veldgroepen, aangepaste acties) door de uid.
De resulterende lading kan worden gebruikt om de reisversie in een andere milieu (zandbak of instantie) in te voeren.

| Methode | Pad | Beschrijving |
|---|---|---|
| `[POST]` | /tripVersions/import | De inhoud van een reisversie importeren die het resultaat is van de export van een reisversie |
| `[GET]` | /tripVersions/`{uid}`/export | Een reisversie exporteren |
| `[GET]` | /trajecten/`{uid}`/last | De nieuwste reisversie voor een reis |
| `[POST]` | /lijst/reizen | Hier worden de metagegevens van de ritten en de reisversies vermeld |


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

* At **exporttijd**, als de reisversie ongeldig is: fout 500

* At **importtijd**, als de lading na wijzigingen niet geldig is of als de geloofsbrieven niet duidelijk in de lading worden bepaald: fout 400

* Als na de importstap de XDM-schema-id voor uw gebeurtenissen niet geldig is in de doelomgeving, wordt een fout weergegeven in de toepassing Journey Orchestration. In dat geval kan de reis niet worden gepubliceerd.