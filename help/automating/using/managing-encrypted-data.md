---
title: Versleutelde data gegevens beheren
description: Leer hoe u gecodeerde gegevens beheert.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows, Encryption
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 1df1552a-6578-47eb-ba14-fb91cd2a3999
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 3%

---

# Versleutelde data gegevens beheren {#managing-encrypted-data}

## Voorbereidende verwerkingsfasen {#about-preprocessing-stages}

In sommige gevallen moeten de gegevens die u wilt importeren, mogelijk worden gecodeerd, bijvoorbeeld als deze PII-gegevens bevatten.

Om uitgaande gegevens te kunnen coderen of inkomende gegevens te decrypteren, moet u sleutels beheren GPG gebruikend het [&#x200B; Controlebord &#x200B;](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html?lang=nl).

>[!NOTE]
>
>Het Configuratiescherm is beschikbaar voor alle klanten die op AWS worden gehost (met uitzondering van klanten die hun marketinginstanties op locatie hosten).

Als u niet in aanmerking komt om het Configuratiescherm te gebruiken, moet u contact opnemen met de klantenservice van Adobe, zodat deze uw exemplaar de benodigde opdrachten voor versleuteling/ontsleuteling kunnen geven. Hiertoe dient u een verzoek in met de volgende gegevens:

* Het **etiket** dat in de interface van de Campagne zal tonen om het bevel te gebruiken. Bijvoorbeeld &quot;Bestand versleutelen&quot;.
* Het **bevel** om op uw instantie te installeren.

Nadat de aanvraag is verwerkt, zijn de opdrachten voor codering/decodering beschikbaar in het veld **[!UICONTROL Pre-processing stage]** uit de activiteiten **[!UICONTROL Load file]** en **[!UICONTROL Extract file]** . U kunt deze gebruiken om de bestanden te decoderen of te coderen die u wilt importeren of exporteren.

![](assets/preprocessing-encryption.png)

**Verwante onderwerpen:**

* [Bestand laden](../../automating/using/load-file.md)
* [Bestand extraheren](../../automating/using/extract-file.md)

## Hoofdlettergebruik: gegevens importeren die zijn versleuteld met een toets die is gegenereerd door het Configuratiescherm {#use-case-gpg-decrypt}

In dit geval kunt u een workflow maken om gegevens die in een extern systeem zijn versleuteld, te importeren met een sleutel die in het Configuratiescherm is gegenereerd.

![](assets/do-not-localize/how-to-video.png) [Ontdek deze functie in video](#video)

De volgende stappen voor dit gebruik zijn nodig:

1. Gebruik het Configuratiescherm om een sleutelpaar (openbaar/privé) te genereren. De gedetailleerde stappen zijn beschikbaar in [&#x200B; documentatie van het Controlebord &#x200B;](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html#decrypting-data).

   * De openbare sleutel zal met het externe systeem worden gedeeld, dat het zal gebruiken om de gegevens te coderen om naar Campagne te verzenden.
   * De persoonlijke sleutel wordt door Campagne gebruikt om de inkomende gecodeerde gegevens te decoderen.

   ![](assets/gpg_generate.png)

1. In het externe systeem gebruikt u de openbare sleutel die u van het Configuratiescherm hebt gedownload om de gegevens te coderen die u naar Campaign Standard wilt importeren.

1. In Campaign Standard maakt u een workflow om de gecodeerde gegevens te importeren en te decoderen met de persoonlijke sleutel die is geïnstalleerd via het Configuratiescherm. Hiervoor maakt u als volgt een workflow:

   ![](assets/gpg_workflow.png)

   * **[!UICONTROL Transfer file]** activity: hiermee wordt het bestand van een externe bron naar Campagne overgebracht. In dit voorbeeld willen we het bestand overbrengen van een SFTP-server.
   * **[!UICONTROL Load file]** activiteit: laadt de gegevens van het bestand in de database en decodeert deze met de persoonlijke sleutel die is gegenereerd in het Configuratiescherm.

1. Open de **[!UICONTROL Transfer file]** -activiteit en configureer deze op basis van uw behoeften. De globale concepten op hoe te om de activiteit te vormen zijn beschikbaar in [&#x200B; deze sectie &#x200B;](../../automating/using/load-file.md).

   Geef op het tabblad **[!UICONTROL Protocol]** details op over de sftp-server en het gecodeerde gpg-bestand dat u wilt overbrengen.

   ![](assets/gpg_transfer.png)

1. Open de **[!UICONTROL Load file]** activiteit, dan vorm het op uw behoeften. De globale concepten op hoe te om de activiteit te vormen zijn beschikbaar in [&#x200B; deze sectie &#x200B;](../../automating/using/load-file.md).

   Voeg een voorbewerkingsstadium aan de activiteit toe, om de inkomende gegevens te decrypteren. Selecteer hiertoe de optie **[!UICONTROL Decryption GPG]** in de lijst.

   >[!NOTE]
   >
   >U hoeft niet de persoonlijke sleutel op te geven die moet worden gebruikt om de gegevens te decoderen. De persoonlijke sleutel wordt opgeslagen in het Configuratiescherm, dat automatisch de sleutel detecteert die moet worden gebruikt om het bestand te decoderen.

   ![](assets/gpg_load.png)

1. Klik op **[!UICONTROL OK]** om de activiteitenconfiguratie te bevestigen.

1. U kunt de workflow nu uitvoeren.

## Hoofdlettergebruik: gegevens coderen en exporteren met een sleutel die is geïnstalleerd in het Configuratiescherm {#use-case-gpg-encrypt}

In dit geval, bouwt een werkschema om gegevens te coderen en uit te voeren gebruikend een sleutel die op Controlebord wordt geïnstalleerd.

![](assets/do-not-localize/how-to-video.png) [Ontdek deze functie in video](#video)

De volgende stappen voor dit gebruik zijn nodig:

1. Genereer een sleutelpaar van GPG (openbaar/privé) gebruikend een nut van GPG, dan installeer de openbare sleutel op Controlebord. De gedetailleerde stappen zijn beschikbaar in [&#x200B; documentatie van het Controlebord &#x200B;](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html#encrypting-data).

   ![](assets/gpg_install.png)

1. In Campaign Standard maakt u een workflow om de gegevens te exporteren en te coderen met de persoonlijke sleutel die via het Configuratiescherm is geïnstalleerd. Hiervoor maakt u als volgt een workflow:

   ![](assets/gpg-workflow-export.png)

   * **[!UICONTROL Query]** activity: In dit voorbeeld willen we een query uitvoeren om de gegevens van de database die we willen exporteren als doel in te stellen.
   * **[!UICONTROL Extract file]** activiteit: codeert en extraheert de gegevens naar een bestand.
   * **[!UICONTROL Transfer file]** activiteit: hiermee wordt het bestand met de gecodeerde gegevens overgebracht naar een SFTP-server.

1. Configureer de **[!UICONTROL Query]** -activiteit om de gewenste gegevens uit de database als doel in te stellen. Raadpleeg [deze sectie](../../automating/using/query.md) voor meer informatie.

1. Open de **[!UICONTROL Extract file]** -activiteit en configureer deze op basis van uw behoeften (uitvoerbestand, kolommen, indeling, enz.). De globale concepten op hoe te om de activiteit te vormen zijn beschikbaar in [&#x200B; deze sectie &#x200B;](../../automating/using/extract-file.md).

   Voeg een voorbewerkingsstadium aan de activiteit toe, om de gegevens te coderen om te halen. Selecteer hiertoe de GPG-sleutel voor versleuteling die u wilt gebruiken om de gegevens te versleutelen.

   ![](assets/gpg-extract-stage.png)

   >[!NOTE]
   >
   >De waarde tussen haakjes is de **commentaar** dat u wanneer het produceren van het zeer belangrijke paar gebruikend uw GPG encryptiegereedschap bepaalde. Zorg ervoor dat u de juiste overeenkomende sleutel selecteert, anders kan de ontvanger het bestand niet decoderen.

1. Open de **[!UICONTROL Transfer file]** -activiteit en geef vervolgens de SFTP-server op waarnaar u het bestand wilt verzenden. De globale concepten op hoe te om de activiteit te vormen zijn beschikbaar in [&#x200B; deze sectie &#x200B;](../../automating/using/transfer-file.md).

   ![](assets/gpg-transfer-encrypt.png)

1. U kunt de workflow nu uitvoeren. Zodra het wordt uitgevoerd, zal het gegevensdoel door de vraag naar de server SFTP in een gecodeerd.gpg- dossier worden uitgevoerd.

## Zelfstudievideo&#39;s {#video}

In deze video wordt getoond hoe u een GPG-sleutel kunt gebruiken voor het decoderen van gegevens.

>[!VIDEO](https://video.tv.adobe.com/v/35753?quality=12)

In deze video ziet u hoe u een GPG-sleutel gebruikt om gegevens te coderen.

>[!VIDEO](https://video.tv.adobe.com/v/36380?quality=12)

De extra hoe te video&#39;s van Campaign Standard zijn beschikbaar [&#x200B; hier &#x200B;](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=nl).
