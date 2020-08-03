---
title: Metriek en afmetingen
description: Meer informatie over de beschikbare afmetingen en meetgegevens voor Journey Orchestration
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 0%

---


# Metriek en afmetingen {#concept_rfj_wpt_52b}

>[!NOTE]
>
>Leveringsgegevens worden alleen ingevuld als u Adobe Campaign Standard hebt.

Hier vindt u de lijst met alle componenten die beschikbaar zijn in dynamische rapporten en hun definities.

In de onderstaande tabel staan de afmetingen die worden gebruikt in reisrapporten en de definities daarvan.

Raadpleeg [deze pagina](../assets/do-not-localize/dynamic_report_compatibility_journey.pdf)voor meer informatie over compatibiliteit tussen afmetingen en metriek.

## Reisafmetingen {#MBE_table_wk4_bnj_w2b}

In de onderstaande tabel staan de afmetingen die worden gebruikt in reisrapporten, de definities en de formules van de reisverslagen.

| Dimension | Definitie |
|--- |--- |
| **Handeling** | Lijst van alle handelingen (naam van de **handeling - actielabel**) die tijdens reizen worden gebruikt, bijvoorbeeld push - Check out bevestiging, Email - Rewards getrouwheid. |
| **Gegevensbron** | Lijst met gegevensbronnen (naam **van** gegevensbron) die worden gebruikt om gegevens te verrijken op een reis, bijvoorbeeld Adobe Experience platform, Reservation System. |
| **[!UICONTROL Event]** | Lijst van alle gebeurtenissen (naam van **gebeurtenis - label** van gebeurtenis) die tijdens reizen worden gebruikt, bijv. gebeurtenis Geometrixx - uitchecken van Geometrixx. |
| **Veldgroep** | Lijst van veldgroepen (**veldgroepsnaam**) die worden gebruikt om gegevens te verrijken tijdens reizen, bijvoorbeeld profielveldgroep, reserveringssysteem Geometrixx. |
| **Reis** | Lijst van elke reis (**reisnaam**) in testmodus en live, bv. stopzetting van de auto, kennisgeving van reservering van het hotel. |
| **Reisversie** | Lijst van elke gepubliceerde versie van een reis (**reisnaam + versienummer**), bv. Afhalen van winkelwagentje v1, kennisgeving van hotelreservering v2. |
| **Orchestratie** | Lijst van elke orkestactiviteit (**Voorwaarde, Eind, Wacht**) bepaald en gebruikt in reizen. |

## Afmetingen van levering {#delivery-dimensions}

In de onderstaande tabel vindt u een overzicht van de afleveringsafmetingen die worden gebruikt in reisrapporten, de definities en de formules van de aflevering.

| Dimension | Definitie |
|--- |--- |
| **Browser** | Browser waarvan het bericht werd geopend of aangeklikt. |
| **Leveringsnaam** | Label en id van de levering. |
| **Apparaat** | Apparaat van waaruit de e-mail/SMS/push-melding is geopend/weergegeven/waarop is geklikt. |
| **Berichttype** | Kanaal dat voor de levering wordt gebruikt, zoals e-mail, SMS, pushmelding of In-App. |
| **Naam van mobiele toepassing** | Naam van de mobiele toepassing |
| **Platform** | Platform van het apparaat waarvan het bericht werd geopend/bekeken/aangeklikt. |
| **[!UICONTROL Push platform]** | Platform van het apparaat waarvan de pushmelding is geopend, zoals iOS of Android. |
| **Ontvangerdomein** | Domein dat wordt gebruikt om de e-mail te openen. |
| **URL bijhouden** | URL waarop de gebruiker via het bericht heeft geklikt. |
| **Categorie URL bijhouden** | Categorie die is toegewezen aan de URL voor bijhouden. |
| **URL-label bijhouden** | Label dat aan de URL wordt gegeven, zoals de spiegelpagina, neemt u contact met ons op of opent u. |
| **Variant** | Variant van het e-mailbericht in het geval van A/B-tests. |


## Reiscijfers {#MBE_p_p22_c4j_w2b}

In de onderstaande tabel vindt u een lijst met maatstaven die worden gebruikt in reisrapporten, de definities en de formules van deze statistieken.

| Metrisch | Definitie |
|--- |---|
| **Voltooid** | Het totale aantal personen dat normaal de reis beëindigde. |
| **Voltooiingsgraad** | Het totale aantal personen dat normaal gesproken de reis beëindigde, vergeleken met het totale aantal personen dat de reis heeft betreden. |
| **Huidig** | Het totale aantal personen dat momenteel op reis is, d.w.z. het aantal personen dat is binnengekomen min het aantal personen dat is vertrokken, de fouten en het tijdstip waarop de reis heeft plaatsgevonden. |
| **Huidige rentevoet** | Het totale aantal personen dat momenteel op reis is, in vergelijking met het aantal personen dat de reis heeft betreden. |
| **Ingegaan** | Het totale aantal gebeurtenissen dat heeft plaatsgevonden om een individuele ingang in de reis te beginnen. |
| **Fout** | Het totale aantal fouten dat tijdens een reis is opgetreden, maar dat de reis niet heeft verhinderd succesvol te zijn. |
| **Fout in handeling** | Het totale aantal fouten dat is opgetreden voor handelingen. |
| **Fout in verrijking** | Het totale aantal fouten dat voor een gegevensverrijking voorkwam toen het roepen van een gegevensbron/gebiedsgroep. |
| **Fout in gebeurtenis** | Het totale aantal fouten dat is opgetreden voor gebeurtenissen. |
| **Foutfrequentie** | Het totale aantal fouten tijdens een reis in vergelijking met het totale aantal voorvallen tijdens de reis. |
| **Uitgevoerde actie** | Totaal aantal uitgevoerde acties voor een reis. |
| **Uitvoerde verrijking** | Het totale aantal verbeteringen dat wordt uitgevoerd door een gegevensbron aan te roepen om specifieke veldgroepen op te halen. |
| **Uitvoerde gebeurtenis** | Totaal aantal uitgevoerde acties voor een reis. |
| **Uitvoerde Orchestratie** | Het totale aantal orkestobjecten (einde, wacht, voorwaarde) dat wordt uitgevoerd voor een reis. |
| **Mislukt** | Het totale aantal ritten dat niet met succes is uitgevoerd. |
| **Mislukte snelheid** | Het totale aantal ritten dat niet met succes werd uitgevoerd in vergelijking met het aantal ritten. |

## Leveringscijfers {#delivery-metrics}

In de onderstaande tabel vindt u een lijst met maatstaven die worden gebruikt in journalistieke rapporten en de bijbehorende definities en formules.

| Metrisch | Definitie |
|--- |--- |
| **Op lijst van afgewezen personen** | Aantal ontvangers die een e-mailbericht hebben gedeclareerd als spam of junk. |
| **Lijst van afgewezen personen** | Het totale aantal berichten op lijst van afgewezen personen vergeleken met verzonden berichten. |
| **Bounces + fouten** | Totaal van fouten die tijdens levering en automatische terugkeerverwerking met betrekking tot het totale aantal verzonden berichten worden gecumuleerd. |
| **Stuiteren + foutenfrequentie** | Het totale aantal berichten dat is teruggevallen in vergelijking met verzonden berichten. |
| **Klik op** | Het aantal keren dat op een inhoud is geklikt in een levering. |
| **Klikken tot snelheid** | Het totale aantal klikken in een levering in verhouding tot het aantal geleverde berichten. |
| **Geleverd** | Het aantal berichten dat is verzonden in verhouding tot het totale aantal verzonden berichten. |
| **Afgeleverde rente** | Het totale aantal berichten dat is afgeleverd in vergelijking met verzonden berichten. |
| **Fout** | Het totale aantal fouten dat tijdens een reis is opgetreden, maar dat de reis niet heeft verhinderd succesvol te zijn. |
| **Hard stuiteren** | Het totale aantal permanente fouten, zoals een onjuist e-mailadres. |
| **Harde stuitsnelheid** | Het totale aantal leveringen dat is mislukt als gevolg van permanente fouten in vergelijking met verzonden berichten. |
| **Pagina spiegelen** | Aantal ontvangers die op de verbinding van de spiegelpagina klikte. |
| **Paginasnelheid spiegelen** | Het totale aantal klikken op de koppeling van de spiegelpagina in verhouding tot het totale aantal geleverde berichten. |
| **Open** | Aantal keren dat een bericht in een levering werd geopend. |
| **OpenRate** | Het totale aantal geopende berichten in verhouding tot het aantal geleverde berichten. |
| **Quarantine** | Aantal berichten die in quarantaine van het adres stuitten en resulteerden. |
| **Quarantine Rate** | Het totale aantal quarantines in vergelijking met verzonden berichten. |
| **Geweigerd** | Aantal berichten die als spam door de servers SMTP worden geclassificeerd. |
| **Geweigerde snelheid** | Het totale aantal berichten gemarkeerd als afgewezen in vergelijking met verzonden berichten. |
| **Verwerkt/verzonden** | Het totale aantal verzendt voor de levering. |
| **Zachte stuit** | Het totale aantal tijdelijke fouten, zoals een volledig postvak. |
| **Zachte stuitsnelheid** | Het totale aantal leveringen dat vanwege een tijdelijke reden is mislukt in vergelijking met verzonden berichten. |
| **Unieke klikken** | Aantal ontvangers die op een inhoud in een levering hebben geklikt. |
| **Unieke openingen** | Aantal ontvangers dat de levering heeft geopend. |
| **Abonnement opgezegd** | Aantal klikken op de verbinding van het unsubscription. |
| **Abonnement opzeggen** | Het totale aantal afmeldingen door de ontvanger in vergelijking met de geleverde berichten. |
