---
title: replaceAll
description: Meer informatie over de functie replaceAll
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


# replaceAll {#replaceAll}

Vervangt alle instanties die overeenkomen met de doeltekenreeks door de vervangende tekenreeks in de basistekenreeks.

De vervanging vindt plaats vanaf het begin van de tekenreeks tot het einde. Als u bijvoorbeeld &quot;aa&quot; vervangt door &quot;b&quot; in de tekenreeks &quot;aaa&quot;, resulteert dit in &quot;ba&quot; in plaats van &quot;ab&quot;.

## Categorie

String

## Functiesyntaxis

`replaceAll(<parameters>)`

## Parameters

| Parameter | Type |
|-----------|--------------|
| basis |  string |
| target |  string |
| vervanging |  string |

## Handtekening en type geretourneerd

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

Retourneert een tekenreeks.

## Voorbeeld

`replaceAll("Hello World", "l", "x")`

Retourneert &quot;Hexxo Worxd&quot;.
