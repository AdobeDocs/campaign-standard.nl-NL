---
title: E-mailberichten testen met doelprofielen
description: Leer hoe u berichten kunt testen met behulp van doelprofielen en vervangende adressen.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
feature: Control Groups
role: User
level: Intermediate
exl-id: aa68914f-0497-40ba-98c8-4d4b2c6705fb
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1533'
ht-degree: 4%

---

# E-mailberichten testen met doelprofielen {#testing-message-profiles}

## Overzicht {#overview}

Aanvullend op [testprofielen](../../audiences/using/managing-test-profiles.md)kunt u een e-mailbericht testen door uzelf in de positie van een van de doelprofielen te plaatsen. Op deze manier kunt u een exacte weergave krijgen van het bericht dat het profiel ontvangt (aangepaste velden, dynamische en persoonlijke gegevens, inclusief aanvullende gegevens van workflows...).

>[!IMPORTANT]
>
>Met deze functie kunt u persoonlijke profielgegevens naar externe e-mailadressen verzenden. Houd er rekening mee dat door het uitvoeren van privacyaanvragen (GDPR en CCPA) in Campaign Standard deze aanvraag NIET extern wordt uitgevoerd.

De belangrijkste stappen zijn:

1. Configureer uw bericht en start vervolgens de **Voorbereiding** fase.
1. **Selecteer een of meerdere profielen** van de profielen waarop het bericht betrekking heeft.
1. Koppelen aan elk profiel a **vervangend adres** aan welke proefstukken zullen worden toegezonden.
1. (optioneel) Definieer voor elk profiel een **prefix** toevoegen aan de onderwerpregel voor het proefdrukken.
1. **Voorvertoning** in de E-mailontwerper hoe het bericht wordt weergegeven voor de profielen.
1. Verzend de proefdrukken.

   >[!IMPORTANT]
   >
   >Proefdrukken worden verwerkt door [!DNL Campaign Standard] als standaardleveringen. Als proefdrukken worden verzonden met behulp van profielvervanging, worden records toegevoegd aan de bezorgings- en trackinglogboeken van de geselecteerde profielen.

![](assets/do-not-localize/how-to-video.png) [Ontdek deze functie in video](#video)

## Profielen en vervangingsadressen selecteren {#selecting-profiles}

Als u doelprofielen wilt gebruiken voor tests, moet u deze eerst selecteren en vervolgens de vervangende adressen definiëren waarop de proefdrukken worden uitgevoerd. U kunt dit doen door [specifieke profielen selecteren](#selecting-individual-profiles) van de beoogde profielen, of [profielen importeren uit een bestaand publiek](#importing-from-audience).

>[!NOTE]
>
>U kunt maximaal 100 profielen selecteren om te testen.

### Afzonderlijke profielen selecteren {#selecting-individual-profiles}

1. Controleer in het berichtdashboard of het bericht is voorbereid en klik vervolgens op de knop **[!UICONTROL Audience]** blokkeren.

   ![](assets/substitution_preparation.png)

1. In de **[!UICONTROL Profile substitutions]** klikt u op de knop **[!UICONTROL Create element]** om de profielen te selecteren die u wilt gebruiken voor testen.

   ![](assets/substitution_tab.png)

1. Klik op de knop Profielselectie om de lijst weer te geven met profielen die het bericht als doel heeft.

   ![](assets/substitution_recipient_selection.png)

1. Selecteer het profiel dat u wilt gebruiken voor testen en typ vervolgens in het dialoogvenster **[!UICONTROL Address]** het gewenste vervangingsadres, dan klik **[!UICONTROL Confirm]**. Alle proefdrukken voor het profiel worden naar dit e-mailadres verzonden en niet naar het adres dat in de database voor dit profiel is gedefinieerd.

   Als u een specifiek voorvoegsel wilt toevoegen aan de onderwerpregel van de proefdrukken, vult u de optie **[!UICONTROL Subject line prefix]** veld.

   >[!NOTE]
   >
   >Het voorvoegsel van de onderwerpregel kan maximaal 500 tekens bevatten.

   ![](assets/substitution_address.png)

   Het voorvoegsel wordt als volgt weergegeven:

   ![](assets/substitution_prefixsample.png)

1. Het profiel wordt aan de lijst toegevoegd met het bijbehorende vervangende adres en voorvoegsel. Herhaal bovenstaande stappen voor alle profielen die u voor het testen wilt gebruiken, en klik dan **[!UICONTROL Confirm]**.

   ![](assets/substitution_recipients_confirm.png)

   Als u een proef naar veelvoudige substitutieadressen voor een zelfde profiel wilt verzenden, moet u dit profiel zo vele tijden toevoegen zoals vereist.

   In het onderstaande voorbeeld wordt de proefdruk op basis van het profiel John Smith verzonden naar twee verschillende vervangende adressen:

   ![](assets/substitution_multiple_addresses.png)

1. Wanneer alle profielen en vervangingsadressen zijn gedefinieerd, kunt u een proefdruk verzenden om het bericht te testen. Om dit te doen, klik **[!UICONTROL Test]** en selecteert u vervolgens het type test dat u wilt uitvoeren.

   Als er geen testprofiel aan het doel van het bericht is toegevoegd, wordt het **[!UICONTROL Email rendering]** en **[!UICONTROL Proof + Email rendering]** zijn niet beschikbaar.  Voor meer informatie over het verzenden van proefdrukken raadpleegt u [deze sectie](../../sending/using/sending-proofs.md).

   ![](assets/substitution_send_test.png)

>[!IMPORTANT]
>
>Als u een wijziging aanbrengt in uw bericht, moet u de voorbereiding van het bericht opnieuw starten. Anders worden de wijzigingen niet doorgevoerd in de proefdruk.

### Profielen van een publiek importeren {#importing-from-audience}

Met Campaign Standard kunt u een publiek met profielen importeren dat u kunt gebruiken voor tests. Zo kunt u bijvoorbeeld een hele reeks berichten voor verschillende profielen naar een uniek e-mailadres verzenden.

Bovendien als uw publiek reeds met de adres en prefixkolommen wordt gevormd, zult u deze informatie in kunnen invoeren **[!UICONTROL Profile substitutions]** tab. Een voorbeeld van het importeren van doelgroepen met vervangende adressen vindt u in [deze sectie](#use-case).

>[!NOTE]
>
>Wanneer het invoeren van een publiek, slechts worden de profielen die aan het berichtdoel beantwoorden geselecteerd en aan toegevoegd **[!UICONTROL Profile substitutions]** tab.

Voer de volgende stappen uit om profielen te importeren die u wilt gebruiken voor tests vanuit een publiek:

1. Controleer in het berichtdashboard of het bericht is voorbereid en klik vervolgens op de knop **[!UICONTROL Audience]** blokkeren.

   ![](assets/substitution_preparation.png)

1. Klik op het tabblad **[!UICONTROL Profile substitutions]** op **[!UICONTROL Import from an audience]**.

   ![](assets/substitution_audience_import.png)

1. Selecteer het publiek dat u wilt gebruiken en voer vervolgens het vervangende adres en het voorvoegsel in dat u wilt gebruiken voor de proefdrukken die naar het publiek worden verzonden.

   >[!NOTE]
   >
   >Het voorvoegsel van de onderwerpregel kan maximaal 500 tekens bevatten.

   ![](assets/substitution_audience_define.png)

   Als de vervangende adressen en/of voorvoegsels die u wilt gebruiken al in uw publiek zijn gedefinieerd, selecteert u de optie **[!UICONTROL From Audience]** en geeft u vervolgens de kolom op die moet worden gebruikt om deze gegevens op te halen.

   ![](assets/substitution_fromaudience.png)

1. Klik op de knop **[!UICONTROL Import]**. De profielen van het publiek die aan het berichtdoel beantwoorden worden toegevoegd aan **[!UICONTROL Profile substitution]** en de bijbehorende vervangende adressen en voorvoegsels.

![](assets/substitution_audience_imported.png)

>[!NOTE]
>
>Als u hetzelfde publiek nogmaals importeert met verschillende vervangende adressen en/of voorvoegsels, worden de profielen toegevoegd aan de lijst, naast de profielen die u eerder hebt geïmporteerd.

## Een voorbeeld van het bericht weergeven met de doelprofielen

>[!NOTE]
>
>Voorvertoning is alleen beschikbaar bij E-mailontwerper.

Als u berichten wilt voorvertonen met behulp van doelprofielen, moet u deze profielen toevoegen aan de **[!UICONTROL Profile substitution]** lijst (zie [Profielen en vervangingsadressen definiëren](#selecting-profiles)).

Als u verpersoonlijkingsgebieden in het bericht wilt gebruiken, moeten zij worden toegevoegd **voor** het lanceren van de berichtvoorbereiding. Anders wordt hiermee in de voorvertoning geen rekening gehouden. Dientengevolge, zorg ervoor u de berichtvoorbereiding opnieuw begint als om het even welke verandering in de verpersoonlijkingsgebieden wordt aangebracht.

Voer de volgende stappen uit om berichten voor te vertonen met behulp van profielvervanging:

1. Klik in het berichtendashboard op de momentopname van de inhoud om het bericht te openen in E-mailontwerper.

   ![](assets/substitution_preview_access.png)

1. Selecteer de **[!UICONTROL Preview]** tab, en klik vervolgens op **[!UICONTROL Change profile]**.

   ![](assets/substitution_preview_changeprofile.png)

1. Klik op de knop **[!UICONTROL Profile Substitution]** om de vervangende profielen weer te geven die voor testen zijn toegevoegd.

   Selecteer de profielen die u wilt gebruiken voor de voorvertoning en klik op **[!UICONTROL Select]**.

   ![](assets/substitution_preview_selection.png)

1. Er wordt een voorbeeld van het bericht weergegeven. Gebruik de pijlen om tussen de geselecteerde profielen te navigeren.

   ![](assets/substitution_preview.png)

## Gebruiksscenario {#use-case}

In dit geval willen we een gepersonaliseerde e-mailnieuwsbrief sturen naar een set specifieke profielen. Voordat u de nieuwsbrief verzendt, wilt u deze met een aantal van de beoogde profielen bekijken en proefdrukken verzenden naar interne e-mailadressen die in een extern bestand zijn gedefinieerd.

De belangrijkste stappen voor dit gebruik zijn als volgt:

1. Maak het publiek dat u wilt gebruiken voor testen.
1. Een workflow maken om profielen als doel in te stellen en de nieuwsbrief te verzenden.
1. Configureer de vervangende profielen van het bericht.
1. Geef een voorvertoning van het bericht weer met behulp van de beoogde profielen.
1. Proefdrukken verzenden.

### Stap 1: Maak het publiek dat u wilt gebruiken voor tests

1. Bereid het bestand voor dat moet worden geïmporteerd om het publiek te maken. In ons geval moet het het vervangende adres bevatten dat voor de proefdruk moet worden gebruikt, en een voorvoegsel dat aan de onderwerpregel van de proefdruk moet worden toegevoegd.

   In dit voorbeeld ontvangt het e-mailadres &quot;oliver.vaughan@internal.com&quot; een bewijs van het bericht voor het profiel met het e-mailadres &quot;john.doe@mail.com&quot;. Het voorvoegsel &#39;JD&#39; wordt toegevoegd aan de onderwerpregel van de proefdruk.

   ![](assets/substitution_uc1.png)

1. Bouw het werkschema om een publiek van het dossier tot stand te brengen. Hiervoor voegt u de volgende activiteiten toe en configureert u deze:

   * **[!UICONTROL Load file]** activiteit: importeert het CSV-bestand (zie voor meer informatie over deze activiteit [deze sectie](../../automating/using/load-file.md)).
   * **[!UICONTROL Reconciliation]** activiteit: Koppelt informatie van het dossier aan informatie van het gegevensbestand. In dit voorbeeld gebruikt u het e-mailadres van het profiel als het afstemmingsveld (zie voor meer informatie over deze activiteit [deze sectie](../../automating/using/reconciliation.md)).
   * **[!UICONTROL Save audience]** activiteit: maakt een publiek op basis van het geïmporteerde bestand (zie voor meer informatie over deze activiteit: [deze sectie](../../automating/using/save-audience.md)).

   ![](assets/substitution_uc2.png)

1. Voer de workflow uit en ga naar de **[!UICONTROL Audiences]** om te controleren of het publiek met de gewenste informatie is gemaakt.

   In dit voorbeeld bestaat het publiek uit drie profielen. Elk van deze is gekoppeld aan een vervangend e-mailadres dat de proefdruk ontvangt, met een voorvoegsel voor gebruik op de onderwerpregel van de proefdruk.

   ![](assets/substitution_uc3.png)

### Stap 2: Bouw een werkschema aan doelprofielen en verzend de nieuwsbrief

1. Toevoegen **[!UICONTROL Query]** en **[!UICONTROL Email delivery]** activiteiten, dan vormen hen volgens uw behoeften (zie [Query](../../automating/using/query.md) en [E-maillevering](../../automating/using/email-delivery.md) secties).

   ![](assets/substitution_uc4.png)

1. Voer de workflow uit en controleer of het bericht is voorbereid.

### Stap 3: Vorm het vervangende lusje van het Profiel van het bericht

1. Open de **[!UICONTROL Email delivery]** activiteit. Klik in het berichtdashboard op de knop **[!UICONTROL Audience]** blokkeren.

   ![](assets/substitution_uc5.png)

1. Selecteer de **[!UICONTROL Profile substitutions]** tab, en klik vervolgens op **[!UICONTROL Import from an audience]**.

   ![](assets/substitution_uc6.png)

1. In de **[!UICONTROL Audience]**  selecteert u het publiek dat u in het bestand hebt gemaakt.

   ![](assets/substitution_uc7.png)

1. Definieer het vervangende adres en het voorvoegsel van de onderwerpregel die u wilt gebruiken wanneer u de proefdrukken verzendt.

   Selecteer de optie **[!UICONTROL From audience]** selecteert u vervolgens de kolom in het publiek die de informatie bevat.

   ![](assets/substitution_uc8.png)

1. Klik op de knop **[!UICONTROL Import]**. Profielen van het publiek worden aan de lijst toegevoegd met de bijbehorende vervangende adressen en voorvoegsels van onderwerpregel.

   ![](assets/substitution_uc9.png)

   >[!NOTE]
   >
   >In ons geval zijn alle profielen van het publiek gericht op de **[!UICONTROL Query]** activiteit. Als een van deze profielen geen deel uitmaakte van het berichtdoel, zou het niet aan de lijst worden toegevoegd.

### Stap 4: Een voorvertoning van het bericht weergeven met de beoogde profielen

1. Klik in het berichtendashboard op de momentopname van de inhoud om het bericht te openen in E-mailontwerper.

   ![](assets/substitution_uc10.png)

1. Selecteer de **[!UICONTROL Preview]** tab, en klik vervolgens op **[!UICONTROL Change profile]**.

   ![](assets/substitution_uc_preview.png)

1. Klik op de knop **[!UICONTROL Profile Substitution]** om de eerder toegevoegde vervangingsprofielen weer te geven.

   Selecteer de profielen die u wilt gebruiken voor de voorvertoning en klik op **[!UICONTROL Select]**.

   ![](assets/substitution_uc_selectpreview.png)

1. Er wordt een voorbeeld van het bericht weergegeven. Gebruik de pijlen om tussen de geselecteerde profielen te navigeren.

   ![](assets/substitution_uc_previewprofile.png)

### Stap 5: proefdrukken verzenden

1. Klik in het berichtdashboard op de knop **[!UICONTROL Test]** en bevestig vervolgens.

   ![](assets/substitution_uc_sendproof.png)

1. De proefdrukken worden verzonden volgens wat in is gevormd **[!UICONTROL Profile substitutions]** tab.

   ![](assets/substitution_uc_proofs.png)

## Video over zelfstudie {#video}

In deze video ziet u hoe u e-mailberichten kunt testen met behulp van Profielvervanging.

>[!VIDEO](https://video.tv.adobe.com/v/32368?quality=12)

Er zijn aanvullende Campaign Standard-to-video&#39;s beschikbaar [hier](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=nl).
