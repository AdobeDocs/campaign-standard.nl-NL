---
title: Versleutelde data gegevens beheren
description: Leer hoe u gecodeerde gegevens beheert.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Experienced
exl-id: 1df1552a-6578-47eb-ba14-fb91cd2a3999
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 4%

---

# Versleutelde data gegevens beheren {#managing-encrypted-data}

## Voorbereidende verwerkingsfasen {#about-preprocessing-stages}

In sommige gevallen moeten de gegevens die u wilt importeren, mogelijk worden gecodeerd, bijvoorbeeld als deze PII-gegevens bevatten.

Als u uitgaande gegevens wilt coderen of binnenkomende gegevens wilt decoderen, moet u de GPG-sleutels beheren met de [Deelvenster Beheer](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html?lang=nl).

>[!NOTE]
>
>Het Configuratiescherm is beschikbaar voor alle klanten die op AWS worden gehost (met uitzondering van klanten die hun marketinginstanties op locatie hosten).

Als u niet verkiesbaar bent om Controlebord te gebruiken, moet u de Zorg van de Klant van de Adobe contacteren zodat zij uw instantie van de noodzakelijke encryptie/decryptiebevelen voorzien. Hiertoe dient u een verzoek in met de volgende gegevens:

* De **label** die in de interface van de Campagne zal tonen om het bevel te gebruiken. Bijvoorbeeld &quot;Bestand versleutelen&quot;.
* De **command** om op uw exemplaar te installeren.

Zodra het verzoek wordt verwerkt, zullen de encryptie/decryptopdrachten in beschikbaar zijn **[!UICONTROL Pre-processing stage]** veld van de **[!UICONTROL Load file]** en **[!UICONTROL Extract file]** activiteiten. U kunt deze gebruiken om de bestanden te decoderen of te coderen die u wilt importeren of exporteren.

![](assets/preprocessing-encryption.png)

**Verwante onderwerpen:**

* [Bestand laden](../../automating/using/load-file.md)
* [Bestand extraheren](../../automating/using/extract-file.md)

## Hoofdlettergebruik: gegevens importeren die zijn versleuteld met een toets die is gegenereerd door het Configuratiescherm {#use-case-gpg-decrypt}

In dit geval kunt u een workflow maken om gegevens die in een extern systeem zijn versleuteld, te importeren met een sleutel die in het Configuratiescherm is gegenereerd.

![](assets/do-not-localize/how-to-video.png) [Ontdek deze functie in video](#video)

De volgende stappen voor dit gebruik zijn nodig:

1. Gebruik het Configuratiescherm om een sleutelpaar (openbaar/privé) te genereren. Gedetailleerde stappen zijn beschikbaar in [Documentatie van het regelpaneel](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html#decrypting-data).

   * De openbare sleutel zal met het externe systeem worden gedeeld, dat het zal gebruiken om de gegevens te coderen om naar Campagne te verzenden.
   * De persoonlijke sleutel wordt door Campagne gebruikt om de inkomende gecodeerde gegevens te decoderen.

   ![](assets/gpg_generate.png)

1. In het externe systeem gebruikt u de openbare sleutel die u van het Configuratiescherm hebt gedownload om de gegevens te coderen die u naar het Campaign Standard wilt importeren.

1. In Campaign Standard, bouwt een werkschema om de gecodeerde gegevens in te voeren en het te decrypteren gebruikend de privé sleutel die via het Controlebord is geïnstalleerd. Hiervoor maakt u als volgt een workflow:

   ![](assets/gpg_workflow.png)

   * **[!UICONTROL Transfer file]** activiteit: hiermee wordt het bestand van een externe bron naar Campagne overgedragen. In dit voorbeeld willen we het bestand overbrengen van een SFTP-server.
   * **[!UICONTROL Load file]** activiteit: laadt de gegevens van het dossier in het gegevensbestand en decrypteert het gebruikend de privé sleutel die in het Controlebord wordt geproduceerd.

1. Open de **[!UICONTROL Transfer file]** activiteit vormt dan het op uw behoeften. Globale concepten over hoe te om de activiteit te vormen zijn beschikbaar in [deze sectie](../../automating/using/load-file.md).

   In de **[!UICONTROL Protocol]** , geeft u gegevens op over de sftp-server en het gecodeerde gpg-bestand dat u wilt overbrengen.

   ![](assets/gpg_transfer.png)

1. Open de **[!UICONTROL Load file]** activiteit, dan vorm het op uw behoeften. Globale concepten over hoe te om de activiteit te vormen zijn beschikbaar in [deze sectie](../../automating/using/load-file.md).

   Voeg een voorbewerkingsstadium aan de activiteit toe, om de inkomende gegevens te decrypteren. Selecteer de optie **[!UICONTROL Decryption GPG]** in de lijst.

   >[!NOTE]
   >
   >U hoeft niet de persoonlijke sleutel op te geven die moet worden gebruikt om de gegevens te decoderen. De persoonlijke sleutel wordt opgeslagen in het Configuratiescherm, dat automatisch de sleutel detecteert die moet worden gebruikt om het bestand te decoderen.

   ![](assets/gpg_load.png)

1. Klikken **[!UICONTROL OK]** om de activiteitenconfiguratie te bevestigen.

1. U kunt de workflow nu uitvoeren.

## Hoofdlettergebruik: gegevens coderen en exporteren met een sleutel die is geïnstalleerd in het Configuratiescherm {#use-case-gpg-encrypt}

In dit geval, bouwt een werkschema om gegevens te coderen en uit te voeren gebruikend een sleutel die op Controlebord wordt geïnstalleerd.

![](assets/do-not-localize/how-to-video.png) [Ontdek deze functie in video](#video)

De volgende stappen voor dit gebruik zijn nodig:

1. Genereer een sleutelpaar van GPG (openbaar/privé) gebruikend een nut van GPG, dan installeer de openbare sleutel op Controlebord. Gedetailleerde stappen zijn beschikbaar in [Documentatie van het regelpaneel](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html#encrypting-data).

   ![](assets/gpg_install.png)

1. In Campaign Standard, bouwt een werkschema om de gegevens uit te voeren en het te coderen gebruikend de privé sleutel die via het Controlebord is geïnstalleerd. Hiervoor maakt u als volgt een workflow:

   ![](assets/gpg-workflow-export.png)

   * **[!UICONTROL Query]** activiteit: In dit voorbeeld, willen wij een vraag uitvoeren om de gegevens van het gegevensbestand te richten dat wij willen uitvoeren.
   * **[!UICONTROL Extract file]** activiteit: versleutelt de gegevens en extraheert deze naar een bestand.
   * **[!UICONTROL Transfer file]** activiteit: hiermee wordt het bestand met de gecodeerde gegevens overgebracht naar een SFTP-server.

1. Vorm **[!UICONTROL Query]** activiteit om de gewenste gegevens van het gegevensbestand te richten. Raadpleeg [deze sectie](../../automating/using/query.md) voor meer informatie.

1. Open de **[!UICONTROL Extract file]** Deze activiteit configureert deze vervolgens naar wens (uitvoerbestand, kolommen, indeling, enz.). Globale concepten over hoe te om de activiteit te vormen zijn beschikbaar in [deze sectie](../../automating/using/extract-file.md).

   Voeg een voorbewerkingsstadium aan de activiteit toe, om de gegevens te coderen om te halen. Selecteer hiertoe de GPG-sleutel voor versleuteling die u wilt gebruiken om de gegevens te versleutelen.

   ![](assets/gpg-extract-stage.png)

   >[!NOTE]
   >
   >De waarde tussen haakjes is de **opmerking** die u hebt gedefinieerd toen u het sleutelpaar genereerde met uw GPG-coderingsgereedschap. Zorg ervoor dat u de juiste overeenkomende sleutel selecteert, anders kan de ontvanger het bestand niet decoderen.

1. Open de **[!UICONTROL Transfer file]** en geeft u vervolgens de SFTP-server op waarnaar u het bestand wilt verzenden. Globale concepten over hoe te om de activiteit te vormen zijn beschikbaar in [deze sectie](../../automating/using/transfer-file.md).

   ![](assets/gpg-transfer-encrypt.png)

1. U kunt de workflow nu uitvoeren. Zodra het wordt uitgevoerd, zal het gegevensdoel door de vraag naar de server SFTP in een gecodeerd.gpg- dossier worden uitgevoerd.

## Tutorialvideo’s {#video}

In deze video wordt getoond hoe u een GPG-sleutel kunt gebruiken voor het decoderen van gegevens.

>[!VIDEO](https://video.tv.adobe.com/v/35753?quality=12)

In deze video ziet u hoe u een GPG-sleutel gebruikt om gegevens te coderen.

>[!VIDEO](https://video.tv.adobe.com/v/36380?quality=12)

Er zijn aanvullende Campaign Standard-to-video&#39;s beschikbaar [hier](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=nl).
