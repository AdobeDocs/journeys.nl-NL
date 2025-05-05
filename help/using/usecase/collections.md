---
product: adobe campaign
solution: Journey Orchestration
title: Verzamelingen dynamisch doorgeven met behulp van aangepaste handelingen
description: Een bericht verzenden met Campaign v7/v8
exl-id: 9ed62a74-3c51-4f15-af8a-d530ddf80b51
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 3%

---

# Verzamelingen dynamisch doorgeven met behulp van aangepaste handelingen{#passing-collection}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


U kunt een verzameling doorgeven in aangepaste handelingsparameters die bij uitvoering dynamisch worden gevuld. Er worden twee soorten verzamelingen ondersteund:

* eenvoudige verzamelingen: arrays van eenvoudige gegevenstypen, bijvoorbeeld met een listString:

  ```
  {
   "deviceTypes": [
       "android",
       "ios"
   ]
  }
  ```

* objectverzamelingen: een array met JSON-objecten, bijvoorbeeld:

  ```
  {
  "products":[
     {
        "id":"productA",
        "name":"A",
        "price":20.1
     },
     {
        "id":"productB",
        "name":"B",
        "price":10.0
     },
     {
        "id":"productC",
        "name":"C",
        "price":5.99
     }
   ]
  }
  ```

## Beperkingen {#limitations}

* Geneste arrays van objecten binnen een objectarray worden momenteel niet ondersteund. Bijvoorbeeld:

  ```
  {
  "products":[
    {
       "id":"productA",
       "name":"A",
       "price":20,
       "locations": [{"name": "Paris"}, {"name": "London"}]
    },
   ]
  }
  ```

* Als u verzamelingen wilt testen in de testmodus, moet u de modus Codeweergave gebruiken. De modus Codeweergave wordt momenteel niet ondersteund voor bedrijfsgebeurtenissen. U kunt alleen een verzameling met één element verzenden.

## Algemene procedure {#general-procedure}

In deze sectie gebruiken we het volgende JSON-payload-voorbeeld. Dit is een array van objecten met een veld dat een eenvoudige verzameling is.

```
{
  "ctxt": {
    "products": [
      {
        "id": "productA",
        "name": "A",
        "price": 20.1,
        "color":"blue",
        "locations": [
          "Paris",
          "London"
        ]
      },
      {
        "id": "productB",
        "name": "B",
        "price": 10.99
      }
    ]
  }
}
```

Je kunt zien dat &#39;products&#39; een array van twee objecten is. U moet ten minste één object hebben.

1. Maak een aangepaste handeling. Zie [deze pagina](../action/about-custom-action-configuration.md).

1. Plak in de sectie **[!UICONTROL Action parameters]** het JSON-voorbeeld. De weergegeven structuur is statisch: bij het plakken van de lading worden alle velden gedefinieerd als constanten.

   ![](../assets/uc-collection-1.png)

1. Pas indien nodig de veldtypen aan. De volgende veldtypen worden ondersteund voor verzamelingen: listString, listInteger, listDecimal, listBoolean, listDateTime, listDateTimeOnly, listDateOnly, listObject

   >[!NOTE]
   >
   >Het veldtype wordt automatisch afgeleid op basis van het voorbeeld van de payload.

1. Als u objecten dynamisch wilt doorgeven, moet u ze instellen als variabelen. In dit voorbeeld stellen we &#39;products&#39; in als variabele. Alle objectvelden in het object worden automatisch ingesteld op variabelen.

   >[!NOTE]
   >
   >Het eerste object van het ladingsvoorbeeld wordt gebruikt om de velden te definiëren.

1. Definieer voor elk veld het label dat op het canvas van de reis wordt weergegeven.

   ![](../assets/uc-collection-2.png)

1. Maak uw reis en voeg de aangepaste actie toe die u hebt gemaakt. Zie [deze pagina](../building-journeys/using-custom-actions.md).

1. Definieer in de sectie **[!UICONTROL Action parameters]** de arrayparameter (&quot;products&quot; in ons voorbeeld) met de geavanceerde expressie-editor.

   ![](../assets/uc-collection-3.png)

1. Typ voor elk van de volgende objectvelden de corresponderende veldnaam in het XDM-bronschema. Als de namen identiek zijn, is dit niet nodig. In ons voorbeeld hoeven we alleen &#39;product id&#39; en &#39;color&#39; te definiëren.

   ![](../assets/uc-collection-4.png)

Voor het matrixveld kunt u ook de geavanceerde expressie-editor gebruiken om gegevensbewerkingen uit te voeren. In het volgende voorbeeld, gebruiken wij de [ filter ](../functions/functionfilter.md) en [&#128279;](../functions/functionintersect.md) functies doorsnijden:

![](../assets/uc-collection-5.png)

## Bijzondere gevallen{#examples}

Voor heterogene typen en arrays van arrays wordt de array gedefinieerd met het listAny-type. U kunt alleen afzonderlijke items toewijzen, maar u kunt de array niet wijzigen in een variabele.

![](../assets/uc-collection-heterogeneous.png)

Voorbeeld van een heterogeen type:

```
{
    "data_mixed-types": [
        "test",
        "test2",
        null,
        0
    ]
}
```

Voorbeeld van array van arrays:

```
{
    "data_multiple-arrays": [
        [
            "test",
            "test1",
            "test2"
        ]
    ]
}
```

**Verwante onderwerpen**

[Aangepaste handelingen gebruiken](../building-journeys/using-custom-actions.md)
