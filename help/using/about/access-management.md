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
source-git-commit: a3114ffe7c087645e97caf3a77e7649d922945eb
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 0%

---


# Toegangsbeheer{#concept_rfj_wpt_52b}

## Over toegangsbeheer {#about-access-management}

[!DNL Journey Orchestration] staat u toe om een reeks rechten aan uw gebruikers toe te wijzen om te bepalen tot welk deel van de interface zij toegang hebben.

Ze kunnen worden beheerd door beheerders die toegang hebben tot de beheerconsole. Raadpleeg deze [documentatie](https://helpx.adobe.com/enterprise/managing/user-guide.html)voor meer informatie over de beheerconsole.

In de beheerconsole kunt u een van de volgende out-of-the-box productprofielen aan uw gebruikers toewijzen:

* **[!UICONTROL Limited Access User]**: alleen-lezen toegang tot reizen en rapporten. Dit productprofiel bevat de volgende rechten:
   * Reizen lezen
   * Rapporten lezen

* **[!UICONTROL Administrators]**: gebruikers die toegang hebben tot de menu&#39;s van de administratie, met de mogelijkheid om reizen, gebeurtenissen en rapporten te beheren. Dit productprofiel bevat de volgende rechten:
   * Reizen beheren
   * Reizen publiceren
   * Gebeurtenissen, gegevensbronnen en handelingen beheren
   * Rapporten beheren
   >[!NOTE]
   >
   >**[!UICONTROL Administrators]** is het enige productprofiel dat het maken, de uitgave en de publicatie van transactiemeldingen (of berichtsjablonen) in Adobe Campagne Standard toestaat. Dit productprofiel is vereist als u met Adobe Campaign Standard berichten tijdens uw reizen verzendt.

* **[!UICONTROL Standard User]**: gebruikers met basistoegang zoals reisbeheer. Dit productprofiel bevat de volgende rechten:
   * Reizen beheren
   * Reizen publiceren
   * Rapporten beheren

U kunt ook uw eigen productprofielen maken als de out-of-box-profielen niet voldoende zijn om uw gebruikers te beheren.
Gebruikers moeten altijd zijn gekoppeld aan een productprofiel, zodat u hun specifieke inbouwrechten kunt toewijzen, zoals:

* **[!UICONTROL Read journeys]**
* **[!UICONTROL Read reports]**
* **[!UICONTROL Manage events, data sources and actions]**
* **[!UICONTROL Read events, data sources and actions]**
* **[!UICONTROL Manage journeys]**
* **[!UICONTROL Publish journeys]**
* **[!UICONTROL Manage reports]**

Hieronder vindt u de compatibiliteit tussen rechten en [!DNL Journey Orchestration]de verschillende functies.

![](../assets/journey_permission.png)

## Een productprofiel maken {#create-product-profile}

[!DNL Journey Orchestration] kunt u uw eigen productprofielen maken en een reeks rechten en sandboxen aan uw gebruikers toewijzen. Met productprofielen kunt u toegang tot bepaalde functies of objecten in de interface toestaan of weigeren.

Raadpleeg de documentatie bij [Adobe Experience Platform voor meer informatie over het maken en beheren van sandboxen](https://docs.adobe.com/content/help/en/experience-platform/sandbox/ui/user-guide.html).

Een productprofiel maken en een set rechten en sandboxen toewijzen:

1. Selecteer in de beheerconsole **[!UICONTROL Journey Orchestration]**. Klik op het tabblad **[!UICONTROL Product profile]** op **[!UICONTROL New Profile]**.

1. Voeg een **[!UICONTROL Profile Name]** en **[!UICONTROL Description]** voor uw nieuwe productprofiel toe. Als u wilt dat uw profiel anders is, schakelt u de optie uit **[!UICONTROL Display name]** en typt u het profiel in **[!UICONTROL Same as Profile Name]** **[!UICONTROL Display name]**.

1. Kies in de **[!UICONTROL User Notifications]** categorie of gebruikers via e-mail op de hoogte worden gesteld wanneer ze uit dit productprofiel worden toegevoegd of verwijderd.

1. Klik wanneer u klaar bent op **[!UICONTROL Done]**. Uw nieuwe productprofiel is nu gemaakt.

1. Selecteer het nieuwe productprofiel om machtigingen te beheren. Voeg op het **[!UICONTROL Users]** tabblad gebruikers toe aan uw productprofiel. Raadpleeg deze [pagina](../about/access-management.md#assigning-product-profile)voor meer informatie.

1. Voer dezelfde stappen uit als hierboven beschreven om toe te voegen **[!UICONTROL Admin]** aan uw productprofiel.

1. Selecteer op het **[!UICONTROL Permissions]** tabblad een van de twee categorieën **[!UICONTROL Sandbox]** of **[!UICONTROL Authoring]** om de **[!UICONTROL Edit Permissions]** pagina te openen en machtigingen voor uw productprofiel toe te voegen of te verwijderen.

1. Kies in de **[!UICONTROL Sandbox]** machtigingencategorie welke sandbox(s) u wilt toewijzen aan uw productprofiel. Klik onder **[!UICONTROL Available Permissions Items]**, op de plusknop (+) om sandboxen aan uw profiel toe te wijzen.

   >[!NOTE]
   >
   >De zandbak van het platform is een bètaeigenschap.
   <br>Zie deze [sectie](../about/access-management.md#sandboxes)voor meer informatie over sandboxen.

1. Klik, indien nodig, onder **[!UICONTROL Included Permission Items]** het X-pictogram naast het verwijderen van machtigingen voor uw productprofiel.

1. Voer vanuit de **[!UICONTROL Authoring]** machtigingencategorie dezelfde stappen uit als hierboven om rechten toe te voegen aan uw productprofiel.
   <br>Zie deze [!DNL Journey Orchestration]sectie voor meer informatie over rechten en compatibiliteit tussen rechten en [de verschillende functies van de rechten](../about/access-management.md#about-access-management).

1. Klik wanneer u klaar bent op **[!UICONTROL Save]**.

Uw productprofiel is nu gemaakt en geconfigureerd. Gebruikers die aan dit profiel zijn gekoppeld, kunnen nu verbinding maken met [!DNL Journey Orchestration].

## Een productprofiel toewijzen {#assigning-product-profile}

Productprofielen worden toegewezen aan een reeks gebruikers die dezelfde rechten hebben binnen uw organisatie.
De lijst met alle out-of-the-box productprofielen met toegewezen rechten vindt u in deze sectie.

Een productprofiel toewijzen dat een gebruiker kan openen [!DNL Journey Orchestration]:

1. Selecteer in de beheerconsole **[!UICONTROL Journey Orchestration]**.

   ![](../assets/user_management.png)

1. Selecteer het productprofiel waaraan de nieuwe gebruiker wordt gekoppeld.

   ![](../assets/user_management_2.png)

1. Klik op **[!UICONTROL Add user]**.

   U kunt uw nieuwe gebruiker aan een gebruikersgroep ook toevoegen om de gedeelde reeks toestemmingen te verfijnen. Raadpleeg deze [pagina](https://helpx.adobe.com/enterprise/using/user-groups.html)voor meer informatie.

   ![](../assets/user_management_3.png)

1. Typ het e-mailadres van de nieuwe gebruiker en klik op **[!UICONTROL Save]**.

   ![](../assets/user_management_4.png)

Uw gebruiker moet dan een e-mail ontvangen die naar uw [!DNL Journey Orchestration] instantie wordt doorgestuurd.

## Sandboxen gebruiken {#sandboxes}

>[!NOTE]
>
>De zandbak van het platform is een bètaeigenschap.

[!DNL Journey Orchestration] kunt u uw instantie opdelen in afzonderlijke virtuele omgevingen, sandboxen genoemd.
Sandboxen worden toegewezen via productprofielen in de beheerconsole. Raadpleeg deze [sectie](../about/access-management.md#create-product-profile)voor meer informatie over het toewijzen van sandboxen.

[!DNL Journey Orchestration] weerspiegelt de platformsandboxen die voor een bepaalde organisatie zijn gemaakt.
Platformsandboxen kunnen worden gemaakt of opnieuw worden ingesteld vanuit uw Adobe Experience Platform-instantie. Raadpleeg de gebruikershandleiding [van de](https://docs.adobe.com/content/help/en/experience-platform/sandbox/ui/user-guide.html) sandbox voor de gedetailleerde stappen.

U kunt het besturingselement voor de sandboxswitch linksboven in het scherm vinden. Als u van de ene naar de andere sandbox wilt schakelen, klikt u op de momenteel actieve sandbox in de switch en selecteert u een andere sandbox in de vervolgkeuzelijst.
