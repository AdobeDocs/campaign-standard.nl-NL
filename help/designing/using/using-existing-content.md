---
title: E-mails ontwerpen met bestaande inhoud
description: Ontdek hoe u e-mailberichten kunt ontwerpen met bestaande inhoud en e-mailinhoud in de e-mailontwerper.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 3bda4227-2a6e-4813-a288-93a4388a9787
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1277'
ht-degree: 3%

---

# Ontwerpen met bestaande inhoud {#designing-using-existing-content}

## Bestaande inhoud selecteren{#selecting-an-existing-content}

Adobe Campaign wordt geleverd met een set vooraf gedefinieerde inhoud waarmee u aan de slag kunt. U kunt een van deze opties gebruiken. Als de inhoud van het bericht dat u wilt verzenden, buiten Adobe Campaign wordt voorbereid, kunt u het vanuit uw computer of een URL importeren.

Wanneer u een e-mail- of landingspagina maakt, kunt u desgewenst bestaande inhoud uit een andere bron laden.

>[!NOTE]
>
>In de onderstaande afbeeldingen ziet u hoe u bestaande inhoud laadt met de [E-mailDesigner](../../designing/using/designing-content-in-adobe-campaign.md).

1. Open na het maken van de e-mail- of landingspagina de inhoud ervan.
1. Klik op het pictogram van de introductiepagina voor toegang tot de **[!UICONTROL Email Designer]** homepage.

   ![](assets/des_loading_1.png)

1. Selecteer de bron van de inhoud die u wilt laden:

   * [Inhoudssjablonen](../../designing/using/using-reusable-content.md#content-templates): klik op de knop **[!UICONTROL Templates]** tab.
   * [Inhoud helemaal opnieuw](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch), om vers te beginnen: klik op de knop **[!UICONTROL Create]** knop.
   * [Inhoud van uw computer als ZIP- of HTML-bestand](#importing-content-from-a-file): klik op de knop **[!UICONTROL Upload]** knop.
   * [Inhoud van een bestaande URL](#importing-content-from-a-url) (alleen voor e-mails): klik op de knop **[!UICONTROL Import from URL]** knop.

   ![](assets/des_loading_2.png)

1. Laad de inhoud. De geselecteerde inhoud vervangt de huidige inhoud.

   Nadat de inhoud is geïmporteerd, kan deze worden bewerkt en gepersonaliseerd.

   >[!NOTE]
   >
   >De [E-mailDesigner](../../designing/using/designing-content-in-adobe-campaign.md) gebruikt specifieke codering. Standaard HTML-inhoud die naar Campagne wordt geüpload, moet overeenkomen met de verwachte codering om volledig compatibel te zijn met en te kunnen worden bewerkt vanuit de e-mailontwerper. Als de inhoud niet overeenkomt, wordt de inhoud geüpload in [compatibiliteitsmodus](#compatibility-mode). Bestaande inhoud compatibel maken, raadpleegt u [deze sectie](#editing-existing-contents-with-the-email-designer).

**Verwante onderwerpen:**

* [Een e-mail maken](../../channels/using/creating-an-email.md)
* [Landingspagina&#39;s beheren](../../channels/using/getting-started-with-landing-pages.md)

## Bestaande inhoud bewerken met de e-mailontwerper{#editing-existing-contents-with-the-email-designer}

De mogelijkheden van de [E-mailDesigner](../../designing/using/designing-content-in-adobe-campaign.md), moet de geüploade HTML specifieke tags bevatten die ervoor zorgen dat deze voldoet aan de WYSIWYG-editor.

Als de HTML deze codering niet geheel of gedeeltelijk heeft, wordt de inhoud geladen in &#39; [compatibiliteitsmodus](#compatibility-mode)&quot;.

Als u een bestaande externe inhoud volledig bewerkbaar wilt maken in de e-mailontwerper, raadpleegt u de [Een e-mail ontwerpen met bestaande inhoud](../../designing/using/using-existing-content.md) sectie.

## Bestaande e-mailinhoud importeren {#importing}

### Inhoud uit een bestand importeren {#importing-content-from-a-file}

Klik op de introductiepagina E-mail Designer op de knop **[!UICONTROL Upload]** om een bestand van uw computer te uploaden, bevestig vervolgens.

Er zijn geen beperkingen op de ZIP-bestandsstructuur. Het verwijzen naar HTML-bestanden moet echter relatief zijn en de boomstructuur van de ZIP-map respecteren.

De volgende indelingen worden ondersteund voor importeren:

* Een HTML-bestand met een opgenomen stijlblad
* Een ZIP-map met het HTML-bestand, de stijlpagina (.CSS) en de afbeeldingen

>[!NOTE]
>
>Voor e-mailinhoud raden we u aan enkele HTML-bestanden te importeren met een opgenomen stijlblad.

#### Inhoud van een URL importeren {#importing-content-from-a-url}

Voordat u inhoud van een URL importeert, moet u controleren of aan de onderstaande vereisten wordt voldaan:

* De inhoud moet openbaar zijn via deze URL.
* Om beveiligingsredenen beginnen alleen URL&#39;s met **[!UICONTROL https]** zijn toegestaan.
* Zorg ervoor dat alle bronnen (afbeeldingen, CSS) zijn ingesteld in absolute koppelingen en in HTTPS. Anders wordt de spiegel na het verzenden van de e-mail weergegeven zonder de bijbehorende bronnen. Hier volgt een voorbeeld van een absolute koppelingsdefinitie:

  ```
  <a href="https://www.mywebsite.com/images/myimage.png">
  ```

>[!NOTE]
>
>Inhoud van een URL laden is alleen beschikbaar voor het e-mailkanaal.

Ga als volgt te werk om bestaande inhoud van een URL op te halen:

1. Selecteer op de introductiepagina E-mail Designer de optie **[!UICONTROL Import from URL]** knop.

   ![](assets/email_designer_importfromurl.png)

1. Definieer de URL waarvan de inhoud wordt opgehaald.
1. Klik op **[!UICONTROL Confirm]**.

Ontdek deze functie in video.

>[!VIDEO](https://video.tv.adobe.com/v/25926?quality=12)

Er zijn aanvullende Campaign Standard-to-video&#39;s beschikbaar [hier](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=nl).

### Inhoud automatisch ophalen van een URL tijdens het voorbereiden {#retrieving-content-from-a-url-automatically-at-preparation-time}

Wanneer u inhoud importeert vanaf een URL tijdens de voorbereiding van berichten, kunt u telkens wanneer de e-mail wordt voorbereid, de meest recente HTML-inhoud ophalen. Op die manier is de inhoud van terugkerende e-mails altijd up-to-date op het moment van verzending. Met deze functie kunt u ook een bericht maken dat op een bepaalde datum is gepland, zelfs als de inhoud nog niet gereed is.

Volg onderstaande stappen om inhoud op te halen tijdens het voorbereiden:

1. Selecteer de **[!UICONTROL Content imported during preparation]** -optie.

   ![](assets/email_designer_importfromurl2.png)

1. De inhoud URL wordt in de editor weergegeven als alleen-lezen.

   >[!CAUTION]
   >
   >Bij deze stap moet geen rekening worden gehouden met de weergave HTML in de inhoudseditor. Het zal in de voorbereidingsfase worden opgehaald.

1. Als u een voorvertoning wilt weergeven van de URL-inhoud die is opgehaald, opent u het bericht nadat u het hebt gemaakt en klikt u op de knop **[!UICONTROL Preview]** knop.

Het is mogelijk om de externe URL te personaliseren waarvan de inhoud wordt opgehaald. Hiervoor voert u de volgende stappen uit:

1. Klik op het e-maillabel boven op het scherm om naar de e-mailontwerper te gaan **[!UICONTROL Properties]** tab.
1. Zoek de **[!UICONTROL Remote URL]** veld.

   ![](assets/email_designer_importfromurl4.png)

1. Voeg het gewenste verpersoonlijkingsveld, inhoudsblok of dynamische tekst in.

   De **[!UICONTROL Current date - YYYYMMDD]** Met inhoudsblok kunt u bijvoorbeeld de datum van de dag invoegen.

   >[!NOTE]
   >
   >De beschikbare verpersoonlijkingsvelden zijn gekoppeld aan **Aflevering** alleen kenmerken (aanmaakdatum, status, campagnelabel...).

Als het downloaden van inhoud bij de eerste poging mislukt, kan deze twee keer opnieuw worden geprobeerd:

1. De tweede poging start 50 ms na de eerste poging.
1. De derde poging start 100 ms na de tweede poging.

Deze pogingen zijn in deze gevallen nuttig:

* Een kortstondige de dienstmislukking op een verre server
* Een serverfout op een cluster, waarbij de pogingen waarschijnlijk meer zullen slagen dankzij taakverdeling op een werkende server

### Compatibiliteitsmodus {#compatibility-mode}

Wanneer u inhoud uploadt, moet deze specifieke codering bevatten om volledig compatibel te zijn met en te kunnen worden bewerkt met de WYSIWYG-editor van de e-mailontwerper.

Als de geüploade HTML geheel of gedeeltelijk niet voldoet aan de verwachte codering, wordt de inhoud vervolgens geladen in de &#39;compatibiliteitsmodus&#39;, die de weergavemogelijkheden via de gebruikersinterface beperkt.

Wanneer inhoud wordt geladen in de compatibiliteitsmodus, kunt u nog steeds de volgende wijzigingen uitvoeren via de interface (niet-beschikbare acties worden verborgen):

* De tekst wijzigen of een afbeelding wijzigen
* Koppelingen en aanpassingsvelden invoegen
* Bewerk enkele opmaakopties voor het geselecteerde HTML-blok
* Voorwaardelijke inhoud definiëren

![](assets/email_designer_compatibility.png)

Andere wijzigingen, zoals het toevoegen van nieuwe secties aan uw e-mail of geavanceerde opmaak, moeten rechtstreeks in de broncode van de e-mail worden uitgevoerd via de modus HTML.

Ga voor meer informatie over het converteren van een bestaande e-mail naar een e-mail die compatibel is met E-mail die compatibel is met E-mail naar [deze sectie](../../designing/using/using-existing-content.md).

**Verwant onderwerp**:

* [Een e-mail maken](../../channels/using/creating-an-email.md)
* [Introductievideo over e-mailontwerper](../../designing/using/designing-content-in-adobe-campaign.md#video)
* [Een geheel nieuwe e-mailinhoud ontwerpen](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## HTML-inhoud omzetten {#converting-an-html-content}

Als u een framework van modulaire sjablonen en fragmenten wilt maken die u kunt combineren voor hergebruik in meerdere e-mails, kunt u uw e-mailsjabloon het beste omzetten in een sjabloon voor e-mailontwerpen.

Met deze kwestie kunt u HTML-e-mailberichten snel converteren naar onderdelen van E-mailontwerper.

>[!CAUTION]
>
>Deze sectie is bedoeld voor geavanceerde gebruikers die vertrouwd zijn met HTML-code.

>[!NOTE]
>
>Net als in de compatibiliteitsmodus kan een HTML-component met beperkte opties worden bewerkt: u kunt alleen op plaats edities uitvoeren.

Buiten de e-mailontwerper, zorg ervoor de originele HTML in herbruikbare secties wordt verdeeld.

Als dit niet het geval is, snijd de verschillende blokken van uw HTML uit. Bijvoorbeeld:

```
<!-- 3 COLUMN w/CTA (SCALED) -->
<table width="100%" align="center" cellspacing="0" cellpadding="0" border="0" role="presentation" style="max-width:680px;">
<tbody>
<tr>
<td class="padh10" align="center" valign="top" style="padding:0 5px 20px 5px;">
<table width="100%" cellspacing="0" cellpadding="0" border="0" role="presentation">
<tbody>
<tr>
...
</tr>
</tbody>
</table>
</td>
</tr>
</tbody>
</table>
<!-- //3 COLUMN w/CTA (SCALED) -->
```

Herhaal de volgende procedure voor elk gedeelte van uw bestaande e-mail als u al uw blokken hebt geïdentificeerd in de e-mailontwerper:

1. Open de E-mailontwerper om een lege e-mailinhoud te maken.
1. Stel de kenmerken voor het tekstniveau in: achtergrondkleuren, breedte, enzovoort. Ga voor meer informatie naar [E-mailstijlen bewerken](../../designing/using/styles.md).
1. Voeg een structuurcomponent toe. Ga voor meer informatie naar [De e-mailstructuur bewerken](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Voeg een HTML-component toe. Ga voor meer informatie naar [Fragmenten en componenten toevoegen](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Kopieer en plak de HTML in die component.
1. Schakel over naar de mobiele weergave. Zie [deze sectie](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)voor meer informatie.

   De responsieve weergave is verbroken, omdat uw CSS ontbreekt.

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
