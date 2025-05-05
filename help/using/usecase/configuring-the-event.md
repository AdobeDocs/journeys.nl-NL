---
product: adobe campaign
title: De gebeurtenis configureren
description: Leer hoe u de gebeurtenis configureert voor het eenvoudige gebruiksgeval van de reis
feature: Journeys
role: User
level: Intermediate
exl-id: 7423f4eb-005d-43a5-a403-97bee1e8d480
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 7%

---

# De gebeurtenis configureren{#concept_y44_hcy_w2b}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


In ons scenario, moeten wij een gebeurtenis ontvangen telkens als een persoon dichtbij een baken loopt dat naast de spanwijdte wordt geplaatst. De **technische gebruiker** moet de gebeurtenis vormen het systeem aan in onze reis zal luisteren.

Voor extra informatie over gebeurtenisconfiguratie, verwijs naar [ deze pagina ](../event/about-events.md).

1. Klik in het bovenste menu op de tab **[!UICONTROL Events]** en klik op **[!UICONTROL Add]** om een nieuwe gebeurtenis te maken.

   ![](../assets/journeyuc1_1.png)

1. We voeren de naam in zonder spaties of speciale tekens: &quot;SpaBeacon&quot;.

   ![](../assets/journeyuc1_2.png)

1. Vervolgens selecteert u het schema en definieert u de lading die voor deze gebeurtenis wordt verwacht. Wij selecteren de gebieden nodig van het genormaliseerde model XDM. Wij hebben Experience Cloud identiteitskaart nodig om de persoon in het gegevensbestand van het Profiel van de Klant in real time te identificeren: _endUserIDs > ervaring > methode > identiteitskaart_. Er wordt automatisch een id voor deze gebeurtenis gegenereerd. Deze identiteitskaart wordt opgeslagen op het **[!UICONTROL eventID]** gebied (_ervaring > campagne > orchestratie > eventID_). Het systeem dat de gebeurtenis duwt zou geen identiteitskaart moeten produceren, zou het moeten gebruiken beschikbaar in de voorproef van de lading. In ons gebruiksgeval, wordt dit ID gebruikt om de bakenplaats te identificeren. Elke keer dat een persoon in de buurt van de spa-baken loopt, wordt een gebeurtenis verzonden die deze specifieke gebeurtenis-id bevat. Dit staat het systeem toe om te weten welk baken de gebeurtenis teweegbracht die verzendt.

   ![](../assets/journeyuc1_3.png)

   >[!NOTE]
   >
   >De lijst met velden verschilt per schema. Volgens de schemadefinitie zijn sommige velden mogelijk verplicht en vooraf geselecteerd.

1. We moeten een naamruimte selecteren. Een naamruimte wordt vooraf geselecteerd op basis van schema-eigenschappen. U kunt de voorinstelling behouden. Voor meer informatie over namespaces, zie [ deze pagina ](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc1_6.png)

1. Een sleutel wordt vooraf geselecteerd gebaseerd op schemaeigenschappen en namespace geselecteerd. Je kunt het houden.

   ![](../assets/journeyuc1_5.png)

1. Klik op **[!UICONTROL Save]**.

1. Klik op het pictogram **[!UICONTROL View Payload]** om een voorvertoning weer te geven van de lading die door het systeem wordt verwacht en deze te delen met de persoon die verantwoordelijk is voor het verzenden van de gebeurtenis. Deze nuttige lading zal in postback van de Mobiele het beleidsconsole van de Diensten moeten worden gevormd.

   ![](../assets/journeyuc1_7.png)

   Het evenement is klaar om op reis te worden gebruikt. U moet nu de mobiele toepassing vormen zodat het de verwachte nuttige lading naar het Streaming Ingestie APIs eindpunt kan verzenden. Zie [deze pagina](../event/additional-steps-to-send-events-to-journey-orchestration.md).
