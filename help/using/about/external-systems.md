---
product: adobe campaign
solution: Journey Orchestration
title: Integratie met externe systemen
description: Leer de beste werkwijzen bij het integreren van externe systemen
feature: Journeys
role: User
level: Beginner
exl-id: e39218bd-fa6e-443f-9843-92b7a07070fa
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 5%

---

# Integratie met externe systemen {#external-systems}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [&#x200B; hier &#x200B;](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._



Deze pagina bevat de verschillende instructies die Journey Orchestration biedt bij de integratie van een extern systeem, evenals de beste werkwijzen: hoe u de beveiliging van uw externe systeem kunt optimaliseren met behulp van de API voor plafonnering, hoe u de time-out van de reis kunt configureren en hoe nieuwe pogingen werken.

Met Journey Orchestration kunt u verbindingen met externe systemen configureren via aangepaste gegevensbronnen en aangepaste handelingen. Zo kunt u bijvoorbeeld uw reizen verrijken met gegevens die afkomstig zijn van een extern reserveringssysteem, of berichten verzenden via een systeem van derden, zoals Epsilon of Facebook.

Wanneer u een extern systeem integreert, kunt u verschillende problemen tegenkomen, kan het systeem traag zijn, kan het niet langer reageren of kan het een groot volume mogelijk niet verwerken. Journey Orchestration biedt verschillende instructies om uw systeem te beschermen tegen overbelasting.

Alle externe systemen hebben verschillende prestaties. U moet de configuratie aan uw gebruiksgevallen aanpassen.

Wanneer Journey Orchestration een aanroep naar een externe API uitvoert, worden de technische instructies als volgt uitgevoerd:

1. De regels van het maximum worden toegepast: als het maximumtarief wordt bereikt, worden de resterende vraag verworpen.

2. Time-out en probeer het opnieuw: als aan de begrenzingsregel is voldaan, probeert Journey Orchestration de aanroep uit te voeren tot het einde van de time-outduur is bereikt.

## Afbeelding{#capping}

De ingebouwde API voor uitlijnen biedt een stroomopwaartse technische hulplijn die u helpt uw externe systeem te beschermen.

Voor externe gegevensbronnen, wordt het maximumaantal vraag per seconde geplaatst aan 15. Als het aantal vraag 15 per seconde overschrijdt, worden de resterende vraag verworpen. U kunt deze limiet verhogen voor externe privégegevensbronnen. Neem contact Adobe op om het eindpunt in de lijst van gewenste personen op te nemen. Dit is niet mogelijk voor openbare externe gegevensbronnen.

Voor aangepaste handelingen moet u de capaciteit van de externe API evalueren. Bijvoorbeeld, als Journey Optimizer 1000 vraag per seconde verzendt en uw systeem slechts 100 vraag per seconde kan steunen, moet u een het begrenzen regel bepalen zodat uw systeem niet verzadigt.

De begrenzingsregels worden bepaald op zandbakniveau voor een specifiek eindpunt (geroepen URL). Tijdens runtime, verifieert Journey Orchestration of er een bepaalde het begrenzen regel is en past het bepaalde tarief tijdens de vraag aan dat eindpunt toe. Als het aantal vraag het bepaalde tarief overschrijdt, worden de resterende vraag verworpen en als fouten in het melden geteld.

Een uitlijningsregel is specifiek voor één eindpunt, maar is globaal voor alle reizen van een sandbox. Dit houdt in dat de begrenzingsgroeven tussen alle reizen van een zandbak worden gedeeld.

Bijvoorbeeld, laten wij zeggen dat u een het begrenzen regel van 100 vraag per seconde voor uw extern systeem hebt bepaald. Uw systeem wordt opgeroepen door een aangepaste actie in 10 verschillende journeys. Als één reis 200 vraag per seconde ontvangt, zal het de 100 beschikbare groeven gebruiken en de 100 resterende groeven verwerpen. Aangezien het maximumaantal is overschreden, hebben de andere 9 journeys geen slot meer. Deze granulariteit helpt het externe systeem te beschermen tegen overbelasting en vastlopen.

Om meer op het in kaart brengen API te leren en hoe te om het in kaart brengen regels te vormen, verwijs naar [&#x200B; deze pagina &#x200B;](../api/capping.md).

## Time-out en opnieuw proberen{#timeout}

Als aan de afschilderregel is voldaan, wordt de time-outregel toegepast.

In elke reis, kunt u een onderbrekingsduur bepalen. Dit staat u toe om een maximumduur te plaatsen wanneer het roepen van een extern systeem. De duur van de onderbreking wordt gevormd in de eigenschappen van een reis. Zie [deze pagina](../building-journeys/changing-properties.md#timeout_and_error).

Deze onderbreking is globaal aan alle externe vraag (externe API vraag in douaneacties en douanegegevensbronnen). De standaardwaarde is 5 seconden.

Tijdens de gedefinieerde time-outduur probeert Journey Orchestration het externe systeem aan te roepen. Na de eerste vraag, kan een maximum van drie herpogingen worden uitgevoerd tot het eind van onderbrekingsduur wordt bereikt. Het aantal pogingen kan niet worden gewijzigd.

Bij elke poging wordt één sleuf gebruikt. Als u een maximum van 100 vraag per seconde hebt en elk van uw vraag vereist twee herpogingen, daalt het tarief aan 30 vraag per seconde (elke vraag gebruikt 3 groeven: de eerste vraag en twee herpogingen).

De waarde voor de time-outduur is afhankelijk van het gebruiksgeval. Als u uw bericht snel wilt verzenden, bijvoorbeeld wanneer de client de winkel binnengaat, wilt u geen lange time-out instellen. Hoe langer de time-out is, hoe meer items in de wachtrij worden geplaatst. Dit kan de prestaties sterk beïnvloeden. Als Journey Orchestration 1000 vraag per seconden uitvoert, kan het houden van 5 of 15 seconden van gegevens het systeem snel overweldigen.

Laten we een voorbeeld nemen voor een time-out van 5 seconden.

* De eerste vraag duurt minder dan 5 seconden: de vraag is succesvol, wordt niet opnieuw uitgevoerd.
* De eerste vraag duurt langer dan 5 seconden: de vraag wordt geannuleerd en er is geen retry. Het wordt geteld als een time-outfout in de rapportage.
* De eerste vraag ontbreekt na 2 seconden (het externe systeem keert een fout terug): 3 seconden worden verlaten voor herpogingen, als het begrenzen van groeven beschikbaar is.
   * Als één van de drie pogingen succesvol vóór het eind van 5 seconden is, wordt de vraag uitgevoerd, en er is geen fout.
   * Als het einde van de time-outduur tijdens de pogingen wordt bereikt, wordt de aanroep geannuleerd en geteld als een time-outfout in de rapportage.

## Veelgestelde vragen{#faq}

**Hoe kan ik een het in kaart brengen regel vormen? Is er een standaard het afschilderen regel?**

Standaard is er geen uitlijningsregel. De begrenzingsregels worden bepaald op zandbakniveau voor een specifiek eindpunt (geroepen URL), gebruikend Capping API. Verwijs naar [&#x200B; deze sectie &#x200B;](../about/external-systems.md#capping) en [&#x200B; deze pagina &#x200B;](../api/capping.md).

**hoeveel pogingen worden uitgevoerd? Kan ik het aantal pogingen veranderen of een minimumwachttijdperiode tussen pogingen bepalen?**

Voor een bepaalde vraag, kan een maximum van drie pogingen na de eerste vraag worden uitgevoerd, tot het eind van onderbrekingsduur wordt bereikt. Het aantal pogingen en de tijd tussen elke keer opnieuw proberen kunnen niet worden gewijzigd. Zie [deze sectie](../about/external-systems.md#timeout).

**waar kan ik onderbreking vormen? Is er een maximumwaarde?**

In elke reis, kunt u een onderbrekingsduur bepalen. De duur van de onderbreking wordt gevormd in de eigenschappen van een reis. De duur van de onderbreking moet tussen 1 seconde en 30 seconden zijn. Verwijs naar [&#x200B; deze sectie &#x200B;](../about/external-systems.md#timeout) en [&#x200B; deze pagina &#x200B;](../building-journeys/changing-properties.md#timeout_and_error).
