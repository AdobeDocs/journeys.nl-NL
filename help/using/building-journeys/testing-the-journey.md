---
product: adobe campaign
title: Journey testen
description: Meer informatie over het testen van reizen
feature: Journeys
role: User
level: Intermediate
exl-id: be413905-0631-4229-a954-80a92651206d
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '1619'
ht-degree: 2%

---

# Journey testen{#testing_the_journey}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


Voordat u uw reis kunt testen, moet u alle eventuele fouten oplossen. Zie [deze sectie](../about/troubleshooting.md#section_h3q_kqk_fhb).

U kunt uw reis testen voordat deze wordt gepubliceerd, met behulp van testprofielen. Dit staat u toe om te analyseren hoe de individuen in de reis stromen en problemen vóór publicatie oplossen.

Alleen testprofielen kunnen een reis maken in de testmodus. U kunt een nieuw testprofiel maken of een bestaand profiel omzetten in een testprofiel. Verwijs naar deze [ sectie ](../building-journeys/creating-test-profiles.md).

Voer de volgende stappen uit om de testmodus te gebruiken:

1. Controleer voordat u de reis test of deze geldig is en of er geen fout optreedt. U kunt geen test starten voor een reis met fouten. Zie [ deze sectie ](../about/troubleshooting.md#section_h3q_kqk_fhb). Er wordt een waarschuwingssymbool weergegeven wanneer er fouten optreden.

1. U activeert de testmodus door te klikken op de schakeloptie **[!UICONTROL Test]** in de rechterbovenhoek.

   ![](../assets/journeytest1.png)

1. Gebruik de parameter **[!UICONTROL Wait time]** in de linkerbenedenhoek om de tijd te bepalen dat elke activiteit van de wachttijd en tijd van de gebeurtenis op testwijze zal duren. De standaardtijd is 10 seconden voor wachttijden en gebeurtenisonderbrekingen. Zo krijgt u de testresultaten snel. Deze parameter verschijnt slechts als u één of meerdere wachtactiviteiten in uw reis hebt gelaten vallen.

   ![](../assets/journeytest_wait.png)

   >[!NOTE]
   >
   >Wanneer een reactiegebeurtenis met een onderbreking in een reis wordt gebruikt, is het gebrek van de wachttijdtijd en de minimumwaarde 40 seconden. Zie [deze sectie](../building-journeys/reaction-events.md).

1. Klik op **[!UICONTROL Trigger an event]** om gebeurtenissen te configureren en naar de rit te verzenden.

   ![](../assets/journeyuctest1.png)

1. Configureer de verschillende verwachte velden. Op het **gebied van Identifier van het 0&rbrace; Profiel &lbrace;, ga de waarde van het gebied in dat wordt gebruikt om het testprofiel te identificeren.** Het kan bijvoorbeeld het e-mailadres zijn. Zorg ervoor dat u gebeurtenissen verzendt die betrekking hebben op testprofielen. Zie [ Vast uw gebeurtenissen ](#firing_events).

   ![](../assets/journeyuctest1-bis.png)

1. Nadat de gebeurtenissen zijn ontvangen, klikt u op de knop **[!UICONTROL Show log]** om het testresultaat weer te geven en te controleren. Zie [ het Bekijken van de logboeken ](#viewing_logs).

   ![](../assets/journeyuctest2.png)

1. Als er een fout optreedt, deactiveert u de testmodus, wijzigt u de journey en test u deze opnieuw. Wanneer de test overtuigend is, kunt u uw reis publiceren. Zie [deze pagina](../building-journeys/publishing-the-journey.md).

## Belangrijke opmerkingen {#important_notes}

* Er is een interface beschikbaar voor het afvuren van gebeurtenissen naar de geteste reis, maar evenementen kunnen ook door systemen van derden, zoals Postman, worden verzonden.
* Alleen personen die zijn gemarkeerd als &quot;testprofielen&quot; in de realtime klantenprofielservice mogen de geteste reis betreden. Verwijs naar deze [ sectie ](../building-journeys/creating-test-profiles.md).
* De testmodus is alleen beschikbaar voor conceptochten waarbij een naamruimte wordt gebruikt. In de testmodus moet worden gecontroleerd of een persoon die de reis betreedt een testprofiel is en moet dus de Adobe Experience Platform kunnen bereiken.
* Het maximumaantal testprofielen dat een reis tijdens een testsessie kan betreden, is 100.
* Wanneer u de testmodus uitschakelt, worden de reizen verwijderd van alle mensen die het in het verleden hebben betreden of die er momenteel in zitten. Ook wordt de rapportage gewist.
* U kunt de testmodus zo vaak als nodig in- en uitschakelen.
* U kunt uw reis niet wijzigen wanneer de testwijze wordt geactiveerd. In de testmodus kunt u de rit rechtstreeks publiceren. U hoeft de testmodus daarvoor niet te deactiveren.
* Bij het bereiken van een splitsing wordt altijd de bovenste vertakking gekozen. U kunt de positie van de gesplitste vertakkingen opnieuw ordenen als u wilt dat de test een ander pad kiest.
* Om prestaties te optimaliseren en verouderd middelgebruik te verhinderen, zullen alle reizen in testwijze die niet voor een week zijn teweeggebracht op de status van het Ontwerp terugschakelen.

## Een profiel omzetten in een testprofiel{#turning-profile-into-test}

U kunt een bestaand profiel omzetten in een testprofiel. In Adobe Experience Platform kunt u profielkenmerken bijwerken via API-aanroepen, maar deze kunnen niet via de interface worden uitgevoerd.

De gemakkelijkste manier om dit te doen is door een **het profiel van de Update** actieactiviteit te gebruiken en het de booleaanse gebied van het testprofiel van vals in waar te veranderen. Zie [deze sectie](../building-journeys/update-profiles.md#using-the-test-mode).

## Een testprofiel maken{#create-test-profile}

Als u een nieuw testprofiel wilt maken, gebeurt dit volgens dezelfde procedure als wanneer u een profiel maakt in de Adobe Experience Platform. Het wordt uitgevoerd door API vraag. Zie deze [ pagina ](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=nl)

U moet een profielschema gebruiken dat de &quot;details van de profieltest&quot;mengen bevat. De markering testProfile maakt deel uit van deze mix.

Wanneer u een profiel maakt, moet u de waarde testProfile = true doorgeven.

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

## Gebeurtenissen starten {#firing_events}

Met de knop **[!UICONTROL Trigger an event]** kunt u een gebeurtenis configureren die ervoor zorgt dat een persoon de reis betreedt.

>[!NOTE]
>
>Wanneer u een gebeurtenis in testmodus activeert, wordt een echte gebeurtenis gegenereerd. Dit betekent dat ook andere reizen naar deze gebeurtenis worden beïnvloed.

Als voorwaarde moet u weten welke profielen in de Adobe Experience Platform zijn gemarkeerd als testprofielen. In de testmodus zijn deze profielen alleen toegestaan tijdens de reis en moet het evenement een id bevatten. De verwachte id is afhankelijk van de gebeurtenisconfiguratie. Het kan bijvoorbeeld een ECID of een e-mailadres zijn. De waarde van deze sleutel moet op het **gebied van het Profiel worden toegevoegd 0&rbrace; Identifier.**

>[!NOTE]
>
>Een vervolgkeuzelijst wordt weergegeven voor velden die een opsomming verwachten. Selecteer gewoon een van de beschikbare waarden.

Als uw reis verscheidene gebeurtenissen bevat, gebruik de drop-down lijst om een gebeurtenis te selecteren. Configureer vervolgens voor elke gebeurtenis de doorgegeven velden en de uitvoering van de gebeurtenis die de gebeurtenis verzendt. De interface helpt u de juiste informatie in de gebeurtenislading over te gaan en ervoor te zorgen het informatietype correct is. In de testmodus worden de laatste parameters die in een testsessie worden gebruikt, opgeslagen voor later gebruik.

![](../assets/journeytest4.png)

Met de interface kunt u eenvoudige gebeurtenisparameters doorgeven. Als u verzamelingen of andere geavanceerde objecten in de gebeurtenis wilt doorgeven, kunt u op **[!UICONTROL Code View]** klikken om de volledige code van de laadbewerking te zien en deze te wijzigen. U kunt bijvoorbeeld gebeurtenisgegevens kopiëren en plakken die door een technische gebruiker zijn voorbereid.

![](../assets/journeytest5.png)

Een technische gebruiker kan deze interface ook gebruiken om gebeurtenislading samen te stellen en gebeurtenissen teweeg te brengen zonder het moeten een derdehulpmiddel gebruiken.

Wanneer u op de knop **[!UICONTROL Send]** klikt, wordt de test gestart. De voortgang van het individu tijdens de reis wordt weergegeven door een visuele stroom. Het pad wordt steeds groen naarmate het individu over de reis beweegt. Als er een fout optreedt, wordt er een waarschuwingssymbool weergegeven bij de bijbehorende stap. U kunt de cursor erop plaatsen om meer informatie over de fout weer te geven en volledige details te openen (indien beschikbaar).

![](../assets/journeytest6.png)

Wanneer u een ander testprofiel in het scherm van de gebeurtenisconfiguratie selecteert en de test opnieuw in werking stelt, wordt de visuele stroom ontruimd en toont de weg van nieuw individu.

Wanneer u een rit tijdens de test opent, komt het weergegeven pad overeen met de laatste uitgevoerde test.

De visuele stroom werkt of de gebeurtenis via de interface of extern (bijvoorbeeld met Postman) wordt geactiveerd.

## Testmodus voor op regels gebaseerde reizen {#test-rule-based}

De testmodus is ook beschikbaar voor reizen die een op regels gebaseerde gebeurtenis gebruiken. Voor meer informatie over op regel-gebaseerde gebeurtenissen, verwijs naar [ deze pagina ](../event/about-events.md).

Wanneer het teweegbrengen van een gebeurtenis, staat het **scherm van de configuratie van de Gebeurtenis 0&rbrace; u toe om de gebeurtenisparameters te bepalen om in de test over te gaan.** U kunt de voorwaarde van de gebeurtenis-identiteitskaart bekijken door het tooltip pictogram in de hoogste juiste hoek te klikken. Er is ook knopinfo beschikbaar naast elk veld dat deel uitmaakt van de regelevaluatie.

![](../assets/alpha-event8.png)

Voor meer informatie over hoe te om de testwijze te gebruiken, verwijs naar [ deze pagina ](../building-journeys/testing-the-journey.md).

## Logboeken weergeven {#viewing_logs}

Met de knop **[!UICONTROL Show log]** kunt u de testresultaten bekijken. Op deze pagina worden de huidige gegevens van de reis in JSON-indeling weergegeven. Met een knop kunt u hele knooppunten kopiëren. U moet de pagina handmatig vernieuwen om de testresultaten van de reis bij te werken.

![](../assets/journeytest3.png)

>[!NOTE]
>
>In de testlogboeken, in het geval van een fout wanneer het roepen van een derdesysteem (gegevensbron of actie), worden de foutencode en foutenreactie getoond.

Het aantal personen (technisch gesproken worden ze instanties genoemd) dat zich momenteel in de reis bevindt, wordt weergegeven. Hier volgt nuttige informatie die voor elk individu wordt weergegeven:

* _Identiteitskaart_: interne identiteitskaart van het individu in de reis. Dit kan voor het zuiveren doeleinden worden gebruikt.
* _huidige stap_: de stap waar het individu bij in de reis is. We raden u aan labels aan uw activiteiten toe te voegen om ze gemakkelijker te kunnen identificeren.
* _huidige stap_ > fase: het statuut van de reis van het individu (het lopen, gebeëindigd, fout of uit tijd). Zie hieronder voor meer informatie.
* _huidige stap_ > _extraInfo_: beschrijving van de fout en andere contextafhankelijke informatie.
* _huidige stap_ > _fetchErrors_: informatie over de fouten van de haalgegevens die tijdens deze stap voorkwamen.
* _externalKeys_: de waarde voor de belangrijkste formule die in de gebeurtenis wordt bepaald.
* _enrichedData_: de gegevens die de reis heeft teruggewonnen als de reis gegevensbronnen gebruikt.
* _transitionHistory_: de lijst van stappen die het individu volgde. Voor gebeurtenissen wordt de payload weergegeven.
* _actionExecutionErrors_ : informatie over de fouten die voorkwamen.

Hier zijn de verschillende statussen van de reis van een individu:

* _Lopend_: het individu is momenteel in de reis.
* _Voltooid_: Het individu is aan het eind van de reis.
* _Fout_: het individu wordt tegengehouden in de reis wegens een fout.
* _Timed out_: het individu wordt tegengehouden in de reis wegens een stap die teveel tijd kostte.

Wanneer een gebeurtenis gebruikend de testwijze wordt teweeggebracht, wordt een dataset automatisch geproduceerd met de naam van de bron.

Wanneer een gebeurtenis gebruikend de testwijze wordt teweeggebracht, wordt een dataset automatisch geproduceerd met de naam van de bron.

In de testmodus wordt automatisch een Experience Event gemaakt en naar Adobe Experience Platform verzonden. De naam van de bron voor deze ervaringsgebeurtenis is &quot;Journey Orchestration Test Events&quot;.
