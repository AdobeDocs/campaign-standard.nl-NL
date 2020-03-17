---
title: De onderwerpregel van een e-mail testen
description: Ontdek hoe u de onderwerpregel van een e-mailbericht kunt definiëren in de e-mailontwerper.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7e61796376a14c279d38107905275172be0dd12d

---

# De onderwerpregel van een e-mail testen {#testing-a-subject}

Volg onderstaande stappen om de onderwerpregel te testen:

1. Maak of open uw e-mail.
1. Open de inhoud en voer het onderwerp van de e-mail in het desbetreffende invoerveld in.
1. Klik op de **[!UICONTROL Test subject]** knop om het **[!UICONTROL Test your subject line]** venster te openen. U kunt het onderwerp nog steeds bewerken vanuit dit venster.
1. Selecteer het juiste model waarmee rekening moet worden gehouden voor de voorspelling van de open snelheid. Er zijn verschillende modellen beschikbaar, elk voor een specifieke bedrijfstak.
1. Klik op **[!UICONTROL Test]**.

Uw onderwerp wordt vervolgens geanalyseerd.

>[!NOTE]
>
>Als de onderwerpregel te kort is, kan deze niet worden geanalyseerd en wordt een foutbericht weergegeven.

Verschillende indicatoren worden berekend en er wordt een set gereedschappen weergegeven om u te helpen:

* **Voorspelde open snelheid**: Deze grafiek geeft u een idee van het open tarief u voor e-mail met zijn huidig onderwerp kunt verwachten.
* **Lengte** onderwerp: Met deze indicator kunt u zien of de huidige lengte van het onderwerp correct is of dat deze langer of korter moet zijn.
* **Kleurwoorden**: Bij het testen van het onderwerp zijn groen gemarkeerde woorden de woorden die het meest bijdragen aan het verhogen van de open-snelheidsvoorspelling. Woorden die rood worden gemarkeerd, zijn de woorden die het minst bijdragen aan het vergroten van de voorspelbaarheid van de open snelheid. Als u woorden aan het onderwerp toevoegt of eruit verwijdert, veranderen de gemarkeerde woorden.
* **Categorieën en suggesties** voor woorden: In het onderste gedeelte van het venster wordt een aantal relevante categorieën voor het geselecteerde model weergegeven. Deze categorieën worden gesorteerd op volgorde van belangrijkheid en u kunt zien of uw onderwerp woorden bevat die eraan gekoppeld zijn via een vinkje. Elke categorie bevat een aantal voorgestelde woorden die in uw onderwerp kunnen worden gebruikt om het relevanter te maken en het open tarief te verhogen. Deze woorden worden het meest gebruikt in een bepaalde categorie.

>[!NOTE]
>
>Personalisatievelden en leestekens worden uit de onderwerpanalyse verwijderd. In het geval van dynamische/voorwaardelijke tekst worden alle varianten beschouwd als één onderwerpregel.

![](assets/predictive_subject_line_example.png)

## Modellen importeren {#importing-models}

Er wordt standaard geen model uitgevoerd op uw Adobe Campaign-server. Er zijn twee manieren om een model op te halen en de functie te activeren:

* U kunt een lokaal model trainen van de gegevens van uw vorige e-mailberichten:

   * Als u Adobe Campaign al gebruikt, wordt het lokale model automatisch opgeleid voor de berichten die u al hebt verzonden.
   * Als Adobe Campagne nieuw voor u is, kunt u een CSV-bestand van uw vorige systeem/ESP extraheren dat vier kolommen bevat: datum, onderwerp, wordt geopend, verzonden. Ga hiertoe naar **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Subject Line Import]** en volg de instructies op de volgende schermen. Importeer een lokaal model zoals hieronder beschreven wanneer het uploaden van het onderwerp is voltooid. Het lokale model wordt automatisch getraind met de gegevens u uploadde.
   * Als u nog geen ervaring hebt met Adobe Campaign en geen CSV-bestand kunt krijgen zoals hierboven beschreven, kunt u een vooraf opgeleid model gebruiken of wachten tot er voldoende leveringsgegevens in uw systeem zijn om een lokaal model op te leiden. Het systeem zal automatisch bepalen of uw huidige gegevensreeks genoeg gegevens bevat om patronen te erkennen en het model op te leiden.

      >[!NOTE]
      >
      >Er is geen gedefinieerd aantal onderwerpregel nodig om uw eigen model te trainen. Om het te kunnen trainen, moeten de onderwerplijnen worden gevarieerd en mogen er geen duplicaten zijn. Als er onvoldoende gegevens zijn om te verwerken, kan het systeem het model niet trainen. U kunt slechts één getraind model op uw exemplaar hebben.
   Als u een lokaal model wilt trainen, downloadt u het subjectLineTraining.xml [hier](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) en uploadt u het naar uw Adobe Campagne-instantie met de functie [package import](../../automating/using/managing-packages.md) . De training wordt automatisch uitgevoerd via een technische workflow.

   De eerste keer dat u een model wilt trainen, kan een beheerder dwingen om te beginnen van **[!UICONTROL SubjectLine Training workflow]** > **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** **[!UICONTROL Workflows]** menu.

   Nadat een model is geüpload en opgeleid, wordt de functie automatisch geactiveerd en wordt een nieuwe optie weergegeven naast het veld voor de onderwerpregel van uw berichten.

   De technische workflow zal dan automatisch elke week uw model trainen.

* U kunt vooraf opgeleide modellen importeren die specifiek zijn voor bepaalde bedrijfstakken (medisch, enz.) met de functie [voor importeren](../../automating/using/managing-packages.md) van pakketten. Klik [hier](https://support.neolane.net/webApp/extranetLogin) om toegang te krijgen tot deze modellen en ga naar **[Downloadcentrum]**. Deze modellen kunnen niet worden getraind.

   Nadat een model is geüpload, wordt de functie automatisch geactiveerd en wordt een nieuwe optie weergegeven naast het veld voor de onderwerpregel van uw berichten.

>[!NOTE]
>
>Het importeren en genereren van getrainde modellen kan alleen door een beheerder worden uitgevoerd.

De modellen die voor gebruik beschikbaar zijn zijn:

* Cosmetische industrie: subjectInsightCosmetic.xml
* Supermarktindustrie: subjectInsightSupermarket.xml
* Medische industrie: subjectInsightMedical.xml
* Model voor training: subjectlineTraining.xml.
