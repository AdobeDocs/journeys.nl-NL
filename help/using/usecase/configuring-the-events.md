---
product: adobe campaign
title: Gebeurtenissen configureren
description: Leer hoe te om de gebeurtenissen voor reis geavanceerd gebruiksgeval te vormen
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: 90139c72-8fae-4e6e-a79b-7c510f41fe38
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 7%

---

# Gebeurtenissen configureren {#concept_sbp_5cy_w2b}

In ons scenario moeten we telkens een evenement ontvangen wanneer een persoon het hotel Marlton en het restaurant binnenkomt. De **technische gebruiker** moet de twee gebeurtenissen vormen wij het systeem willen om aan in onze reis te luisteren.

Raadpleeg [deze pagina](../event/about-events.md) voor meer informatie over gebeurtenisconfiguratie.

1. Klik in het bovenste menu op de tab **[!UICONTROL Events]** en klik op **[!UICONTROL Add]** om een nieuwe gebeurtenis te maken.

   ![](../assets/journeyuc1_1.png)

1. U voert de naam in zonder spaties of speciale tekens: &quot;LobbyBeacon&quot;.

   ![](../assets/journeyuc2_1.png)

1. Vervolgens selecteert u het schema en definieert u de lading die voor deze gebeurtenis wordt verwacht. We selecteren de velden die nodig zijn in het genormaliseerde XDM-model. We hebben de Experience Cloud-id nodig om de persoon te identificeren in de realtime database voor klantprofielen: &quot;endUserIDs > _experience > mcid > id&quot;.

   Het registratietoken is ook nodig voor het verzenden van pushberichten: &quot;_experience > campagne > bericht > profiel > pushNotificationTokens > token&quot;

   Er wordt automatisch een id voor deze gebeurtenis gegenereerd. Deze id wordt opgeslagen in het veld **[!UICONTROL eventID]** (&quot;_experience > Campagne > Orchestratie > eventID&quot;). Het systeem dat de gebeurtenis duwt zou geen identiteitskaart moeten produceren, zou het moeten gebruiken beschikbaar in de voorproef van de lading. In ons gebruiksgeval, wordt dit ID gebruikt om de bakenplaats te identificeren. Elke keer dat een persoon in de buurt van het lobby-baken loopt, wordt een gebeurtenis verzonden die deze specifieke gebeurtenis-id bevat. Hetzelfde beginsel geldt voor de restaurantbakenevenementen. Dit staat het systeem toe om te weten welk baken de gebeurtenis teweegbracht die verzendt.

   ![](../assets/journeyuc2_2.png)

   >[!NOTE]
   >
   >De lijst met velden verschilt per schema. Volgens de schemadefinitie zijn sommige velden mogelijk verplicht en vooraf geselecteerd.

1. We moeten een naamruimte selecteren. Een naamruimte wordt vooraf geselecteerd op basis van schema-eigenschappen. U kunt de voorinstelling behouden. Zie [deze pagina](../event/selecting-the-namespace.md) voor meer informatie over naamruimten.

   ![](../assets/journeyuc2_4.png)

1. Een sleutel wordt vooraf geselecteerd gebaseerd op schemaeigenschappen en namespace geselecteerd. Je kunt het houden.

   ![](../assets/journeyuc2_4bis.png)

1. Klik op **[!UICONTROL Save]**.

1. Klik op het pictogram **[!UICONTROL View Payload]** om een voorvertoning weer te geven van de lading die door het systeem wordt verwacht en deze te delen met de persoon die verantwoordelijk is voor het verzenden van de gebeurtenis.  Deze nuttige lading zal in postback van de Mobiele het beleidsconsole van de Diensten moeten worden gevormd.

   ![](../assets/journeyuc2_5.png)

Maak op dezelfde manier de gebeurtenis &quot;RestaurantBeacon&quot;. Uw twee baken-gebeurtenissen worden gecreëerd en kunnen nu worden gebruikt op onze reis. U moet nu de mobiele toepassing vormen zodat het de verwachte nuttige lading naar het Streaming Ingestie APIs eindpunt kan verzenden. Zie [deze pagina](../event/additional-steps-to-send-events-to-journey-orchestration.md).
