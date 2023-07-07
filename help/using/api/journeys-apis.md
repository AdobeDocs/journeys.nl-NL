---
product: adobe campaign
title: Aan de slag met journey-API's
description: Meer informatie over journey-API's
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: a5dd3d23-c820-4ab7-bc6c-b1dcfe15022c
source-git-commit: 03a58d765a6c98df6a976a5b9c537bdb5cc3ce99
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 100%

---

# Aan de slag met journey-API&#39;s

## Informatie over afkappings- en beperkings-API&#39;s

Wanneer u een databron of een actie configureert, maakt u een verbinding met een systeem om extra informatie op te halen voor gebruik in uw journeys of om berichten of API-oproepen te versturen.

Journey-API&#39;s ondersteunen tot 5000 gebeurtenissen per seconde, maar sommige externe systemen of API&#39;s hebben mogelijk geen equivalente verwerkingscapaciteit. Om overbelasting van deze systemen te voorkomen kunt u API&#39;s voor **Afkappen** en **Beperken** gebruiken om het aantal per seconde verzonden gebeurtenissen te beperken.

Telkens wanneer een API-oproep wordt uitgevoerd door journeys, passeert deze de API-engine. Als de in de API ingestelde limiet is bereikt, wordt de oproep geweigerd als u de afkappings-API gebruikt, of tot 6 uur in een wachtrij geplaatst en zo snel mogelijk verwerkt in de volgorde van ontvangst als u de beperkings-API gebruikt.

Stel bijvoorbeeld dat u voor uw externe systeem een regel voor afkappen of beperken hebt gedefinieerd van 100 oproepen per seconde. Uw systeem wordt opgeroepen door een aangepaste actie in 10 verschillende journeys. Indien één journey 200 oproepen per seconde ontvangt, gebruikt deze de 100 beschikbare slots en de 100 resterende slots verwijderen of in een wachtrij plaatsen. Aangezien het maximumaantal is overschreden, hebben de andere 9 journeys geen slot meer. Deze granulariteit helpt het externe systeem te beschermen tegen overbelasting en vastlopen.

>[!IMPORTANT]
>
>**Afkappingsregels** worden op sandboxniveau geconfigureerd voor een specifiek eindpunt (de opgeroepen URL), maar globaal voor alle journeys van deze sandbox.
>
>**Beperkingsregels** worden voor productiesandboxen alleen geconfigureerd voor een specifiek eindpunt, maar globaal voor alle journeys in alle sandboxes. U kunt slechts één beperkingsconfiguratie per organisatie hebben.

Voor meer informatie over werken met deze API&#39;s raadpleegt u deze secties:

* [Afkappings-API](capping.md)
* [API voor beperken](throttling.md)

Beide API&#39;s worden ook beschreven in een Swagger-bestand dat [hier](https://adobedocs.github.io/JourneyAPI/docs/) beschikbaar is.

## Capaciteit gegevensbronnen en aangepaste acties {#capacity}

Voor **externe gegevensbronnen** is het maximum aantal oproepen per seconde beperkt tot 15. Als deze limiet wordt overschreden, worden alle verdere oproepen ofwel afgewezen ofwel in de wachtrij geplaatst, afhankelijk van de gebruikte API. Het is mogelijk om deze limiet te verhogen voor externe privédatabronnen door contact op te nemen met Adobe om het eindpunt op te nemen in de lijst van gewenste personen, maar dit is geen optie voor externe openbare databronnen. * [Leer hoe u databronnen kunt configureren](../datasource/about-data-sources.md).

>[!NOTE]
>
>Als een databron een aangepaste authenticatie gebruikt met een ander eindpunt dan het eindpunt dat voor de databron wordt gebruikt, moet u contact opnemen met Adobe om ook dat eindpunt in de lijst van gewenste personen op te nemen.

Voor **aangepaste acties** moet u de capaciteit van uw externe API evalueren. Als Journey Optimizer bijvoorbeeld 1000 oproepen per seconde verstuurt en uw systeem slechts 100 oproepen per seconde kan ondersteunen, moet u een afkappings- of beperkingsconfiguratie definiëren zodat uw systeem niet verzadigd raakt. [Ontdek hoe u acties kunt configureren](../action/action.md)

## API-toegang instellen {#api}

Om deze API&#39;s met uw [!DNL Journey Orchestration]-versie te gebruiken moet u de AdobeI/O-console gebruiken. [!DNL Journey Orchestration] API-toegang wordt ingesteld via de onderstaande stappen. Elk van deze stappen is gedetailleerd beschreven in de [Adobe I/O-documentatie](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Om certificaten te beheren in Adobe I/O hebt u <b>systeembeheerders</b>rechten nodig voor de organisatie of een [ontwikkelaarsaccount](https://helpx.adobe.com/nl/enterprise/using/manage-developers.html) in de Admin-console.

1. **Controleer of u een digitaal certificaat hebt**, of maak er zo nodig een. De bij het certificaat geleverde openbare en privésleutels zijn nodig bij de volgende stappen.
1. **Maak een nieuwe integratie met [!DNL Journey Orchestration] Service** in Adobe I/O en configureer deze. De toegang tot het productprofiel is nodig voor [!DNL Journey Orchestration] en Adobe Experience Platform. Uw referenties worden dan gegenereerd (API-sleutel, klantgeheim...).
1. **Maak een JSON-webtoken (JWT)** van de eerder gegenereerde referenties en onderteken deze met uw privésleutel. De JWT codeert alle identiteits- en beveiligingsinformatie die Adobe nodig heeft om uw identiteit te verifiëren en u toegang te verlenen tot de API. Deze stap wordt in detail beschreven in deze [sectie](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Uw JWT uitwisselen voor een toegangstoken** via een POST-verzoek of via de Developer Console Interface. Deze toegangstoken moet worden gebruikt in elke header van uw API-verzoeken.

Om een veilige Adobe I/O API-sessie tussen services tot stand te brengen moet elk verzoek aan een Adobe-service de onderstaande informatie bevatten in de autorisatieheader.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZATION>**: dit is uw persoonlijke ORGANISATIE-ID. Adobe verstrekt één ORGANISATIE-ID voor elk van uw instanties. Voor het verkrijgen van uw ORGANISATIE-ID-waarde raadpleegt u uw beheerder of uw technische contactpersoon bij Adobe. U kunt hem ook ophalen in Adobe I/O wanneer u een nieuwe integratie maakt, in de licentielijst (zie de <a href="https://www.adobe.io/authentication.html">Adobe I/O-documentatie</a>).

* **&lt;ACCESS_TOKEN>**: uw persoonlijke toegangstoken, dat is opgehaald bij het uitwisselen van uw JWT via een POST-verzoek.

* **&lt;API_KEY>**: uw persoonlijke API-sleutel. Deze wordt geleverd in Adobe I/O na het maken van een nieuwe integratie met [!DNL Journey Orchestration] Service.