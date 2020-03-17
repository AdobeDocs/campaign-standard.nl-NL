---
title: Het gebruiken van de Verenigde Bouwer van het Segment
description: Leer hoe te om de Verenigde Bouwer van het Segment te gebruiken om publiek tot stand te brengen.
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2ef524d1d276abb1ff0a7149462452cafe8e5cd3

---


# Het gebruiken van de Verenigde Bouwer van het Segment {#using-the-unified-segment-builder}

>[!IMPORTANT]
>
>De dienst van de Doelen van het publiek is momenteel in bèta, die aan regelmatige updates zonder bericht kan worden onderworpen. Klanten moeten op Azure (momenteel alleen in bèta voor Noord-Amerika) worden gehost om toegang te krijgen tot deze mogelijkheden. Neem contact op met de klantenservice van Adobe als u toegang wilt.

De Verenigde Bouwer van het Segment staat u toe om publiek te bouwen door regels te bepalen die op gegevens worden gebaseerd die uit de [Verenigde Dienst](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation.html)van het Profiel komen.

In deze sectie worden algemene concepten beschreven wanneer u een segment maakt. Voor gedetailleerde informatie over de Verenigde Bouwer van het Segment zelf, verwijs naar de de gebruikersgids [van de Bouwer van het](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)Segment.

De interface van de Bouwer van het Verenigde Segment wordt samengesteld als volgt:

* Het linkerpaneel verstrekt alle attributen, gebeurtenissen en publiek beschikbaar om het segment te bouwen door gewenste gebieden in de werkruimte van de segmentbouwer te slepen en te laten vallen.
* Het middelste gebied biedt een werkruimte om het segment te maken door regels van de beschikbare velden te definiëren en te combineren.
* In de koptekst en het rechterdeelvenster worden de eigenschappen van het segment weergegeven (naam, beschrijving en geschatte gekwalificeerde profielen voor het segment).

![](assets/aep_audiences_interface.png)

## Een segment maken

Voer de volgende stappen uit om een segment te maken:

De Unified Segment Builder moet nu in uw werkruimte worden weergegeven. Hiermee kunt u een segment maken met behulp van gegevens van het Adobe Experience Platform die uiteindelijk worden gebruikt om uw publiek te maken.

1. Geef het segment een naam en voer vervolgens een beschrijving in (optioneel).

   ![](assets/aep_audiences_creation_edit_name.png)

1. Controleer of het gewenste samenvoegbeleid is geselecteerd in het instellingenvenster.

   Voor meer informatie over fusiebeleid, verwijs naar de specifieke sectie van de de gebruikersgids [van de Bouwer van het](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)Segment.

   ![](assets/aep_audiences_mergepolicy.png)

1. Zoek de gewenste velden in het linkerdeelvenster en sleep deze naar de werkruimte in het midden.

   ![](assets/aep_audiences_dragfield.png)

1. Configureer de regels die overeenkomen met de gesleepte velden.

   ![](assets/aep_audiences_configure_rules.png)

1. Klik op de **[!UICONTROL Create segment]** knop.

## De juiste velden voor een segment zoeken

In het linkerdeelvenster worden alle kenmerken, gebeurtenissen en doelgroepen weergegeven die u kunt gebruiken om regels samen te stellen.

De vermelde velden zijn kenmerken die door uw bedrijf zijn vastgelegd en die beschikbaar zijn gesteld via het XDM-systeem ( [Experience Data Model)](https://www.adobe.io/apis/experienceplatform/home/xdm.html).

Velden zijn ingedeeld in tabbladen:

* **[!UICONTROL Attributes]**: Kenmerken voor bestaande profielen die kunnen ontstaan uit uw Adobe Campagne-database en/of Adobe Experience Platform. Zij verwijzen naar statische informatie die bij een profiel is gevoegd (bijv. e-mailadres, land van verblijf, status van loyaliteitsprogramma, enz.).

   ![](assets/aep_audiences_attributestab.png)

* **[!UICONTROL Events]**: Activiteiten die consumenten identificeren die enige interactie hebben gehad met de klantenaanraakpunten van uw bedrijf, zoals &quot;iedereen die tweemaal in twee weken bestelde&quot;. U kunt deze functie vanuit Adobe Analytics streamen of rechtstreeks via externe ETL-programma&#39;s opnemen in het Adobe Experience Platform.

   ![](assets/aep_audiences_eventstab.png)

>[!NOTE]
>
>**Met segmentatie** over meerdere entiteiten kunt u de profielgegevens uitbreiden met aanvullende gegevens op basis van producten, opslagruimten of andere klassen zonder profiel. Zodra verbonden, worden de gegevens van extra klassen beschikbaar alsof zij aan het schema van het Profiel inheems waren.
>
>Raadpleeg de [desbetreffende documentatie](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/tutorials/segmentation/multi_entity_segmentation.md)voor meer informatie hierover.

Door gebrek, de Verenigde bouwer van het Segment toont gebieden waarin de gegevens reeds aanwezig zijn. Als u het volledige schema wilt weergeven, inclusief de velden waarvoor geen gegevens aanwezig zijn, schakelt u de **[!UICONTROL Show full XDM schema]** optie van de instellingen in.

![](assets/aep_audiences_populatedfields.png)

Het symbool aan het eind van elk gebied verstrekt extra informatie over de attributen en hoe te om het te gebruiken.

![](assets/aep_audiences_isymbol.png)

## Regels voor een segment definiëren

>[!NOTE]
>
>In de onderstaande sectie vindt u algemene informatie over de definitie van regels. Raadpleeg voor meer informatie de gebruikershandleiding [van](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)Segment Builder.

Voer de volgende stappen uit om een regel te maken:

1. Zoek het veld in het linkerdeelvenster dat de kenmerken of gebeurtenissen aangeeft waarop de regel wordt gebaseerd.

1. Sleep het gebied op de middelste werkruimte, dan vorm het volgens de gewenste segmentdefinitie. Hiervoor zijn verschillende tekenreeks- en datum-/tijdfuncties beschikbaar.

   In het onderstaande voorbeeld zal de regel gelden voor alle profielen met een geslacht dat gelijk is aan &quot;Mannelijk&quot;.

   ![](assets/aep_audiences_malegender.png)

   De geschatte populatie die overeenkomt met het segment wordt automatisch opnieuw berekend in de **[!UICONTROL Segment Properties]** sectie.

1. De **[!UICONTROL View Profiles]** knoop geeft u een voorproef van de eerste 20 verslagen die aan de regel beantwoorden, toelatend u om het segment snel te bevestigen.

   ![](assets/aep_audiences_samplepreview.png)

   U kunt zo veel extra regels toevoegen als u wilt om de juiste profielen als doel in te stellen.

   Wanneer het toevoegen van een regel aan een container, zal het aan om het even welke bestaande regels met de EN logische exploitant worden toegevoegd. Klik zo nodig op de logische operator om deze te wijzigen.

   ![](assets/aep_audiences_andoperator.png)

Nadat de twee regels zijn gekoppeld, vormen ze een container.

## Velden vergelijken

De Verenigde Bouwer van het Segment laat u twee gebieden vergelijken om een regel te bepalen. Bijvoorbeeld, vrouwtjes het waarvan huisadres in een verschillende code van het ZIP van hun het werkadres is.

Ga als volgt te werk om dit te doen:

1. Sleep het eerste veld dat u wilt vergelijken (bijvoorbeeld de postcode van het thuisadres) naar de werkruimte in het midden.

   ![](assets/aep_audiences_comparing_1.png)

1. Selecteer het tweede veld (bijvoorbeeld de postcode van het werkadres) dat met het eerste veld wordt vergeleken.

   Sleep het naar de werkruimte in het midden, in dezelfde container als het eerste veld, in het **[!UICONTROL Drop here to compare operands]** vak.

   ![](assets/aep_audiences_comparing_2.png)

1. Configureer de operator tussen de twee velden naar wens. In dit voorbeeld, willen wij ons segment profielen met het huisadres verschillend van het het werkadres richten.

   ![](assets/aep_audiences_comparing_3.png)

De regel is nu gevormd en klaar om als publiek worden geactiveerd.
