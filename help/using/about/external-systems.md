---
product: adobe campaign
solution: Journey Orchestration
title: Integratie met externe systemen
description: Leer de beste werkwijzen bij het integreren van externe systemen
feature: Journeys
role: User
level: Beginner
exl-id: e39218bd-fa6e-443f-9843-92b7a07070fa
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 1%

---

# Integratie met externe systemen {#external-systems}

Deze pagina bevat de verschillende instructies die Journey Orchestration biedt bij de integratie van een extern systeem en de beste werkwijzen: hoe u de beveiliging van uw externe systeem kunt optimaliseren met behulp van de API voor aftopping, hoe u de time-out van de reis kunt configureren en hoe nieuwe pogingen werken.

Met Journey Orchestration kunt u verbindingen met externe systemen configureren via aangepaste gegevensbronnen en aangepaste handelingen. Zo kunt u bijvoorbeeld uw reizen verrijken met gegevens die afkomstig zijn van een extern reserveringssysteem, of berichten verzenden via een systeem van derden, zoals Epsilon of Facebook.

Wanneer u een extern systeem integreert, kunt u verschillende problemen tegenkomen, kan het systeem traag zijn, kan het niet langer reageren of kan het een groot volume mogelijk niet verwerken. Journey Orchestration biedt verschillende hulplijnen om uw systeem te beschermen tegen overbelasting.

Alle externe systemen hebben verschillende prestaties. U moet de configuratie aan uw gebruiksgevallen aanpassen.

Wanneer Journey Orchestration een aanroep van een externe API uitvoert, worden de technische instructies als volgt uitgevoerd:

1. Er worden afkapregels toegepast: als het maximumtarief wordt bereikt, worden de resterende vraag verworpen.

2. Time-out en opnieuw proberen: als de het begrenzen regel wordt vervuld, probeert Journey Orchestration om de vraag uit te voeren tot het eind van de onderbrekingsduur wordt bereikt.

## Afbeelding{#capping}

De ingebouwde API voor uitlijnen biedt een stroomopwaartse technische hulplijn die u helpt uw externe systeem te beschermen.

Voor externe gegevensbronnen, wordt het maximumaantal vraag per seconde geplaatst aan 15. Als het aantal vraag 15 per seconde overschrijdt, worden de resterende vraag verworpen. U kunt deze limiet verhogen voor externe privégegevensbronnen. Adobe van het contact om het eindpunt in de lijst van gewenste personen te omvatten. Dit is niet mogelijk voor openbare externe gegevensbronnen.

Voor aangepaste handelingen moet u de capaciteit van de externe API evalueren. Bijvoorbeeld, als Journey Optimizer 1000 vraag per seconde verzendt en uw systeem slechts 100 vraag per seconde kan steunen, moet u een afschilderingsregel bepalen zodat uw systeem niet verzadigt.

De begrenzingsregels worden bepaald op zandbakniveau voor een specifiek eindpunt (geroepen URL). Bij runtime, verifieert Journey Orchestration of er een het begrenzen regel wordt bepaald en past het bepaalde tarief tijdens de vraag aan dat eindpunt toe. Als het aantal vraag het bepaalde tarief overschrijdt, worden de resterende vraag verworpen en als fouten in het melden geteld.

Een uitlijningsregel is specifiek voor één eindpunt, maar is globaal voor alle reizen van een sandbox. Dit houdt in dat de begrenzingsgroeven tussen alle reizen van een zandbak worden gedeeld.

Bijvoorbeeld, laten wij zeggen dat u een het begrenzen regel van 100 vraag per seconde voor uw extern systeem hebt bepaald. Uw systeem wordt opgeroepen door een aangepaste actie tijdens 10 verschillende reizen. Als één reis 200 vraag per seconde ontvangt, zal het de 100 beschikbare groeven gebruiken en de 100 resterende groeven verwerpen. Aangezien het maximumtarief is overschreden, zullen de overige 9 reizen geen slots meer hebben. Deze granulariteit helpt het externe systeem te beschermen tegen overbelasting en vastlopen.

Voor meer informatie over de API voor aftiteling en over het configureren van aftapregels raadpleegt u [deze pagina](../api/capping.md).

## Time-out en opnieuw proberen{#timeout}

Als aan de afschilderregel is voldaan, wordt de time-outregel toegepast.

In elke reis, kunt u een onderbrekingsduur bepalen. Dit staat u toe om een maximumduur te plaatsen wanneer het roepen van een extern systeem. De duur van de onderbreking wordt gevormd in de eigenschappen van een reis. Zie [deze pagina](../building-journeys/changing-properties.md#timeout_and_error).

Deze onderbreking is globaal aan alle externe vraag (externe API vraag in douaneacties en de bronnen van douanegegevens). De standaardwaarde is 5 seconden.

Tijdens de bepaalde onderbrekingsduur, probeert Journey Orchestration om het externe systeem te roepen. Na de eerste vraag, kan een maximum van drie herpogingen worden uitgevoerd tot het eind van onderbrekingsduur wordt bereikt. Het aantal pogingen kan niet worden gewijzigd.

Bij elke poging wordt één sleuf gebruikt. Als u een maximum van 100 vraag per seconde hebt en elk van uw vraag vereist twee herpogingen, daalt het tarief aan 30 vraag per seconde (elke vraag gebruikt 3 groeven: de eerste oproep en twee pogingen).

De waarde voor de time-outduur is afhankelijk van het gebruiksgeval. Als u uw bericht snel wilt verzenden, bijvoorbeeld wanneer de client de winkel binnengaat, wilt u geen lange time-out instellen. Hoe langer de time-out is, hoe meer items in de wachtrij worden geplaatst. Dit kan de prestaties sterk beïnvloeden. Als Journey Orchestration 1000 vraag per seconden uitvoert, kan het houden van 5 of 15 seconden van gegevens het systeem snel overweldigen.

Laten we een voorbeeld nemen voor een time-out van 5 seconden.

* De eerste vraag duurt minder dan 5 seconden: de vraag succesvol is, wordt geen opnieuw uitgevoerd.
* De eerste vraag duurt langer 5 seconden: de oproep wordt geannuleerd en er wordt niet opnieuw geprobeerd. Het wordt geteld als een time-outfout in de rapportage.
* De eerste vraag ontbreekt na 2 seconden (het externe systeem keert een fout terug): 3 seconden over voor nieuwe pogingen, als er afsluitende sleuven beschikbaar zijn.
   * Als één van de drie pogingen succesvol vóór het eind van 5 seconden is, wordt de vraag uitgevoerd, en er is geen fout.
   * Als het einde van de time-outduur tijdens de pogingen wordt bereikt, wordt de aanroep geannuleerd en geteld als een time-outfout in de rapportage.

## Veelgestelde vragen{#faq}

**Hoe kan ik een het in kaart brengen regel vormen? Is er een standaard het in kaart brengen regel?**

Standaard is er geen uitlijningsregel. De begrenzingsregels worden bepaald op zandbakniveau voor een specifiek eindpunt (geroepen URL), gebruikend Capping API. Zie [deze sectie](../about/external-systems.md#capping) en [deze pagina](../api/capping.md).

**Hoeveel pogingen worden uitgevoerd? Kan ik het aantal pogingen veranderen of een minimumwachttijd tussen pogingen bepalen?**

Voor een bepaalde vraag, kan een maximum van drie pogingen na de eerste vraag worden uitgevoerd, tot het eind van onderbrekingsduur wordt bereikt. Het aantal pogingen en de tijd tussen elke keer opnieuw proberen kunnen niet worden gewijzigd. Zie [deze sectie](../about/external-systems.md#timeout).

**Waar kan ik de onderbreking vormen? Is er een maximumwaarde?**

In elke reis, kunt u een onderbrekingsduur bepalen. De duur van de onderbreking wordt gevormd in de eigenschappen van een reis. De time-outduur moet liggen tussen 1 en 30 seconden. Zie [deze sectie](../about/external-systems.md#timeout) en [deze pagina](../building-journeys/changing-properties.md#timeout_and_error).
