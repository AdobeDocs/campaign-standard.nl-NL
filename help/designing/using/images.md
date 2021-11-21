---
title: Werken met afbeeldingen
description: Ontdek hoe u afbeeldingen in e-mailberichten kunt beheren met de e-mailontwerper.
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

U kunt afbeeldingen invoegen in uw e-mails en bestemmingspagina&#39;s.

Afhankelijk van uw configuratie zijn de volgende typen afbeeldingen beschikbaar:

* Lokale afbeeldingen
* Afbeeldingen gedeeld vanuit Adobe Experience Cloud - raadpleeg [Werken met de Campagne en de Dienst van de Kern van Activa](../../integrating/using/working-with-campaign-and-assets-core-service.md) / Activa op aanvraag
* Dynamische afbeeldingen uit Adobe Target - raadpleeg [Werken met campagne en doel](../../integrating/using/about-campaign-target-integration.md)

>[!CAUTION]
>
>If you choose to add an image directly by editing the HTML version of the email, you must not call up **external files in a &lt;script> tag** of the HTML page. Deze bestanden worden niet geïmporteerd op de Adobe Campaign-server.

### Afbeeldingen in een e-mail invoegen {#inserting-images-in-an-email}

1. Voeg een structuurcomponent toe. Ga voor meer informatie naar [De e-mailstructuur bewerken](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Voeg binnen deze structuurcomponent een **[!UICONTROL Image]** inhoudscomponent.

   ![](assets/des_insert_images_1.png)

1. Klik op **[!UICONTROL Browse]**. Sleep een afbeelding en zet deze neer of klik om een bestand op uw computer te selecteren.

   ![](assets/des_insert_images_2.png)

1. Selecteer de inhoudscomponent die u zojuist hebt toegevoegd.
1. Controleer de afbeeldingseigenschappen en pas deze indien nodig aan.

   ![](assets/des_insert_images_3.png)

## Afbeeldingseigenschappen instellen{#setting-up-image-properties}

Wanneer u een blok selecteert dat een afbeelding bevat, worden de volgende eigenschappen in het palet aangeboden:

* **Personalisatie inschakelen** kunt u de afbeeldingsbron aanpassen. Zie [Een afbeeldingsbron aanpassen](../../designing/using/personalization.md#personalizing-an-image-source).
* **Afbeeldingstitel** Hiermee kunt u een titel voor de afbeelding definiëren.
* **Alt-tekst** (e-mail) of **Bijschrift** (landingspagina) kunt u het bijschrift definiëren dat is gekoppeld aan de afbeelding (komt overeen met de **alt** HTML, kenmerk).
* Bij het bewerken van een e-mail: **Stijl** Hiermee kunt u de afbeeldingsgrootte, achtergrond en rand opgeven.
* Bij het bewerken van een openingspagina **Dimension** Hiermee kunt u de afbeeldingsgrootte opgeven in pixels.

Met de editor kunt u werken **alle afbeeldingstypen** waarvan de indelingen compatibel zijn met browsers. Om compatibel te zijn met de editor, **Animaties van het type &quot;Flash&quot;** moeten als volgt op een pagina HTML worden ingevoegd:

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
