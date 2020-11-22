---
solution: Campaign Standard
product: campaign
title: De onderwerpregel van een e-mail testen
description: Ontdek hoe u de onderwerpregel van een e-mailbericht kunt definiëren in de e-mailontwerper.
audience: sending
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1095'
ht-degree: 2%

---

# De onderwerpregel van een e-mail testen {#testing-a-subject}


## Informatie over een voorspelbare onderwerpregel {#about-predictive-subject-line}

Wanneer u een e-mailbericht bewerkt, kunt u verschillende onderwerpregel uitproberen en een schatting krijgen van de openstaande frequentie voordat u het bericht verzendt.

Deze functie is standaard uitgeschakeld. Deze optie wordt ingeschakeld wanneer het eerste model wordt geïmporteerd. Een model is het resultaat van reeksen van opleidingsgegevens die specifiek zijn voor een bepaalde bedrijfstak. Met modellen kan het systeem voorspellen wat de open snelheid van de e-mail is wanneer een nieuwe onderwerpregel wordt verzonden.

>[!NOTE]
>
>Deze functie is beschikbaar voor e-mailberichten en voor databases die alleen Engelse inhoud bevatten. Het getrainde model is inconsistent en leidt tot onjuiste resultaten als uw exemplaar e-mails in andere talen bevat. De optie waarmee u een onderwerp kunt testen, is alleen zichtbaar als er al een model beschikbaar is in uw exemplaar.

For more on importing models, see this [section](#importing-models).

## De onderwerpregel testen {#testing-subject-line}

Volg onderstaande stappen om de onderwerpregel te testen:

1. Maak of open uw e-mail.
1. Open de inhoud en voer het onderwerp van de e-mail in het desbetreffende invoerveld in.
1. Click the **[!UICONTROL Test subject]** button to access the **[!UICONTROL Test your subject line]** window. U kunt het onderwerp nog steeds bewerken vanuit dit venster.
1. Selecteer het juiste model waarmee rekening moet worden gehouden voor de voorspelling van de open snelheid. Er zijn verschillende modellen beschikbaar, elk voor een specifieke bedrijfstak. For more on using models, see this [section](#importing-models).
1. Klik op **[!UICONTROL Test]**.

Uw onderwerp wordt vervolgens geanalyseerd.

>[!NOTE]
>
>Als de onderwerpregel te kort is, kan deze niet worden geanalyseerd en wordt een foutbericht weergegeven.

Verschillende indicatoren worden berekend en er wordt een set gereedschappen weergegeven om u te helpen:

* **Voorspelde open snelheid**: Deze grafiek geeft u een idee van het open tarief u voor e-mail met zijn huidig onderwerp kunt verwachten.
* **Lengte** onderwerp: Met deze indicator kunt u zien of de huidige lengte van het onderwerp correct is of dat deze langer of korter moet zijn.
* **Kleurwoorden**: Bij het testen van het onderwerp zijn groen gemarkeerde woorden de woorden die het meest bijdragen aan het verhogen van de open-snelheidsvoorspelling. Woorden die rood worden gemarkeerd, zijn de woorden die het minst bijdragen aan het vergroten van de voorspellingen van de open snelheid. Als u woorden aan het onderwerp toevoegt of eruit verwijdert, veranderen de gemarkeerde woorden.
* **Categorieën en suggesties** voor woorden: In het onderste gedeelte van het venster wordt een aantal relevante categorieën voor het geselecteerde model weergegeven. Deze categorieën worden gesorteerd op volgorde van belangrijkheid en u kunt zien of uw onderwerp woorden bevat die eraan gekoppeld zijn via een vinkje. Elke categorie bevat een aantal voorgestelde woorden die in uw onderwerp kunnen worden gebruikt om het relevanter te maken en het open tarief te verhogen. Deze woorden worden het meest gebruikt in een bepaalde categorie.

>[!NOTE]
>
>Personalisatievelden en leestekens worden uit de onderwerpanalyse verwijderd. In het geval van dynamische/voorwaardelijke tekst worden alle varianten beschouwd als één onderwerpregel.

![](assets/predictive_subject_line_example.png)

## Modellen importeren {#importing-models}

Er wordt standaard geen model uitgevoerd op uw Adobe Campaign-server. Er zijn twee manieren om een model op te halen en de functie te activeren:

* U kunt een lokaal model trainen van de gegevens van uw vorige e-mailberichten.
* U kunt vooraf opgeleide modellen importeren die specifiek zijn voor bepaalde bedrijfstakken (medisch, enz.) met de functie [voor importeren](../../automating/using/managing-packages.md) van pakketten.

### Een lokaal model trainen {#training-local-model}

* Als u Adobe Campaign al gebruikt, wordt het lokale model automatisch opgeleid voor de berichten die u al hebt verzonden.
* Als u nog geen ervaring hebt met Adobe Campaign, kunt u een CSV-bestand van uw vorige systeem/ESP extraheren dat vier kolommen bevat: datum, onderwerp, wordt geopend, verzonden. Ga hiertoe naar **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Subject Line Import]** en volg de instructies op de volgende schermen. Importeer een lokaal model zoals hieronder beschreven wanneer het uploaden van het onderwerp is voltooid. Het lokale model wordt automatisch getraind met de gegevens u uploadde.
* Als u nog geen ervaring hebt met Adobe Campaign en geen CSV-bestand kunt krijgen zoals hierboven beschreven, kunt u een [vooraf opgeleid model](#pre-trained-models) gebruiken of wachten tot u voldoende leveringsgegevens in uw systeem hebt om een lokaal model op te leiden. Het systeem zal automatisch bepalen of uw huidige gegevensreeks genoeg gegevens bevat om patronen te erkennen en het model op te leiden.

>[!NOTE]
>
>Er is geen gedefinieerd aantal onderwerpregel nodig om uw eigen model te trainen. For more on this, see [Troubleshooting](#troubleshooting).
>
>U kunt slechts één getraind model op uw exemplaar hebben.

Een lokaal model trainen:
1. Download subjectLineTraining.xml van [hier](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html) en gebruik de functie [package import](../../automating/using/managing-packages.md) om deze naar uw Adobe Campaign-instantie te uploaden. De training wordt automatisch uitgevoerd via een technische workflow.
1. De eerste keer dat u een model wilt trainen, kan een beheerder dwingen om te beginnen van **[!UICONTROL SubjectLine Training workflow]** > **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** **[!UICONTROL Workflows]** menu.
1. Nadat een model is geüpload en opgeleid, wordt de functie automatisch geactiveerd en wordt een nieuwe optie weergegeven naast het veld voor de onderwerpregel van uw berichten.
1. De technische workflow zal dan automatisch elke week uw model trainen.

### Voorgeschoolde modellen importeren {#pre-trained-models}

Klik [hier](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html)om deze modellen te openen. Gebruik de functie voor het importeren van [pakketten](../../automating/using/managing-packages.md) om een model te uploaden naar uw Adobe Campaign-instantie.

De modellen die voor gebruik beschikbaar zijn zijn:

* Cosmetische industrie: subjectInsightCosmetic.xml
* Supermarktindustrie: subjectInsightSupermarket.xml
* Medische industrie: subjectInsightMedical.xml
* Model voor training: subjectlineTraining.xml.

Deze modellen kunnen niet worden opgeleid.

Nadat een model is geüpload, wordt de functie automatisch geactiveerd en wordt een nieuwe optie weergegeven naast het veld voor de onderwerpregel van uw berichten.

>[!NOTE]
>
>Het importeren en genereren van getrainde modellen kan alleen door een beheerder worden uitgevoerd.

## Problemen oplossen {#troubleshooting}

Een voorspellende onderwerpregel is een automatisch leerproces waarin alle onderwerpregel die u met hun open snelheid hebt geüpload, in aanmerking wordt genomen. Hierdoor kan het systeem de openheid van een e-mail voorspellen wanneer een nieuwe onderwerpregel wordt ingediend.

Om uw eigen model te kunnen trainen, moeten de onderwerpreeksen worden gevarieerd en mogen geen duplicaten hebben, ongeacht het aantal onderwerpreeksen dat wordt gebruikt om uw model op te leiden.

De kwaliteit van de onderwerpregel is essentieel. Als er onvoldoende kwaliteitsgegevens zijn om te verwerken of als alle vorige onderwerpregel te veel op elkaar lijken, kan het systeem het model niet trainen en krijgt u mogelijk een foutbericht. Dit betekent dat uw bestaande set records geen betrouwbare voorspellende suggestie biedt.

In dit geval moet u de gegevens die u uploadt controleren en ervoor zorgen dat de onderwerpregel zo gevarieerd is dat het model efficiënt wordt opgeleid.

<!--Some clients have reported this issue: I have had the subject line training workflow running for about a year now.  It has trained on 883 records and I am still seeing the message "The existing dataset is not enough to generate a model."  I do get an error in the workflow every time it runs "XML-110009 Unable to find the element 'runwf' of path '/' (document with schema 'serverConf')".

For this, campaign takes the subject line as training data and tries to come up with significant enough model to predict open rate with 95% confidence.

The 400 subject line number is mention with at least and is only indicative, model generation will also depend on quality of these lines.

It may happen that even 10k subject lines don't lead to model generation if they are too similar.

It means that it can be case that you don't have enough subject lines to generate the model and it is giving this error.

If you are getting an error/warning message, it means that your existing set of records is not enough for the predictive subject module to give a high confidence suggestion.

Adobe recommends reviewing the data you are uploading as the similarity of the subject lines might be the issue.-->
