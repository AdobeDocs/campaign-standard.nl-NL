---
title: Groepen en gebruikers beheren
description: Leer hoe u beveiligingsgroepen maakt en gebruikers beheert.
page-status-flag: never-activated
uuid: b3a3a2e3-9d69-4231-b724-8f37419f7a61
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 12f896ab-ee79-4d96-976d-cf34643491b4
context-tags: user,overview;user,main;security,overview;security,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e31e8c63fa94d190211c7a51e7f1091657c9f479

---


# Groepen en gebruikers beheren{#managing-groups-and-users}

## Informatie over beveiligingsgroepen {#about-security-groups}

De groepen van de veiligheid zijn reeksen gebruikers die de zelfde rollen en de rechten binnen uw organisatie delen.

Gebruikers moeten altijd zijn gekoppeld aan een beveiligingsgroep. Op deze manier kunt u specifieke rollen en organisatorische eenheden toewijzen aan deze groepen.

Voor meer informatie over rollen, presenteren de lijsten in de volgende pagina de verschillende beschikbare verrichtingen volgens de rol(s) van een gebruiker: [Adobe Campaign Standard-autorisaties](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

Standaardbeveiligingsgroepen zijn:

* **[!UICONTROL Administrators]**
* **[!UICONTROL Delivery supervisors]**
* **[!UICONTROL Message Center agents]**
* **[!UICONTROL Standard Users]**
* **[!UICONTROL Workflow supervisors]**

Als een gebruiker niet is gekoppeld aan een beveiligingsgroep, heeft hij geen toegang tot Adobe Campaign.

Als u de toegang van een gebruiker wilt beperken, voegt u de gebruiker niet toe aan de gebruikersgroep Campagnestandaard, aangezien deze is gekoppeld aan de **[!UICONTROL All]** organisatie.

>[!NOTE]
>
>Standaard wordt de **[!UICONTROL All (all)]** organisatorische eenheid toegewezen aan de **[!UICONTROL Administrators]** beveiligingsgroep. Het is alleen-lezen en kan niet worden gewijzigd.

## Een beveiligingsgroep maken en gebruikers toewijzen {#creating-a-security-group-and-assigning-users}

>[!IMPORTANT]
>
>Houd er rekening mee dat in de beheerconsole beveiligingsgroepen profielen worden genoemd.

U kunt uw eigen veiligheidsgroepen tot stand brengen als de uit-van-de-doos groepen niet genoeg zijn om uw gebruikers te beheren. Ze kunnen worden beheerd door beheerders die toegang hebben tot de beheermenu&#39;s van Adobe Campagne en de beheerconsole van Adobe. Raadpleeg deze [documentatie](https://helpx.adobe.com/enterprise/managing/user-guide.html)voor meer informatie over de beheerconsole.

Hier, moeten wij eerst de twee uit-van-de-doosgroepen Standaardgebruiker en Beheerder aan onze gebruikers toewijzen. Deze beveiligingsgroepen beperken een aantal functies van Adobe Campaign: De standaardgebruiker heeft basistoegang tot de Campagne van Adobe terwijl de Beheerder tot de beleidsmenu&#39;s bijvoorbeeld kan toegang hebben.

Wijzigingen die worden aangebracht in beveiligingsgroepen op de beheerconsole, worden gesynchroniseerd zodra gebruikers zich aanmelden bij Adobe Campagne.

Dan, willen wij een reeks veiligheidsgroepen Geometrixx en de Kleuren van Geometrixx tot stand brengen die wat toegang afhankelijk van de organisatorische eenheden van onze Standaardgebruiker en Beheerder zal beperken.

![](assets/ootb_security_group_1.png)

U moet eerst een van de uit-van-de-doos veiligheidsgroep aan uw gebruikers toewijzen:

1. Selecteer in de beheerconsole eerst uw exemplaar en vervolgens het tabblad **Gebruikers** .

   ![](assets/manage_security_group_2.png)

1. Klik op de **[!UICONTROL Add user]** knop en voer het e-mailadres van de gebruiker in.
1. Selecteer op het **[!UICONTROL Assign Products]** tabblad uw instantie en kies vervolgens de **[!UICONTROL Administrators]** uit-van-de-box beveiligingsgroep uit de vervolgkeuzelijst. Hierdoor kan de gebruiker toegang hebben tot de beheermenu&#39;s en de volgende beveiligingsgroepen maken.

   ![](assets/ootb_security_group_2.png)

1. Klik **[!UICONTROL Save]** **[!UICONTROL Standard Users]** en volg de zelfde procedures om de uit-van-de-doos veiligheidsgroep aan uw nieuwe gebruiker toe te wijzen.

   ![](assets/ootb_security_group_3.png)

Zodra uw twee gebruikers in bijlage aan de **[!UICONTROL Administrators]** en **[!UICONTROL Standard users]** uit-van-de-doos veiligheidsgroepen zijn die rollen aan onze gebruikers toewijzen, kan de gebruiker van de Beheerder de twee veiligheidsgroepen **Geometrixx** en de Kleuren **van** Geometrixx nu tot stand brengen die organisatorische eenheden aan onze gebruikers naast de uit-van-de-doos veiligheidsgroepen zullen toewijzen.

1. In de Admin console, selecteer uw geval toen de **Producten** tabel.
1. Klik op de knop **Nieuw profiel** om de **beveiligingsgroep Geometrixx** te maken.

   ![](assets/create_security_1.png)

1. Typ de **[!UICONTROL Profile name]** exacte syntaxis: **[!UICONTROL Campaign Standard- instance name - ID of the security group]** en klik op **[!UICONTROL Done]**.

   De gekozen id wordt vervolgens gebruikt tijdens het maken van de beveiligingsgroep in Adobe Campaign.

   >[!NOTE]
   >
   >Als de bovenstaande syntaxis niet met een oudere instantie lijkt te werken, moet deze worden vervangen door **[!UICONTROL Campaign - instance name - ID of the security group]**.

   ![](assets/manage_security_group_1.png)

1. Dan, volg de zelfde procedures om de de veiligheidsgroep van de Kleuren van **Geometrixx** tot stand te brengen.
1. Wijs uw beveiligingsgroep toe aan uw gebruiker door het **[!UICONTROL Users]** tabblad te selecteren.

   ![](assets/manage_security_group_2.png)

1. Klik op de eerder gemaakte gebruiker en klik vervolgens op het ![](assets/managing_security_group_10.png) pictogram in de **[!UICONTROL Products]** categorie.

   Selecteer deze optie **[!UICONTROL Edit products assigned directly]** om de nieuwe beveiligingsgroep aan de gebruiker toe te wijzen.

   ![](assets/manage_security_group_8.png)

1. Selecteer op het **[!UICONTROL Assign Products]** tabblad de instantie die u eerder hebt gemaakt in de vervolgkeuzelijst de beveiligingsgroepen Geometrixx om deze toe te wijzen aan uw beheerder.

   Klik op **[!UICONTROL Save]**.

   ![](assets/manage_security_group_3.png)

   Als een gebruiker in verscheidene groepen is:

   * De rollen van de verschillende groepen worden gecumuleerd. Hier bevinden gebruikers zich in twee verschillende groepen: één die op rollen de andere op eenheden zal handelen.
   * Het is de eenheid die de hoogste in de hiërarchie is die zal worden gebruikt (zie voorbeeld in de sectie [Organisatorische eenheden](../../administration/using/organizational-units.md) ).
   * De gebruiker kan geen verbinding meer maken als de eenheden hetzelfde niveau hebben en zich in parallelle vertakkingen in de hiërarchie bevinden.

1. Volg de zelfde procedures om de de veiligheidsgroep van de KLEUREN van Geometrixx aan uw Standaardgebruiker toe te wijzen.

   ![](assets/manage_security_group_9.png)

De nieuwe beveiligingsgroepen worden nu gemaakt in de beheerconsole. Als u ze volledig wilt synchroniseren, moet u ze ook maken in Adobe Campaign.

De gebruiker van de Beheerder moet de reeks veiligheidsgroepen tot stand brengen die worden gebruikt om organisatorische eenheden toe te wijzen: Geometrixx en Geometrixx kleding. Zie [Eenheden](../../administration/using/organizational-units.md#creating-and-managing-units) maken en beheren voor meer informatie over het maken van organisatorische eenheden.

1. Klik op het **[!UICONTROL Adobe Campaign]** logo in de linkerbovenhoek en selecteer **[!UICONTROL Administration > Users & Security > Security groups]**.
1. Maak uw nieuwe beveiligingsgroep en geef de groep **[!UICONTROL Label]** en **[!UICONTROL ID]** groep op.

   De id moet dezelfde zijn als de id die u in de beheerconsole hebt gekozen.

1. Wijs in het **[!UICONTROL User access]** veld organisatorische eenheid toe. Hier, wordt de de veiligheidsgroep van Geometrixx toegewezen de **[!UICONTROL All]** organisatorische eenheid.

   ![](assets/manage_security_group_6.png)

1. U kunt ook rollen toewijzen aan uw beveiligingsgroep. In ons geval, is deze stap niet nodig aangezien de uit-van-de-doos veiligheidsgroepen **[!UICONTROL Administrators]** en gebruikt **[!UICONTROL Standard users]** worden om rollen toe te wijzen.
1. Volg de zelfde procedures om de laatste de kleren van de veiligheid te creëren Geometrixx en de organisatorische eenheid toe te wijzen van de KLEUREN van Geometrixx.

   ![](assets/manage_security_group_7.png)

Uw gebruikers worden nu toegewezen aan een beveiligingsgroep en kunnen verbinding maken met Adobe Campagne.

>[!IMPORTANT]
>
>Als gebruikers uit een beveiligingsgroep in de beheerconsole worden verwijderd, blijven ze deel uitmaken van de beveiligingsgroep van Adobe Campagne en kunnen ze zich niet meer aanmelden in Adobe Campaign. Verwijder in dit geval de e-mailadressen van de gebruikers in de beheerconsole om te voorkomen dat ze vertrouwelijke informatie ontvangen.

