---
title: 'E-mail met de oude editor converteren naar e-mailontwerper '
description: Ontdek hoe u e-mailberichten kunt gebruiken die zijn gemaakt in de E-mail van de Oudere Editor naar de e-mailontwerper.
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
source-git-commit: caab111b583534cc2e52aa9e45d9fd37c770783c

---


# E-mailinhoud van verouderde editor converteren {#converting-an-html-content}

Werk met de e-mailontwerper en maak herbruikbare sjablonen en fragmenten op van uw e-mailHTML die u hebt gemaakt in de Verouderde editor.

>[!IMPORTANT]
>
>Deze sectie is bedoeld voor geavanceerde gebruikers die vertrouwd zijn met HTML-code.

Met dit gebruiksgeval kunt u een E-mailDesigner-sjabloon maken door een HTML-e-mail te gebruiken en deze in HTML-componenten te verdelen in de e-mailontwerper.

>[!NOTE]
>
>Net als in de compatibiliteitsmodus kan een HTML-component met beperkte opties worden bewerkt: u kunt alleen op plaats een editie uitvoeren.

## E-mailinhoud voorbereiden

1. Selecteer een HTML-e-mail.
1. Secties identificeren om de HTML-e-mail te delen.
1. Knip de verschillende blokken uit uw HTML.

## Uw e-mailstructuur maken

1. Open het dialoogvenster **[!UICONTROL Email Designer]** om een lege e-mailinhoud te maken.
1. Stel de kenmerken voor het hoofdtekstniveau in: achtergrondkleuren, breedte, enz. Zie E-mailstijlen [](../../designing/using/styles.md)bewerken voor meer informatie.
1. Voeg zoveel structuurcomponenten toe als secties. Zie [De e-mailstructuur](../../designing/using/designing-from-scratch.md#defining-the-email-structure)bewerken voor meer informatie.

## HTML-inhoud toevoegen

1. Voeg een HTML-component toe aan elke structuurcomponent. Zie Fragmenten en componenten [](../../designing/using/designing-from-scratch.md#defining-the-email-structure)toevoegen voor meer informatie.
1. Kopieer en plak de HTML in elke component.

## De stijl van uw e-mail beheren {#manage-the-style-of-your-email}

1. Schakel over naar **[!UICONTROL Mobile view]**. Zie [deze sectie](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)voor meer informatie.

1. U kunt dit corrigeren door over te schakelen naar de modus Broncode en de stijlsectie te kopiëren en te plakken in een nieuwe stijlsectie. Bijvoorbeeld:

   ```
   <style type="text/css">
   a {text-decoration:none;}
   body {min-width:100% !important; margin:0 auto !important; padding:0 !important;}
   img {line-height:100%; text-decoration:none; -ms-interpolation-mode:bicubic;}
   ...
   </style>
   ```

   >[!NOTE]
   >
   >Voeg vervolgens de stijl in een andere aangepaste stijltag toe.
   >
   >Wijzig de CSS die is gegenereerd door de e-mailontwerper niet:
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`


1. Ga terug naar de mobiele weergave om te controleren of uw inhoud correct wordt weergegeven en sla uw wijzigingen op.

## Hoofdletters gebruiken

Laten we proberen deze e-mail die in de verouderde editor is gemaakt, om te zetten in een **[!UICONTROL Email Designer]** sjabloon.

## Het gedeelte van uw e-mail identificeren

We kunnen elf secties in deze e-mail identificeren.

![](assets/html-dce-view-mail.png)

Als u wilt weten welk element het gedeelte van de HTML is, kunt u het selecteren.

![](assets/breadcrumbs.png)

Klik op **[!UICONTROL Show source]** om de HTML-versie van de e-mail weer te geven.

### De e-mailsjabloon en de structuur ervan maken

1. Sleep en zet de lay-out van onze e-mail **[!UICONTROL Structure components]** in beeld.

1. Herhaal dit zo vaak als nodig is. We moeten elf structuurcomponenten maken.

   ![](assets/structure-components-migration.png)

### HTML-inhoudscomponenten invoegen

1. Voeg een **[!UICONTROL HTML component]** insteekmodule in **[!UICONTROL Structure component]** .

   ![](assets/html-components.png)

1. Klik voor elke sectie op **[!UICONTROL Show source code]** .

   ![](assets/show-source-code.png)

1. Voeg de HTML-sectie in.

1. Klik op **[!UICONTROL Save]**.

U kunt nu de weergave van uw e-mail controleren.

![](assets/migrated-email-result.png)

### Stijlen beheren voor mobiele weergave

1. Voeg CSS-elementen in om ervoor te zorgen dat uw e-mail geschikt is voor de mobiele weergave.

1. Schakel over naar broncode en kopieer en plak de stijlsectie in een nieuwe stijlsectie.

Raadpleeg [De stijl van uw e-mail](#manage-the-style-of-your-email)beheren voor meer informatie hierover.

Uw verouderde e-mail is nu beschikbaar in de e-mailontwerper.