---
product: adobe campaign
solution: Journey Orchestration
title: Integratie met externe systemen
description: Leer de beste werkwijzen bij het integreren van externe systemen
feature: Journeys
role: Business Practitioner
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: a25ff95e0b74d3a0693310179670c7fe7b0de51c
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---

# Integreren met externe systemen {#external-systems}

Deze pagina bevat de verschillende instructies die Journey Orchestration biedt bij de integratie van een extern systeem en de beste werkwijzen: hoe u de bescherming van uw externe systeem kunt optimaliseren met de API voor plafonnering, hoe u de time-out van de reis kunt configureren en hoe nieuwe pogingen werken.

Met Journey Orchestration kunt u verbindingen met externe systemen configureren via aangepaste gegevensbronnen en aangepaste handelingen. Zo kunt u bijvoorbeeld uw reizen verrijken met gegevens die afkomstig zijn van een extern reserveringssysteem, of berichten verzenden via systemen van derden zoals Epsilon of Facebook.

Wanneer u een extern systeem integreert, kunt u verschillende problemen tegenkomen, kan het systeem traag zijn, kan het niet langer reageren of kan het een groot volume mogelijk niet verwerken. Journey Orchestration biedt verschillende hulplijnen om uw systeem te beschermen tegen overbelasting.

Alle externe systemen hebben verschillende prestaties. U moet de configuratie aan elk gebruiksgeval aanpassen.

Wanneer Journey Orchestration een aanroep van een externe API uitvoert, worden de technische instructies als volgt uitgevoerd:

1. Afbeelding: er worden afkapregels toegepast
2. Time-out en opnieuw proberen:

## Afbeelding

De ingebouwde API voor uitlijnen biedt een stroomopwaartse technische hulplijn die u helpt uw externe systeem te beschermen. U moet eerst de capaciteit van de externe API evalueren. Bijvoorbeeld, als Journey Orchestration 1000 vraag per seconde verzendt en uw systeem slechts 100 vraag per seconde kan steunen, moet u een het begrenzen regel bepalen zodat uw systeem niet verzadigt.

De begrenzingsregels worden bepaald op zanddoxniveau voor een specifiek eindpunt (genoemd URL). Bij runtime, verifieert Journey Orchestration of er een het begrenzen regel wordt bepaald en past het bepaalde tarief tijdens de vraag aan dat eindpunt toe. Als het aantal vraag het bepaalde tarief overschrijdt, worden de resterende vraag verworpen.

Een begrenzingsregel is specifiek voor één eindpunt, maar is globaal voor alle reizen van een sandbox. Dit betekent dat de vraaggroeven tussen alle reizen van een zandbak worden gedeeld. Bijvoorbeeld, laten wij zeggen dat uw extern systeem een bepaalde maximum van 100 vraag per seconde heeft en het door een douaneactie in 10 verschillende reizen wordt geroepen. Als één reis 200 vraag per seconde ontvangt, zal het de 100 groeven beschikbaar houden en de 100 resterende groeven verwerpen. Aangezien het maximumtarief reeds wordt overschreden, zullen de overige 9 reizen geen enkele ruimte hebben. Deze granulariteit helpt het externe systeem te beschermen tegen overbelasting en vastlopen.

Een vraag die wegens het begrenzen wordt verworpen wordt geteld als fout in rapportering.

Leren hoe te om het begrenzen regels te vormen, verwijs naar [deze pagina](../api/timezone-management.md).

## Time-out en opnieuw proberen

Ensuite -> timeout defini, et qui definir le temps maximal qu&#39;on aloue a lappel au sys extern. Pendant ce temps là, on essaie de faire des appels. Op fait un appel, si l&#39;appel procedure moinre longtemps que le timeout ca marche, si plus longtemps on voit kan une timeout error, et coté reporting compabilisé comme une erreur. si l &#39; appel echoue ( planter sur 500 ou autre ) , retry . 3 probeer max. opnieuw, pas configureerbaar. SI kan de timeoutglobal (par example 2 essais, mais depasse le timeout) erreur de timeout overschrijden. plsu de temps que necessary aire . De time-outduur van max qu&#39;on alloue a appel et aux retry is fout.

