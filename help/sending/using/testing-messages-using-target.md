---
title: E-mailberichten testen met doelprofielen
description: Leer hoe u berichten kunt testen met behulp van doelprofielen en vervangende adressen.
page-status-flag: never-activated
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a6e81927aad7bf06eca6d0dc7436c4dc2a1c21c5

---


# E-mailberichten testen met doelprofielen {#testing-message-profiles}

## Overzicht {#overview}

Naast [testprofielen](../../audiences/using/managing-test-profiles.md)kunt u ook een e-mailbericht testen door uzelf in de positie van een van de doelprofielen te plaatsen. Op deze manier kunt u een exacte weergave krijgen van het bericht dat het profiel ontvangt (aangepaste velden, dynamische en persoonlijke gegevens, inclusief aanvullende gegevens van workflows...).

>[!NOTE]
>
> Deze functie is alleen beschikbaar bij e-mailberichten.

De belangrijkste stappen zijn:

1. Configureer uw bericht en start vervolgens de **voorbereidingsfase** .
1. **Selecteer een of meerdere profielen** in de profielen die het bericht als doel heeft.
1. Koppel aan elk profiel een **vervangend adres** waarnaar proefdrukken worden verzonden.
1. (optioneel) Geef voor elk profiel een **voorvoegsel** op dat u aan de onderwerpregel van de proefdruk wilt toevoegen.
1. **Geef in de e-mailontwerper een voorbeeld** weer van hoe het bericht voor de profielen wordt weergegeven.
1. Verzend de proefdrukken.

Voor meer informatie over het globale proces, verwijs naar de tutorial video beschikbaar [hier](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html).

>[!IMPORTANT]
>
>Met deze functie kunt u persoonlijke profielgegevens naar externe e-mailadressen verzenden. Houd er rekening mee dat het uitvoeren van privacyverzoeken (GDPR en CCPA) in Campagnestandaard dat verzoek niet extern zal uitvoeren.

## Profielen en vervangingsadressen selecteren {#selecting-profiles}

Als u doelprofielen wilt gebruiken voor tests, moet u deze eerst selecteren en vervolgens de vervangende adressen definiëren waarop de proefdrukken worden uitgevoerd. Hiertoe kunt u specifieke profielen [](#selecting-individual-profiles) selecteren in de doelprofielen of profielen [importeren uit een bestaand publiek](#importing-from-audience).

>[!NOTE]
>
>U kunt maximaal 100 profielen selecteren om te testen.

### Afzonderlijke profielen selecteren {#selecting-individual-profiles}

1. Controleer in het berichtdashboard of het bericht is voorbereid en klik op het **[!UICONTROL Audience]** blok.

   ![](assets/substitution_preparation.png)

1. Klik op het **[!UICONTROL Profile substitutions]** tabblad op de **[!UICONTROL Create element]** knop om de profielen te selecteren die u wilt gebruiken voor testen.

   ![](assets/substitution_tab.png)

1. Klik op de knop Profielselectie om de lijst weer te geven met profielen die het bericht als doel heeft.

   ![](assets/substitution_recipient_selection.png)

1. Selecteer het profiel dat u voor de test wilt gebruiken, voer in het **[!UICONTROL Address]** veld het gewenste vervangende adres in en klik op **[!UICONTROL Confirm]**. Alle proefdrukken voor het profiel worden naar dit e-mailadres verzonden en niet naar het adres dat in de database voor dit profiel is gedefinieerd.

   Als u een specifiek voorvoegsel wilt toevoegen aan de onderwerpregel van de proefdrukken, vult u het **[!UICONTROL Subject line prefix]** veld in.

   ![](assets/substitution_address.png)

   Het voorvoegsel wordt als volgt weergegeven:

   ![](assets/substitution_prefixsample.png)

1. Het profiel wordt aan de lijst toegevoegd met het bijbehorende vervangende adres en voorvoegsel. Herhaal bovenstaande stappen voor alle profielen die u voor het testen wilt gebruiken, en klik dan **[!UICONTROL Confirm]**.

   ![](assets/substitution_recipients_confirm.png)

   Als u een proef naar veelvoudige substitutieadressen voor een zelfde profiel wilt verzenden, moet u dit profiel zo vele tijden toevoegen zoals vereist.

   In het onderstaande voorbeeld wordt de proefdruk op basis van het profiel John Smith verzonden naar twee verschillende vervangende adressen:

   ![](assets/substitution_multiple_addresses.png)

1. Wanneer alle profielen en vervangingsadressen zijn gedefinieerd, kunt u een proefdruk verzenden om het bericht te testen. Klik hiertoe op de **[!UICONTROL Test]** knop en selecteer het type test dat u wilt uitvoeren.

   Als er geen testprofiel is toegevoegd aan het doel van het bericht, zijn de opties **[!UICONTROL Email rendering]** en **[!UICONTROL Proof + Email rendering]** opties niet beschikbaar.  Raadpleeg [deze sectie](../../sending/using/sending-proofs.md)voor meer informatie over het verzenden van proefdrukken.

   ![](assets/substitution_send_test.png)

>[!IMPORTANT]
>
>Als u een wijziging aanbrengt in uw bericht, moet u de voorbereiding van het bericht opnieuw starten. Anders worden de wijzigingen niet doorgevoerd in de proefdruk.

### Profielen van een publiek importeren {#importing-from-audience}

Met de campagnestandaard kunt u een publiek met profielen importeren dat u kunt gebruiken voor tests. Zo kunt u bijvoorbeeld een hele reeks berichten voor verschillende profielen naar een uniek e-mailadres verzenden.

Bovendien als uw publiek reeds met de adres en prefixkolommen wordt gevormd, zult u deze informatie in het **[!UICONTROL Profile substitutions]** lusje kunnen invoeren. In [deze sectie](#use-case)wordt een voorbeeld gegeven van het importeren van doelgroepen met vervangende adressen.

>[!NOTE]
>
>Wanneer u een publiek importeert, worden alleen de profielen die overeenkomen met het berichtdoel geselecteerd en aan het **[!UICONTROL Profile substitutions]** tabblad toegevoegd.

Voer de volgende stappen uit om profielen te importeren die u wilt gebruiken voor tests vanuit een publiek:

1. Controleer in het berichtdashboard of het bericht is voorbereid en klik op het **[!UICONTROL Audience]** blok.

   ![](assets/substitution_preparation.png)

1. In the **[!UICONTROL Profile substitutions]** tab, click **[!UICONTROL Import from an audience]**.

   ![](assets/substitution_audience_import.png)

1. Selecteer het publiek dat u wilt gebruiken en voer vervolgens het vervangende adres en het voorvoegsel in dat u wilt gebruiken voor de proefdrukken die naar het publiek worden verzonden.

   ![](assets/substitution_audience_define.png)

   Als de te gebruiken substitutieadressen en/of voorvoegsels reeds in uw publiek zijn bepaald, selecteer de **[!UICONTROL From Audience]** optie, dan specificeer de kolom om deze informatie terug te winnen.

   ![](assets/substitution_fromaudience.png)

1. Klik op de **[!UICONTROL Import]** knop. De profielen van het publiek die aan het berichtdoel beantwoorden worden toegevoegd aan het **[!UICONTROL Profile substitution]** lusje, evenals de bijbehorende substitutieadressen en prefixen.

>[!NOTE]
>
>Als u hetzelfde publiek nogmaals importeert met verschillende vervangende adressen en/of voorvoegsels, worden de profielen toegevoegd aan de lijst, naast de profielen die u eerder hebt geïmporteerd.

    ![](assets/substitution_audience_added.png)

## Een voorbeeld van het bericht weergeven met de doelprofielen

>[!NOTE]
>
>Voorvertoning is alleen beschikbaar bij E-mailontwerper.

Als u berichten wilt voorvertonen met behulp van doelprofielen, moet u deze profielen aan de **[!UICONTROL Profile substitution]** lijst toevoegen (zie Profielen en vervangende adressen [](#selecting-profiles)definiëren).

Als u verpersoonlijkingsgebieden in het bericht wilt gebruiken, moeten zij worden toegevoegd **alvorens** de berichtvoorbereiding te lanceren. Anders wordt hiermee in de voorvertoning geen rekening gehouden. Dientengevolge, zorg ervoor u de berichtvoorbereiding opnieuw begint als om het even welke verandering in de verpersoonlijkingsgebieden wordt aangebracht.

Voer de volgende stappen uit om berichten voor te vertonen met behulp van profielvervanging:

1. Klik in het berichtendashboard op de momentopname van de inhoud om het bericht te openen in E-mailontwerper.

   ![](assets/substitution_preview_access.png)

1. Selecteer het **[!UICONTROL Preview]** tabblad en klik op **[!UICONTROL Change profile]**.

   ![](assets/substitution_preview_changeprofile.png)

1. Klik op het **[!UICONTROL Profile Substitution]** tabblad om de vervangende profielen weer te geven die voor testen zijn toegevoegd.

   Selecteer de profielen die u wilt gebruiken voor de voorvertoning en klik op **[!UICONTROL Select]**.

   ![](assets/substitution_preview_selection.png)

1. Er wordt een voorbeeld van het bericht weergegeven. Gebruik de pijlen om tussen de geselecteerde profielen te navigeren.

   ![](assets/substitution_preview.png)

## Hoofdletters gebruiken {#use-case}

In dit geval willen we een gepersonaliseerde e-mailnieuwsbrief sturen naar een set specifieke profielen. Voordat u de nieuwsbrief verzendt, wilt u deze met een aantal van de beoogde profielen bekijken en proefdrukken verzenden naar interne e-mailadressen die in een extern bestand zijn gedefinieerd.

De belangrijkste stappen voor dit gebruik zijn als volgt:

1. Maak het publiek dat u wilt gebruiken voor testen.
1. Een workflow maken om profielen als doel in te stellen en de nieuwsbrief te verzenden.
1. Configureer de vervangende profielen van het bericht.
1. Geef een voorvertoning van het bericht weer met behulp van de beoogde profielen.
1. Proefdrukken verzenden.

### Stap 1: Het publiek maken dat moet worden gebruikt voor tests

1. Bereid het bestand voor om te importeren en het publiek te maken. In ons geval moet het het vervangende adres bevatten dat voor de proefdruk moet worden gebruikt, en een voorvoegsel dat aan de onderwerpregel van de proefdruk moet worden toegevoegd.

   In dit voorbeeld ontvangt het e-mailadres &quot;oliver.vaughan@internal.com&quot; een bewijs van het bericht voor het profiel met het e-mailadres &quot;john.doe@mail.com&quot;. Het voorvoegsel &#39;JD&#39; wordt toegevoegd aan de onderwerpregel van de proefdruk.

   ![](assets/substitution_uc1.png)

1. Bouw het werkschema om een publiek van het dossier tot stand te brengen. Hiervoor voegt u de volgende activiteiten toe en configureert u deze:

   * **[!UICONTROL Load file]** activiteit: Hiermee importeert u het CSV-bestand (raadpleeg [deze sectie](../../automating/using/load-file.md)voor meer informatie over deze activiteit).
   * **[!UICONTROL Reconciliation]** activiteit: Koppelt informatie uit het bestand aan informatie uit de database. In dit voorbeeld gebruiken we het e-mailadres van het profiel als verzoeningsveld (voor meer informatie over deze activiteit, zie [deze sectie](../../automating/using/reconciliation.md)).
   * **[!UICONTROL Save audience]** activiteit: Hiermee maakt u een publiek op basis van het geïmporteerde bestand (raadpleeg [deze sectie](../../automating/using/save-audience.md)voor meer informatie over deze activiteit).
   ![](assets/substitution_uc2.png)

1. Voer de workflow uit en ga naar het **[!UICONTROL Audiences]** tabblad om te controleren of het publiek met de gewenste informatie is gemaakt.

   In dit voorbeeld bestaat het publiek uit drie profielen. Elk van deze is gekoppeld aan een vervangend e-mailadres dat de proefdruk ontvangt, met een voorvoegsel voor gebruik op de onderwerpregel van de proefdruk.

   ![](assets/substitution_uc3.png)

### Stap 2: Een workflow maken om profielen als doel in te stellen en de nieuwsbrief te verzenden

1. Voeg **[!UICONTROL Query]** en **[!UICONTROL Email delivery]** activiteiten toe, dan vorm hen volgens uw behoeften (zie de secties van de [Vraag](../../automating/using/query.md) en van de [E-mail levering](../../automating/using/email-delivery.md) ).

   ![](assets/substitution_uc4.png)

1. Voer de workflow uit en controleer of het bericht is voorbereid.

### Stap 3: Het tabblad Profielvervanging van het bericht configureren

1. Open de **[!UICONTROL Email delivery]** activiteit. Klik op het **[!UICONTROL Audience]** blok in het berichtdashboard.

   ![](assets/substitution_uc5.png)

1. Selecteer het **[!UICONTROL Profile substitutions]** tabblad en klik op **[!UICONTROL Import from an audience]**.

   ![](assets/substitution_uc6.png)

1. Selecteer in het **[!UICONTROL Audience]** veld het publiek dat u in het bestand hebt gemaakt.

   ![](assets/substitution_uc7.png)

1. Definieer het vervangende adres en het voorvoegsel van de onderwerpregel die u wilt gebruiken wanneer u de proefdrukken verzendt.

   Selecteer hiertoe de **[!UICONTROL From audience]** optie en selecteer vervolgens de kolom in het publiek dat de informatie bevat.

   ![](assets/substitution_uc8.png)

1. Klik op de **[!UICONTROL Import]** knop. Profielen van het publiek worden aan de lijst toegevoegd met de bijbehorende vervangende adressen en voorvoegsels van onderwerpregel.

   ![](assets/substitution_uc9.png)

   >[!NOTE]
   >
   >In ons geval zijn alle profielen van het publiek het doelwit van de **[!UICONTROL Query]** activiteit. Als een van deze profielen geen deel uitmaakte van het berichtdoel, zou het niet aan de lijst worden toegevoegd.

### Stap 4: Een voorbeeld van het bericht weergeven met de doelprofielen

1. Klik in het berichtendashboard op de momentopname van de inhoud om het bericht te openen in E-mailontwerper.

   ![](assets/substitution_uc10.png)

1. Selecteer het **[!UICONTROL Preview]** tabblad en klik op **[!UICONTROL Change profile]**.

   ![](assets/substitution_uc_preview.png)

1. Klik op het **[!UICONTROL Profile Substitution]** tabblad om de eerder toegevoegde vervangingsprofielen weer te geven.

   Selecteer de profielen die u wilt gebruiken voor de voorvertoning en klik op **[!UICONTROL Select]**.

   ![](assets/substitution_uc_selectpreview.png)

1. Er wordt een voorbeeld van het bericht weergegeven. Gebruik de pijlen om tussen de geselecteerde profielen te navigeren.

   ![](assets/substitution_uc_previewprofile.png)

### Stap 5: Proefdrukken verzenden

1. Klik in het berichtendashboard op de **[!UICONTROL Test]** knop en bevestig vervolgens het bericht.

   ![](assets/substitution_uc_sendproof.png)

1. De proefdrukken worden verzonden volgens wat in het **[!UICONTROL Profile substitutions]** lusje is gevormd.

   ![](assets/substitution_uc_proofs.png)
