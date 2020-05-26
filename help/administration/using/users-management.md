---
title: Gebruikersbeheer
description: 'Gebruikers van Adobe Campagne hebben specifieke rollen. Ontdek de belangrijkste gebruikerstypen. '
page-status-flag: never-activated
uuid: 8c4cc74a-815f-4815-af66-a7c21bc754f1
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 08c8712a-0066-4b8b-8471-2656b8fb23ed
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '1144'
ht-degree: 0%

---


# Gebruikersbeheer{#users-management}

## Gebruikers {#about-users}

Met Adobe Campaign kunt u een set rollen toewijzen aan uw gebruikers om te bepalen tot welk deel van de interface zij toegang hebben.

De specifieke rollen en de bijbehorende machtigingen worden in de volgende secties nader beschreven: [het begrijpen van rollen](../../administration/using/list-of-roles.md) en [toestemmingen](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

Beheerders kunnen gebruikers beheren via de beheerconsole. Gebruikers worden dan automatisch gesynchroniseerd met Adobe Campaign. Raadpleeg de documentatie bij de [beheerconsole](https://helpx.adobe.com/enterprise/using/users.html) voor meer informatie.

Als u de gebruikers in Adobe Campaign wilt weergeven, klikt u op het **[!UICONTROL Adobe Campaign]** logo in de linkerbovenhoek en selecteert u **[!UICONTROL Administration > Users & Security > Users]**.

Klik op de knop voor toegang tot de gebruikersbeheerinterface van Adobe Campaign **[!UICONTROL User administration]**.

![](assets/user_management_5.png)

**Verwante onderwerpen:**

* [Video over gebruikersmachtigingen](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/access-management.html) beheren
* [Lijst met rollen](../../administration/using/list-of-roles.md)
* [Lijst van vergunningen](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)

## Type gebruikers {#type-of-users}

Deze gebruikerssegmentatie is niet verplicht, het is alleen een weergave van het meest gebruikte gebruik van Adobe Campaign.

In deze sectie krijgt u inzicht in de belangrijkste typen gebruikers van Adobe Campagne. Hier, zullen wij niet op alle specifieke rollen ingaan die een gebruiker kan houden (beginleveringen, de uitvoer, bereidt leveranties, enz.). Voor meer informatie over rollen, verwijs naar [Lijst van rollen](../../administration/using/list-of-roles.md) en [het Leiden groepen en gebruikerspagina](../../administration/using/managing-groups-and-users.md) .

We zullen ons liever concentreren op de manier waarop de verschillende taken in Adobe Campagne worden verdeeld over drie hoofdgebruikerstypen:

* [Functionele beheerders](#functional-administrators): onder alle gebruikers van uw organisatie zijn zij de meest technische.
* [Geavanceerde gebruikers](#advanced-users): zij zetten alle elementen op die de marketers moeten verzenden en hun leveringen controleren.
* [Basisgebruikers](#basic-users): zij zijn de marketeers die hun campagnes personaliseren , leveren en controleren .

>[!NOTE]
>
>Functionele beheerders zijn anders dan de technische beheerders van Adobe. Technische beheerders van Adobe hebben een interne Adobe-rol die geen enkele klant kan gebruiken. Ze beheren de levering, hosting, controle en toezicht op de infrastructuur, technische probleemoplossing.

### Functionele beheerders {#functional-administrators}

Functionele beheerders zijn gebruikers die toegang hebben tot de meest technische onderdelen van de interface. Zij spelen een **[!UICONTROL Administration]** rol en zorgen ervoor dat het platform zo is opgezet dat de marketeers zich alleen hoeven te richten op het leveren van hun campagnes.

Functionele beheerders zijn de enige gebruikers die toegang hebben tot het **[!UICONTROL Administration]** menu in de Adobe Campagne-interface. Aangezien deze gebruikers tot technische middelen moeten toegang hebben, zouden de geavanceerdere rollen aan hen, zoals de **[!UICONTROL Administration]** en **[!UICONTROL Datamodel]** uit-van-de-doos rollen moeten worden toegewezen. Deze rollen worden gecombineerd in de **[!UICONTROL Administrators]** uit-van-de-doos veiligheidsgroep. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

Hier volgen de belangrijkste taken die ze kunnen uitvoeren:

* [Gebruikers en machtigingen](../../administration/using/about-access-management.md)beheren: de toegang tot het platform (gebruikers, rollen, beveiligingsgroepen, eenheden) beheren.
* [Configureer de verschillende kanalen](../../administration/using/about-channel-configuration.md): het opzetten van de verschillende platformkanalen en van typologie en quarantainebeheer.
* [Configureer de algemene toepassingsinstellingen](../../administration/using/external-accounts.md): de verschillende toepassingselementen configureren (externe accounts, opties, technische workflows).
* [Nieuwe functies ontwikkelen om functies](../../developing/using/data-model-concepts.md)buiten de box te verbeteren: beheer uw aangepaste bronnen en open diagnostische hulpmiddelen.
* [Stel de parameters](../../administration/using/branding.md)voor de instantie in: de verschillende merken definiëren en hun instellingen configureren (logo, bijhouden beheren, URL-domein voor toegang tot de bestemmingspagina&#39;s, enz.).
* [Gegevenspakketten](../../automating/using/managing-packages.md)exporteren en importeren: U kunt bronnen uitwisselen tussen verschillende Adobe Campagne-instanties via gestructureerde XML-bestanden.
* [Logboeken](../../automating/using/exporting-logs.md) exporteren en [importsjablonen](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)definiëren.

### Geavanceerde gebruikers {#advanced-users}

Geavanceerde gebruikers zijn marketinggebruikers die de meest technische gebruiksgevallen in Adobe Campaign uitvoeren. Zij vormen preconfigure alle elementen die de marketers gebruiken om hun leveringen te verzenden en te controleren.

Dit type van gebruiker vereist meer algemene rollen dan functionele beheerders maar zou nog sommige technische handelingen moeten kunnen uitvoeren. Daartoe moeten ze bijvoorbeeld de rollen **[!UICONTROL Export]**, **[!UICONTROL Generic import]** of **[!UICONTROL Workflow]** out-of-the-box krijgen. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

Hier volgen de belangrijkste taken die ze kunnen uitvoeren:

* [Maak en voer complexe workflows](../../automating/using/about-data-management-activities.md)voor gegevensbeheer uit: importeren, verrijken en transformeren van gegevens om uw database te voeden, of de gegevens die u nodig hebt in externe bestanden exporteren om deze te verwerken in uw eigen gereedschappen.
* [Sjablonen](../../start/using/marketing-activity-templates.md)beheren: beheren uw malplaatjes om bepaalde parameters van uw marketing activiteiten afhankelijk van uw behoeften vooraf te vormen.
* [Maak query](../../automating/using/editing-queries.md#about-query-editor) &#39;s en [beheer uw publiek](../../audiences/using/about-audiences.md): maak handmatig uw publiek met query&#39;s of gebruik automatisch speciale workflows.
* [Geavanceerde expressies bewerken](../../automating/using/editing-queries.md#about-query-editor): gebruik geavanceerde functies om de waarden te manipuleren die worden gebruikt om specifieke vragen uit te voeren zoals data, koorden, numerieke gebieden, het sorteren, enz.
* [Lijsten](../../automating/using/exporting-lists.md) exporteren en gegevens [importeren met bestaande importsjablonen](../../automating/using/importing-data-with-import-templates.md).

### Basisgebruikers {#basic-users}

Dankzij de functionele beheerder en de geavanceerde gebruikers kunnen marketers hun campagnes personaliseren, leveren en controleren zonder zich zorgen te hoeven maken over de technische configuratie. Daartoe moeten ze bijvoorbeeld de rollen **[!UICONTROL Prepare deliveries]**, **[!UICONTROL Workflow]** en **[!UICONTROL Start deliveries]** out-of-the-box krijgen. Deze rollen worden gecombineerd in de **[!UICONTROL Standard Users]** uit-van-de-doos veiligheidsgroep. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

Hier volgen de belangrijkste taken die ze kunnen uitvoeren:

* [Programma&#39;s en campagnes](../../start/using/programs-and-campaigns.md)beheren: marketingcampagnes op te zetten met verschillende soorten activiteiten (e-mails, SMS-berichten, pushberichten, workflows, landingspagina&#39;s).
* Profielen [en](../../audiences/using/about-profiles.md) testprofielen [](../../audiences/using/managing-test-profiles.md)beheren: beheert de geïdentificeerde en testontvangers waarop uw leveringen betrekking zullen hebben. Voeg gegevens toe zoals voornaam, achternaam, contactgegevens, abonnementen, e-mails, enz.
* [Berichten](../../sending/using/confirming-the-send.md)maken en verzenden: Maak uw bericht, selecteer het publiek, definieer de inhoud van het bericht en de bijbehorende personalisatie-elementen, verzend proefdrukken en verzend het laatste bericht naar uw publiek.
* [bestemmingspagina](../../channels/using/getting-started-with-landing-pages.md)&#39;s maken en publiceren: Maak en beheer een reeks services die u aan uw klanten wilt aanbieden, zoals abonnements- of abonnementsformulieren.
* [Workflows](../../automating/using/building-a-workflow.md)voor campagnes maken en uitvoeren: automatiseer uw campagneprocessen gebruikend werkschema&#39;s.
* Volg uw marketingactiviteiten via de [beschikbare rapporten](../../reporting/using/defining-the-report-period.md).

## Een gebruiker maken {#creating-a-user}

Als u een gebruiker aan een instantie wilt toevoegen, moet u deze eerst maken in de beheerconsole voordat u deze beheert in Adobe Campagnestandaard.

1. Selecteer in het geavanceerde menu de optie **[!UICONTROL Administration > Users & Security > Users]** en klik **[!UICONTROL User administration]** om de beheerconsole te openen.

   ![](assets/user_management_5.png)

1. Klik in het **[!UICONTROL Admin Console]** deelvenster op het **[!UICONTROL Users]** tabblad.

1. Klik op **[!UICONTROL Add User]**.

   ![](assets/create_user_2.png)

1. Vul op het **[!UICONTROL User details]** tabblad de gegevens van de gebruiker in, zoals het e-mailadres, de naam en de achternaam.

   ![](assets/create_user_3.png)

1. Wijs via het **[!UICONTROL Assign products]** tabblad een of meerdere beveiligingsgroepen toe aan uw gebruiker. Raadpleeg deze [pagina](../../administration/using/managing-groups-and-users.md)voor meer informatie over beveiligingsgroepen.

   Klik **[!UICONTROL Save]** wanneer klaar het vormen.

   ![](assets/create_user_4.png)

Uw gebruiker wordt nu gecreeerd en zou een e-mail moeten ontvangen die aan het volgende venster opnieuw richt waar de gebruiker een wachtwoord moet plaatsen dan de gebruiksovereenkomst goedkeuren. Deze gebruiker kan dan verbinding maken met uw Adobe Campagne Standard-exemplaar.

![](assets/create_user_5.png)

Uw gebruiker wordt gesynchroniseerd met Adobe Campagne Standard zodra hij zich aanmeldt bij uw exemplaar.

Vervolgens kunt u controleren of de gebruiker correct is gesynchroniseerd met Adobe Campaign:

1. Selecteer in het menu Geavanceerd de eerder gemaakte gebruiker **[!UICONTROL Administration > Users & Security > Users]** .

1. Werk het **[!UICONTROL Mobile]** bij **[!UICONTROL Time zone]** of **[!UICONTROL Regional settings]** indien nodig.

1. Controleer de beveiligingsgroep van uw gebruiker. Hier, kunt u zien dat de gebruiker de **[!UICONTROL Administrators]** veiligheidsgroep is toegewezen.

   >[!Nofferte]
   >
   >Beveiligingsgroepen kunnen alleen worden verwijderd of toegevoegd aan een gebruiker in de beheerconsole.

   ![](assets/create_user_6.png)

1. Controleer **[!UICONTROL Account disabled]** of u deze gebruiker wilt deactiveren.

1. Selecteer in het **[!UICONTROL Authorized connection zone]** veld op welke manier de gebruiker verbinding maakt met deze instantie, bijvoorbeeld een intern netwerk of VPN.

1. Klik op **[!UICONTROL Save]**.

Uw gebruiker is nu klaar om Adobe Campaign Standard te gebruiken.
