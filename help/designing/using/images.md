---
title: Werken met afbeeldingen
description: Ontdek hoe u afbeeldingen in e-mails kunt beheren met de Email Designer.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: b58a378d-18da-4c0f-b4e7-5d0a02aab4c2
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 3%

---

# Werken met afbeeldingen {#images}

## Afbeeldingen invoegen{#inserting-images}

U kunt afbeeldingen invoegen in uw e-mails en landingspagina’s.

Afhankelijk van uw configuratie zijn de volgende typen afbeeldingen beschikbaar:

* Lokale afbeeldingen
* Afbeeldingen die worden gedeeld vanuit Adobe Experience Cloud - zie [ Werken met Campaign en de Assets-kernservice ](../../integrating/using/working-with-campaign-and-assets-core-service.md) / Assets On Demand
* Dynamische afbeeldingen van Adobe Target - zie [Werken met Campaign en Target](../../integrating/using/about-campaign-target-integration.md)

>[!CAUTION]
>
>Als u ervoor kiest om een afbeelding rechtstreeks toe te voegen door de HTML-versie van de e-mail te bewerken, mag u **externe bestanden niet aanroepen in een &lt;script> tag** van de HTML-pagina. Deze bestanden worden niet geïmporteerd naar de Adobe Campaign-server.

### Afbeeldingen invoegen in een e-mail {#inserting-images-in-an-email}

1. Voeg een structuurcomponent toe. Ga voor meer informatie naar [De e-mailstructuur bewerken](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Voeg binnen deze structuurcomponent een component **[!UICONTROL Image]** toe aan de content.

   ![](assets/des_insert_images_1.png)

1. Klik op **[!UICONTROL Browse]**. Sleep een afbeelding en zet deze neer of klik om een bestand op uw computer te selecteren.

   ![](assets/des_insert_images_2.png)

1. Selecteer de contentcomponent die u zojuist hebt toegevoegd.
1. Controleer de afbeeldingseigenschappen en pas deze indien nodig aan.

   ![](assets/des_insert_images_3.png)

## Eigenschappen van afbeeldingen instellen{#setting-up-image-properties}

Wanneer u een blok selecteert dat een afbeelding bevat, worden de volgende eigenschappen aangeboden in het palet:

* Met **Personalisatie inschakelen** kunt u de afbeeldingsbron aanpassen. Zie [ Een afbeeldingsbron personaliseren](../../designing/using/personalization.md#personalizing-an-image-source).
* Met **Afbeeldingstitel** kunt u een titel voor de afbeelding definiëren.
* Met **Alt text** (e-mail) of **Caption** (landingspagina) kunt u het bijschrift definiëren dat aan de afbeelding is gekoppeld (komt overeen met het kenmerk **alt** HTML).
* Wanneer u een e-mailbericht bewerkt, kunt u met **Style** de afbeeldingsgrootte, achtergrond en rand opgeven.
* Wanneer u een landingspagina bewerkt, kunt u met **Dimension** de afbeeldingsgrootte in pixels opgeven.

Met de editor kunt u werken met **alle afbeeldingstypen** waarvan de indelingen compatibel zijn met browsers. Om compatibel te zijn met de editor, **Animaties van het type &quot;Flash&quot;** moeten als volgt op een pagina HTML worden ingevoegd:

```
<object type="application/x-shockwave-flash" data="http://www.mydomain.com/flash/your_animation.swf" width="200" height="400">
 <param name="movie" value="http://www.mydomain.com/flash/your_animation.swf" />
 <param name="quality" value="high" />
 <param name="play" value="true"/>
 <param name="loop" value="true"/> 
</object>
```

<!--
## Modifying images with the Adobe Creative SDK{#modifying-images-with-the-adobe-creative-sdk}

You can edit images and use a complete set of features powered by the Adobe Creative SDK to enhance your images directly in the content editor when editing emails or landing pages.

The image editor offers a powerful, full-featured image editing UI component that allows you to edit images and apply effects and frames, original high-quality stickers, beautiful overlays, fun features like tilt shift and color splash, pro-level adjustments and more.

To modify an image with the Adobe Creative SDK:

1. Select the image.
1. In the toolbar, click the Creative Cloud icon.

   ![](assets/des_creative_sdk_icon.png)

1. Select the tool you want to use through the icons on the top of the window to modify the image.

   ![](assets/email_designer_ccsdktoolbar.png)

1. Click **[!UICONTROL Save]** when modifications are done. The updated image is saved on Adobe Campaign server and ready to be used.

>[!NOTE]
>
>Tools offered in the image editor cannot be customized.
-->
