---
title: De Segment Builder gebruiken
description: Leer hoe u de Segment Builder kunt gebruiken om een publiek te maken.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 9a6c542e-10ed-4e77-abb3-36324e1cb38f
hide: true
hidefromtoc: true
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 3%

---

# De Segment Builder gebruiken {#using-the-segment-builder}

>[!IMPORTANT]
>
>De dienst van de Doelen van het publiek is momenteel in bèta, die aan regelmatige updates zonder bericht kan worden onderworpen. Klanten moeten op Azure (momenteel alleen in bèta voor Noord-Amerika) worden gehost om toegang te krijgen tot deze mogelijkheden. Neem contact op met de klantenservice van Adobe als u toegang wilt.

De Bouwer van het Segment staat u toe om publiek te bouwen door regels te bepalen die op gegevens worden gebaseerd die uit het [&#x200B; in real time Profiel van de Klant &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=nl-NL) komen.

In deze sectie worden algemene concepten beschreven bij het maken van een segment. Voor gedetailleerde informatie over de Bouwer van het Segment zelf, verwijs naar de [&#x200B; gebruikersgids van de Bouwer van het Segment &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=nl-NL).

De interface van de Bouwer van het Segment wordt samengesteld als volgt:

* Het linkerpaneel verstrekt alle attributen, gebeurtenissen en publiek beschikbaar om het segment te bouwen door gewenste gebieden in de werkruimte van de segmentbouwer te slepen en te laten vallen.
* Het middelste gebied biedt een werkruimte om het segment te maken door regels van de beschikbare velden te definiëren en te combineren.
* De kopbal en juiste ruit tonen de eigenschappen van het segment (d.w.z., naam, beschrijving, en geschat gekwalificeerde profielen voor het segment).

![](assets/aep_audiences_interface.png)

## Een segment maken

Voer de volgende stappen uit om een segment te maken:

De Segment Builder moet nu in uw werkruimte worden weergegeven. Hiermee kunt u een segment maken met gegevens uit Adobe Experience Platform die uiteindelijk worden gebruikt om uw publiek te maken.

1. Geef het segment een naam en voer vervolgens een beschrijving in (optioneel).

   ![](assets/aep_audiences_creation_edit_name.png)

1. Controleer of het gewenste samenvoegbeleid is geselecteerd in het instellingenvenster.

   Voor meer informatie over samenvoegbeleid, verwijs naar de specifieke sectie van de [&#x200B; gebruikersgids van de Bouwer van het Segment &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=nl-NL).

   ![](assets/aep_audiences_mergepolicy.png)

1. Zoek de gewenste velden in het linkerdeelvenster en sleep deze naar de werkruimte in het midden.

   ![](assets/aep_audiences_dragfield.png)

1. Configureer de regels die overeenkomen met de gesleepte velden.

   ![](assets/aep_audiences_configure_rules.png)

1. Klik op de knop **[!UICONTROL Create segment]**.

## De juiste velden voor een segment zoeken

In het linkerdeelvenster worden alle kenmerken, gebeurtenissen en doelgroepen weergegeven die u kunt gebruiken om regels samen te stellen.

De vermelde gebieden zijn attributen die door uw bedrijf worden gevangen en door het [&#x200B; Model van de Gegevens van de Ervaring (XDM) Systeem &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=nl-NL) beschikbaar zijn gemaakt.

Velden zijn ingedeeld in tabbladen:

* **[!UICONTROL Attributes]**: bestaande profielkenmerken die afkomstig kunnen zijn uit uw Adobe Campaign-database en/of Adobe Experience Platform. Zij verwijzen naar statische informatie die bij een profiel is gevoegd (bijv. e-mailadres, land van verblijf, status van loyaliteitsprogramma, enz.).

  ![](assets/aep_audiences_attributestab.png)

* **[!UICONTROL Events]**: Activiteiten die consumenten identificeren die enige interactie hebben gehad met de klantenaanraakpunten van uw bedrijf, zoals &quot;iedereen die twee keer in twee weken heeft besteld&quot;. Dit kan van Adobe Analytics worden gestroomd, of direct in Adobe Experience Platform worden opgenomen gebruikend derdehulpmiddelen ETL.

  ![](assets/aep_audiences_eventstab.png)

>[!NOTE]
>
>**Meerdere-entiteitssegmentatie** staat u toe om de gegevens van het Profiel met extra gegevens uit te breiden die op producten, opslag, of andere niet-profielklassen worden gebaseerd. Zodra verbonden, worden de gegevens van extra klassen beschikbaar alsof zij aan het schema van het Profiel inheems waren.
>
>Raadpleeg de [desbetreffende documentatie](https://experienceleague.adobe.com/docs/experience-platform/segmentation/multi-entity-segmentation.html?lang=nl-NL) voor meer informatie.

Door gebrek, toont de Bouwer van het Segment gebieden waarin de gegevens reeds aanwezig zijn. Als u het volledige schema wilt weergeven, inclusief de velden waarvoor geen gegevens aanwezig zijn, schakelt u de optie **[!UICONTROL Show full XDM schema]** van de instellingen in.

![](assets/aep_audiences_populatedfields.png)

Het symbool aan het eind van elk gebied verstrekt extra informatie over de attributen en hoe te om het te gebruiken.

![](assets/aep_audiences_isymbol.png)

## Regels voor een segment definiëren

>[!NOTE]
>
>In de onderstaande sectie vindt u algemene informatie over de definitie van regels. Voor meer op dit, verwijs naar de [&#x200B; gebruikersgids van de Bouwer van het Segment &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=nl-NL).

Voer de volgende stappen uit om een regel te maken:

1. Zoek het veld in het linkerdeelvenster dat de kenmerken of gebeurtenissen aangeeft waarop de regel wordt gebaseerd.

1. Sleep het gebied op de middelste werkruimte, dan vorm het volgens de gewenste segmentdefinitie. Hiervoor zijn verschillende tekenreeks- en datum-/tijdfuncties beschikbaar.

   In het onderstaande voorbeeld zal de regel gelden voor alle profielen met een geslacht dat gelijk is aan &quot;Mannelijk&quot;.

   ![](assets/aep_audiences_malegender.png)

   De geschatte populatie die overeenkomt met het segment, wordt automatisch opnieuw berekend in de sectie **[!UICONTROL Segment Properties]** .

1. Met de knop **[!UICONTROL View Profiles]** krijgt u een voorvertoning van de eerste 20 records die overeenkomen met de regel, zodat u het segment snel kunt valideren.

   ![](assets/aep_audiences_samplepreview.png)

   U kunt zo veel extra regels toevoegen als u wilt om de juiste profielen als doel in te stellen.

   Wanneer het toevoegen van een regel aan een container, zal het aan om het even welke bestaande regels met de EN logische exploitant worden toegevoegd. Klik zo nodig op de logische operator om deze te wijzigen.

   ![](assets/aep_audiences_andoperator.png)

Nadat de twee regels zijn gekoppeld, vormen ze een container.

## Velden vergelijken

Met de Segment Builder kunt u twee velden vergelijken om een regel te definiëren. Bijvoorbeeld, vrouwtjes het waarvan huisadres in een verschillende code van het ZIP van hun het werkadres is.

Ga als volgt te werk om dit te doen:

1. Sleep het eerste veld dat u wilt vergelijken (bijvoorbeeld de postcode van het thuisadres) naar de werkruimte in het midden.

   ![](assets/aep_audiences_comparing_1.png)

1. Selecteer het tweede veld (bijvoorbeeld de postcode van het werkadres) dat met het eerste veld wordt vergeleken.

   Sleep het naar de werkruimte in het midden, in dezelfde container als het eerste veld, in het vak **[!UICONTROL Drop here to compare operands]** .

   ![](assets/aep_audiences_comparing_2.png)

1. Configureer de operator tussen de twee velden naar wens. In dit voorbeeld, willen wij ons segment profielen met het huisadres verschillend van het het werkadres richten.

   ![](assets/aep_audiences_comparing_3.png)

De regel is nu gevormd en klaar om als publiek worden geactiveerd.
