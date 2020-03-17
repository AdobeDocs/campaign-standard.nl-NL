---
title: Pakketten beheren
description: Beheerders kunnen pakketten definiëren om bronnen tussen verschillende Adobe Campagneinstanties uit te wisselen via gestructureerde XML-bestanden.
page-status-flag: never-activated
uuid: d041f549-bfc5-4e6b-87bf-a63c7c224bca
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: c3015cdc-8432-4e57-8ac0-43ae7827e3b0
context-tags: packageDef,overview;packageInstall,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Pakketten beheren{#managing-packages}

Beheerders kunnen pakketten definiëren om bronnen tussen verschillende Adobe Campagneinstanties uit te wisselen via gestructureerde XML-bestanden. Dit kunnen configuratieparameters of gegevens zijn.

Dit kan nuttig zijn om gegevens van één server naar een andere over te brengen of voor het herhalen van de configuratie van een instantie.

Pakketten zijn beschikbaar onder **[!UICONTROL Administration]** > **[!UICONTROL Deployment]** > **[!UICONTROL Package exports]** of **[!UICONTROL Package imports]** menu&#39;s. De twee menu&#39;s werken op dezelfde manier.

De elementen van elke lijst worden standaard weergegeven op basis van hun wijzigings- of installatiedatum, van de meest recente tot de minst recente.

![](assets/packages_1.png)

Als u de inhoud van een element wilt weergeven en wijzigen, klikt u op het label ervan. Raadpleeg de secties [Een pakket](#exporting-a-package) exporteren en een pakket [](#importing-a-package) importeren.

## Pakket exporteren {#package-exports}

### Standaardpakketten {#standard-packages}

**[!UICONTROL Platform]** en **[!UICONTROL Administration]** zijn twee ingebouwde pakketten die elk een vooraf gedefinieerde lijst met te exporteren bronnen bevatten. Ze kunnen alleen worden geopend in de modus Alleen-lezen en ze zijn alleen geschikt voor export.

![](assets/packages_14.png)

>[!CAUTION]
>
>Het exporteren van pakketten is niet toegestaan als de geëxporteerde bronnen standaard-id&#39;s hebben. De id&#39;s van bronnen die kunnen worden geëxporteerd, moeten daarom worden gewijzigd met een andere naam dan de sjablonen die standaard worden geleverd door Adobe Campagne Standard. Bijvoorbeeld, om testprofielen uit te voeren, moet identiteitskaart die de waarde &quot;SDM&quot;of &quot;sdm&quot;bevat niet worden gebruikt. Wanneer u probeert pakketten met standaard-id&#39;s te exporteren, worden bijvoorbeeld de volgende fouten weergegeven: Het type entiteit &#39;Merken (branding)&#39; gebruikt een standaard-id (&#39;BRD1&#39;) die bij het importeren van het pakket een conflict kan veroorzaken. Wijzig deze naam en herhaal de bewerking.&quot;

De stappen voor het exporteren van het pakket worden beschreven in de sectie Een pakket [](#exporting-a-package) exporteren.

* Het **[!UICONTROL Platform]** pakket groepeert alle middelen die tijdens technische configuratie worden toegevoegd: aangepaste bronnen, aangepaste bronsets, triggers en toepassingsopties met het **[!UICONTROL System]** type.
* Het **[!UICONTROL Administration]** pakket groepeert alle voorwerpen die tijdens bedrijfsconfiguratie zoals worden toegevoegd: campagnemalplaatjes, inhoudsmalplaatjes, leveringsmalplaatjes, het landen paginasjablonen, programmasjablonen en werkschemasjablonen.

   Het omvat ook de volgende objecten: inhoudsblokken, doeltoewijzingen, externe accounts, organisatorische eenheden, toepassingsopties met het **[!UICONTROL User]** type, rollen, typologieën, typologische regels en gebruikers.

>[!NOTE]
>
>De inhoud van deze twee pakketten kan ik niet wijzigen. Deze pakketten bevatten daarentegen altijd de meest actuele gegevens die beschikbaar zijn. U kunt uw eigen pakketten [](#creating-a-package) maken om specifieke elementen te exporteren.

### Een pakket maken {#creating-a-package}

U moet een pakket maken als u specifieke gegevenssets wilt exporteren.

Als u een pakket wilt maken, hebt u de beheerrechten nodig.

1. Kies **[!UICONTROL Administration]** > **[!UICONTROL Deployment]** > **[!UICONTROL Package exports]**, klik op de **[!UICONTROL Create]** knop in de lijst met pakketinhoud.

   Het element wordt onmiddellijk gemaakt. Als u het maken wilt annuleren, gaat u terug naar de lijst en schakelt u het bijbehorende selectievakje in om het te verwijderen.

1. Geef een naam en een id op in het scherm met pakketinhoud.
1. Klik op de **[!UICONTROL Edit properties]** knop als u een beschrijving wilt toevoegen en de toegang tot bepaalde gebruikers wilt beperken.

   ![](assets/packages_18.png)

1. Gebruik de **[!UICONTROL Create element]** knop op het **[!UICONTROL Export content]** tabblad om de bronnen te selecteren die u wilt exporteren.

   ![](assets/packages_2.png)

1. De middelen worden getoond in alfabetische orde en kunnen door naam worden gefiltreerd. Hun technische naam wordt getoond tussen haakjes. Selecteer een element in de lijst en bevestig het.

   ![](assets/packages_3.png)

1. De naam van de bron wordt weergegeven op het **[!UICONTROL Export content]** tabblad. Om een middel te wijzigen, controleer de overeenkomstige doos en gebruik de **[!UICONTROL Show detail of the element selected]** knoop.

   ![](assets/packages_4.png)

1. Met de queryeditor kunt u de elementen filteren die u wilt exporteren. Raadpleeg de sectie [Bewerkquery](../../automating/using/editing-queries.md#creating-queries) voor meer informatie hierover.

   ![](assets/packages_5.png)

   >[!NOTE]
   >
   >U kunt maximaal 5000 objecten per bron exporteren.

1. Nadat u alle bronnen hebt opgegeven die u wilt exporteren, slaat u uw selectie op.

Uw pakket is nu gemaakt en klaar om te worden geëxporteerd.

### Een pakket exporteren {#exporting-a-package}

Wanneer u een pakket exporteert, kunt u een specifieke status van een bron opslaan die u opnieuw kunt importeren in een andere instantie of later op dezelfde instantie.

>[!CAUTION]
>
>Het exporteren van pakketten is niet toegestaan als de geëxporteerde bronnen id&#39;s buiten de doos hebben. De id&#39;s van bronnen die kunnen worden geëxporteerd, moeten daarom worden gewijzigd met een andere naam dan de sjablonen die standaard worden geleverd door Adobe Campagne Standard. Bijvoorbeeld, om testprofielen uit te voeren, moet identiteitskaart die de waarde &quot;SDM&quot;of &quot;sdm&quot;bevat niet worden gebruikt.

1. Kies **[!UICONTROL Administration]** > **[!UICONTROL Deployment]** > **[!UICONTROL Package exports]** een pakket voor toegang tot de details.
1. Controleer of het pakket de benodigde gegevens bevat.
1. Klik op de **[!UICONTROL Start export]** knop.

Het geëxporteerde bestand wordt opgeslagen in de downloadmap van de gebruikte browser. Deze krijgt automatisch de naam &quot;package_xxx.xml&quot;, waarbij &quot;xxx&quot; overeenkomt met de pakket-id.

Wanneer de bewerking is voltooid, worden verschillende secties weergegeven:

* **[!UICONTROL Export status]**: in dit deel wordt aangegeven of de operatie correct is uitgevoerd.

   ![](assets/packages_6.png)

* Via het **[!UICONTROL Log]** tabblad kunt u de verschillende stappen van het exporteren raadplegen. Hierin staan de statussen van alle vroegere uitvoertransacties.

   ![](assets/packages_7.png)

>[!NOTE]
>
>Wanneer u een element selecteert uit de lijst met pakketinhoud dat al is geëxporteerd, zijn de tabbladen **[!UICONTROL Log]** en **[!UICONTROL Last export]** tabbladen nog steeds beschikbaar.

## Pakketimport {#package-imports}

### Systeemupdates {#system-updates}

De bovenstaande lijst met geïmporteerde pakketten bevat de automatische import die is gekoppeld aan updates die door Adobe worden uitgevoerd.

![](assets/packages_15.png)

Op het **[!UICONTROL Execution logs]** tabblad worden alle importstappen opgeslagen. De algemene informatie wordt weergegeven in een zijpaneel.

![](assets/packages_11.png)

>[!NOTE]
>
>Deze elementen zijn alleen-lezen beschikbaar.

### Een pakket importeren {#importing-a-package}

Een beheerder kan handmatig een pakket importeren dat afkomstig is van een exportbewerking die eerder is uitgevoerd vanuit een Adobe Campagne-instantie. Raadpleeg voor meer informatie de sectie [Pakket exporteren](#package-exports) .

Het handmatige pakket importeren bestaat uit twee stappen: eerst moet u een bestand uploaden en vervolgens kunt u de inhoud ervan importeren.

1. Kies **[!UICONTROL Administration]** > **[!UICONTROL Deployment]** > **[!UICONTROL Package imports]**, klik op de **[!UICONTROL Create]** knop in de lijst met geïmporteerde pakketten.

   Het element wordt onmiddellijk gemaakt. Als u het maken wilt annuleren, gaat u terug naar de lijst en schakelt u het bijbehorende selectievakje in om het te verwijderen.

1. Geef een naam en een id op voor het nieuwe importeren.
1. Selecteer het bestand dat u wilt uploaden door het te slepen en neer te zetten of door op de **[!UICONTROL Select from folder]** koppeling te klikken.

   Geïmporteerde bestanden moeten de indeling XML of ZIP (met een XML-bestand) hebben.

   ![](assets/packages_16.png)

   >[!NOTE]
   >
   >Als u het geüploade document wilt vervangen, begint u met het verwijderen van het bestand via het X-pictogram rechts van de naam ervan en herhaalt u de bewerking.

1. Wanneer het bestand is geüpload, importeert u de inhoud ervan in de database met de **[!UICONTROL Start import]** knop.

   ![](assets/packages_19.png)

Wanneer de bewerking is voltooid, worden verschillende secties weergegeven:

* **[!UICONTROL Import status]**: in dit deel wordt aangegeven of de operatie correct is uitgevoerd.
* U kunt de verschillende stappen van de import raadplegen via het **[!UICONTROL Execution logs]** tabblad. Dit is met name belangrijk om fouten te bekijken.

   ![](assets/packages_20.png)

Nadat een pakket is geïmporteerd, kunt u het niet opnieuw importeren vanuit hetzelfde element. U kunt het label en de id alleen wijzigen.

Als u hetzelfde pakket opnieuw wilt importeren, moet u teruggaan naar de lijst met geïmporteerde pakketten, een element maken en het geselecteerde bestand vervolgens opnieuw uploaden.
