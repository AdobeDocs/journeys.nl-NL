---
product: adobe campaign
title: replace
description: Meer informatie over de functie replace
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: f30377c2-4d5e-4905-a972-8f4ccb272bc0
source-git-commit: 8980df5cc238a7195f01a1631e418a8de677fbea
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 4%

---

# replace {#replace}

Vervangt de eerste instantie die overeenkomt met de doeltekenreeks door de vervangende tekenreeks in de basistekenreeks.

De vervanging vindt plaats vanaf het begin van de tekenreeks tot het einde. Als u bijvoorbeeld &quot;aa&quot; vervangt door &quot;b&quot; in de tekenreeks &quot;aaa&quot;, resulteert dit in &quot;ba&quot; in plaats van &quot;ab&quot;.

## Categorie

Tekenreeks

## Functiesyntaxis

`replace(<parameters>)`

## Parameters

| Parameter | Type |
|-----------|--------------|
| basis | string |
| target | tekenreeks (RegExp) |
| vervanging | string |

## Handtekening en type geretourneerd

`replace(<base>,<target>,<replacement>)`

Retourneer een tekenreeks.

## Voorbeeld 1

`replace("Hello World", "l", "x")`

Retourneert &quot;Hexlo World&quot;.

## Voorbeeld 2 {#example_2}

Omdat de doelparameter een RegExp is, moet u, afhankelijk van de tekenreeks die u wilt vervangen, mogelijk enkele tekens verwijderen. Hier volgt een voorbeeld:

* te evalueren tekenreeks: `|OFFER_A|OFFER_B`
* verstrekt door een profielattribuut `#{ExperiencePlatform.myFieldGroup.profile.myOffers}`
* Te vervangen tekenreeks: `|OFFER_A`
* Tekenreeks vervangen door: `''`
* U moet toevoegen `\\` vóór de `|` teken.

De expressie is:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|OFFER_A', '')`

De geretourneerde tekenreeks is: `|OFFER_B`

U kunt ook de tekenreeks maken die moet worden vervangen door een bepaald kenmerk:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|' + #{ExperiencePlatform.myFieldGroup.profile.myOfferCode}, '')`
