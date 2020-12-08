---
solution: Campaign Standard
product: campaign
title: Organisatorische eenheden
description: Bepaal de toegangsniveaus van uw gebruikers gebruikend organisatorische eenheden.
audience: administration
content-type: reference
topic-tags: users-and-security
context-tags: orgUnit,overview;orgUnit,main;geoUnit,overview;geoUnit,main
translation-type: tm+mt
source-git-commit: 824c91669bd717e5bf31dab9005e4c3b9e497edf
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 4%

---


# Organisatorische eenheden{#organizational-units}

## Informatie over eenheden {#about-units}

Elk object en elke gebruiker van het platform is gekoppeld aan een organisatorische eenheid. Met deze eenheid kan een hiërarchische structuur worden gedefinieerd om gebruikers een gefilterde weergave te geven. De eenheid van een gebruiker bepaalt hun toegangsniveau voor verschillende platformvoorwerpen.

>[!IMPORTANT]
>
>Als een gebruiker niet is gekoppeld aan een eenheid, kan die gebruiker geen verbinding maken met Adobe Campaign. Als u toegang voor een bepaalde gebruiker of een groep gebruikers wilt beperken, koppel het niet aan de **[!UICONTROL All]** eenheid. Wij adviseren toevoegend de optie **de gebieden van het het vergunningsbeheer van de Toegang** alvorens om het even welke profielen in te voeren. Raadpleeg deze [sectie](../../administration/using/organizational-units.md#partitioning-profiles) voor meer informatie.
>
>Standaard wordt de organisatie-eenheid **[!UICONTROL All (all)]** toegewezen aan de beveiligingsgroep **[!UICONTROL Administrators]**. Deze is alleen-lezen en kan niet worden gewijzigd.

Een gebruiker heeft alleen-lezen toegang tot alle objecten in de bovenliggende eenheden. Hij heeft toegang tot alle voorwerpen van zijn eenheid en kindeenheden gelezen en geschreven. Een gebruiker heeft geen toegang tot objecten in parallelle vertakkingen.

Standaard zijn alleen de eenheden **[!UICONTROL All]** beschikbaar.

Wanneer aan de gebruiker een organisatorische eenheid wordt toegewezen, wordt deze eenheid altijd toegepast op de objecten die de gebruiker heeft gemaakt.

![](assets/user_management_2.png)

>[!NOTE]
>
>Wanneer een gebruiker in verscheidene groepen verbonden aan verschillende eenheden is, worden bepaalde regels toegepast. Raadpleeg de sectie [Groepen en gebruikers beheren](../../administration/using/managing-groups-and-users.md) voor meer informatie.

## Eenheden maken en beheren {#creating-and-managing-units}

Met de eenheden van de organisatie kunt u uw exemplaar filteren, afhankelijk van de organisatie waaraan uw gebruikers zijn gekoppeld. Deze eenheid kan een regio, land of zelfs een merk in uw exemplaar vertegenwoordigen.

Hier, creeerden wij eerder veiligheidsgroepen met verschillende rollen aan twee gebruikers: één gebruiker wordt toegewezen de beheerders en de Geometrixx van de veiligheidsgroepen, de andere gebruiker behoort tot de standaardgebruikers en van de Geometrixx Standaardgebruikers Zie [Het creëren van een veiligheidsgroep en het toewijzen van gebruikers](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) voor het volledige voorbeeld.

We moeten nu de organisatorische eenheden creëren voor de Geometrixx Clothes en de veiligheidsgroepen van de Geometrixx:

1. Selecteer **[!UICONTROL Administration]** > **[!UICONTROL Users & security]** > **[!UICONTROL Organizational units]** in het geavanceerde menu van de Adobe-campagne.
1. Klik **[!UICONTROL Create]** beginnen uw organisatorische eenheid te vormen.

   ![](assets/manage_units_1.png)

1. Wijzig de standaard **[!UICONTROL Label]** en **[!UICONTROL ID]** in Geometrixx.
1. Koppel deze eenheid vervolgens aan een bovenliggende eenheid. Hier kiezen we **[!UICONTROL All]**.

   ![](assets/manage_units_2.png)

1. Tot slot klik **[!UICONTROL Create]** beginnen uw nieuwe organisatorische eenheid aan veiligheidsgroep toe te wijzen.
1. Volg dezelfde procedure voor de eenheid van de Kleuren van de Geometrixx, behalve dat moet zijn oudereenheid eerder gecreeerd eenheid, Geometrixx zijn.

   ![](assets/manage_units_3.png)

Om het effect van het toewijzen van verschillende eenheden aan verschillende veiligheidsgroep te zien, zal de gebruiker die aan de Beheerder en de groepen van Geometrixx wordt toegewezen twee e-mailmalplaatjes creëren om te zien wat de andere gebruiker aan StandaardGebruiker en de Kleuren van de Geometrixx kan of niet kan toegang hebben.

1. Selecteer **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery Templates]** in het geavanceerde menu.
1. Dupliceer een bestaande sjabloon en pas deze zo nodig aan. Raadpleeg voor meer informatie de sectie [Informatie over sjablonen](../../start/using/marketing-activity-templates.md).
1. Wanneer de sjabloon wordt gemaakt, selecteert u het pictogram **[!UICONTROL Edit properties]** om eenheden aan uw sjabloon toe te wijzen.

   ![](assets/manage_units_6.png)

1. Selecteer de organisatorische eenheid in het vervolgkeuzemenu **[!UICONTROL Access authorization]**.

   Hier gaan wij één malplaatje met de eerder gecreeerde organisatorische eenheid Geometrixx tot stand brengen.

   ![](assets/manage_units_5.png)

1. Volg de zelfde procedures om het tweede malplaatje tot stand te brengen dat aan de eerder gecreeerde organisatorische eenheid van de Kleuren van de Geometrixx wordt toegewezen.

De gebruiker die aan de StandaardGroepen van de Gebruiker en van de Kleuren van de Geometrixx wordt toegewezen zal beide malplaatjes kunnen zien. Wegens de hiërarchische structuur van de organisatorische eenheden, zal hij lees- en schrijftoegang tot het malplaatje hebben verbonden aan de eenheid van de Kleuren van de Geometrixx en slechts read-only toegang tot het malplaatje verbonden aan de eenheid van de Geometrixx.

![](assets/manage_units_7.png)

Aangezien de eenheid van de Geometrixx kleding een kindeenheid van Geometrixx is, verschijnt het volgende bericht wanneer de gebruiker probeert om het malplaatje van de Geometrixx te wijzigen:

![](assets/manage_units_8.png)

Organisatorische eenheden kunnen de toegang tot verschillende functies, zoals profielen, beperken. Bijvoorbeeld, als onze Geometrixx Kleuren van de gebruiker tot **[!UICONTROL Profiles]** tabel toegang hebben, zal hij tot de profielen met de organisatorische eenheid van de Geometrixx Kleuren volledig toegang hebben en kunnen wijzigen.

Terwijl de profielen bij de organisatie van de Geometrixx alleen-lezen zijn, wordt de volgende fout weergegeven als onze gebruiker één profiel probeert te wijzigen: **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## Profielen {#partitioning-profiles} partitioneren

>[!IMPORTANT]
>
>U wordt aangeraden deze optie toe te voegen voordat u profielen importeert, omdat profielen zonder organisatie niet door gebruikers kunnen worden geopend.
>
>Als u uw klantengegevensbestand reeds hebt ingevoerd, is een update noodzakelijk om de organisatorische eenheidswaarden op de reeds ingevoerde profielen te plaatsen.

Als uw organisatie de profielen moet isoleren die door elk van uw verschillende merken worden gecontacteerd, kunt u uw profielen door hun organisatorische eenheden verdelen.

Standaard zijn de velden voor de organisatie-eenheid niet beschikbaar in uw profielen en moeten deze worden toegevoegd.

1. Selecteer **Beheer > Ontwikkeling > Aangepaste bronnen** in het geavanceerde menu via het Adobe Campaign-logo.
1. Selecteer **Profiel** of maak een nieuwe aangepaste bron om de profielen uit te breiden. Raadpleeg deze [pagina](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-1--extend-the-profile-resource) voor meer informatie over het uitbreiden van de profielen.
1. Schakel het selectievakje **Beheervelden voor toegangsmachtigingen toevoegen** in om de organisatorische eenheden in de **Profieluitbreiding** toe te voegen.

   ![](assets/user_management_9.png)

1. Klik op **[!UICONTROL Save]**.
1. Werk de structuur bij door de aangepaste bronnen opnieuw te publiceren. Raadpleeg [De sectie Structuur](../../developing/using/updating-the-database-structure.md) bijwerken voor meer informatie over het publicatieproces.

Het veld Organisatorische eenheid wordt toegevoegd aan uw profielen in de sectie **[!UICONTROL Access authorization]**.

![](assets/user_management_10.png)

**Verwante onderwerpen**:

* [Eenheden](../../administration/using/organizational-units.md#about-units)
* [Toegangsbeheer](../../administration/using/about-access-management.md)

