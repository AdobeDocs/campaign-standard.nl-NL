---
title: Direct mail maken
description: Voer de volgende stappen uit om een levering via e-mail te maken in Adobe Campaign.
page-status-flag: never-activated
uuid: 3b1365c4-4ea1-4434-818b-05ff0c9b42c1
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: 5b02227f-9438-4001-bc2f-3d8661d173b3
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 012546e109b085b7ed968bcefa8f76482656ae0d
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 0%

---


# Direct mail maken{#creating-the-direct-mail}

Het maken van een directe postbezorging lijkt veel op het maken van een gewone e-mail. In de volgende stappen wordt de configuratie beschreven die specifiek is voor dit kanaal. Zie Een e-mail [](../../channels/using/creating-an-email.md) maken voor meer informatie over andere opties.

1. Maak een nieuwe direct-maillevering. U kunt er een maken op de Adobe Campaign- [startpagina](../../start/using/interface-description.md#home-page), in een [campagne](../../start/using/marketing-activities.md#creating-a-marketing-activity) of in een lijst met [marketingactiviteiten](../../start/using/programs-and-campaigns.md#creating-a-campaign).

   >[!NOTE]
   >
   >U kunt ook direct-mailactiviteiten toevoegen aan een workflow. Raadpleeg de handleiding [Workflows](../../automating/using/direct-mail-delivery.md) voor meer informatie.

   ![](assets/direct_mail_1.png)

1. Kies de uit-van-de-doos sjabloon of één van uw eigen malplaatjes. **[!UICONTROL Direct mail]** Raadpleeg de sectie [Sjablonen](../../start/using/marketing-activity-templates.md) beheren voor meer informatie over sjablonen.

   ![](assets/direct_mail_2.png)

1. Voer de algemene eigenschappen van de levering in.

   ![](assets/direct_mail_3.png)

1. Definieer het publiek dat u wilt opnemen in het extractiebestand en de test- en overvulprofielen. Zie [Het directe-mailpubliek](../../channels/using/defining-the-direct-mail-audience.md)definiëren.

   ![](assets/direct_mail_4.png)

   >[!NOTE]
   >
   >De definitie van het publiek lijkt sterk op het definiëren van een normaal e-mailpubliek. Zie [Soorten publiek](../../audiences/using/creating-audiences.md)maken.

1. Bewerk de inhoud van het bestand: kolommen die moeten worden opgenomen voor elk profiel, elke bestandsstructuur, elke kop- en voettekst. Zie [De inhoud](../../channels/using/defining-the-direct-mail-content.md)voor directe e-mail definiëren.

   ![](assets/direct_mail_5.png)

1. Klik op de **[!UICONTROL Schedule]** sectie van het leveringsdashboard om de contactdatum te bepalen. Voor direct mail, is de contactdatum verplicht. Voor meer informatie, verwijs naar het [Plannen van verzenden](../../sending/using/about-scheduling-messages.md).

   ![](assets/direct_mail_8.png)

1. Als u testprofielen hebt toegevoegd (zie test- en overvulprofielen [](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)toevoegen), kunt u de levering testen voordat u het definitieve bestand voorbereidt. Hiermee kunt u een voorbeeldbestand maken dat alleen de geselecteerde testprofielen bevat.

   Klik op **[!UICONTROL Test]** om het voorbeeldbestand te genereren. Klik op **[!UICONTROL Summary]**, in de linkerbovenhoek en selecteer **[!UICONTROL Proofs]**. Selecteer de proefdruk in het linkergedeelte van het scherm en klik op **[!UICONTROL Download file]**.

   >[!NOTE]
   >
   >De **[!UICONTROL Export]** rol is vereist om Adobe Campaign in staat te stellen het bestand te exporteren en beschikbaar te maken voor downloaden. Neem contact op met uw beheerder.

   ![](assets/direct_mail_19.png)

1. Nadat u de inhoud, het publiek en de contactdatum van de levering hebt gedefinieerd, klikt u op de **[!UICONTROL Prepare]** knop op het dashboard voor de levering.

   ![](assets/direct_mail_16.png)

   Er worden typologische regels toegepast. Alle niet-opgegeven postadressen worden bijvoorbeeld van het doel uitgesloten. Daarom moet u ervoor zorgen dat u het **[!UICONTROL Address specified]** vakje in de informatie van uw profielen (zie [Aanbevelingen](../../channels/using/about-direct-mail.md#recommendations)) hebt gecontroleerd. Als u een waarde hebt gedefinieerd **[!UICONTROL Maximum volume of message]** in de eigenschappen direct mail of op sjabloonniveau, wordt deze ook hier toegepast.

   ![](assets/direct_mail_25.png)

   >[!NOTE]
   >
   >U kunt algemene regels voor vermoeidheid tussen kanalen instellen die overgevulde profielen automatisch uitsluiten van campagnes. Zie [Vermoeidheidsregels](../../sending/using/fatigue-rules.md).

1. Klik op **[!UICONTROL Explore file]** om een voorvertoning van de eerste 100 regels van het bestand weer te geven.

   ![](assets/direct_mail_18.png)

   Het volledige bestand kan lokaal worden gedownload in het linkergedeelte van het scherm. Wanneer u het bestand downloadt, wordt een logbestandvermelding in het **[!UICONTROL Export audits]** menu gegenereerd. Raadpleeg voor meer informatie over exportaudits de sectie [Audit export](../../administration/using/auditing-export-logs.md) .

   >[!NOTE]
   >
   >De **[!UICONTROL Export]** rol is vereist om Adobe Campaign in staat te stellen het bestand te exporteren en beschikbaar te maken voor downloaden. Neem contact op met uw beheerder.

   Als u de inhoud van de levering moet wijzigen, hoeft u alleen op de **[!UICONTROL Regenerate file]** knop te klikken om rekening te houden met de wijziging. De voorbereiding hoeft niet opnieuw te worden doorlopen.

   ![](assets/direct_mail_21.png)

1. Om te bevestigen dat het dossier definitief is, klik op **[!UICONTROL Confirm]** in het leveringsdashboard.

   ![](assets/direct_mail_20.png)

U kunt het extractiebestand nu naar uw directe-mailprovider verzenden. Hiervoor hebt u verschillende opties:

* Verzend het via een gewone e-mail, met het bijgevoegde dossier
* Verzenden via campagne: direct mail uitvoeren binnen een [campagneworkflow](../../automating/using/direct-mail-delivery.md) en een bericht toevoegen **[!UICONTROL Transfer file]** om het bestand bijvoorbeeld via FTP te verzenden. Zie Bestand [](../../automating/using/transfer-file.md)overbrengen.

De leverancier wint de lijst van onjuiste adressen terug en verzendt deze informatie naar Adobe Campaign die automatisch aan de bloklijst de onjuiste adressen toevoegt. Zie [Terug naar afzender](../../channels/using/return-to-sender.md).
