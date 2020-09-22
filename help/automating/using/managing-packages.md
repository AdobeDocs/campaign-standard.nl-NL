---
title: Pakketten beheren
description: Beheerders kunnen pakketten definiëren om resources tussen verschillende Adobe Campaign-instanties uit te wisselen via gestructureerde XML-bestanden.
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
source-git-commit: eac45f6e5491703a39c19a4787be6f285e841e14
workflow-type: tm+mt
source-wordcount: '1053'
ht-degree: 100%

---


# Pakketten beheren{#managing-packages}

Beheerders kunnen pakketten definiëren om resources tussen verschillende Adobe Campaign-instanties uit te wisselen via gestructureerde XML-bestanden. Dit kunnen configuratieparameters of data zijn.

Dit kan nuttig zijn om data van één server naar een andere over te brengen of voor het repliceren van de configuratie van een instantie.

Pakketten zijn beschikbaar via het menu **[!UICONTROL Administration]** > **[!UICONTROL Deployment]** > **[!UICONTROL Package exports]** of **[!UICONTROL Package imports]**. De twee menu’s werken op dezelfde manier.

De elementen van elke lijst worden standaard weergegeven op basis van de wijzigings- of installatiedatum, van de meest recente tot de minst recente.

![](assets/packages_1.png)

Als u de content van een element wilt weergeven en wijzigen, klikt u op het elementlabel. Raadpleeg de secties [Een pakket exporteren](#exporting-a-package) en [Een pakket importeren](#importing-a-package).

## Pakketexports {#package-exports}

### Standaardpakketten {#standard-packages}

**[!UICONTROL Platform]** en **[!UICONTROL Administration]** zijn twee ingebouwde pakketten die elk een vooraf gedefinieerde lijst met te exporteren resources bevatten. Ze kunnen worden geopend in de modus Alleen-lezen en ze zijn alleen geschikt voor export.

![](assets/packages_14.png)

>[!IMPORTANT]
>
>Het exporteren van pakketten is niet toegestaan als de geëxporteerde resources standaard-id’s hebben. De id’s van resources die kunnen worden geëxporteerd, moeten daarom worden veranderd in een naam die afwijkt van de sjablonen die standaard worden geleverd door Adobe Campaign Standard. Voor het exporteren van testprofielen mag bijvoorbeeld niet een id met de waarde ‘SDM’ of ‘sdm’ worden gebruikt.
>
>Wanneer u probeert pakketten met standaard-id’s te exporteren, kunt u te maken krijgen met fouten zoals: “Het type entiteit ‘Merken (branding)’ gebruikt een standaard-id (BRD1)”. Dergelijke fouten kunnen bij het importeren van het pakket een conflict veroorzaken. Wijzig deze naam en herhaal de bewerking.”

De stappen voor het exporteren van het pakket worden beschreven in de sectie [Een pakket exporteren](#exporting-a-package).

* Het pakket **[!UICONTROL Platform]** hergroepeert alle resources die tijdens technische configuratie zijn toegevoegd: aangepaste resources, aangepaste resourcesets, triggers en applicatieopties van het type **[!UICONTROL System]**.
* Het pakket **[!UICONTROL Administration]** hergroepeert alle objecten die tijdens bedrijfsconfiguratie zijn toegevoegd, waaronder: campagnesjablonen, contentsjablonen, leveringssjablonen, landingspaginasjablonen, programmasjablonen en workflowsjablonen.

   Het omvat ook de volgende objecten: contentblokken, doeltoewijzingen, externe accounts, organisatie-eenheden, applicatieopties van het type **[!UICONTROL User]**, rollen, typologieën, typologische regels en gebruikers.

>[!NOTE]
>
>De content van deze twee pakketten kan niet worden gewijzigd. Deze pakketten bevatten echter altijd de meest actuele data die beschikbaar zijn. U kunt [uw eigen pakketten maken](#creating-a-package) om specifieke elementen te exporteren.

### Een pakket maken {#creating-a-package}

U moet een pakket maken als u specifieke datasets wilt exporteren.

Als u een pakket wilt maken, hebt u de beheerrechten nodig.

1. Kies **[!UICONTROL Administration]** > **[!UICONTROL Deployment]** > **[!UICONTROL Package exports]** en klik op de knop **[!UICONTROL Create]** in de lijst met pakketcontent.

   Het element wordt onmiddellijk gemaakt. Als u het maken wilt annuleren, gaat u terug naar de lijst en schakelt u het bijbehorende selectievakje in om het te verwijderen.

1. Geef een naam en een id op in het scherm met pakketcontent.
1. Klik op de knop **[!UICONTROL Edit properties]** als u een beschrijving wilt toevoegen en de toegang voor bepaalde gebruikers wilt beperken.

   ![](assets/packages_18.png)

1. Gebruik de knop **[!UICONTROL Create element]** op het tabblad **[!UICONTROL Export content]** om de resources te selecteren die u wilt exporteren.

   ![](assets/packages_2.png)

1. Resources worden in alfabetische volgorde weergegeven en kunnen op naam worden gefilterd. Hun technische naam wordt tussen haakjes weergegeven. Selecteer een element in de lijst en bevestig.

   ![](assets/packages_3.png)

1. De naam van de resource wordt weergegeven op het tabblad **[!UICONTROL Export content]**. Om een resource te wijzigen schakelt u het corresponderende vakje in en gebruikt u de knop **[!UICONTROL Show detail of the element selected]**.

   ![](assets/packages_4.png)

1. Met de queryeditor kunt u de elementen filteren die u wilt exporteren. Raadpleeg de sectie [Query’s bewerken](../../automating/using/editing-queries.md#creating-queries) voor meer informatie.

   ![](assets/packages_5.png)

   >[!NOTE]
   >
   >U kunt maximaal 5000 objecten per resource exporteren.

1. Nadat u alle resources hebt opgegeven die u wilt exporteren, slaat u uw selectie op.

Uw pakket is nu gemaakt en kan worden geëxporteerd.

### Een pakket exporteren {#exporting-a-package}

Wanneer u een pakket exporteert, kunt u een specifieke status van een resource opslaan, die u opnieuw kunt importeren in een andere instantie of later in dezelfde instantie.

>[!CAUTION]
>
>Het exporteren van pakketten is niet toegestaan als de geëxporteerde resources standaard-id’s hebben. De id’s van resources die kunnen worden geëxporteerd, moeten daarom worden veranderd in een naam die afwijkt van de sjablonen die standaard worden geleverd door Adobe Campaign Standard. Voor het exporteren van testprofielen mag bijvoorbeeld niet een id met de waarde ‘SDM’ of ‘sdm’ worden gebruikt.

1. Kies **[!UICONTROL Administration]** > **[!UICONTROL Deployment]** > **[!UICONTROL Package exports]** en selecteer een pakket om de pakketdetails weer te geven.
1. Controleer of het pakket de benodigde data bevat.
1. Klik op de knop **[!UICONTROL Start export]**.

Het geëxporteerde bestand wordt opgeslagen in de downloadmap van de gebruikte browser. Het bestand krijgt automatisch de naam ‘package_xxx.xml’, waarbij ‘xxx’ overeenkomt met de pakket-id.

Wanneer de bewerking is voltooid, worden verschillende secties weergegeven:

* **[!UICONTROL Export status]**: In deze sectie wordt aangegeven of de bewerking correct is uitgevoerd.

   ![](assets/packages_6.png)

* Via het tabblad **[!UICONTROL Log]** kunt u de verschillende exportstappen raadplegen. Dit tabblad bevat de statussen van alle eerdere exporttransacties.

   ![](assets/packages_7.png)

>[!NOTE]
>
>Wanneer u een element selecteert in de lijst met pakketcontent die al is geëxporteerd, zijn de tabbladen **[!UICONTROL Log]** en **[!UICONTROL Last export]** nog steeds beschikbaar.

## Pakketimports {#package-imports}

### Systeemupdates {#system-updates}

De lijst met geïmporteerde pakketten bovenaan bevat de automatische importtransacties die gekoppeld zijn aan updates die door Adobe zijn uitgevoerd.

![](assets/packages_15.png)

Het tabblad **[!UICONTROL Execution logs]** bevat alle importstappen. De algemene informatie wordt weergegeven in een zijpaneel.

![](assets/packages_11.png)

>[!NOTE]
>
>Deze elementen zijn toegankelijk in de modus Alleen-lezen.

### Een pakket importeren {#importing-a-package}

Een beheerder kan handmatig een pakket importeren dat afkomstig is van een exportbewerking die eerder is uitgevoerd vanuit een Adobe Campaign-instantie. Raadpleeg de sectie [Pakketexports](#package-exports) voor meer informatie.

De handmatige importbewerking bestaat uit twee stappen: eerst moet u een bestand uploaden en vervolgens kunt u de content ervan importeren.

1. Kies **[!UICONTROL Administration]** > **[!UICONTROL Deployment]** > **[!UICONTROL Package imports]** en klik op de knop **[!UICONTROL Create]** in de lijst met geïmporteerde pakketten.

   Het element wordt onmiddellijk gemaakt. Als u het maken wilt annuleren, gaat u terug naar de lijst en schakelt u het bijbehorende selectievakje in om het te verwijderen.

1. Geef een naam en een id op voor de nieuwe importbewerking.
1. Selecteer het bestand dat u wilt uploaden door het te verslepen of door op de koppeling **[!UICONTROL Select from folder]** te klikken.

   Geïmporteerde bestanden moeten in xml- of zip-indeling (met een xml-bestand) zijn.

   ![](assets/packages_16.png)

   >[!NOTE]
   >
   >Als u het geüploade document wilt vervangen, begint u met het verwijderen van het bestand via het X-pictogram rechts van de bestandsnaam en herhaalt u de bewerking.

1. Wanneer het bestand is geüpload, importeert u de content ervan in de database met de knop **[!UICONTROL Start import]**.

   ![](assets/packages_19.png)

Wanneer de bewerking is voltooid, worden verschillende secties weergegeven:

* **[!UICONTROL Import status]**: In deze sectie wordt aangegeven of de bewerking correct is uitgevoerd.
* Via het tabblad **[!UICONTROL Execution logs]** kunt u de verschillende importstappen raadplegen. Dit is met name belangrijk om fouten te bekijken.

   ![](assets/packages_20.png)

Nadat een pakket is geïmporteerd, kunt u het niet opnieuw importeren vanuit hetzelfde element. U kunt alleen het label en de id van het pakket wijzigen.

Als u hetzelfde pakket opnieuw wilt importeren, moet u teruggaan naar de lijst met geïmporteerde pakketten, een element maken en het geselecteerde bestand vervolgens opnieuw uploaden.
