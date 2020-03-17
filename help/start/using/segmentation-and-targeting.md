---
title: Segmentering en doelgerichtheid
description: '"Meer informatie over profielen, doelframes en publiek maken in Campagne: publiek te maken, contactpersonen voor importeren te delen met oplossingen voor Experience Cloud en moeheid met marketing te voorkomen."'
page-status-flag: never-activated
uuid: 71f53808-0309-49f6-a4ee-3446eac9758a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: about-adobe-campaign
discoiquuid: d8c8a318-9433-4aec-b378-fd0beb50e9fb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 13430243e8f2840ca85e557798168f6380a7b0fa

---


# Segmentering en doelgerichtheid{#segmentation-and-targeting}

## Profielen {#profiles}

Gebruik het flexibele gegevensmodel van de Campagne van Adobe om uw gegevens van het klantenprofiel te verrijken en nieuwe attributen of lijsten toe te voegen. Dan, gebruik deze klantenprofielen voor nauwkeurigere segmentatie, verpersoonlijking, en rapportering.

Adobe Campagneprofielen vertegenwoordigen alle contactpersonen die in de database zijn opgeslagen. Elk profiel komt overeen met één item in de database dat de nodige informatie bevat om dat profiel als doel, gekwalificeerd en afzonderlijk te kunnen traceren. Dit betekent dat een profiel: een cliënt, een vooruitzicht, een individu aan een nieuwsbrief, een ontvanger, een gebruiker, of een andere denominatie die afhankelijk van de organisatie wordt ingetekend.

De eigenschap van de profielen van de klant integreert al uw klantengegevens in één plaats:

![](assets/mkt_hist_view.png)

Adobe Campaign stelt verschillende mechanismen voor het aanschaffen van profielen voor: gegevens online verzamelen via [bestemmingspagina](../../channels/using/getting-started-with-landing-pages.md)&#39;s, handmatige of [geautomatiseerde importmechanismen](../../automating/using/about-data-import-and-export.md), [directe invoer](../../audiences/using/creating-profiles.md) in de Adobe Campagne-interface, bulkcreatie via [campagne-API&#39;s](../../api/using/about-campaign-standard-apis.md).

**Verwante onderwerpen:**

* In de sectie [Profielen](../../audiences/using/about-profiles.md) vindt u meer informatie over de verschillende typen profielen.
* Open het aantal **actieve profielen** in uw organisatie in [deze sectie](../../audiences/using/active-profiles.md).
* Leer hoe u uw gegevens aanpast, complexe taken voor gegevensbeheer, zoals berekeningen, aggregaten, deduplicaten en samenvoegingen, afhandelt met [workflowgerichte mogelijkheden](../../automating/using/about-targeting-activities.md)

## Audiences {#audiences}

Om u in staat te stellen relevante en efficiënte berichten te leveren en uw klanten effectief te betrekken, integreert de Campagne van Adobe geavanceerde analyse en gerichte functionaliteit. Dankzij de workflows en de query-editor kunt u een publiek maken dat de verschillende campagnes als doelgroep hebben, afhankelijk van de informatie die u over de campagnes hebt, hun activiteiten, hun taal, voorkeuren of hun marketinggeschiedenis. Zo kunt u bijvoorbeeld geabonneerde profielen filteren of doelsoorten maken op een onbeperkt aantal criteria.

De doelgroepen worden weergegeven [op deze pagina](../../audiences/using/about-audiences.md) en nader beschreven in de sectie [Soorten publiek](../../audiences/using/creating-audiences.md) .

**Verwante onderwerpen:**

* Leer hoe u een meertalig publiek in meerdere regio&#39;s kunt bereiken door [meertalige pushmeldingen](../../channels/using/creating-a-multilingual-push-notification.md) of [meertalige e-mails te verzenden](../../channels/using/creating-a-multilingual-email.md)
* Leer hoe u query [&#39;s kunt](../../audiences/using/creating-audiences.md#creating-query-audiences) maken om een publiek te maken
* Leer hoe u een lijstpubliek [kunt](../../audiences/using/creating-audiences.md#creating-list-audiences) maken in een workflow
* Leer hoe u een publiek [importeert uit een bestand](../../audiences/using/creating-audiences.md#creating-file-audiences) in een workflow
* Leer hoe u publiek kunt [delen](../../audiences/using/creating-audiences.md#creating-experience-cloud-audiences) met Experience Cloud-oplossingen

## Algemene verordening inzake gegevensbescherming {#general-data-protection-regulation}

GDPR is de nieuwe privacywet van de Europese Unie (EU) die de vereisten inzake gegevensbescherming harmoniseert en moderniseert. GDPR is van toepassing op klanten van de Campagne van Adobe die gegevens voor de Onderwerpen van Gegevens in de EU houden. Naast de privacymogelijkheden die al beschikbaar zijn in Adobe Campaign (waaronder beheer van toestemming, instellingen voor gegevensbewaring en gebruikersrollen), maken we van deze gelegenheid gebruik in onze rol als gegevensprocessor om extra mogelijkheden op te nemen, zodat u gemakkelijker klaar bent als Data Controller voor bepaalde GDPR-verzoeken.

Raadpleeg deze [handleiding](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html) voor meer informatie over de gereedschappen en functies die Adobe Campaign biedt om u te helpen aan de GDPR-standaard te voldoen.

## Vermogensbeheer {#fatigue-management}

Met moeheidsregels kunnen marketers wereldwijde regels voor kanaaloverschrijdende bedrijven instellen die overgevraagde profielen automatisch van campagnes uitsluiten.

Als u vermoeidheidsregels wilt toepassen, definieert u een maximumaantal berichten per profiel en selecteert u een periode waarop de regel van toepassing is. Tijdens de voorbereiding van de levering worden, indien van toepassing, profielen uitgesloten van de levering, afhankelijk van het aantal berichten dat al naar hen is verzonden.

**Verwante onderwerpen:**

* Leer hoe u vermoeidheidsregels [kunt](../../administration/using/fatigue-rules.md#examples) ontwerpen aan de hand van een set voorbeelden
* Leer hoe u [typologische regels maakt](../../administration/using/about-typology-rules.md)
* Gebruik [filterregels](../../administration/using/filtering-rules.md) om het publiek van uw berichten te verfijnen
