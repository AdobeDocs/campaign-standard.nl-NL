---
solution: Campaign Standard
product: campaign
title: De e-mailontwerper gebruiken
description: Ontdek de E-mailontwerper en hoe deze inhoud voor e-mailontwerp inschakelt.
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 88%

---


# De e-mailontwerper gebruiken {#email-designer}

## E-mail Designer - overzicht {#about-the-email-designer}

Met Email Designer kunt u e-mailcontent en e-mailcontentsjablonen maken. Email Designer is compatibel met eenvoudige e-mails, transactionele e-mails, e-mails voor A/B-tests, meertalige e-mails en terugkerende e-mails.

Om aan de slag te gaan met Email Designer bekijkt u deze [video’s](https://docs.adobe.com/content/help/nl-NL/campaign-standard-learn/tutorials/designing-content/email-designer/email-designer-overview.html#GettingStarted) waarin de algemene functionaliteit van Email Designer wordt uitgelegd en waarin wordt aangetoond hoe u een nieuw e-mailbericht kunt ontwerpen of sjablonen kunt gebruiken.

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

### E-mail Designer-interface {#email-designer-interface}

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

### Terminologie {#terminology}

**Sjablonen**: Sjablonen zijn e-mailstructuren die u kunt maken en hergebruiken voor meerdere leveringen.

**Fragmenten**: Een fragment is een herbruikbaar onderdeel waarnaar in een of meer e-mails kan worden verwezen.

**Structuuronderdelen**: Structurele elementen die de lay-out van de e-mail bepalen

**Contentonderdelen**: Contentonderdelen zijn onbewerkte, lege onderdelen die u kunt bewerken zodra ze in een e-mail zijn geplaatst.

### Best practices voor het ontwerpen van content {#content-design-best-practices}

Als u Email Designer goed wilt gebruiken en op de eenvoudigste manier de beste e-mails wilt maken, raden we u aan de volgende principes toe te passen:

* Gebruik inline opmaak in plaats van een afzonderlijke CSS en een CSS in de &lt;head>-sectie van de HTML. Met inline opmaak kunt u het opslaan en opnieuw gebruiken van contentfragmenten optimaliseren.

   Zie [Inline opmaakkenmerken toevoegen](../../designing/using/styles.md#adding-inline-styling-attributes).

* Als u ZIP-bestanden met uw HTML-content importeert, gebruikt u gewone CSS. SCSS-stijlpagina’s worden niet ondersteund.

* U kunt uw branding eenvoudig regelen door contentfragmenten te maken en opnieuw te gebruiken, zodat uw marketingcampagnes consistent blijven.

   Zie [Een contentfragment maken](../../designing/using/using-reusable-content.md#creating-a-content-fragment).

* Tijdens het bewerken van **e-mailcontent**:

   Bekijk uw berichten voordat u ze verzendt. Adobe Campaign biedt een manier om het renderen van e-mail te testen met Litmus. Zie [E-mail renderen](../../sending/using/email-rendering.md) voor meer informatie.

Meer ontwerp en algemene beste praktijken betreffende berichten worden voorgesteld in de volgende sectie: [Best practices voor levering](../../sending/using/delivery-best-practices.md)

### Beperkingen van E-mail Designer {#email-designer-limitations}

* U kunt geen personalisatievelden gebruiken in een fragment. Zie [deze sectie](../../designing/using/using-reusable-content.md#about-fragments)voor meer informatie over fragmenten.

<!--* You cannot save directly as a fragment some content of an email that you are editing within the Email Designer. You need to copy-paste the HTML corresponding to that content into a new fragment. For more on this, see [Saving content as a fragment](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).-->
* Bij het bewerken van stijlen zijn alleen weblettertypen beschikbaar die door de meeste e-mailclients officieel worden ondersteund.
* Stijlen kunnen niet worden opgeslagen als thema voor toekomstig hergebruik. De CSS-stijl kan echter worden opgeslagen in een contentsjabloon of in een e-mail. Zie [deze sectie](../../designing/using/styles.md)voor meer informatie over stijlen.
* De meta-tag Referrer wordt niet ondersteund in de e-mailontwerper.
* Surrogaatparen, tekens die niet in het meertalig basisvlak van de Unicode-tekenset staan, kunnen niet in 2 bytes (16 bits) worden opgeslagen en moeten in 2 UTF-16-tekens worden gecodeerd. Deze tekens zijn enkele CJK-ideografieën, de meeste emojis en sommige talen.
Deze tekens kunnen onverenigbaarheidsproblemen veroorzaken in dynamische tekst. U moet sterke tests uitvoeren alvorens uw berichten te verzenden.

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