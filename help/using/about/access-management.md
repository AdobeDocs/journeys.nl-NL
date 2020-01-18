---
title: Toegangsbeheer
description: Meer informatie over toegangsbeheer
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: fed6fd8d8ee497ec47727f7297dc72f319fabe27

---


# Toegangsbeheer{#concept_rfj_wpt_52b}

## Over toegangsbeheer {#about-access-management}

Productprofielen worden toegewezen aan een reeks gebruikers die dezelfde rechten hebben binnen uw organisatie.

In de beheerconsole kunt u een van de volgende out-of-the-box productprofielen aan uw gebruikers toewijzen:

* **[!UICONTROL Limited Access User]**: alleen-lezen toegang tot reizen en rapporten. Dit productprofiel bevat de volgende rechten:
   * Reizen lezen
   * Rapporten lezen

* **[!UICONTROL Administrators]**: gebruikers die toegang hebben tot de menu&#39;s van de administratie, met de mogelijkheid om reizen, gebeurtenissen en rapporten te beheren. Dit productprofiel bevat de volgende rechten:
   * Reizen beheren en uitvoeren
   * Gebeurtenissen, gegevensbronnen en handelingen beheren
   * Rapporten beheren
   >[!NOTE]
   >
   >**[!UICONTROL Administrators]**is het enige productprofiel dat het maken, de uitgave en de publicatie van transactiemeldingen (of berichtsjablonen) in Adobe Campagne Standard toestaat. Dit productprofiel is vereist als u met Adobe Campaign Standard berichten tijdens uw reizen verzendt.

* **[!UICONTROL Standard User]**: gebruikers met basistoegang zoals reisbeheer. Dit productprofiel bevat de volgende rechten:
   * Reizen beheren en uitvoeren
   * Rapporten beheren

U kunt [hier](../assets/do-not-localize/acs_rights_journeys.pdf) de verenigbaarheid vinden tussen rechten en de verschillende functies van de Journey Orchestration.

## Een productprofiel toewijzen {#assigning-product-profile}

Productprofielen worden beheerd in de beheerconsole. Raadpleeg de documentatie [bij de](https://helpx.adobe.com/enterprise/managing/user-guide.html)beheerconsole voor meer informatie.

Een productprofiel toewijzen aan een gebruiker om toegang te krijgen tot Journey Orchestration:

1. Selecteer in de beheerconsole **[!UICONTROL Journey orchestration]**.

   ![](../assets/user_management.png)

1. Selecteer het productprofiel waaraan de nieuwe gebruiker wordt gekoppeld.

   ![](../assets/user_management_2.png)

1. Klik **[!UICONTROL Add user]**.

   U kunt uw nieuwe gebruiker aan een gebruikersgroep ook toevoegen om de gedeelde reeks toestemmingen te verfijnen. Raadpleeg deze [pagina](https://helpx.adobe.com/enterprise/using/user-groups.html)voor meer informatie.

   ![](../assets/user_management_3.png)

1. Typ het e-mailadres van de nieuwe gebruiker en klik op **[!UICONTROL Save]**.

   ![](../assets/user_management_4.png)

Uw gebruiker moet dan een e-mail ontvangen die wordt doorgestuurd naar uw instantie van de Journey Orchestration.