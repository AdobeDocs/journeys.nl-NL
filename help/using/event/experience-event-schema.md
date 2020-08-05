---
title: 'Over ExperienceEvent-schema''s voor Journey Orchestration-gebeurtenissen '
description: 'Meer informatie over ExperienceEvent-schema''s voor Journey Orchestration Events '
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
source-wordcount: '321'
ht-degree: 0%

---



# Over ExperienceEvent-schema&#39;s voor [!DNL Journey Orchestration] gebeurtenissen

[!DNL Journey Orchestration] Gebeurtenissen zijn XDM Experience Events die via Streaming Ingestie naar de Adobe Experience Platform worden verzonden.

Daarom is een belangrijke voorwaarde voor het instellen van gebeurtenissen voor [!DNL Journey Orchestration] dat u bekend bent met het Adobe Experience Platform&#39;s Experience Data Model (of XDM) en hoe u XDM Experience Event-schema&#39;s kunt samenstellen, en hoe u XDM-opgemaakte gegevens kunt streamen naar de Adobe Experience Platform.

## Schemavereisten voor [!DNL Journey Orchestration] gebeurtenissen

De eerste stap bij het opzetten van een gebeurtenis voor [!DNL Journey Orchestration] is ervoor te zorgen dat u een XDM-schema hebt dat wordt gedefinieerd om de gebeurtenis te vertegenwoordigen, en een dataset die wordt gecreeerd om instanties van de gebeurtenis op Adobe Experience Platform te registreren. Het hebben van een dataset voor uw gebeurtenissen is niet strikt noodzakelijk, maar het verzenden van de gebeurtenissen naar een specifieke dataset zal u toestaan om gebruikers&#39; gebeurtenisgeschiedenis voor toekomstige verwijzing en analyse te handhaven, zodat is het altijd een goed idee. Als u nog geen geschikt schema en dataset voor uw gebeurtenis hebt, kunnen beide taken in de Adobe Experience Platform-webinterface worden uitgevoerd.

![](../assets/schema1.png)

Om het even welk schema XDM dat voor [!DNL Journey Orchestration] gebeurtenissen zal worden gebruikt zou aan de volgende vereisten moeten voldoen:

* Het schema moet van de klasse XDM ExperienceEvent zijn.

![](../assets/schema2.png)

* Het schema moet de Orchestration eventID-mix bevatten. [!DNL Journey Orchestration] gebruikt dit veld om gebeurtenissen te identificeren die tijdens reizen worden gebruikt.

![](../assets/schema3.png)

* Declareer een identiteitsveld voor het identificeren van het onderwerp van de gebeurtenis. Als er geen identiteit is opgegeven, kan een identiteitskaart worden gebruikt. Dit wordt niet aanbevolen.

![](../assets/schema4.png)

* Als u deze gegevens voor raadpleging later in een Reis beschikbaar zou willen zijn, merk het schema en de dataset voor profiel.

![](../assets/schema5.png)

![](../assets/schema6.png)

* U kunt gegevensvelden vrij gebruiken om andere contextgegevens vast te leggen die u met de gebeurtenis wilt opnemen, zoals informatie over de gebruiker, het apparaat waaruit de gebeurtenis is gegenereerd, de locatie of andere betekenisvolle omstandigheden die met de gebeurtenis verband houden.

![](../assets/schema7.png)

![](../assets/schema8.png)