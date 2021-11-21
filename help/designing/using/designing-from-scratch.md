---
title: 'Geheel nieuwe e-mails ontwerpen '
description: Ontdek hoe u e-mailberichten kunt ontwerpen op basis van nieuwe e-mailinhoud in de e-mailontwerper.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Beginner
exl-id: 052d24b7-d3e0-41d7-8b2c-92bd3addb3a2
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1239'
ht-degree: 2%

---

# Geheel nieuwe e-mails ontwerpen {#designing-an-email-content-from-scratch}

Leer hoe u e-mailinhoud kunt master. Met E-mailontwerper kunt u e-mails en sjablonen maken die beginnen met of zonder uw eigen vooraf gedefinieerde inhoud.

Hier volgen de belangrijkste stappen voor het maken en ontwerpen van een geheel nieuwe e-mailinhoud met de e-mailontwerper:

1. Maak een e-mail en open de inhoud ervan.
1. Voeg structuurcomponenten toe om de e-mail vorm te geven. Zie [De e-mailstructuur bewerken](#defining-the-email-structure).
1. Voeg inhoudscomponenten en fragmenten in de structuurcomponenten in. Zie [Fragmenten en inhoudscomponenten toevoegen](#defining-the-email-structure).
1. Voeg afbeeldingen toe en bewerk de tekst van de e-mail. Zie [Afbeeldingen invoegen](../../designing/using/images.md#inserting-images).
1. Pas uw e-mail aan door personaliseringsgebieden, verbindingen, etc. toe te voegen. Zie [Een aanpassingsveld invoegen](../../designing/using/personalization.md#inserting-a-personalization-field), [Een koppeling invoegen](../../designing/using/links.md#inserting-a-link) en [Dynamische inhoud in een e-mail definiëren](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).
1. Bepaal de onderwerpregel van uw e-mail. Zie [De onderwerpregel van een e-mail aanpassen](../../designing/using/subject-line.md#defining-the-subject-line-of-an-email).
1. Een voorvertoning van uw e-mail bekijken.
1. Sla de inhoud op en voer het bericht verder nadat u hebt bepaald dat u een publiek hebt gedefinieerd en het verzenden op de juiste wijze hebt gepland.

U kunt dit ook uitchecken [inleidende video](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true).

>[!NOTE]
>
>U kunt het ontwerpen van nieuwe e-mailinhoud voorkomen door sjablonen voor inhoud buiten de verpakking te gebruiken. Zie voor meer informatie [Inhoudssjablonen](../../designing/using/using-reusable-content.md#content-templates).

## E-mailstructuur definiëren {#defining-the-email-structure}

>[!CONTEXTUALHELP]
>id="ac_structure_components"
>title="Informatie over de componenten Structuur"
>abstract="Structuurelementen definiëren de indeling van de e-mail."

>[!CONTEXTUALHELP]
>id="ac_edition_columns"
>title="E-mailkolommen definiëren"
>abstract="Met de E-mailontwerper kunt u de indeling van uw e-mail eenvoudig definiëren door de kolomstructuur te definiëren."

Met de e-mailontwerper kunt u de structuur van uw e-mail eenvoudig definiëren. Door structuurelementen toe te voegen en te bewegen met eenvoudige belemmering-en-dalingsacties, kunt u de vorm van uw e-mail binnen seconden ontwerpen.

De structuur van een e-mail bewerken:

1. Open een bestaande inhoud of maak een nieuwe e-mailinhoud.
1. Toegang krijgen tot **[!UICONTROL Structure components]** door **+** links.

   ![](assets/email_designer_structure.png)

1. Sleep de structuurcomponenten die u nodig hebt om uw e-mail vorm te geven en zet deze neer.

   ![](assets/email_designer_structure_components.png)

   Een blauwe lijn materialiseert de nauwkeurige plaats van de structuurcomponenten alvorens u het laat vallen. U kunt het boven, tussen of onder een andere component, maar niet binnen laten vallen.

   >[!NOTE]
   >
   >Kolommen zijn niet compatibel met alle e-mailprogramma&#39;s. Kolommen worden niet gestapeld als deze functie niet wordt ondersteund.
   >
   >Nadat u de onderdelen in de e-mail hebt geplaatst, kunt u deze alleen verplaatsen of verwijderen als er al een inhoudscomponent of een fragment in de e-mail is geplaatst.

1. Er zijn verschillende structuurcomponenten beschikbaar die uit een of meer kolommen zijn samengesteld.

   Selecteer **[!UICONTROL n:n column]** om het aantal kolommen van uw keus (tussen 3 en 10) te bepalen. U kunt de breedte van elke kolom ook bepalen door de pijlen bij de bodem van elke kolom te bewegen.

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >Elke kolomgrootte mag niet kleiner zijn dan 10% van de totale breedte van de structuurcomponent. U kunt geen kolom verwijderen die niet leeg is.

Nadat de structuur is gedefinieerd, kunt u inhoudsfragmenten en -componenten aan uw e-mail toevoegen.

## Een preheader gebruiken {#preheader}

>[!CONTEXTUALHELP]
>id="ac_edition_preheader"
>title="Een preheader gebruiken"
>abstract="Met de preheader kunt u een korte samenvattingstekst configureren die een hogere open snelheid voor uw e-mail biedt."

Een preheader is een korte samenvattingstekst die op de onderwerpregel volgt wanneer een e-mail van uw Postvak IN wordt weergegeven. De preheader biedt een hogere open snelheid.

Selecteer **[!UICONTROL Preheader]** te bewerken en de inhoud in te vullen.

![](assets/email_designer_preheader.png)

U kunt een **[!UICONTROL Content block]**, **[!UICONTROL Dynamic content]** of **[!UICONTROL Personalization fields]** in de preheader-inhoud.

>[!NOTE]
>
>De preheader is niet compatibel met alle e-mailprogramma&#39;s. Voorheader wordt niet weergegeven als dit niet wordt ondersteund.

## Inhoudscomponenten gebruiken {#about-content-components}

>[!CONTEXTUALHELP]
>id="ac_content_components"
>title="Informatie over inhoudscomponenten"
>abstract="Inhoudscomponenten zijn lege plaatsaanduidingen voor inhoud die u kunt bewerken om een e-mail te maken."

Inhoudscomponenten zijn onbewerkte, lege componenten die u kunt bewerken wanneer u ze eenmaal in een e-mail hebt geplaatst.

U kunt zoveel inhoudscomponenten toevoegen als u wilt in een structuurcomponent. U kunt ze ook binnen de structuurcomponent of naar een andere structuurcomponent verplaatsen.

Hier volgt een lijst met de beschikbare onderdelen in E-mailontwerper:

### **[!UICONTROL Button]**

Als u meerdere knoppen moet gebruiken in plaats van elke knop helemaal opnieuw te bewerken, kunt u de opdracht **[!UICONTROL Button]** gebruiken met de contextafhankelijke werkbalk.

U kunt knoppen ook opslaan in fragmenten die opnieuw kunnen worden gebruikt. Zie voor meer informatie [Een inhoudsfragment maken](../../designing/using/using-reusable-content.md#creating-a-content-fragment) en [Inhoud opslaan als een fragment](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).

Selecteren **[!UICONTROL Fallback view]** om de fallback-afbeelding weer te geven in de e-mailontwerper.

### **[!UICONTROL Text]**

Gebruik deze component om tekst in te voegen in uw e-mail. U kunt de kleur, stijl en grootte van de tekst aanpassen in **[!UICONTROL Component Settings]**.

### **[!UICONTROL Divider]**

Gebruik deze component om een scheidingslijn in te voegen in uw e-mail. U kunt de kleur, stijl en grootte van de eindlijn selecteren in **[!UICONTROL Component Settings]**.

### **[!UICONTROL HTML]**

Met deze component kunt u de verschillende onderdelen van de bestaande HTML kopiëren en plakken. Hierdoor kunt u gratis modulaire HTML-componenten maken.

>[!NOTE]
>
>Een gratis HTML-component kan met beperkte opties worden bewerkt. Als niet alle stijlen zijn gekanteld, moet u de juiste CSS toevoegen in het dialoogvenster **kop** van de HTML-code, anders reageert de e-mail niet. Gebruik de **[!UICONTROL Preview]** om de reactiesnelheid van uw inhoud te testen (zie [Berichten voorvertonen](../../sending/using/previewing-messages.md)).

Om een externe inhoud eenvoudig compatibel te maken met de e-mailontwerper, raadt Adobe u aan een geheel nieuw bericht te maken en de inhoud van uw bestaande e-mail te kopiëren naar fragmenten en componenten.

Als u inhoud hebt die niet opnieuw kan worden gemaakt, kunt u de HTML-code uit het originele e-mailbericht kopiëren en plakken met de opdracht **[!UICONTROL Html]** inhoudscomponent. Zorg ervoor dat u bekend bent met HTML voordat u verdergaat.

>[!NOTE]
>
>De nieuwe inhoud is niet de exacte kopie van uw oorspronkelijke e-mail, maar de onderstaande stappen begeleiden u bij het maken van een bericht dat zo dicht mogelijk bij u ligt.

**Voordat u de inhoud kopieert**

1. In uw originele e-mail, identificeer de herbruikbare secties van de secties die aan elke e-mail uniek zullen zijn die u zult verzenden.
1. Sla alle afbeeldingen en elementen op die u wilt gebruiken.
1. Als u bekend bent met HTML, splitst u de originele HTML in verschillende delen.

### Video {#video-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_video"
>title="Video-instellingen"
>abstract="Gebruik deze component om een video in te voegen in uw e-mail. Video&#39;s werken niet voor alle e-mailclients. We raden u aan een fallback-afbeelding in te stellen."
>additional-url="https://www.emailonacid.com/blog/article/email-development/a_how_to_guide_to_embedding_html5_video_in_email/" text="Aanvullende informatie"

De videocomponent invoegen in een structuurcomponent van uw e-mail en de videokoppeling invoeren in het dialoogvenster **[!UICONTROL Component Settings]**.

>[!NOTE]
>
>Video is niet compatibel met alle e-mailprogramma&#39;s. Als dit niet wordt ondersteund, wordt fallback weergegeven.

### Afbeelding

Gebruik deze component om een afbeelding in te voegen in uw e-mail.

Voeg de afbeeldingscomponent in een structuurcomponent in en klik op Bladeren om een afbeeldingsbestand van uw computer te uploaden.

### **[!UICONTROL Social]**

Gebruik deze component om koppelingen naar pagina&#39;s met sociale media in uw e-mail in te voegen. U kunt selecteren welke koppelingen u wilt weergeven en de grootte van het bijbehorende pictogram in **[!UICONTROL Component Settings]**.

### Carousel {#carousel-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_carousel"
>title="Carrouselinstellingen"
>abstract="Leer hoe u een carrousel invoegt en configureert in uw inhoud.carrousel werkt niet op alle e-mailclients en er wordt een fallback-afbeelding weergegeven als dit niet wordt ondersteund."

1. Sleep de **[!UICONTROL Carousel]** in een structuurcomponent.
1. Blader naar de gewenste afbeeldingen op uw computer.

   ![](assets/des_carousel_browse.png)

1. Van de **[!UICONTROL Settings]** stelt u het gewenste aantal miniaturen in de carrousel in.
1. Selecteer een fallback-afbeelding op uw computer.

   ![](assets/des_carousel_fallback.png)

De carrouselcomponent is niet compatibel met alle e-mailprogramma&#39;s. Upload een fallback om een afbeelding weer te geven wanneer de carrousel niet in de e-mail wordt ondersteund.

>[!NOTE]
>
>De carrouselcomponent is compatibel met de volgende e-mailplatforms: Apple Mail 7, Apple Mail 8, Outlook 2011 voor Mac, Outlook 2016 voor Mac, Mozilla Thunderird, iPad en iPad mini iOS, iPhone iOS, Android, AOL (Chrome, Firefox en Safari).

**Verwante onderwerpen**:

- [Een e-mail maken](../../channels/using/creating-an-email.md)
- [Een doelgroep in een bericht selecteren](../../audiences/using/selecting-an-audience-in-a-message.md)
- [Berichten plannen](../../sending/using/about-scheduling-messages.md)
- [Berichten voorvertonen](../../sending/using/previewing-messages.md)
- [E-mailweergave](../../sending/using/email-rendering.md)
