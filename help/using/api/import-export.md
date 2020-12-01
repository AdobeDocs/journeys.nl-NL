---
product: adobe campaign
solution: Journey Orchestration
title: Export API-beschrijving importeren
description: Meer informatie over de import-API voor exporteren.
products: journeys
translation-type: tm+mt
source-git-commit: 8da1d4a6c01279bf502c3ec39bdaba8fcc8e64f8
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 2%

---


# Werken met API voor exporteren

Exporteer een reisversie en alle bijbehorende objecten (transport, gebeurtenissen, gegevensbronnen, veldgroepen, aangepaste handelingen) met één API-aanroep. De resulterende exportlading kan worden gebruikt om de reis in een andere milieu (instantie of zandbak) gemakkelijk in te voeren.
Met deze functie kunt u uw reizen in meerdere exemplaren of voor meerdere workflows voor testomgevingen beheren.


## Bronnen

De API voor exporteren en importeren van Journey Orchestration wordt beschreven in een [hier](https://adobedocs.github.io/JourneyAPI/docs/)beschikbaar wagerbestand.

Als u deze API met uw Journey Orchestration-instantie wilt gebruiken, moet u de AdobeI/O-console gebruiken. U kunt beginnen door dit te volgen [Aan de slag met de Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) van de Ontwikkelaar van Adobe en dan de secties in deze pagina te gebruiken.

Om uw integratie te testen en voor te bereiden, is een inzameling van Postman beschikbaar [hier](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json).


## Exporteren en importeren, stroom

We raden u aan deze stappen te volgen om uw reizen te exporteren en te importeren in verschillende omgevingen:

1. Maak en parameter een reis in uw beginomgeving. [Meer informatie hier](https://docs.adobe.com/content/help/nl-NL/journeys/using/building-journeys/about-journey-building/journey.html)
1. Controleer of de reisversie geen fout bevat. [Meer informatie hier](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/testing-the-journey.html)
1. Bel **de API voor lijsten/reizen** om de UID-reis en de UID van uw nieuwste reisversie op te halen. Indien nodig kunt u bellen **/reizen/`{uid}`/laatste** zoeken naar de UID van uw meest recente reisversie.
1. Roep de **export** -API aan met de parameters van de beginomgeving (orgID en sandboxName).
1. Open de geretourneerde lading en controleer vervolgens de volgende items:
   * Als uw geëxporteerde reis **specifieke gegevens** bevat, moet u deze gegevens vervangen door de gegevens die overeenkomen met de nieuwe omgeving.
   * Als uw geëxporteerde reis **gebeurtenissen** bevat die naar een **XDM-schema** wijzen, moet u de referentie van de schema-id handmatig bijwerken met de schema-id van de nieuwe omgeving in het xdmEntiteitsknooppunt als de waarden van de id&#39;s verschillend zijn. Deze update moet voor elke gebeurtenis worden uitgevoerd. [Meer informatie hier](https://docs.adobe.com/content/help/en/journeys/using/events-journeys/experience-event-schema.html)
   * Als uw reis e-mail, sms of duw acties bevat, kunt u de malplaatjenaam of de naam moeten bijwerken mobileApp als de naam in het doelmilieu van verschillend is dan die in uw beginmilieu.
1. Roep de API voor **importeren** aan met de parameters van de doelomgeving (orgID en sandboxName). Let erop dat u de import-API zo vaak kunt aanroepen als u wilt. De UUID en de naam van elk voorwerp in de reis worden geproduceerd telkens als u de invoer API roept.
1. Nadat u de Reis hebt geïmporteerd, kunt u deze publiceren in de Journey Orchestration-toepassing. Meer informatie [hier](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/publishing-the-journey.html)


## Verificatie

### API-toegang instellen

Journey Orchestration API-toegang wordt ingesteld via de onderstaande stappen. Elk van deze stappen wordt beschreven in de documentatie [van](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)Adobe I/O.

>[!CAUTION]
>
>Om certificaten in Adobe I/O te beheren, zorg ervoor u de beheerderrechten van het <b>Systeem</b> op de organisatie of een rekening [van de](https://helpx.adobe.com/enterprise/using/manage-developers.html) ontwikkelaar in de Admin console hebt.

1. **Controleer of u een digitaal certificaat** hebt of maak er zo nodig een. De openbare en persoonlijke sleutels die van het certificaat worden voorzien zijn vereist in de volgende stappen.
1. **Creëer een nieuwe integratie van de [!DNL Journey Orchestration] Dienst** in Adobe I/O en vorm het. Toegang tot het productprofiel is vereist voor Journey Orchestration en Adobe Experience Platform. Uw referenties worden vervolgens gegenereerd (API-sleutel, clientgeheim...).
1. **Maak een JSON Web Token (JWT)** van de eerder gegenereerde referenties en onderteken deze met uw persoonlijke sleutel. De JWT codeert alle identiteits- en beveiligingsgegevens die Adobe nodig heeft om uw identiteit te verifiëren en u toegang tot de API te verlenen. Deze stap wordt beschreven in deze [sectie](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Uitwisseling uw JWT voor een Token** van de Toegang door een verzoek van de POST of via de Interface van de Console van de Ontwikkelaar. Dit toegangstoken moet worden gebruikt in elke header van uw API-aanvragen.

Om een veilige dienst-aan-dienst Adobe I/O API zitting tot stand te brengen, moet elk verzoek aan de dienst van de Adobe in de kopbal van de Vergunning de informatie hieronder omvatten.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANISATIE>**: Dit is uw persoonlijke ORGANIZATION ID, één ORGANIZATION ID wordt verstrekt door Adobe voor elk van uw instanties:

   * &lt;ORGANISATIE>: productie-instantie
   Raadpleeg de beheerder of uw technische contactpersoon voor Adobe om de waarde van uw ORGANISATIE-id op te vragen. U kunt de toepassing ook ophalen in Adobe I/O wanneer u een nieuwe integratie maakt, in de lijst met licenties (zie de documentatie bij [](https://www.adobe.io/authentication.html)Adobe I/O).

* **&lt;ACCESS_TOKEN>**: Uw persoonlijk toegangstoken, dat werd teruggewonnen toen het ruilen van uw JWT door een verzoek van de POST.

* **&lt;API_KEY>**: uw persoonlijke API-sleutel. Het wordt geleverd in Adobe I/O na het creëren van een nieuwe integratie aan de [!DNL Journey Orchestration] Dienst.



## Beschrijving van API voor exporteren

Met deze API kunt u een reisversie exporteren die wordt geïdentificeerd door de bijbehorende UID en alle gerelateerde objecten (transport, gebeurtenissen, gegevensbronnen, veldgroepen, aangepaste acties) door de uid.
De resulterende lading kan worden gebruikt om de reisversie in een andere milieu (zandbak of instantie) in te voeren.

| Methode | Pad | Beschrijving |
|---|---|---|
| `[POST]` | /tripVersions/import | De inhoud van een reisversie importeren die het resultaat is van de export van een reisversie |
| `[GET]` | /transportVersions/`{uid}`/export | Een reisversie exporteren |
| `[GET]` | /trajecten/`{uid}`/laatste | De nieuwste reisversie voor een reis |
| `[POST]` | /lijst/reizen | Hier worden de metagegevens van de reizen en de reisversies vermeld |


### Exportkenmerken en -geleiders

* De reis moet geldig zijn vóór de uitvoer.

* De geloofsbrieven worden niet uitgevoerd en placeholder (d.w.z. INSERT_SECRET_HERE) wordt opgenomen in de antwoordlading.
Na de de uitvoervraag, moet u de nieuwe geloofsbrieven (die aan het doelmilieu beantwoorden) manueel opnemen alvorens de lading in het doelmilieu in te voeren.

* De volgende objecten worden geëxporteerd, maar worden nooit geïmporteerd in de doelomgeving. Dit zijn systeemmiddelen die automatisch door Journey Orchestration worden beheerd. U hoeft &quot;INSERT_SECRET_HERE&quot; niet te vervangen.
   * **DataProviders**:  &quot;Adobe Campaign Standard Data Provider&quot; (acsDataProvider) en &quot;Experience Platform&quot; (acppsDataProvider)
   * **Veldgroepen** (dataEntities): &quot;ProfileFieldGroup&quot; (acppsDataPack)



### Importkenmerken

* Tijdens het importeren worden de reisobjecten gemaakt met een nieuwe UID en een nieuwe naam om ervoor te zorgen dat de doelomgeving (instantie of sandbox) uniek is.

* Als de importpayload geheime plaatsaanduidingen bevat, wordt een fout gegenereerd. U moet de referentie-informatie vervangen voordat de POST belt om de reis te importeren.

## Waarschuwing en fouten

De mogelijke fouten zijn:

* Bij **uitvoer**, indien de reisversie niet geldig is: fout 500

* Tijdens het **importeren**, als de lading niet geldig is na wijzigingen of als de referenties niet goed gedefinieerd zijn in de lading: fout 400

* Als na de importstap de XDM-schema-id voor uw gebeurtenissen niet geldig is in de doelomgeving, wordt een fout weergegeven in de Journey Orchestration-toepassing. In dat geval kan de reis niet worden gepubliceerd.