---
title: aantal
description: Meer informatie over het aantal functies
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608

---


# aantal {#count}

Telt de elementen van de lijst die geen rekening houden met de ongeldige waarden.

## Categorie

Samenvoeging

## Functiesyntaxis

`count(<listAny>)`

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

## Handtekeningen en type geretourneerd

`count(<listAny>)`

Retourneert een geheel getal.

## Voorbeeld

`count([10,2,10,null])`

Retourneert 3.
