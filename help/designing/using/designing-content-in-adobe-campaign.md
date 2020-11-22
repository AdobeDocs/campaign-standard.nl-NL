---
solution: Campaign Standard
product: campaign
title: Content ontwerpen in Adobe Campaign
description: Maak vanaf het begin e-mailinhoud, importeer HTML of gebruik bestaande sjablonen.
audience: designing
content-type: reference
topic-tags: about-content-design
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1208'
ht-degree: 90%

---


# Email Designer in Campaign{#designing-content-in-adobe-campaign}

Nadat u in Adobe Campaign een e-mailbericht hebt gemaakt, moet u de content definiëren.

Met de e-mailontwerper kunt u fascinerende, individueel op maat gemaakte e-mails maken door middel van slepen en neerzetten. Of u nu vanaf nul begint of bestaande contentfragmenten of contentsjablonen gebruikt, u ontwerpt en verfijnt alle content voor elke e-mail, zowel promotionele als transactionele e-mails.

Email Designer is ontworpen om HTML te leveren en is geoptimaliseerd voor responsief ontwerp. Zo kunt u rechtstreeks via de gebruikersinterface gemakkelijk dynamische content en zichtbaarheidsvoorwaarden definiëren en toepassen op e-mails, sjablonen of fragmenten. U kunt naadloos met een klik op een knop schakelen tussen de interface voor slepen en neerzetten en HTML-code.

Met Email Designer kunt u e-mailcontent en e-mailcontentsjablonen maken. Email Designer is compatibel met eenvoudige e-mails, transactionele e-mails, e-mails voor A/B-tests, meertalige e-mails en terugkerende e-mails.

Om aan de slag te gaan met Email Designer bekijkt u deze [video’s](https://docs.adobe.com/content/help/nl-NL/campaign-standard-learn/tutorials/designing-content/email-designer/email-designer-overview.html#GettingStarted) waarin de algemene functionaliteit van Email Designer wordt uitgelegd en waarin wordt aangetoond hoe u een nieuw e-mailbericht kunt ontwerpen of sjablonen kunt gebruiken.

<!--The Email Designer has more features than the Legacy Editor and is backward compatible.-->

* Zie [Aan de slag met Email Designer](../../designing/using/quick-start.md) voor informatie over het maken van e-mailcontent.
* Zie [Email Designer gebruiken](../../designing/using/designing-content-in-adobe-campaign.md) voor een overzicht van Email Designer.
* Voor meer informatie over het samenstellen van content:
   * Nieuwe maken: zie [Nieuwe e-mails ontwerpen](../../designing/using/designing-from-scratch.md).
   * Bestaande content gebruiken: zie [Ontwerpen aan de hand van bestaande content](../../designing/using/using-existing-content.md).
   * Creative Cloud-integraties gebruiken: zie [E-mails ontwerpen met meerdere oplossingen](../../designing/using/using-integrations.md).
* Voor meer informatie over personalisatie: zie [Personalisatie](../../designing/using/personalization.md).

Wanneer u een e-mailbericht maakt, kunt u een vooraf gedefinieerde sjabloon gebruiken of bestaande content uit een andere bron laden. Zie [Bestaande content selecteren](../../designing/using/using-existing-content.md#selecting-an-existing-content).

Pas uw content aan om de efficiëntie van uw marketingcampagnes te verhogen. Zie [Een personalisatieveld invoegen](../../designing/using/personalization.md#inserting-a-personalization-field) en [Een contentblok invoegen](../../designing/using/personalization.md#adding-a-content-block).

U kunt ook dynamische content definiëren die varieert per profiel. Zie [Dynamische content definiëren in een e-mail](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) en [Dynamische content definiëren in een landingspagina](../../channels/using/designing-a-landing-page.md#defining-dynamic-content-in-a-landing-page).

Verbeter uw berichten en landingspagina’s met koppelingen en afbeeldingen. Zie [Een koppeling invoegen](../../designing/using/links.md#inserting-a-link) en [Afbeeldingen invoegen](../../designing/using/images.md#inserting-images).

## E-mail Designer-interface {#email-designer-interface}

Email Designer biedt een groot aantal opties waarmee u elk aspect van uw content kunt maken, bewerken en aanpassen.

De interface bestaat uit verschillende gebieden met verschillende functies:

![](assets/email_designer_overview.png)

Sleep vanuit de beschikbare elementen in het **palet** (1) structuuronderdelen en contentfragmenten en zet ze neer in de hoofd **werkruimte** (2). Selecteer een onderdeel of element in de **werkruimte** (2) en pas de hoofdstijlen en weergavekenmerken aan in het deelvenster met **instellingen** (3).

Ga naar meer algemene opties en instellingen op de hoofd **werkbalk** (4).

>[!NOTE]
>
>Het deelvenster met **instellingen** kan naar links worden verplaatst, afhankelijk van de schermresolutie en de weergave.

![](assets/email_designer_toolbar.png)

De **contextuele werkbalk** van de editorinterface biedt verschillende functies, afhankelijk van de geselecteerde zone. U vindt er actieknoppen en knoppen waarmee u de stijl van de tekst kunt wijzigen. De uitgevoerde wijzigingen zijn altijd van toepassing op de geselecteerde zone.

### Startpagina van E-mail Designer {#email-designer-home-page}

Wanneer u [een e-mail maakt](../../channels/using/creating-an-email.md), wordt de **[!UICONTROL Email Designer]**-startpagina automatisch weergegeven als u de e-mailcontent selecteert.

![](assets/email_designer_home_page.png)

Op het tabblad **[!UICONTROL Properties]** kunt u de e-mailgegevens bewerken zoals het label, het adres en de naam van de afzender of het e-mailonderwerp. U kunt dit tabblad ook openen door op het e-maillabel bovenaan het scherm te klikken.

![](assets/email_designer_home_properties.png)

Op het tabblad **[!UICONTROL Templates]** kunt u kiezen uit kant-en-klare HTML-content of de sjablonen die u al hebt gemaakt, om snel te beginnen met het ontwerpen van uw e-mail. Zie [Contentsjablonen](../../designing/using/using-reusable-content.md#content-templates).

![](assets/email_designer_home_templates.png)

Op het tabblad **[!UICONTROL Learn & support]** hebt u eenvoudig toegang tot de bijbehorende documentatie en tutorials.

![](assets/email_designer_home_support.png)

Als u geen sjabloon selecteert, kunt u op de startpagina van Email Designer ook kiezen hoe u wilt beginnen met het ontwerpen van uw content:

* Klik op de knop **[!UICONTROL Create]** om geheel nieuwe content te schrijven. Zie [Nieuwe e-mailcontent ontwerpen](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
* Klik op de knop **[!UICONTROL Upload]** om een bestand van uw computer te uploaden. Zie [Content importeren vanuit een bestand](../../designing/using/using-existing-content.md#importing-content-from-a-file).
* Klik op de knop **[!UICONTROL Import from URL]** om bestaande content op te halen via een URL. Zie [Content importeren via een URL](../../designing/using/using-existing-content.md#importing-content-from-a-url).

## Terminologie {#terminology}

**Sjablonen**: Sjablonen zijn e-mailstructuren die u kunt maken en hergebruiken voor meerdere leveringen.

**Fragmenten**: Een fragment is een herbruikbaar onderdeel waarnaar in een of meer e-mails kan worden verwezen.

**Structuuronderdelen**: Structurele elementen die de lay-out van de e-mail bepalen.

**Contentonderdelen**: Contentonderdelen zijn onbewerkte, lege onderdelen die u kunt bewerken zodra ze in een e-mail zijn geplaatst.

## Best practices voor het ontwerpen van content {#content-design-best-practices}

Als u Email Designer goed wilt gebruiken en op de eenvoudigste manier de beste e-mails wilt maken, raden we u aan de volgende principes toe te passen:

* Gebruik inline opmaak in plaats van een afzonderlijke CSS en een CSS in de &lt;head>-sectie van de HTML. Met inline opmaak kunt u het opslaan en opnieuw gebruiken van contentfragmenten optimaliseren.

   Zie [Inline opmaakkenmerken toevoegen](../../designing/using/styles.md#adding-inline-styling-attributes).

* Als u ZIP-bestanden met uw HTML-content importeert, gebruikt u gewone CSS. SCSS-stijlpagina’s worden niet ondersteund.

* U kunt uw branding eenvoudig regelen door contentfragmenten te maken en opnieuw te gebruiken, zodat uw marketingcampagnes consistent blijven.

   Zie [Een contentfragment maken](../../designing/using/using-reusable-content.md#creating-a-content-fragment).

* Tijdens het bewerken van **e-mailcontent**:

   Bekijk uw berichten voordat u ze verzendt. Adobe Campaign biedt een manier om het renderen van e-mail te testen met Litmus. Zie [E-mail renderen](../../sending/using/email-rendering.md) voor meer informatie.

Meer ontwerp en algemene beste praktijken betreffende berichten worden voorgesteld in de volgende sectie: [Aanbevolen procedures](../../sending/using/delivery-best-practices.md)voor levering.

### Fragmenten bijwerken {#email-designer-updates}

Email Designer wordt voortdurend verbeterd. Als u geheel nieuwe e-mailcontent hebt gemaakt, op basis van een meegeleverde sjabloon of met fragmenten die u hebt gemaakt, ontvangt u mogelijk het volgende updatebericht wanneer u de content de volgende keer opent:

![](assets/email_designer_fragment_patch_message.png)

Adobe raadt u aan de content bij te werken naar de nieuwste versie om problemen zoals CSS-conflicten te voorkomen. Klik op **[!UICONTROL Update now]**.

Als er een fout optreedt tijdens het bijwerken van de content, controleert en repareert u de HTML voordat u deze update opnieuw uitvoert.

Let bij fragmenten op het volgende:

* Als u een fragment aan een nieuwe e-mail of sjabloon wilt toevoegen en dit bericht ontvangt, moet u het fragment eerst bijwerken.

* Als u meerdere fragmenten hebt, moet u elk fragment bijwerken dat u in e-mailcontent wilt gebruiken.

* U kunt ervoor kiezen om bepaalde fragmenten niet bij te werken om te voorkomen dat dit gevolgen heeft voor de huidige e-mailberichten die nog niet zijn voorbereid.

* U kunt nog steeds e-mailberichten verzenden waarin een fragment wordt gebruikt dat nog niet is bijgewerkt, maar dat fragment kan niet worden bewerkt.

* Het bijwerken van fragmenten die worden gebruikt in e-mailberichten die al zijn voorbereid, heeft geen invloed op deze e-mails.

## Beperkingen van E-mail Designer {#email-designer-limitations}

* U kunt geen personalisatievelden gebruiken in een fragment. Zie [deze sectie](../../designing/using/using-reusable-content.md#about-fragments)voor meer informatie over fragmenten.

<!--* You cannot save directly as a fragment some content of an email that you are editing within the Email Designer. You need to copy-paste the HTML corresponding to that content into a new fragment. For more on this, see [Saving content as a fragment](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).-->

* Bij het bewerken van stijlen zijn alleen weblettertypen beschikbaar die door de meeste e-mailclients officieel worden ondersteund.
* Stijlen kunnen niet worden opgeslagen als thema voor toekomstig hergebruik. De CSS-stijl kan echter worden opgeslagen in een contentsjabloon of in een e-mail. Zie [deze sectie](../../designing/using/styles.md)voor meer informatie over stijlen.
* De meta-tag Referrer wordt niet ondersteund in de e-mailontwerper.
* Surrogaatparen, tekens die niet in het meertalig basisvlak van de Unicode-tekenset staan, kunnen niet in 2 bytes (16 bits) worden opgeslagen en moeten in 2 UTF-16-tekens worden gecodeerd. Deze tekens zijn enkele CJK-ideografieën, de meeste emojis en sommige talen.<br>Deze tekens kunnen onverenigbaarheidsproblemen veroorzaken in dynamische tekst. U moet sterke tests uitvoeren alvorens uw berichten te verzenden.

**Verwante onderwerpen**

* [Een e-mail maken](../../channels/using/creating-an-email.md)
* [Een landingspagina ontwerpen](../../channels/using/designing-a-landing-page.md)
* [Een sms-bericht maken](../../channels/using/creating-an-sms-message.md)
* [Een pushbericht maken en verzenden](../../channels/using/preparing-and-sending-a-push-notification.md)
