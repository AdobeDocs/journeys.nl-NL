---
product: adobe campaign
title: Segmentkwalificatiegebeurtenissen
description: Meer informatie over segmentkwalificatiegebeurtenissen
feature: Journeys
role: User
level: Intermediate
exl-id: e8e54dbd-8178-4c70-907c-68eb4dc54da7
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 1%

---

# Segmentkwalificatiegebeurtenissen {#segment-qualification}

## Informatie over segmentkwalificatiegebeurtenissen{#about-segment-qualification}

Met deze activiteit kunt u luisteren naar de ingangen en uitgangen van profielen in Adobe Experience Platform-segmenten om ervoor te zorgen dat individuen op reis kunnen gaan of vooruit kunnen gaan. Voor meer informatie over segmentverwezenlijking, verwijs naar dit [sectie](../segment/about-segments.md).

Laten we zeggen dat je een &quot;zilveren klant&quot;-segment hebt. Met deze activiteit, kunt u alle nieuwe zilveren klanten een reis maken en hen een reeks gepersonaliseerde berichten verzenden.

Dit type gebeurtenis kan als eerste stap of later in de reis worden geplaatst.

>[!IMPORTANT]
>
>Adobe Experience Platform-segmenten worden één keer per dag berekend (**partij** segmenten) of in realtime (**gestreamd** segmenten, met gebruik van de optie High Frequency Audiences van Adobe Experience Platform).
>
>Als het geselecteerde segment wordt gestreamd, zullen de individuen die tot dit segment behoren potentieel de reis in real time ingaan. Als het segment partij is, zullen de mensen die nieuw voor dit segment worden gekwalificeerd de reis potentieel ingaan wanneer de segmentberekening op Adobe Experience Platform wordt uitgevoerd.


1. De **[!UICONTROL Events]** categorie en een **[!UICONTROL Segment qualification]** op uw canvas.

   ![](../assets/segment5.png)

1. Voeg een **[!UICONTROL Label]** aan de activiteit. Deze stap is optioneel.

1. Klik in het dialoogvenster **[!UICONTROL Segment]** en selecteer de segmenten die u wilt benutten.

   >[!NOTE]
   >
   >U kunt de kolommen in de lijst aanpassen en sorteren.

   ![](../assets/segment6.png)

   Nadat het segment is toegevoegd, wordt het **[!UICONTROL Copy]** kunt u de naam en de id kopiëren:

   `{"name":"Loyalty membership“,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-copy.png)

1. In de **[!UICONTROL Behaviour]** in het veld kiest u of u wilt luisteren naar segmentingangen, afsluiten of beide.

   >[!NOTE]
   >
   >Let op: **[!UICONTROL Enter]** en **[!UICONTROL Exit]** komt overeen met de **Gerealiseerd** en **Verlaat** de deelnamestatistieken van Adobe Experience Platform. Raadpleeg voor meer informatie over het evalueren van een segment de [Documentatie voor segmentatieservice](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

1. Selecteer een naamruimte. Dit is alleen nodig als de gebeurtenis als eerste stap van de reis wordt geplaatst.

   ![](../assets/segment7.png)

De nuttige lading bevat de volgende contextinformatie, die u in voorwaarden en acties kunt gebruiken:

* het gedrag (ingang, uitgang)
* het tijdstempel van de kwalificatie
* segment-id

Wanneer u de expressieeditor gebruikt in een voorwaarde of handeling die volgt op een **[!UICONTROL Segment qualification]** activiteit, hebt u toegang tot **[!UICONTROL SegmentQualification]** knooppunt. U kunt kiezen tussen **[!UICONTROL Last qualification time]** en de **[!UICONTROL status]** (Enter of exit).

Zie [Condition-activiteit](../building-journeys/condition-activity.md#about_condition).

![](../assets/segment8.png)

Een nieuwe reis die een gebeurtenis van de segmentkwalificatie omvat is operationeel tien minuten nadat u het hebt gepubliceerd. Dit tijdinterval beantwoordt aan het geheime voorgeheugen verfrist interval van de specifieke dienst. Daarom moet u tien minuten wachten voordat u deze reis gebruikt.

## Best practices {#best-practices-segments}

De **[!UICONTROL Segment Qualification]** de activiteit maakt het mogelijk dat personen die gekwalificeerd of gediskwalificeerd zijn van een Adobe Experience Platform-segment onmiddellijk toegang krijgen tot de reis.

De ontvangstsnelheid van deze informatie is hoog. Uit de uitgevoerde metingen blijkt een snelheid van 10.000 ontvangen gebeurtenissen per seconde. Als gevolg hiervan moet u er zeker van zijn dat u begrijpt hoe pieken in de toegang kunnen optreden, hoe u ze kunt vermijden en hoe u uw reis voor hen gereed kunt maken.

### Batchsegmenten{#batch-speed-segment-qualification}

Wanneer het gebruiken van segmentkwalificatie voor een partijsegment, merk op dat een piek van ingang op het tijdstip van de dagelijkse berekening zal gebeuren. De omvang van de piek hangt af van het aantal personen dat dagelijks het segment betreedt (of verlaat).

Als het batchsegment nieuw wordt gemaakt en onmiddellijk wordt gebruikt in een reis, kan de eerste batch van de berekening bovendien een zeer groot aantal personen de reis binnenkomen.

### Gestroomde segmenten{#streamed-speed-segment-qualification}

Wanneer het gebruiken van segmentkwalificatie voor gestroomde segmenten, is er minder risico om grote pieken van ingangen/uitgangen te krijgen toe te schrijven aan de ononderbroken evaluatie van het segment. Maar als de segmentdefinitie ertoe leidt dat een groot aantal klanten tegelijkertijd in aanmerking komt, kan er ook een piek zijn.

Raadpleeg deze voor meer informatie over streamingsegmentatie [page](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/streaming-segmentation.html#api)

### Overbelasting voorkomen{#overloads-speed-segment-qualification}

Hier volgen een paar voorbeelden van beste praktijken die zullen helpen om overladende systemen te vermijden leveraged in reizen (gegevensbronnen, douaneacties, acties van Adobe Campaign Standard).

Niet gebruiken in een **[!UICONTROL Segment Qualification]** activiteit, een batchsegment onmiddellijk na de aanmaak ervan. Hiermee wordt de eerste rekenpiek vermeden. Merk op dat er een gele waarschuwing in het reiscanvas zal zijn als u op het punt staat om een segment te gebruiken dat nooit is berekend.

![](../assets/segment-error.png)

Plaats een plafondregel voor gegevensbronnen en handelingen die tijdens reizen worden gebruikt om overbelasting te voorkomen (verwijs naar deze [sectie](../api/capping.md)). De bijschilderregel hoeft niet opnieuw te worden uitgevoerd. Als u het opnieuw moet proberen, moet u een alternatief pad in de reis gebruiken door de doos te controleren **[!UICONTROL Add an alternative path in case of a timeout or an error]** in omstandigheden of acties.

Voordat u het segment in een productietraject gaat gebruiken, moet u altijd eerst het aantal personen beoordelen dat dagelijks voor dit segment in aanmerking komt. Om dit te doen, kunt u controleren **[!UICONTROL Segments]** in de Adobe Experience Platform en bekijk de grafiek aan de rechterkant.

![](../assets/segment-overload.png)
