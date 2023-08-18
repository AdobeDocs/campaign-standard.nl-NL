---
title: Organisatorische eenheden
description: De toegangsniveaus van uw gebruikers bepalen gebruikend organisatorische eenheden
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: fbab695a-2672-4183-8c3b-78af7aefd5b1
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '840'
ht-degree: 4%

---

# Organisatorische eenheden{#organizational-units}

## Eenheden {#about-units}

Elk object en elke gebruiker van het platform is gekoppeld aan een organisatorische eenheid. Met deze eenheid kan een hiërarchische structuur worden gedefinieerd om gebruikers een gefilterde weergave te geven. De eenheid van een gebruiker bepaalt hun toegangsniveau voor verschillende platformvoorwerpen.

>[!IMPORTANT]
>
>Als een gebruiker niet is gekoppeld aan een eenheid, kan die gebruiker geen verbinding maken met Adobe Campaign. Als u de toegang voor een bepaalde gebruiker of groep gebruikers wilt beperken, moet u deze niet koppelen aan de **[!UICONTROL All]** -eenheid. We raden u aan de optie toe te voegen **Toegangsmachtigingsbeheervelden** voordat u profielen importeert. Raadpleeg deze [sectie](../../administration/using/organizational-units.md#partitioning-profiles) voor meer informatie.
>
>Standaard wordt de organisatie-eenheid **[!UICONTROL All (all)]** toegewezen aan de beveiligingsgroep **[!UICONTROL Administrators]**. Deze is alleen-lezen en kan niet worden gewijzigd.

Een gebruiker heeft alleen-lezen toegang tot alle objecten in de bovenliggende eenheden. Deze gebruiker heeft lees- en schrijftoegang tot alle objecten van zijn eenheid en onderliggende eenheden. Een gebruiker heeft geen toegang tot objecten in parallelle vertakkingen.

Standaard worden alleen de **[!UICONTROL All]** de eenheden zijn beschikbaar.

Wanneer aan de gebruiker een organisatorische eenheid wordt toegewezen, wordt deze eenheid altijd toegepast op de objecten die de gebruiker heeft gemaakt.

![](assets/user_management_2.png)

>[!NOTE]
>
>Wanneer een gebruiker in verscheidene groepen verbonden aan verschillende eenheden is, worden bepaalde regels toegepast. Raadpleeg voor meer informatie de [Groepen en gebruikers beheren](../../administration/using/managing-groups-and-users.md) sectie.

## Eenheden maken en beheren {#creating-and-managing-units}

Met de eenheden van de organisatie kunt u uw exemplaar filteren, afhankelijk van de organisatie waaraan uw gebruikers zijn gekoppeld. Deze eenheid kan een regio, land of zelfs een merk in uw exemplaar vertegenwoordigen.

Hier, creeerden wij eerder veiligheidsgroepen met verschillende rollen aan twee gebruikers: één gebruiker wordt toegewezen de beheerders en de Geometrixx van de veiligheidsgroepen, de andere gebruiker behoort tot de standaardgebruikers en van de Geometrixx zie [Een beveiligingsgroep maken en gebruikers toewijzen](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) voor het volledige voorbeeld.

We moeten nu de organisatorische eenheden creëren voor de Geometrixx Clothes en de veiligheidsgroepen van de Geometrixx:

1. Kies in het geavanceerde menu van de campagne Adobe de optie **[!UICONTROL Administration]** > **[!UICONTROL Users & security]** > **[!UICONTROL Organizational units]**.
1. Klikken **[!UICONTROL Create]** om uw organisatorische eenheid te configureren.

   ![](assets/manage_units_1.png)

1. De standaardinstelling wijzigen **[!UICONTROL Label]** en **[!UICONTROL ID]** naar Geometrixx.
1. Koppel deze eenheid vervolgens aan een bovenliggende eenheid. Hier kiezen we **[!UICONTROL All]**.

   ![](assets/manage_units_2.png)

1. Tot slot klikt u op **[!UICONTROL Create]** om uw nieuwe organisatorische eenheid aan veiligheidsgroep toe te wijzen.
1. Volg dezelfde procedure voor de eenheid van de Kleuren van de Geometrixx, behalve dat moet zijn oudereenheid eerder gecreeerd eenheid, Geometrixx zijn.

   ![](assets/manage_units_3.png)

Om het effect van het toewijzen van verschillende eenheden aan verschillende veiligheidsgroep te zien, zal de gebruiker die aan de Beheerder en de groepen van Geometrixx wordt toegewezen twee e-mailmalplaatjes creëren om te zien wat de andere gebruiker aan StandaardGebruiker en de Kleuren van de Geometrixx kan of niet kan toegang hebben.

1. Selecteer in het menu Geavanceerd de optie **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery Templates]**.
1. Dupliceer een bestaande sjabloon en pas deze zo nodig aan. Raadpleeg voor meer informatie de [Over sjablonen](../../start/using/marketing-activity-templates.md) sectie.
1. Selecteer bij het maken van de sjabloon de optie **[!UICONTROL Edit properties]** pictogram om eenheden aan uw sjabloon toe te wijzen.

   ![](assets/manage_units_6.png)

1. In de **[!UICONTROL Access authorization]** Selecteer de organisatie-eenheid in het keuzemenu.

   Hier gaan wij één malplaatje met de eerder gecreeerde organisatorische eenheid Geometrixx tot stand brengen.

   ![](assets/manage_units_5.png)

1. Volg de zelfde procedures om het tweede malplaatje tot stand te brengen dat aan de eerder gecreeerde organisatorische eenheid van de Kleuren van de Geometrixx wordt toegewezen.

Aan de **Standaardgebruiker** en **Geometrixx** groepen kunnen beide sjablonen bekijken. Wegens de hiërarchische structuur van de organisatorische eenheden, zullen zij lees en schrijven toegang tot het malplaatje verbonden aan de eenheid van de Kleuren van de Geometrixx hebben en slechts read-only toegang tot het malplaatje verbonden aan de eenheid van de Geometrixx.

![](assets/manage_units_7.png)

Aangezien de eenheid van de Kleuren van de Geometrixx een kindeenheid van Geometrixx is, verschijnt het volgende bericht wanneer de gebruikers proberen om het malplaatje van de Geometrixx te wijzigen:

![](assets/manage_units_8.png)

Organisatorische eenheden kunnen de toegang tot verschillende functies, zoals profielen, beperken. Als gebruikers van onze Geometrixx bijvoorbeeld toegang hebben tot de **[!UICONTROL Profiles]** met de organisatorische eenheid Geometrixx Clothes.

Terwijl de profielen bij de organisatie van de Geometrixx alleen-lezen zijn, wordt de volgende fout weergegeven als gebruikers proberen één profiel te wijzigen: **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## Profielen partitioneren {#partitioning-profiles}

>[!IMPORTANT]
>
>U wordt aangeraden deze optie toe te voegen voordat u profielen importeert, omdat profielen zonder organisatie niet door gebruikers kunnen worden geopend.
>
>Als u uw klantengegevensbestand reeds hebt ingevoerd, is een update noodzakelijk om de organisatorische eenheidswaarden op de reeds ingevoerde profielen te plaatsen.

Als uw organisatie de profielen moet isoleren die door elk van uw verschillende merken worden gecontacteerd, kunt u uw profielen door hun organisatorische eenheden verdelen.

Standaard zijn de velden voor de organisatie-eenheid niet beschikbaar in uw profielen en moeten deze worden toegevoegd.

1. Selecteer in het geavanceerde menu via het Adobe Campaign-logo de optie **Beheer > Ontwikkeling > Aangepaste bronnen**.
1. Selecteren **Profiel** of maak een nieuwe aangepaste bron om de profielen uit te breiden. Raadpleeg voor meer informatie over het uitbreiden van profielen de volgende [page](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-1--extend-the-profile-resource).
1. Controleer de **Voeg de beheersgebieden van de toegangsvergunning toe** om de organisatorische eenheden in het dialoogvenster **Profiel** extensie.

   ![](assets/user_management_9.png)

1. Klik op **[!UICONTROL Save]**.
1. Werk de structuur bij door de aangepaste bronnen opnieuw te publiceren. Voor meer informatie over het publicatieproces raadpleegt u [De structuur bijwerken](../../developing/using/updating-the-database-structure.md) sectie.

Het veld Organisatorische eenheid wordt toegevoegd aan uw profielen in het gedeelte **[!UICONTROL Access authorization]** sectie.

![](assets/user_management_10.png)

**Verwante onderwerpen**:

* [Eenheden](../../administration/using/organizational-units.md#about-units)
* [Informatie over toegangsbeheer](../../administration/using/about-access-management.md)
