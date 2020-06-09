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
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '1004'
ht-degree: 0%

---


# Problemen oplossen{#concept_nlv_bcv_2fb}

In deze sectie leert u hoe u problemen met reizen kunt oplossen voordat u gaat testen of publiceren. Alle hieronder vermelde controles kunnen worden uitgevoerd wanneer de reis in testmodus is of wanneer de reis live is. De aanbeveling is om alle onderstaande controles in testmodus uit te voeren en vervolgens tot publicatie over te gaan. Zie [](../building-journeys/testing-the-journey.md).

## Controleren op fouten voordat wordt getest{#section_h3q_kqk_fhb}

Voordat u uw reis gaat testen en publiceren, controleert u of alle activiteiten correct zijn geconfigureerd. U kunt geen tests of publicaties uitvoeren als de fouten nog door het systeem worden ontdekt.

Fouten worden weergegeven met een waarschuwingssymbool dat wordt weergegeven op de activiteiten zelf op het canvas. Plaats de cursor op het uitroepteken om het foutbericht weer te geven. Als u op de activiteit klikt, zou u de lijn in fout met een waarschuwing moeten zien. Als een verplicht veld bijvoorbeeld leeg is, wordt een fout weergegeven.

![](../assets/journey63.png)

Als bijvoorbeeld op het canvas twee activiteiten worden losgekoppeld, wordt een waarschuwing weergegeven.

![](../assets/canvas-disconnected.png)

Naast de **[!UICONTROL Test]** schakeloptie en de **[!UICONTROL Publish]** knop kan een waarschuwingsbord worden weergegeven. Dit waarschuwingsteken bevat fouten die door het systeem zijn gedetecteerd en voorkomt activering van de testmodus of publicatie van de reis. Meestal zijn fouten die door het systeem worden gedetecteerd gekoppeld aan fouten die zichtbaar zijn voor de activiteiten, maar soms zijn ze gekoppeld aan andere problemen. In dit geval kunt u deze weergeven en proberen het probleem te identificeren aan de hand van de foutbeschrijving. Als u het probleem niet kunt identificeren, kunt u de gegevens kopiëren en naar de beheerder of ter ondersteuning verzenden. Fouten die de test blokkeren en fouten die de publicatie blokkeren, zijn vergelijkbaar.

Het systeem detecteert twee soorten problemen: fouten en waarschuwingen. Foutenblokkering en activering van tests. Waarschuwingen geven mogelijke problemen aan die activering of publicatie van de test niet blokkeren. U zult een beschrijving van de kwestie en een identiteitskaart van het puntenlogboek van type ERR_XXX_XXX zien. Dit zal technische steun helpen de kwestie identificeren.

Er kunnen twee verschillende kleuren worden weergegeven op het teken naast de **[!UICONTROL Test]** schakelknop en de **[!UICONTROL Publish]** knop. Het teken wordt rood weergegeven in het geval van fouten. Het wordt oranje weergegeven in het geval van waarschuwingen.

![](../assets/journey75.png)

Fouten en waarschuwingen die globaal zijn voor de rit, worden eerst in de lijst weergegeven. Fouten en waarschuwingen met betrekking tot specifieke activiteiten worden na, op volgorde van activiteit of uiterlijk op de reis van links naar rechts vermeld. De **[!UICONTROL Copy details]** knoop kopieert technische informatie over de reis die het steunteam kan gebruiken om problemen op te lossen.

## Controleren of gebeurtenissen correct zijn verzonden{#section_rqz_11t_dgb}

Het startpunt van een reis is altijd een evenement. U kunt tests uitvoeren met gereedschappen als Postman.

U kunt controleren of de API-aanroep die u via deze gereedschappen verzendt, correct is verzonden of niet. Als u een fout terug krijgt, betekent het dat uw vraag een kwestie heeft. Controleer opnieuw de lading, de kopbal (en vooral organisatie identiteitskaart) en bestemmingsURL. U kunt de beheerder vragen wat de juiste URL is.

Gebeurtenissen worden niet rechtstreeks van de bron naar [!DNL Journey Orchestration]geduwd. Vertrouw inderdaad [!DNL Journey Orchestration] op de streaming opname-API&#39;s van Experience Platform. Als gevolg hiervan kunt u in geval van problemen met gebeurtenissen naar deze [pagina](https://docs.adobe.com/content/help/en/experience-platform/ingestion/streaming/troubleshooting.html) verwijzen voor het oplossen van problemen met opname-API&#39;s voor streaming.

## Controleren of mensen de reis betreden{#section_x4v_zzs_dgb}

[!DNL Journey Orchestration] rapportage meet de toegang van mensen tot een reis in real-time.

Als je het evenement met succes verzendt maar geen toegang ziet, betekent het dat er iets mis gaat tussen het verzenden van het evenement en de ontvangst van het evenement op de reis.

Hier volgen een paar dingen die de beheerder moet controleren:

* Weet u zeker dat de reis waar u de inkomende gebeurtenis verwacht, in testmodus of live is?
* Hebt u de gebeurtenis opgeslagen voordat u de lading uit de voorvertoning van de lading kopieerde?
* Bevat de payload van de gebeurtenis een gebeurtenis-id?
* Heb je de juiste URL bereikt?
* Hebt u de payload-structuur van de Streaming-API&#39;s gevolgd met de voorvertoning van de payload-structuur in het deelvenster voor gebeurtenisconfiguratie? Zie [](../event/previewing-the-payload.md).
* Hebt u de juiste sleutel-/waardeparen in de koptekst van de gebeurtenis gebruikt?

   ```
   X-gw-ims-org-id - your ORGID
   Content-type - application/json
   ```

## Controleren hoe mensen door de reis navigeren{#section_l5y_yzs_dgb}

[!DNL Journey Orchestration] de rapportage meet de voortgang van individuen tijdens een reis . Het is gemakkelijk om te identificeren waar en waarom een persoon werd tegengehouden.

Hier volgen enkele zaken:

* Is het te wijten aan een voorwaarde die de persoon uitsluit? De aandoening is bijvoorbeeld &quot;geslacht = man&quot; en de persoon is een vrouw. Deze controle kan door een bedrijfsgebruiker worden uitgevoerd als de voorwaarde niet te complex is.
* Is het toe te schrijven aan een vraag aan een gegevensbron niet antwoordt? Wanneer de reis in test is, kan deze informatie in testmoduslogboeken worden gezien. Wanneer de reis levend is, kan een beheerder directe vraag aan de gegevensbron testen en het ontvangen antwoord controleren. Een beheerder kan de reis ook dupliceren en testen.

## Controleren of berichten zijn verzonden{#section_qb1_yzs_dgb}

Als individuen de juiste manier in de reis stromen maar geen berichten ontvangen zij zouden moeten ontvangen, kunt u controleren of:

* Het Transactionele Overseinen heeft correct rekening gehouden met het verzoek om het bericht te verzenden. Een zakelijke gebruiker heeft toegang tot het transactiebericht dat wordt geacht te zijn verzonden en controleert of de tijd van de meest recente uitvoering overeenkomt met de uitvoeringstijd van uw reis. Hij kan de recentste API vraag/de gebeurtenissen ook controleren die door transactioneel overseinen worden ontvangen.
* Het Transactionele overseinen heeft met succes het bericht verzonden. In de verzendende logboeken van het transactiebericht, kunt u het statuut van elke uitvoering zien. Je kunt zien of het groen, rood is en wat het probleem was. Een bedrijfsgebruiker kan tot dit scherm toegang hebben en de logboeken naar een beheerder voor verdere onderzoeken verzenden.

In het geval van een bericht dat via een douaneactie wordt verzonden, is het enige wat tijdens reistest kan worden gecontroleerd het feit dat de vraag van het systeem van de douaneactie tot een fout of niet leidt. Als de aanroep van het externe systeem dat aan de aangepaste actie is gekoppeld, niet tot een fout leidt, maar niet tot het verzenden van een bericht, moeten sommige onderzoeken aan de kant van het externe systeem worden uitgevoerd.

