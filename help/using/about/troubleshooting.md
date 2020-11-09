---
title: Problemen oplossen
description: Meer informatie over probleemoplossing
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: e353d593ab2710f50a88a3715378c86c2e37b4f6
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 98%

---


# Problemen oplossen{#concept_nlv_bcv_2fb}

In deze sectie leert u hoe u problemen met journey’s kunt oplossen voordat u gaat testen of publiceren. Alle hieronder vermelde controles kunnen worden uitgevoerd in de testmodus van de journey of wanneer de journey live is. De aanbeveling is om alle onderstaande controles in de testmodus uit te voeren en vervolgens tot publicatie over te gaan. Zie [deze pagina](../building-journeys/testing-the-journey.md).

## Controleren op fouten voordat wordt getest{#section_h3q_kqk_fhb}

Controleer voordat u uw journey gaat testen en publiceren of alle activiteiten correct zijn geconfigureerd. U kunt geen tests of publicaties uitvoeren als het systeem nog steeds fouten detecteert.

Fouten worden weergegeven met een waarschuwingssymbool dat wordt weergegeven op de activiteiten zelf op het canvas. Plaats de cursor op het uitroepteken om het foutbericht weer te geven. Als u op de activiteit klikt, ziet u de regel waarin de fout voorkomt en een waarschuwing. Als een verplicht veld bijvoorbeeld leeg is, wordt een fout weergegeven.

![](../assets/journey63.png)

Als op het canvas bijvoorbeeld twee activiteiten zijn losgekoppeld, wordt een waarschuwing weergegeven.

![](../assets/canvas-disconnected.png)

Naast de schakeloptie **[!UICONTROL Test]** en de knop **[!UICONTROL Publish]** kan een waarschuwingsteken worden weergegeven. Dit waarschuwingsteken duidt op fouten die door het systeem zijn gedetecteerd en voorkomt activering van de testmodus of publicatie van de journey. Meestal zijn fouten die door het systeem worden gedetecteerd, gekoppeld aan fouten die zichtbaar zijn in de activiteiten, maar soms zijn ze gekoppeld aan andere problemen. In dit geval kunt u de fout weergeven en proberen het probleem te identificeren aan de hand van de foutbeschrijving. Als u het probleem niet kunt identificeren, kunt u de details kopiëren en naar de beheerder of ondersteuning verzenden. Fouten die tests blokkeren en fouten die publicatie blokkeren, lijken op elkaar.

Het systeem detecteert twee soorten problemen: fouten en waarschuwingen. Fouten blokkeren publicatie en testactivering. Waarschuwingen geven mogelijke problemen aan die testactivering of publicatie niet blokkeren. U ziet een beschrijving van het probleem en een probleemlog-id van het type ERR_XXX_XXX. Dit helpt de technische ondersteuning om het probleem te identificeren.

Er kunnen twee verschillende kleuren worden weergegeven op het teken naast de schakeloptie **[!UICONTROL Test]** en de knop **[!UICONTROL Publish]**. Het teken is rood in geval van fouten. En het is oranje in geval van waarschuwingen.

![](../assets/journey75.png)

Fouten en waarschuwingen die globaal zijn voor de journey, worden als eerste in de lijst weergegeven. Fouten en waarschuwingen met betrekking tot specifieke activiteiten worden daarna vermeld, op volgorde van activiteit of weergave in de journey van links naar rechts. Met de knop **[!UICONTROL Copy details]** wordt technische informatie over de journey gekopieerd waarmee het ondersteuningsteam problemen kan oplossen.

Wanneer er een fout in een actie of een voorwaarde optreedt, eindigt de journey van een individu. De enige manier om door te gaan is het selectievakje **[!UICONTROL Add an alternative path in case of a timeout or an error]** in te schakelen. Zie [deze sectie](../building-journeys/using-the-journey-designer.md#paths).

## Controleren of gebeurtenissen correct zijn verzonden{#section_rqz_11t_dgb}

Het startpunt van een journey is altijd een gebeurtenis. U kunt tests uitvoeren met tools zoals Postman.

U kunt controleren of de API-aanroep die u via deze tools verzendt, correct is verzonden of niet. Als een fout wordt geretourneerd, betekent dit dat er een probleem is met uw aanroep. Controleer opnieuw de payload, de koptekst (vooral de organisatie-id) en de bestemmings-URL. U kunt de beheerder vragen wat de juiste URL is.

Gebeurtenissen worden niet rechtstreeks van de bron naar [!DNL Journey Orchestration] gepusht. [!DNL Journey Orchestration] is in feite afhankelijk van streamingopname-API’s van Adobe Experience Platform. As a result, in case of event related issues, you can refer to [this page](https://docs.adobe.com/content/help/nl-NL/experience-platform/ingestion/streaming/troubleshooting.html) for Streaming ingestion APIs troubleshooting.

## Controleren of mensen de journey betreden{#section_x4v_zzs_dgb}

Met [!DNL Journey Orchestration]-rapportage wordt de toegang van mensen tot een journey in real time gemeten.

Als u de gebeurtenis zonder problemen verzendt maar geen toegang tot de journey ziet, betekent dit dat er iets misgaat tussen het verzenden van de gebeurtenis en de ontvangst van de gebeurtenis in de journey.

Hier volgen een paar dingen die de beheerder moet controleren:

* Weet u zeker dat de journey waar u de eerste gebeurtenis verwacht, in de testmodus of live is?
* Hebt u de gebeurtenis opgeslagen voordat u de payload uit de payloadvoorvertoning hebt gekopieerd?
* Bevat de gebeurtenispayload een gebeurtenis-id?
* Hebt u de juiste URL gebruikt?
* Hebt u de payloadstructuur van de streamingopname-API’s gevolgd en de voorvertoning van de payloadstructuur in het deelvenster voor gebeurtenisconfiguratie gebruikt? Zie [deze pagina](../event/previewing-the-payload.md).
* Hebt u de juiste sleutel-/waardeparen in de koptekst van de gebeurtenis gebruikt?

   ```
   X-gw-ims-org-id - your ORGID
   Content-type - application/json
   ```

## Controleren hoe mensen door de journey navigeren{#section_l5y_yzs_dgb}

[!DNL Journey Orchestration]-rapportage meet de voortgang van individuen binnen een journey. Het is gemakkelijk te bepalen waar en waarom een persoon is gestopt.

Controleer bijvoorbeeld het volgende:

* Komt het door een voorwaarde die de persoon uitsluit? De voorwaarde is bijvoorbeeld ‘geslacht = man’ en de persoon is een vrouw. Deze controle kan door een zakelijke gebruiker worden uitgevoerd als de voorwaarde niet te complex is.
* Komt het doordat een aanroep aan een databron niet wordt beantwoord? Wanneer de journey in de testmodus verkeert, is deze informatie in testmoduslogboeken te zien. Wanneer de journey live is, kan een beheerder directe aanroepen aan de databron testen en het ontvangen antwoord controleren. Een beheerder kan de journey ook dupliceren en testen.

## Controleren of berichten goed zijn verzonden{#section_qb1_yzs_dgb}

Als personen de juiste stroom in de journey volgen, maar geen berichten ontvangen die ze wel zouden moeten ontvangen, kunt u het volgende controleren:

* Heeft transactionele berichten correct rekening gehouden met de aanvraag om het bericht te verzenden? Een zakelijke gebruiker heeft toegang tot het transactionele bericht dat moet zijn verzonden, en controleert of de tijd van de meest recente uitvoering overeenkomt met de uitvoeringstijd van uw journey. Deze gebruiker kan tevens de meest recente API-aanroepen/gebeurtenissen controleren die door transactionele berichten zijn ontvangen.
* Is het bericht goed verzonden door transactionele berichten? In de verzendingslogboeken van transactionele berichten kunt u de status van alle uitvoeringen zien. U kunt zien of deze groen of rood is, en wat het probleem was. Een zakelijke gebruiker kan dit scherm openen en de logboeken naar een beheerder verzenden voor nader onderzoek.

Als een bericht via een aangepaste actie is verzonden, kan tijdens de journeytest alleen worden gecontroleerd of de aanroep van het systeem van de aangepaste actie tot een fout leidt of niet. Als de aanroep naar het externe systeem dat aan de aangepaste actie is gekoppeld, niet tot een fout leidt, maar ook niet tot het verzenden van een bericht, moet er enig onderzoek worden gedaan aan de kant van het externe systeem.

