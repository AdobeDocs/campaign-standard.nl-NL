---
title: E-mailstijlen beheren
description: Ontdek hoe u e-mailstijlen kunt beheren in de e-mailontwerper.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 2%

---


# E-mailstijlen beheren {#managing-styles}


Als u in de e-mailontwerper een element selecteert, worden in het **[!UICONTROL Settings]** deelvenster verschillende opties weergegeven die specifiek zijn voor het type geselecteerde inhoud. U kunt deze opties gebruiken om de stijl van uw e-mail gemakkelijk te veranderen.

## Een element selecteren {#selecting-an-element}

Als u een element wilt selecteren in de interface E-mailontwerper, kunt u:

* klik rechtstreeks in de e-mail,
* U kunt ook bladeren door de beschikbare boomstructuur via de opties in het linker **palet**.

![](assets/des_tree_structure.png)

Door in de boomstructuur te bladeren, kunt u een nauwkeurigere selectie maken. U kunt kiezen uit:

* de volledige structuurcomponent,
* een van de kolommen waaruit de structuurcomponent bestaat,
* of alleen een component die zich in een kolom bevindt.

![](assets/des_tree_structure_selection.png)

Als u een kolom wilt selecteren, kunt u ook het volgende doen:

1. Selecteer een structuurcomponent (rechtstreeks in de e-mail of met gebruik van de boomstructuur die beschikbaar is in het linker **palet**).
1. Klik in de **contextafhankelijke werkbalk** op **[!UICONTROL Select a column]** de gewenste kolom.

Zie een voorbeeld in [deze sectie](#example--adjusting-vertical-alignment-and-padding).

## Stijlinstellingen aanpassen {#adjusting-style-settings}

1. Selecteer een element in uw e-mail. Zie Een element [](#selecting-an-element)selecteren voor meer informatie.
1. Pas de instellingen naar wens aan. Elk geselecteerd element heeft een andere set instellingen.

   U kunt achtergronden invoegen, formaten wijzigen, horizontale of verticale uitlijning wijzigen, kleuren beheren, [opvulling of marge](#selecting-an-element)toevoegen enzovoort.

   Hiervoor gebruikt u de opties in het **[!UICONTROL Settings]** deelvenster of [voegt u inline opmaakkenmerken](#adding-inline-styling-attributes)toe.

   ![](assets/des_settings_pane.png)

1. Sla uw inhoud op.

## Opvulling en marge aanpassen {#about-padding-and-margin}

Met de e-mailDesigner-interface kunt u snel opvulling- en marge-instellingen aanpassen.

**[!UICONTROL Padding]**: met deze instelling kunt u de ruimte beheren die zich binnen de rand van een element bevindt.

![](assets/des_padding.png)

Bijvoorbeeld:

* Gebruik opvulling om marges in te stellen aan de linker- en rechterzijde van een afbeelding.
* Gebruik opvulling boven en onder om meer ruimte aan een **[!UICONTROL Text]** of een **[!UICONTROL Divider]** component toe te voegen.
* Als u randen tussen kolommen in een structuurelement wilt instellen, definieert u de opvulling voor elke kolom.

**[!UICONTROL Margin]**: met deze instelling kunt u de ruimte tussen de rand van het element en het volgende element beheren.

![](assets/des_margin.png)

>[!NOTE]
>
>Afhankelijk van uw selectie (structuurcomponent, kolom of inhoudscomponent), is het resultaat niet hetzelfde. Adobe raadt u aan de **[!UICONTROL Padding]** parameters en de **[!UICONTROL Margin]** parameters op kolomniveau in te stellen.

Voor zowel **[!UICONTROL Padding]** als **[!UICONTROL Margin]**, klik het slotpictogram om synchronisatie tussen bovenkant en bodem of juist en linkerparameters te breken. Hierdoor kunt u elke parameter afzonderlijk aanpassen.

![](assets/des_padding_lock_icon.png)

## Stijluitlijning {#about-alignment}

* **Tekstuitlijning**: Plaats de cursor van uw muis op tekst en gebruik de contextafhankelijke werkbalk om deze uit te lijnen.

   ![](assets/des_text_alignment.png)

* **Horizontale uitlijning** kan worden toegepast op tekst, afbeeldingen en knoppen, momenteel niet op de **[!UICONTROL Divider]** componenten en **[!UICONTROL Social]** componenten.

   ![](assets/des_horizontal_alignment.png)

* Als u de **verticale uitlijning** wilt instellen, selecteert u een kolom in een structuurcomponent en kiest u een optie in het deelvenster Instellingen.

   ![](assets/des_set_vertical_alignment.png)

## Achtergronden instellen {#about-backgrounds}

>[!CONTEXTUALHELP]
>id="ac_edition_backgroundimage"
>title="Achtergrondinstellingen"
>abstract="Met de e-mailontwerper kunt u de achtergrondkleur of achtergrondafbeelding voor uw inhoud personaliseren. Achtergrondafbeelding wordt niet door alle e-mailclients ondersteund."
>additional-url="https://docs.google.com/spreadsheets/d/1TLo62YKm3tThUWDOIliCQFWs3dpNjpDfw6DdTr1oGOw/edit#gid=0" text="Aanvullende informatie"

Als het gaat om het instellen van achtergronden met de e-mailontwerper, raadt Adobe het volgende aan:

1. Pas een achtergrondkleur toe op de tekst van uw e-mail, indien dat door uw ontwerp wordt vereist.
1. In de meeste gevallen stelt u achtergrondkleuren in op kolomniveau.
1. Probeer geen achtergrondkleuren te gebruiken voor afbeeldings- of tekstcomponenten, omdat deze moeilijk te beheren zijn.

Hieronder vindt u de beschikbare achtergrondinstellingen die u kunt gebruiken.

* Stel een **[!UICONTROL Background color]** voor de hele e-mail in. Selecteer de instellingen voor de hoofdtekst in de boomstructuur die toegankelijk is in het linkerpalet.

   ![](assets/des_background_body.png)

* Stel dezelfde achtergrondkleur in voor alle structuurcomponenten door deze te selecteren **[!UICONTROL Viewport background color]**. Met deze optie kunt u een andere instelling selecteren dan de achtergrondkleur.

   ![](assets/des_background_viewport.png)

* Stel een andere achtergrondkleur in voor elke structuurcomponent. Selecteer een structuur in de boomstructuur die toegankelijk is vanuit het linkerpalet als u alleen een specifieke achtergrondkleur op die structuur wilt toepassen.

   ![](assets/des_background_structure.png)

   Zorg ervoor dat u geen achtergrondkleur voor de viewport instelt, omdat hierdoor de achtergrondkleuren van de structuur kunnen worden verborgen.

* Stel een waarde in **[!UICONTROL Background image]** voor de inhoud van een structuurcomponent.

   ![](assets/des_background_image.png)

   >[!NOTE]
   >
   >Sommige e-mailprogramma&#39;s ondersteunen achtergrondafbeeldingen niet. Als deze optie niet wordt ondersteund, wordt in plaats daarvan de achtergrondkleur van de rij gebruikt. Selecteer de gewenste achtergrondkleur voor fallback als de afbeelding niet kan worden weergegeven.

* Stel een achtergrondkleur in op kolomniveau.

   ![](assets/des_background_column.png)

   >[!NOTE]
   >
   >Dit is het meest gebruikte geval. Adobe raadt aan achtergrondkleuren in te stellen op kolomniveau, omdat dit meer flexibiliteit biedt bij het bewerken van de volledige e-mailinhoud.

   U kunt ook een achtergrondafbeelding instellen op kolomniveau, maar dit wordt zelden gebruikt.

### Voorbeeld: verticale uitlijning en opvulling aanpassen {#example--adjusting-vertical-alignment-and-padding}

U wilt de opvulling en de verticale uitlijning aanpassen binnen een structuurcomponent die uit drie kolommen bestaat. Volg de onderstaande stappen om dit te doen:

1. Selecteer de structuurcomponent rechtstreeks in de e-mail of met gebruik van de boomstructuur die beschikbaar is in het linker **palet**.
1. Klik op de **contextafhankelijke werkbalk****[!UICONTROL Select a column]** en kies de werkbalk die u wilt bewerken. U kunt deze ook selecteren in de boomstructuur.

   ![](assets/des_selecting_column.png)

   De bewerkbare parameters voor die kolom worden weergegeven in het **[!UICONTROL Settings]** deelvenster aan de rechterkant.

1. Selecteer onder **[!UICONTROL Vertical alignment]** de optie **[!UICONTROL Up]**.

   ![](assets/des_vertical_alignment.png)

   De inhoudcomponent wordt vóór de kolom weergegeven.

1. Definieer onder **[!UICONTROL Padding]** de opvulling boven in de kolom. Klik op het vergrendelingspictogram om de synchronisatie met de onderste opvulling te verbreken.

   Definieer de linker- en rechteropvulling voor die kolom.

   ![](assets/des_adjusting_padding.png)

1. Ga op dezelfde manier te werk om de uitlijning en opvulling van de andere kolommen aan te passen.

   ![](assets/des_adjusting_columns.png)

1. Sla uw wijzigingen op.

## Koppelingen opmaken {#about-styling-links}

U kunt een koppeling onderstrepen en de kleur en het doel ervan selecteren in de e-mailontwerper.

1. In een component waar een verbinding wordt opgenomen, selecteer de etikettekst van uw verbinding.

1. In de componentenmontages, controleer **[!UICONTROL Underline link]** om de etikettekst van uw verbinding te onderstrepen.

   ![](assets/stylelinks-selecttext.png)

1. Als u wilt selecteren in welke browsercontext de koppeling wordt geopend, selecteert u een **[!UICONTROL Target]**.

   ![](assets/stylelinks-target.png)

1. Klik op om de kleur van de koppeling te wijzigen **[!UICONTROL Link color]**.

   ![](assets/stylelinks-colorpicker.png)

1. Kies de gewenste kleur.

   ![](assets/stylelinks-colorchanged.png)

1. Sla uw wijzigingen op.

## Adding inline styling attributes {#adding-inline-styling-attributes}

Wanneer u in de interface E-mailontwerper een element selecteert en de instellingen van het element in het zijpaneel weergeeft, kunt u de inline-kenmerken en de bijbehorende waarde voor dat specifieke element aanpassen.

1. Selecteer een element in de inhoud.
1. Zoek in het zijpaneel naar de **[!UICONTROL Styles Inline]** instellingen.

   ![](assets/email_designer_inlineattributes.png)

1. Wijzig de waarden van de bestaande kenmerken of voeg nieuwe toe met de knop **+** . U kunt alle kenmerken en waarden toevoegen die CSS-compatibel zijn.

De stijl wordt vervolgens toegepast op het geselecteerde element. Als voor de onderliggende elementen geen specifieke stijlkenmerken zijn gedefinieerd, wordt de opmaak van het bovenliggende element overgeërfd.
