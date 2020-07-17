---
title: De berichtparameters definiëren
description: Leer hoe te om de berichtparameters te bepalen
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
source-wordcount: '214'
ht-degree: 0%

---


# De berichtparameters definiëren {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

Plak in de **[!UICONTROL Message parameters]** sectie een voorbeeld van de JSON-payload die u naar de externe service wilt verzenden.


![](../assets/customactionpayloadmessage.png)

U kunt bepalen of het type van de parameter juist is (bijvoorbeeld: tekenreeks, geheel getal, enz.).

U hebt ook de keuze tussen het opgeven van een parameter als constante of variabele:

* Constante betekent dat de waarde van de parameter in de ruit van de actieconfiguratie door een technische persoon wordt bepaald. De waarde zal altijd het zelfde over reizen zijn. De kleur verandert niet en de markeerstift ziet deze niet wanneer u de aangepaste handeling voor de reis gebruikt. Het kan bijvoorbeeld een id zijn die het externe systeem verwacht. In dat geval is het veld rechts van de schakelconstante/variabele de doorgegeven waarde.
* Variabele betekent dat de waarde van de parameter varieert. De markering die deze aangepaste actie gebruikt, kan de gewenste waarde doorgeven of opgeven waar de waarde voor deze parameter moet worden opgehaald (bijvoorbeeld van de gebeurtenis, van het Adobe Experience Platform, enz.). In dat geval is het veld aan de rechterkant van de schakelconstante/variabele het label dat de markator in de reis ziet om deze parameter een naam te geven.
