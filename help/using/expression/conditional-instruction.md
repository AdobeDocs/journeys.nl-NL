---
title: Voorwaardelijke instructie (indien, then, else)
description: Meer informatie over voorwaardelijke instructies
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 0%

---


# Voorwaardelijke instructie (indien, then, else) {#section_cdz_lsk_w3b}

De voorwaardelijke instructie (als vervolgens anders) wordt ondersteund in de geavanceerde editor. Hiermee kunnen complexere expressies worden gedefinieerd. Het bestaat uit de volgende elementen:

* **[!UICONTROL if]**: de eerst te beoordelen voorwaarde.
* **[!UICONTROL then]**: de expressie die moet worden geëvalueerd als het resultaat van de evaluatie van de voorwaarde waar is.
* **[!UICONTROL else]**: de expressie die moet worden geëvalueerd als het resultaat van de evaluatie van de voorwaarde onwaar is.

>[!NOTE]
>
>Haakjes zijn vereist voor alle expressies.

```
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` moet een **booleaanse waarde** retourneren.

`<expression2>` en `<expression3>` moeten hetzelfde type of compatibele typen hebben. De ondersteunde handtekeningen en geretourneerde typen zijn:

```
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
listDecimal,listDecimal : listDecimal
listInteger,listInteger : listInteger
listString,listString : listString
```

**Gebruik**

Met de voorwaardelijke instructie kunt u de workflow van de reis optimaliseren door het aantal conditieactiviteiten te verminderen. Binnen dezelfde actieactiviteit kunt u bijvoorbeeld twee alternatieven voor een velddefinitie opgeven met slechts één voorwaarde-expressie.

Voorbeeld voor een actieactiviteit (voor een gebied dat een koord als resultaat van de voorwaardelijke instructie verwacht):

```
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
