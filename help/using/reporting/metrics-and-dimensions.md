---
product: adobe campaign
title: Statistieken en afmetingen
description: Meer informatie over de afmetingen en maatstaven die beschikbaar zijn voor Journey Orchestration
feature: Journeys
role: User
level: Intermediate
exl-id: f6897011-0a5e-4094-a18e-ba2aa25f902c
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '1080'
ht-degree: 0%

---

# Statistieken en afmetingen {#concept_rfj_wpt_52b}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


>[!NOTE]
>
>Leveringsgegevens worden alleen ingevuld als u Adobe Campaign Standard hebt.

Hier vindt u de lijst met alle componenten die beschikbaar zijn in dynamische rapporten en hun definities.

In de onderstaande tabel staan de afmetingen die worden gebruikt in reisrapporten en de definities daarvan.

Meer op verenigbaarheid tussen dimensies en metriek leren, verwijs naar [ deze pagina ](../assets/do-not-localize/dynamic_report_compatibility_journey.pdf).

## Reisafmetingen {#MBE_table_wk4_bnj_w2b}

In de onderstaande tabel staan de afmetingen die worden gebruikt in reisrapporten, de definities en de formules van de reisverslagen.

| Afmetingen | Definitie |
|--- |--- |
| **Actie** | Lijst van elke actie (**actienaam - actielabel**) die in reizen wordt gebruikt b.v. duw - de bevestiging van de Controle, E-mail - beloningen trouw. |
| **Gegevensbron** | Lijst van gegevensbronnen (**gegevens bronnaam**) die worden gebruikt om gegevens in een reis te verrijken b.v. Adobe Experience Platform, het systeem van de Voorbehoud. |
| **[!UICONTROL Event]** | Lijst van elke gebeurtenis (**gebeurtenisnaam - gebeurtenisetiket**) die in reizen b.v. gebeurtenis Geometrixx wordt gebruikt - de controle van Geometrixx. |
| **de groep van het Gebied** | Lijst van gebiedsgroepen (**naam van de gebiedsgroep**) die wordt gebruikt om gegevens in reizen te verrijken b.v. de het gebiedsgroep van het Profiel, het reserveringssysteem van Geometrixx. |
| **Reis** | Lijst van elke reis (**reisnaam**) op testwijze en levende b.v. het verlaten van het Kart, het bericht van de boeking van het Hotel. |
| **versie van de Reis** | Lijst van elke gepubliceerde versie van een reis (**reisnaam + aantal van de versie**) b.v. het verlaten van de kunst v1, het bericht van de Boeking van het Hotel v2. |
| **Orchestration** | Lijst van elke orkestactiviteit (**Voorwaarde, Eind, wacht**) bepaald en gebruikt in reizen. |

## Afmetingen van levering {#delivery-dimensions}

In de onderstaande tabel vindt u een overzicht van de afleveringsafmetingen die worden gebruikt in reisrapporten, de definities en de formules van de aflevering.

| Dimension | Definitie |
|--- |--- |
| **Browser** | Browser waarvan het bericht werd geopend of aangeklikt. |
| **Naam van de Levering** | Label en id van de levering. |
| **Apparaat** | Apparaat van waaruit de e-mail/SMS/push-melding is geopend/bekeken/aangeklikt. |
| **Type van Bericht** | Kanaal dat voor de levering wordt gebruikt, zoals e-mail, SMS, pushmelding of In-App. |
| **Mobiele App naam** | Naam van de mobiele toepassing |
| **Platform** | Platform van het apparaat waarvan het bericht werd geopend/bekeken/aangeklikt. |
| **[!UICONTROL Push platform]** | Platform van het apparaat waarvan de pushmelding is geopend, zoals iOS of Android. |
| **Ontvangend domein** | Domein dat wordt gebruikt om de e-mail te openen. |
| **het Volgen URL** | URL waarop de gebruiker via het bericht heeft geklikt. |
| **het Volgen categorie URL** | Categorie die is toegewezen aan de URL voor bijhouden. |
| **het Volgen URL etiket** | Label dat aan de URL wordt gegeven, zoals de spiegel, neemt contact met ons op of opent. |
| **Variant** | Variant van het e-mailbericht in het geval van A/B-tests. |

## Reiscijfers {#MBE_p_p22_c4j_w2b}

In de onderstaande tabel vindt u een lijst met maatstaven die worden gebruikt in reisrapporten, de definities en de formules van deze statistieken.

| Metrisch | Definitie |
|--- |---|
| **Voltooid** | Het totale aantal personen dat normaal de reis beëindigde. |
| **het tarief van de Voltooiing** | Het totale aantal personen dat normaal gesproken de reis beëindigde, vergeleken met het totale aantal personen dat de reis heeft betreden. |
| **Huidige** | Het totale aantal personen dat momenteel op reis is, d.w.z. het aantal personen dat is binnengekomen min het aantal personen dat is vertrokken, de fouten en het tijdstip waarop de reis heeft plaatsgevonden. |
| **Huidige tarief** | Het totale aantal personen dat momenteel op reis is, in vergelijking met het aantal personen dat de reis heeft betreden. |
| **binnengekomen** | Het totale aantal gebeurtenissen dat zich heeft voorgedaan om een individuele ingang in de reis te beginnen. |
| **Fout** | Het totale aantal fouten dat tijdens een reis is opgetreden, maar dat de reis niet heeft verhinderd succesvol te zijn. |
| **Fout in Actie** | Het totale aantal fouten dat is opgetreden voor handelingen. |
| **Fout in Verrijking** | Het totale aantal fouten dat voor een gegevensverrijking voorkwam toen het roepen van een gegevensbron/gebiedsgroep. |
| **Fout in Gebeurtenis** | Het totale aantal fouten dat is opgetreden voor gebeurtenissen. |
| **Tarief van de Fout** | Het totale aantal fouten tijdens een reis in vergelijking met het totale aantal voorvallen tijdens de reis. |
| **Uitvoerde Actie** | Totaal aantal uitgevoerde acties voor een reis. |
| **Uitvoerde Verrijking** | Het totale aantal verbeteringen dat wordt uitgevoerd door een gegevensbron aan te roepen om specifieke veldgroepen op te halen. |
| **Uitvoerde Gebeurtenis** | Totaal aantal uitgevoerde acties voor een reis. |
| **Uitvoerd Orchestration** | Het totale aantal orkestobjecten (einde, wacht, voorwaarde) dat wordt uitgevoerd voor een reis. |
| **Ontbroken** | Het totale aantal ritten dat niet met succes is uitgevoerd. |
| **Ontbroken tarief** | Het totale aantal ritten dat niet met succes werd uitgevoerd in vergelijking met het aantal ritten. |

## Leveringscijfers {#delivery-metrics}

In de onderstaande tabel vindt u een lijst met maatstaven die tijdens de reis worden gebruikt
verslagen, hun definities en formules.

| Metrisch | Definitie |
|--- |--- |
| **op lijst van gewezen personen** | Aantal ontvangers die een e-mailbericht hebben gedeclareerd als spam of junk. |
| **tarief van de Lijst van gewezen personen** | Het totale aantal berichten op lijst van gewezen personen vergeleken met verzonden berichten. |
| **Bounces + fouten** | Totaal van fouten die tijdens levering en automatische terugkeerverwerking met betrekking tot het totale aantal verzonden berichten worden gecumuleerd. |
| **Stuiteren + foutentarief** | Het totale aantal berichten dat is teruggevallen in vergelijking met verzonden berichten. |
| **klik** | Het aantal keren dat op een inhoud is geklikt in een levering. |
| **klik door tarief** | Het totale aantal klikken in een levering in verhouding tot het aantal geleverde berichten. |
| **Geleverd** | Het aantal berichten dat is verzonden in verhouding tot het totale aantal verzonden berichten. |
| **Geleverd tarief** | Het totale aantal berichten dat is afgeleverd in vergelijking met verzonden berichten. |
| **Fout** | Het totale aantal fouten dat tijdens een reis is opgetreden, maar dat de reis niet heeft verhinderd succesvol te zijn. |
| **Harde stuiteren** | Het totale aantal permanente fouten, zoals een onjuist e-mailadres. |
| **Harde het stuiteren tarief** | Het totale aantal leveringen dat is mislukt als gevolg van permanente fouten in vergelijking met verzonden berichten. |
| **Spiegel pagina** | Aantal ontvangers die op de verbinding van de spiegelpagina klikte. |
| **Spiegel paginatarief** | Het totale aantal klikken op de koppeling van de spiegelpagina in verhouding tot het totale aantal geleverde berichten. |
| **Open** | Aantal keren dat een bericht in een levering werd geopend. |
| **Open Tarief** | Het totale aantal geopende berichten in verhouding tot het aantal geleverde berichten. |
| **Quarantine** | Aantal berichten die in quarantaine van het adres stuitten en resulteerden. |
| **Tarief van de Quarantine** | Het totale aantal quarantines in vergelijking met verzonden berichten. |
| **Afgewezen** | Aantal berichten die als spam door de servers SMTP worden geclassificeerd. |
| **Geweigerd tarief** | Het totale aantal berichten gemarkeerd als afgewezen in vergelijking met verzonden berichten. |
| **Verwerkt/verzonden** | Het totale aantal verzendt voor de levering. |
| **Zachte stuit** | Het totale aantal tijdelijke fouten, zoals een volledig postvak. |
| **Zwak stuitpercentage** | Het totale aantal leveringen dat vanwege een tijdelijke reden is mislukt in vergelijking met verzonden berichten. |
| **Unieke kliks** | Aantal ontvangers die op een inhoud in een levering hebben geklikt. |
| **Uniek opent** | Aantal ontvangers dat de levering heeft geopend. |
| **Unsubscribed** | Aantal klikken op de verbinding van het unsubscription. |
| **Unsubscribe tarief** | Het totale aantal afmeldingen door de ontvanger in vergelijking met de geleverde berichten. |
