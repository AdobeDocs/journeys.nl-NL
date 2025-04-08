---
product: adobe campaign
title: Voorwaardelijke instructie (indien, then, else)
description: Meer informatie over voorwaardelijke instructies
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 48fb4944-5b78-4ccd-9b9b-ffe0719e7c21
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---

# Voorwaardelijke instructie (indien, then, else) {#section_cdz_lsk_w3b}


>[!CAUTION]
>
>**zoekend Adobe Journey Optimizer**? Klik [ hier ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} voor de documentatie van Journey Optimizer.
>
>
>_Deze documentatie verwijst naar erfenismaterialen van Journey Orchestration die door Journey Optimizer zijn vervangen. Neem contact op met uw accountteam als u vragen hebt over uw toegang tot Journey Orchestration of Journey Optimizer._


De voorwaardelijke instructie (als vervolgens anders) wordt ondersteund in de geavanceerde editor. Hiermee kunnen complexere expressies worden gedefinieerd. Het bestaat uit de volgende elementen:

* **[!UICONTROL if]** : de voorwaarde die eerst moet worden geëvalueerd.
* **[!UICONTROL then]**: de expressie die moet worden geëvalueerd als het resultaat van de evaluatie van de voorwaarde waar is.
* **[!UICONTROL else]**: de expressie die moet worden geëvalueerd als het resultaat van de evaluatie van de voorwaarde onwaar is.

>[!NOTE]
>
>Haakjes zijn vereist voor alle expressies.

```json
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` moet a **boolean** terugkeren.

`<expression2>` en `<expression3>` moeten hetzelfde type of compatibele typen hebben. De ondersteunde handtekeningen en geretourneerde typen zijn:

```json
boolean,boolean : boolean
dateTime,dateTime : dateTime
dateTimeOnly,dateTimeOnly : dateTimeOnly
decimal,integer : decimal
integer,decimal : integer
integer,decimal : decimal
duration,duration : duration
string,string : string
listBoolean,listBoolean : listBoolean
listDateTime,listDateTime : listDateTime
listDateTimeOnly,listDateTimeOnly : listDateTimeOnly
listDateOnly,listDateOnly : listDateOnly
listDecimal,listDecimal : listDecimal
listInteger,listInteger : listInteger
listString,listString : listString
```

**Gebruik**

Met de voorwaardelijke instructie kunt u de workflow van de reis optimaliseren door het aantal conditieactiviteiten te verminderen. Binnen dezelfde actieactiviteit kunt u bijvoorbeeld twee alternatieven voor een velddefinitie opgeven met slechts één voorwaarde-expressie.

Voorbeeld voor een actieactiviteit (voor een gebied dat een koord als resultaat van de voorwaardelijke instructie verwacht):

```json
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
