---
product: adobe campaign
title: De gebeurtenis configureren
description: Leer hoe u de gebeurtenis configureert voor het eenvoudige gebruiksgeval van de reis
feature: Journeys
role: User
level: Intermediate
exl-id: 7423f4eb-005d-43a5-a403-97bee1e8d480
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 8%

---

# De gebeurtenis configureren{#concept_y44_hcy_w2b}

In ons scenario, moeten wij een gebeurtenis ontvangen telkens als een persoon dichtbij een baken loopt dat naast de spanwijdte wordt geplaatst. De **technisch gebruiker** moet de gebeurtenis vormen het systeem aan in onze reis zal luisteren.

Voor meer informatie over gebeurtenisconfiguratie raadpleegt u [deze pagina](../event/about-events.md).

1. Klik in het bovenste menu op de knop **[!UICONTROL Events]** en klik op **[!UICONTROL Add]** om een nieuwe gebeurtenis te maken.

   ![](../assets/journeyuc1_1.png)

1. De naam wordt ingevoerd zonder spaties of speciale tekens: &quot;SpaBeacon&quot;.

   ![](../assets/journeyuc1_2.png)

1. Vervolgens selecteert u het schema en definieert u de lading die voor deze gebeurtenis wordt verwacht. We selecteren de velden die nodig zijn in het genormaliseerde XDM-model. We hebben de Experience Cloud-id nodig om de persoon te identificeren in de realtime database voor klantprofielen: _endUserIDs > Experience > mcid > id_. Er wordt automatisch een id voor deze gebeurtenis gegenereerd. Deze id is opgeslagen in het dialoogvenster **[!UICONTROL eventID]** field (_Experience > Campagne > Orchestration > eventID_). Het systeem dat de gebeurtenis duwt zou geen identiteitskaart moeten produceren, zou het moeten gebruiken beschikbaar in de voorproef van de lading. In ons gebruiksgeval, wordt dit ID gebruikt om de bakenplaats te identificeren. Elke keer dat een persoon in de buurt van de spa-baken loopt, wordt een gebeurtenis verzonden die deze specifieke gebeurtenis-id bevat. Dit staat het systeem toe om te weten welk baken de gebeurtenis teweegbracht die verzendt.

   ![](../assets/journeyuc1_3.png)

   >[!NOTE]
   >
   >De lijst met velden verschilt per schema. Volgens de schemadefinitie zijn sommige velden mogelijk verplicht en vooraf geselecteerd.

1. We moeten een naamruimte selecteren. Een naamruimte wordt vooraf geselecteerd op basis van schema-eigenschappen. U kunt de voorinstelling behouden. Voor meer informatie over naamruimten raadpleegt u [deze pagina](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc1_6.png)

1. Een sleutel wordt vooraf geselecteerd gebaseerd op schemaeigenschappen en namespace geselecteerd. Je kunt het houden.

   ![](../assets/journeyuc1_5.png)

1. Klik op **[!UICONTROL Save]**.

1. Klik op de knop **[!UICONTROL View Payload]** pictogram om een voorvertoning weer te geven van de lading die door het systeem wordt verwacht en deze te delen met de persoon die verantwoordelijk is voor het verzenden van de gebeurtenis. Deze nuttige lading zal in de postback van de het beleidsconsole van de Diensten van Mobile moeten worden gevormd.

   ![](../assets/journeyuc1_7.png)

   Het evenement is klaar om op reis te worden gebruikt. U moet nu de mobiele toepassing vormen zodat het de verwachte nuttige lading naar het Streaming Ingestie APIs eindpunt kan verzenden. Zie [deze pagina](../event/additional-steps-to-send-events-to-journey-orchestration.md).
