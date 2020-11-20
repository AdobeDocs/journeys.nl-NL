---
product: adobe campaign
solution: Journey Orchestration
title: countWithNull
description: Meer informatie over de functie countWithNull
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 23%

---


# countWithNull {#countWithNull}

Telt alle elementen van de lijst met inbegrip van ongeldige waarden.

## Categorie

Samenvoeging

## Functiesyntaxis

`countWithNull(<listAny>)`

## Parameters

| Parameter | Type |
|-----------|------------------|
| Lijst | listString |
| Lijst | listBoolean |
| Lijst | listInteger |
| Lijst | listDecimal |
| Lijst | listDuration |
| Lijst | listDateTime |
| Lijst | listDateTimeOnly |

## Handtekening en type geretourneerd

`countWithNull(<listAny>)`

Retourneert een geheel getal.

## Voorbeeld

`count([10,2,10,null])`

Retourneert 4.
