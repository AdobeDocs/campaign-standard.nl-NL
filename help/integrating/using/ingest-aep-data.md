---
title: Adobe Experience Platform-doelgroepen opnemen in Campaign
description: Leer hoe je Adobe Experience Platform-publiek inneemt in Campaign Standard.
audience: integrating
content-type: reference
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 5c266c44-535b-4954-862d-74c83a6f6406
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 6%

---

# Adobe Experience Platform-doelgroepen opnemen in Campaign {#destinations}

Om het publiek van Adobe Experience Platform in Campagne op te nemen en hen in uw werkschema&#39;s te gebruiken, moet u eerst Adobe Campaign als Adobe Experience Platform **Bestemming** verbinden en het met het segment vormen om uit te voeren.

Zodra de Bestemming is gevormd, zullen de gegevens naar uw opslagplaats worden uitgevoerd, en u zult een specifieke werkschema in Campaign Standard moeten bouwen om het in te voeren.

## Adobe Campaign verbinden als doel

In het Adobe Experience-platform configureert u een verbinding met Adobe Campaign door een opslaglocatie voor de geëxporteerde segmenten te selecteren. Met deze stappen kunt u ook de segmenten selecteren die u wilt exporteren en aanvullende XDM-velden opgeven die u wilt opnemen.

Voor meer op dit, verwijs naar de [&#x200B; documentatie van Doelen &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email-marketing/adobe-campaign.html?lang=nl-NL).

Nadat de Bestemming is gevormd, leidt Adobe Experience Platform tot een lusje-afgebakend .txt of .csv- dossier in de opslagplaats die u verstrekte. Deze bewerking is gepland en wordt één keer per 24 uur uitgevoerd.

U kunt nu een Campaign Standard-workflow configureren om het segment in te voeren in Campagne.

## Een importworkflow maken in Campaign Standard

Als Campaign Standard eenmaal is geconfigureerd als een doel, moet u een specifieke workflow maken om het bestand te importeren dat door Adobe Experience Platform is geëxporteerd.

Hiervoor moet u een **[!UICONTROL Transfer file]** -activiteit toevoegen en configureren. Voor meer op hoe te om deze activiteit te vormen, verwijs naar [&#x200B; deze sectie &#x200B;](../../automating/using/transfer-file.md).

![](assets/rtcdp-transfer-file.png)

Vervolgens kunt u uw workflow naar wens samenstellen (werk de database bij met behulp van de segmentgegevens, verzend een levering tussen kanalen naar het segment, enz.)

In de onderstaande workflow wordt het bestand bijvoorbeeld dagelijks vanaf de opslaglocatie gedownload en vervolgens wordt de Campagne-database bijgewerkt met de segmentgegevens.

![](assets/rtcdp-workflow.png)

De voorbeelden van werkschema&#39;s van het gegevensbeheer zijn beschikbaar in de [&#x200B; werkschema&#39;s gebruiken gevallen &#x200B;](../../automating/using/about-workflow-use-cases.md#management) sectie.

Verwante onderwerpen:

* [Gegevensbeheeractiviteiten](../../automating/using/about-data-management-activities.md)
* [Informatie over gegevens importeren en exporteren](../../automating/using/about-data-import-and-export.md)
