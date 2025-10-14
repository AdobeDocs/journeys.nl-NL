---
product: adobe campaign
title: Gebeurtenissen configureren
description: Leer hoe te om de gebeurtenissen voor reis geavanceerd gebruiksgeval te vormen
feature: Journeys
role: User
level: Intermediate
exl-id: 90139c72-8fae-4e6e-a79b-7c510f41fe38
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 6%

---

# Gebeurtenissen configureren {#concept_sbp_5cy_w2b}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [&#x200B; hier &#x200B;](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


In ons scenario moeten we telkens een evenement ontvangen wanneer een persoon het hotel Marlton en het restaurant binnenkomt. De **technische gebruiker** moet de twee gebeurtenissen vormen wij het systeem willen in onze reis luisteren.

Voor extra informatie over gebeurtenisconfiguratie, verwijs naar [&#x200B; deze pagina &#x200B;](../event/about-events.md).

1. Klik in het bovenste menu op de tab **[!UICONTROL Events]** en klik op **[!UICONTROL Add]** om een nieuwe gebeurtenis te maken.

   ![](../assets/journeyuc1_1.png)

1. We voeren de naam in zonder spaties of speciale tekens: &quot;LobbyBeacon&quot;.

   ![](../assets/journeyuc2_1.png)

1. Vervolgens selecteert u het schema en definieert u de lading die voor deze gebeurtenis wordt verwacht. Wij selecteren de gebieden nodig van het genormaliseerde model XDM. We hebben de Experience Cloud-id nodig om de persoon te identificeren in de realtime database van het klantprofiel: &quot;endUserIDs > _experience > mcid > id&quot;.

   We hebben het registratietoken ook nodig om pushberichten te verzenden: &quot;_experience > campagne > bericht > profiel > pushNotificationTokens > token&quot;

   Er wordt automatisch een id voor deze gebeurtenis gegenereerd. Deze id wordt opgeslagen in het veld **[!UICONTROL eventID]** (&quot;_experience > Campagne > Orchestratie > eventID&quot;). Het systeem dat de gebeurtenis duwt zou geen identiteitskaart moeten produceren, zou het moeten gebruiken beschikbaar in de voorproef van de lading. In ons gebruiksgeval, wordt dit ID gebruikt om de bakenplaats te identificeren. Elke keer dat een persoon in de buurt van het lobby-baken loopt, wordt een gebeurtenis verzonden die deze specifieke gebeurtenis-id bevat. Hetzelfde beginsel geldt voor de restaurantbakenevenementen. Dit staat het systeem toe om te weten welk baken de gebeurtenis teweegbracht die verzendt.

   ![](../assets/journeyuc2_2.png)

   >[!NOTE]
   >
   >De lijst met velden verschilt per schema. Volgens de schemadefinitie zijn sommige velden mogelijk verplicht en vooraf geselecteerd.

1. We moeten een naamruimte selecteren. Een naamruimte wordt vooraf geselecteerd op basis van schema-eigenschappen. U kunt de voorinstelling behouden. Voor meer informatie over namespaces, zie [&#x200B; deze pagina &#x200B;](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc2_4.png)

1. Een sleutel wordt vooraf geselecteerd gebaseerd op schemaeigenschappen en namespace geselecteerd. Je kunt het houden.

   ![](../assets/journeyuc2_4bis.png)

1. Klik op **[!UICONTROL Save]**.

1. Klik op het pictogram **[!UICONTROL View Payload]** om een voorvertoning weer te geven van de lading die door het systeem wordt verwacht en deze te delen met de persoon die verantwoordelijk is voor het verzenden van de gebeurtenis.  Deze nuttige lading zal in postback van de Mobiele het beleidsconsole van de Diensten moeten worden gevormd.

   ![](../assets/journeyuc2_5.png)

Maak op dezelfde manier de gebeurtenis &quot;RestaurantBeacon&quot;. Uw twee baken-gebeurtenissen worden gecreëerd en kunnen nu worden gebruikt op onze reis. U moet nu de mobiele toepassing vormen zodat het de verwachte nuttige lading naar het Streaming Ingestie APIs eindpunt kan verzenden. Zie [deze pagina](../event/additional-steps-to-send-events-to-journey-orchestration.md).
