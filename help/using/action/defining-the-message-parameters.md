---
product: adobe campaign
title: Actieparameters definiëren
description: Leer hoe u de actieparameters definieert
feature: Journeys
role: User
level: Intermediate
exl-id: ea9cdb1d-dde6-4080-8f35-7f8cd3cf3644
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 2%

---

# Actieparameters definiëren {#concept_wy4_bf1_2gb}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/nl/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


![](../assets/messageparameterssection.png)

Plak in de sectie **[!UICONTROL Action parameters]** een voorbeeld van de JSON-payload die u naar de externe service wilt verzenden.

![](../assets/customactionpayloadmessage.png)

>[!NOTE]
>
>Veldnamen in de payload mogen geen &quot;.&quot; bevatten teken. Ze kunnen niet beginnen met het teken ‘$’.

U kunt het parametertype definiëren (bijvoorbeeld: tekenreeks, geheel getal, enz.).

U kunt ook opgeven of een parameter een constante of een variabele is.

* Constante betekent dat de waarde van de parameter in de ruit van de actieconfiguratie door een technische persoon wordt bepaald. De waarde zal altijd het zelfde over reizen zijn. Het zal niet variëren en de marktleider zal het niet zien wanneer het gebruiken van de douaneactie in de reis. Het kan bijvoorbeeld een id zijn die het externe systeem verwacht. In dat geval is het veld rechts van de schakelconstante/variabele de doorgegeven waarde.
* Variabele betekent dat de waarde van de parameter varieert. De markering die deze aangepaste actie gebruikt, kan de gewenste waarde doorgeven of opgeven waar de waarde voor deze parameter moet worden opgehaald (bijvoorbeeld van het evenement, van de Adobe Experience Platform, enz.). In dat geval is het veld aan de rechterkant van de schakelconstante/variabele het label dat de markator in de reis ziet om deze parameter een naam te geven.

![](../assets/customactionpayloadmessage2.png)
