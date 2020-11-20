---
product: adobe campaign
solution: Journey Orchestration
title: toDateTime
description: Meer informatie over de functie toDateTime
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 4%

---

# toDateTime {#toDateTime}

Zet parameters om in een datumtijdwaarde, afhankelijk van hun types.

## Categorie

Conversie

## Functiesyntaxis

`toDateTime(<parameters>)`

## Parameters

| Parameter | Type |
|-----------|------------------|
| datumtijd in ISO-8601-indeling | string |
| tijdzone-id | string |
| datumtijd zonder tijdzone | dateTimeOnly |
| geheel-getalwaarde van een tijdperk in milliseconden | integer |

>[!NOTE]
>
>Tijdzone-id moet een tekenreeksconstante zijn. Het kan geen veldverwijzing of expressie zijn. For more information on data types, refer to [this page](../expression/data-types.md).

## Handtekeningen en geretourneerde typen

`toDateTime(<string>)`

`toDateTime(<dateTimeOnly>,<stringified time zone id>)`

`toDateTime(<integer>)`

Retourneer een **dateTime**.

<!--`toDateTime(<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`

Returns a date time with default time zone UTC.

`toDateTime(<year>,<month>,<dayOfMonth>)`
`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>)`
`toDateTime(<timeZone>,<year>,<month>,<dayOfMonth>)`

Return a datetime where hour, minute and second set to 0.

`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`
`toDateTime(<string>)`
`toDateTime(<string>,<integer>)`
`toDateTime(<stringified timeZone>,<dateTimeOnly)`

`toDateTime(<timeZone>,<integer>)`

Return a datetime.

-->

## Voorbeelden

`toDateTime ("2016-08-18T23:17:59.123Z")`

Retourneert 2016-08-18T23:17:59.123Z

`toDateTime(toDateTimeOnly("2016-08-18T23:17:59.123"),"UTC")`

Retourneert 2016-08-18T23:17:59.123Z

`toDateTime(1560762190189)`

Retourneert 2019-06-17T09:03:10.189Z

<!--`toDateTime ("2016-08-18T23:17:59.123", "UTC")`

Returns 2016-08-18T23:17:59.123Z.

`toDateTime("Z",2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000Z.

`toDateTime("Z",2016,8,18)`

Returns 2016-08-18T00:00:00.000Z.-->
