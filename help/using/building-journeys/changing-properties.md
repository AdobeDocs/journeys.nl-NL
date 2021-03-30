---
product: adobe campaign
solution: Journey Orchestration
title: Eigenschappen wijzigen
description: Meer informatie over het wijzigen van eigenschappen
feature: Journeys
role: Business Practitioner
level: Intermediair
translation-type: tm+mt
source-git-commit: a8bfd4fd829ff8fadc68de87dc0b9de085a962e3
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 1%

---



# Eigenschappen wijzigen {#concept_prq_wqt_52b}

Klik op het potloodpictogram in de rechterbovenhoek om de eigenschappen van de rit te openen.

U kunt de naam van de reis wijzigen, een beschrijving toevoegen, terugkeer toestaan, begin- en einddatum kiezen en een **[!UICONTROL Timeout and error]** duur definiëren als u beheerder bent.

![](../assets/journey32.png)

## Enter{#entrance}

Nieuwe reizen zijn standaard geschikt voor herbinnenkomst. U kunt de optie uitschakelen voor &#39;één opname&#39;-reizen, bijvoorbeeld als u een eenmalige gift wilt aanbieden wanneer een persoon een winkel betreedt. In dat geval, wilt u niet de klant de reis kunnen opnieuw ingaan en de aanbieding opnieuw ontvangen.

Wanneer een reis &quot;beëindigt&quot;, zal het de status **[!UICONTROL Closed (no entrance)]** hebben. De reis zal het niet langer mogelijk maken dat nieuwe individuen de reis betreden. Personen die al op reis zijn, zullen de reis normaal afmaken.

Na de standaard globale onderbreking van 30 dagen, zal de reis aan **Voltooid** status schakelen. Zie deze [sectie](#global_timeout).

## Time-out en fout in reisactiviteiten {#timeout_and_error}

Wanneer u een actie of voorwaardenactiviteit bewerkt, kunt u een alternatief pad definiëren in het geval van een fout of time-out. Als de verwerking van de activiteit die een derdesysteem ondervraagt de onderbrekingsduur overschrijdt die in de eigenschappen van de reis (**[!UICONTROL Timeout and  error]** gebied) wordt bepaald, zal de tweede weg worden gekozen om een potentiële reserveactie uit te voeren.

Toegestane waarden liggen tussen 1 en 30 seconden.

Wij adviseren dat u een zeer korte **[!UICONTROL Timeout and error]** waarde bepaalt als uw reis tijdgevoelig is (voorbeeld: reageren op de locatie in real time van een persoon) omdat u de handeling niet langer dan een paar seconden kunt uitstellen. Als uw reis minder tijdgevoelig is, kunt u een langere waarde gebruiken om meer tijd aan het geroepen systeem te geven om een geldige reactie te verzenden.

[!DNL Journey Orchestration] gebruikt ook een algemene time-out. Zie [volgende sectie](#global_timeout).

## Globale time-out {#global_timeout}

Naast de [timeout](#timeout_and_error) die in reisactiviteiten wordt gebruikt, is er ook een globale reisonderbreking die niet in de interface wordt getoond en niet kan worden veranderd. Deze onderbreking zal de vooruitgang van individuen in de reis 30 dagen na hun binnengaan stoppen. Dit betekent dat de reis van een individu niet langer mag duren dan 30 dagen. Na de periode van 30 dagen worden de gegevens van het individu verwijderd. Personen die aan het einde van de time-outperiode nog onderweg zijn, worden gestopt en als fouten in de rapportage worden ze in aanmerking genomen.

>[!NOTE]
>
>[!DNL Journey Orchestration] reageert niet rechtstreeks op verzoeken om privacy te weigeren, toegang te krijgen of te verwijderen. De wereldwijde time-out zorgt er echter voor dat individuen nooit langer dan 30 dagen op een reis blijven.

Vanwege de 30 dagen durende reistijd, wanneer het niet is toegestaan om de reis opnieuw te betreden, kunnen we er niet voor zorgen dat de heringstop meer dan 30 dagen werkt. Aangezien we alle informatie over personen die 30 dagen na hun binnenkomst de reis hebben betreden, verwijderen, kunnen we niet weten dat de persoon eerder, meer dan 30 dagen geleden, is binnengekomen.

## Tijdzone en profieltijdzone {#timezone}

De tijdzone wordt gedefinieerd op het niveau van de reis.

U kunt een vaste tijdzone invoeren of Adobe Experience Platform-profielen gebruiken om de tijdzone van de reis te definiëren.

Zie [deze pagina](../building-journeys/timezone-management.md) voor meer informatie over tijdzonebeheer.
