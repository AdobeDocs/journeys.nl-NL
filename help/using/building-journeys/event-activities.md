---
title: Gebeurtenisactiviteiten
description: Meer informatie over gebeurtenisactiviteiten
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 957e72de7feccb33684523e26b2bdccb2074e4ca
workflow-type: tm+mt
source-wordcount: '969'
ht-degree: 0%

---


# Gebeurtenisactiviteiten {#concept_rws_1rt_52b}

De gebeurtenissen die door de technische gebruiker worden gevormd (zie allen [](../event/about-events.md) worden getoond in de eerste categorie van het palet, op de linkerkant van het scherm.

![](../assets/journey43.png)

Begin altijd uw reis door een gebeurtenisactiviteit te slepen en neer te zetten. U kunt er ook op dubbelklikken.

![](../assets/journey44.png)

Wanneer u op de gebeurtenisactiviteit in het canvas klikt, wordt de ruit van de activiteitenconfiguratie getoond. Wanneer u dezelfde gebeurtenis meerdere keren gebruikt, wordt standaard een verhoogd getal toegevoegd aan de naam van de gebeurtenis op het canvas. Bovendien kunt u het **[!UICONTROL Label]** veld gebruiken om een achtervoegsel toe te voegen aan de naam van de gebeurtenis die onder uw activiteit op het canvas wordt weergegeven. Dit is handig als u gebeurtenissen op het canvas wilt identificeren, vooral als u dezelfde gebeurtenis meerdere keren gebruikt. Het zal ook het zuiveren in het geval van fouten gemakkelijker maken en het zal rapporten gemakkelijker te lezen maken.

![](../assets/journey33.png)

## Algemene gebeurtenissen {#section_ofg_jss_dgb}

Voor dit type gebeurtenis kunt u alleen een label en een beschrijving toevoegen. De rest van de configuratie kan niet worden bewerkt. Het werd uitgevoerd door de technische gebruiker. Zie [](../event/about-events.md).

## Gebeurtenissen van Reaction {#section_dhx_gss_dgb}

De ingebouwde gebeurtenis **Reacties** is een van de verschillende gebeurtenisactiviteiten die beschikbaar zijn in het palet. Met deze activiteit kunt u reageren op volggegevens met betrekking tot een bericht dat is verzonden met e-mail, SMS of push-activiteiten binnen dezelfde reis. Deze informatie is afkomstig van transactiemeldingen in Adobe Campaign Standard. We leggen deze informatie in real time vast op het moment dat ze wordt gedeeld met het gegevensplatform. Voor pushberichten kunt u reageren op geklikte, verzonden of mislukte berichten. Voor SMS-berichten kunt u reageren op verzonden of mislukte berichten. Voor e-mailberichten kunt u reageren op geklikte, verzonden, geopende of mislukte berichten.

U kunt dit mechanisme ook gebruiken om een actie uit te voeren wanneer er geen reactie op uw berichten is. Hiertoe maakt u een tweede pad parallel aan de reactieactiviteit en voegt u een wachtactiviteit toe. Als er geen reactie optreedt tijdens de periode die is gedefinieerd in de wachtdienst, wordt het tweede pad gekozen. U kunt bijvoorbeeld een vervolgbericht verzenden.

Let op: u kunt alleen reactieactiviteiten op het canvas gebruiken als er al eerder een e-mail-, push- of SMS-activiteit is.

Zie [](../building-journeys/about-action-activities.md).

![](../assets/journey45.png)

Hier volgen de verschillende stappen voor het configureren van reactiegebeurtenissen:

1. Voeg een reactie toe **[!UICONTROL Label]** aan de reactie. Deze stap is optioneel.
1. Selecteer in de vervolgkeuzelijst de activiteit waarop u wilt reageren. U kunt alle handelingen selecteren die zich in de vorige stappen van het pad bevinden.
1. Afhankelijk van de actie die u hebt geselecteerd (een e-mail, SMS of een pushmelding), kiest u waarop u wilt reageren.
1. U kunt een voorwaarde definiëren als een optionele stap. Zo kunt u na een e-mailactie bijvoorbeeld besluiten om twee paden te maken, één met een reactiegebeurtenis om alleen klikken voor VIP-klanten te volgen en één met een reactiegebeurtenis om door vrouwen uitgevoerde klikbewerkingen te volgen.

>[!NOTE]
>
>Reactiegebeurtenissen kunnen geen e-mail-, SMS- of pushacties bijhouden die op een andere reis plaatsvinden.
>
>Gebeurtenissen van Reaction volgen klikt op koppelingen van het type &quot;bijgehouden&quot; (zie deze [pagina](https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/links.html#about-tracked-urls)). Er wordt geen rekening gehouden met abonnements- en spiegelpaginakoppelingen.

>[!CAUTION]
>
>E-mailclients zoals Gmail staan het blokkeren van afbeeldingen toe. E-mails die worden geopend, worden bijgehouden met een afbeelding van 0 pixels die in de e-mail is opgenomen. Als afbeeldingen worden geblokkeerd, wordt er geen rekening gehouden met het openen van e-mail.

## Segmentkwalificatiegebeurtenissen {#segment-qualification}

Deze activiteit staat uw reis toe om aan de ingangen en de uitgang van profielen in de segmenten van het Platform te luisteren om individuen te maken binnen of zich op een reis vooruit te bewegen. Raadpleeg deze [sectie](../segment/about-segments.md)voor meer informatie over het maken van segmenten.

Laten we zeggen dat je een &quot;zilveren klant&quot;-segment hebt. Met deze activiteit, kunt u alle nieuwe zilveren klanten een reis maken en hen een reeks gepersonaliseerde berichten verzenden.

Dit type gebeurtenis kan als eerste stap of later in de reis worden geplaatst.

Wanneer het segment wordt gestreamd met de optie High Frequency Audiences van Platform, wordt er in real-time naar toegang en uitgangen geluisterd. Als het segment niet wordt gestreamd, wordt bij de berekening van het segment rekening gehouden met de in- en uitgangen.

1. Ontgrendel de categorie **Gebeurtenissen** en zet een **segmentkwalificatieactiviteit** neer op uw canvas.

   ![](../assets/segment5.png)

1. Voeg een **Label** toe aan de activiteit. Deze stap is optioneel.

1. Klik in het veld **Segment** en selecteer de segmenten die u wilt benutten.

   ![](../assets/segment6.png)

1. Kies in het veld **Gedrag** of u wilt luisteren naar segmentingangen, uitgangen of beide.

1. Selecteer een naamruimte. Dit is alleen nodig als het evenement als de eerste stap van de reis wordt geplaatst.

   ![](../assets/segment7.png)

De nuttige lading bevat de volgende contextinformatie, die u in voorwaarden en acties kunt gebruiken:

* het gedrag (ingang, uitgang)
* het tijdstempel van de kwalificatie
* segment-id

## Geavanceerd gebruik: gebeurtenissen met een wachttijd parallel{#section_vxv_h25_pgb}

**Hoe kunt u alleen tijdens een bepaalde tijd naar een gebeurtenis luisteren?**

Een gebeurtenisactiviteit die in de reis wordt geplaatst luistert voor onbepaalde tijd naar gebeurtenissen. Als u alleen gedurende een bepaalde tijd naar een gebeurtenis wilt luisteren, moet u een wachtactiviteit toevoegen parallel aan het gebeurtenispad. De reis zal dan aan de gebeurtenis tijdens de tijd luisteren die in de wachttijdactiviteit wordt gespecificeerd. Als een gebeurtenis tijdens die periode wordt ontvangen, zal de persoon in de gebeurtenisweg stromen. Als niet, zal de klant in de wachttijdweg stromen.

U hebt bijvoorbeeld een welkomstpushbericht naar een klant gestuurd en u wilt alleen een pushbericht voor maaltijdkortingen verzenden als de klant het restaurant binnen de volgende 6 uur betreedt. Hiervoor maakt u een tweede pad (parallel aan de restaurantgebeurtenis één) met een wachtactiviteit van 6 uur. Als de restaurantgebeurtenis minder dan 6 uur na de welkomstpush wordt ontvangen, wordt de pushactiviteit voor de maaltijdkorting verzonden. Als er geen restaurantgebeurtenis binnen de volgende 6 uur wordt ontvangen, loopt de persoon door het wachttijdpad.

![](../assets/journeyuc2_31.png)
