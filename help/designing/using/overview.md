---
title: De e-mailontwerper gebruiken
description: Ontdek de E-mailontwerper en hoe deze inhoud voor e-mailontwerp inschakelt.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9ab3cc5a23b9b31b463bc3557b8164307d367d25
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 3%

---


# De e-mailontwerper gebruiken {#email-designer}

## Overzicht van E-mailDesigner {#about-the-email-designer}

Met de e-mailontwerper kunt u e-mailinhoud en sjablonen voor e-mailinhoud maken. Het is compatibel met eenvoudige e-mails, transactionele e-mails, e-mails voor A/B-tests, meertalige e-mails en terugkerende e-mails.

Om aan de slag te gaan met de e-mailontwerper bekijkt u deze [set video](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html#GettingStarted) &#39;s waarin de algemene functionaliteit van de e-mailontwerper wordt uitgelegd en wordt uitgelegd hoe u een e-mailbericht helemaal zelf kunt ontwerpen of sjablonen kunt gebruiken.

### Homepage van E-mail Designer {#email-designer-home-page}

Wanneer u een e-mail [](../../channels/using/creating-an-email.md)maakt, wordt de **[!UICONTROL Email Designer]** startpagina automatisch weergegeven wanneer u de e-mailinhoud selecteert.

![](assets/email_designer_home_page.png)

Op het **[!UICONTROL Properties]** tabblad kunt u de e-mailgegevens bewerken, zoals het label, het adres en de naam van de afzender of het e-mailonderwerp. U kunt dit tabblad ook openen door op het e-maillabel boven aan het scherm te klikken.

![](assets/email_designer_home_properties.png)

Op het **[!UICONTROL Templates]** tabblad kunt u kiezen uit de HTML-inhoud uit de doos of de sjablonen die u al hebt gemaakt om snel uw e-mail te gaan ontwerpen. Zie [Inhoudssjablonen](../../designing/using/using-reusable-content.md#content-templates).

![](assets/email_designer_home_templates.png)

Op het **[!UICONTROL Learn & support]** tabblad hebt u eenvoudig toegang tot de bijbehorende documentatie en zelfstudies.

![](assets/email_designer_home_support.png)

Als u geen sjabloon selecteert, kunt u op de introductiepagina E-mail Designer ook kiezen hoe u begint met het ontwerpen van uw inhoud:

* Klik op de **[!UICONTROL Create]** knop om een geheel nieuwe inhoud te starten. Zie Een geheel nieuwe e-mailinhoud [ontwerpen](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
* Klik op de **[!UICONTROL Upload]** knop om een bestand van uw computer te uploaden. Zie Inhoud [importeren uit een bestand](../../designing/using/using-existing-content.md#importing-content-from-a-file).
* Klik op de **[!UICONTROL Import from URL]** knop om bestaande inhoud van een URL op te halen. Zie Inhoud [importeren via een URL](../../designing/using/using-existing-content.md#importing-content-from-a-url).

### E-mailDesigner-interface {#email-designer-interface}

De e-mailontwerper biedt een groot aantal opties waarmee u elk aspect van uw inhoud kunt maken, bewerken en aanpassen.

De interface bestaat uit verschillende gebieden die verschillende functies bieden:

![](assets/email_designer_overview.png)

Sleep vanuit de elementen in het **palet** (1) de structuurcomponenten en inhoudsfragmenten naar de hoofdwerkruimte **** (2). Selecteer een component of element in de **werkruimte** (2) en pas de hoofdstijlen en weergavekenmerken aan in het deelvenster **Instellingen** (3).

Toegang tot meer algemene opties en instellingen op de hoofdwerkbalk **** (4).

>[!NOTE]
>
>Het deelvenster **Instellingen** kan naar links worden verplaatst op basis van de schermresolutie en de weergave.

![](assets/email_designer_toolbar.png)

De **contextuele toolbar** van de redacteursinterface biedt diverse functionaliteit afhankelijk van de geselecteerde streek aan. Het bevat actieknoppen en knoppen waarmee u de stijl van de tekst kunt wijzigen. De uitgevoerde wijzigingen zijn altijd van toepassing op de geselecteerde zone.

### Terminologie {#terminology}

**Sjablonen**: Sjablonen zijn e-mailstructuren die u kunt samenstellen en hergebruiken voor verschillende leveringen.

**Fragmenten**: Een fragment is een herbruikbare component waarnaar in een of meer e-mails kan worden verwezen.

**Structuurcomponenten**: Structurele elementen die de lay-out van de e-mail bepalen

**Inhoudscomponenten**: Inhoudscomponenten zijn onbewerkte, lege componenten die u kunt bewerken wanneer u ze eenmaal in een e-mail hebt geplaatst.

### Aanbevolen werkwijzen voor het ontwerpen van inhoud {#content-design-best-practices}

Als u de e-mailontwerper correct wilt gebruiken en de beste e-mails zo eenvoudig mogelijk wilt maken, raden we u aan de volgende principes toe te passen:

* Gebruik inline opmaak in plaats van een afzonderlijke CSS en CSS in de sectie &lt;head> van de HTML. Met inline opmaak kunt u het opslaan en opnieuw gebruiken van inhoudsfragmenten optimaliseren.

   Zie [Inline-opmaakkenmerken](../../designing/using/styles.md#adding-inline-styling-attributes)toevoegen.

* Als u ZIP-bestanden importeert die uw HTML-inhoud bevatten, gebruikt u gewone CSS. SCSS-stijlpagina&#39;s worden niet ondersteund.

* U kunt uw branding eenvoudig regelen door inhoudsfragmenten te maken en opnieuw te gebruiken, zodat uw marketingcampagnes consistent blijven.

   Zie [Een inhoudsfragment](../../designing/using/using-reusable-content.md#creating-a-content-fragment)maken.

* Tijdens het bewerken van **e-mailinhoud**:

   Bekijk uw berichten voordat u ze verzendt. Adobe Campaign biedt een manier om het renderen van e-mail te testen met Litmus. Zie [E-mailrendering](../../sending/using/email-rendering.md)voor meer informatie.

Meer ontwerp en algemene beste praktijken betreffende berichten worden voorgesteld in de volgende sectie: [Best practices voor levering](../../sending/using/delivery-best-practices.md)

### Beperkingen van e-mailDesigner {#email-designer-limitations}

* U kunt geen verpersoonlijkingsgebieden in een fragment gebruiken. For more on fragments, see [this section](../../designing/using/using-reusable-content.md#about-fragments).

<!--* You cannot save directly as a fragment some content of an email that you are editing within the Email Designer. You need to copy-paste the HTML corresponding to that content into a new fragment. For more on this, see [Saving content as a fragment](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).-->
* Bij het bewerken van stijlen zijn alleen weblettertypen beschikbaar die officieel door de meeste e-mailclients worden ondersteund.
* Stijlen kunnen niet worden opgeslagen als thema voor toekomstig hergebruik. De CSS-stijl kan echter worden opgeslagen in een inhoudssjabloon of in een e-mail. For more on styles, see [this section](../../designing/using/styles.md).
* De meta-tag Referrer wordt niet ondersteund in de e-mailontwerper.
* Surrogaatparen, tekens die niet in het meertalig basisvlak van de Unicode-tekenset staan, kunnen niet in 2 bytes (16 bits) worden opgeslagen en moeten in 2 UTF-16-tekens worden gecodeerd. Deze tekens zijn enkele CJK-ideografieën, de meeste emojis en sommige talen.
Deze tekens kunnen onverenigbaarheidsproblemen veroorzaken in dynamische tekst. U moet sterke tests uitvoeren alvorens uw berichten te verzenden.

### Fragmenten bijwerken {#email-designer-updates}

De e-mailontwerper wordt voortdurend verbeterd. Als u een geheel nieuwe e-mailinhoud hebt gemaakt, op basis van een sjabloon buiten de box of als u fragmenten hebt gemaakt, ontvangt u mogelijk de volgende update wanneer u de inhoud de volgende keer opent:

![](assets/email_designer_fragment_patch_message.png)

Adobe raadt u aan uw inhoud bij te werken naar de meest recente versie om problemen zoals problemen met CSS-botsingen te voorkomen. Klik op **[!UICONTROL Update now]**.

Als er een fout optreedt tijdens het bijwerken van de inhoud, controleert u de HTML en repareert u deze voordat u deze update opnieuw uitvoert.

Wat fragmenten betreft, moet u het volgende opmerken:

* Als u een fragment aan een nieuwe e-mail of een malplaatje wilt toevoegen en als u dit bericht krijgt, moet u dit fragment eerst bijwerken.

* Als u meerdere fragmenten hebt, moet u elk fragment bijwerken dat u in e-mailinhoud wilt gebruiken.

* U kunt ervoor kiezen om bepaalde fragmenten niet bij te werken om te voorkomen dat dit gevolgen heeft voor de huidige e-mailberichten die nog niet zijn voorbereid.

* U kunt nog steeds e-mailberichten verzenden waarin een fragment dat niet is bijgewerkt, al wordt gebruikt, maar dat fragment kan niet worden bewerkt.

* Het bijwerken van fragmenten die worden gebruikt in e-mailberichten die al zijn voorbereid, heeft geen invloed op deze e-mails.