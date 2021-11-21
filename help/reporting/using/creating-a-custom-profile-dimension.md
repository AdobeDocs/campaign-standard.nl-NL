---
title: Een aangepaste profieldimensie maken
description: Leer hoe u een aangepaste profieldimensie maakt op basis van aangepaste profielgegevens.
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: 98516af1-d4dd-4c1f-b360-f19208c22f82
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 5%

---

# Een aangepaste profieldimensie maken{#creating-a-custom-profile-dimension}

Rapporten kunnen ook worden gemaakt en beheerd op basis van aangepaste profielgegevens die zijn gemaakt tijdens de uitbreiding van de aangepaste profielbron.

In dit voorbeeld willen we het veld Aangepast profiel maken **Loyaliteitsprogramma&#39;s** die in drie niveaus worden onderverdeeld: goud, zilver en brons. Dit aangepaste profiel wordt vervolgens uitgebreid zodat het kan worden gebruikt als een aangepaste profieldimensie in dynamische rapporten.

* [Stap 1: Een nieuw profielveld maken](#step-1--create-a-new-profile-field)
* [Stap 2: De verzendende logboeken uitbreiden met het profielveld](#step-2--extend-the-sending-logs-with-the-profile-field)
* [Stap 3: Een levering maken voor ontvangers die zijn ingeschreven voor het loyaliteitsprogramma](#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [Stap 4: Maak een dynamisch rapport om ontvangers met de dimensie van het aangepaste profiel te filteren](#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## Stap 1: Een nieuw profielveld maken {#step-1--create-a-new-profile-field}

We moeten eerst het nieuwe profielveld maken **Loyaliteitsprogramma** dat zal het loyaliteitsniveau aan onze ontvangers toewijzen : goud, zilver of brons.

>[!NOTE]
>
>De middelen van de douane kunnen slechts door een beheerder worden beheerd.

Dit doet u als volgt:

1. Selecteer in het menu Geavanceerd de optie **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** dan de **[!UICONTROL Profile (profile)]** aangepaste bron.

   ![](assets/custom_profile_1.png)

1. Van de **[!UICONTROL Data structure]** tabblad, in het dialoogvenster **[!UICONTROL Fields]** categorie, klikt u op de **[!UICONTROL Add field]** knop.

   ![](assets/custom_profile_2.png)

1. Voer de **[!UICONTROL Label]**, **[!UICONTROL ID]** en selecteer de aangepaste bron **[!UICONTROL Type]**. Hier, hebben wij geselecteerd **[!UICONTROL Text]** aangezien de begunstigden de keuze zullen hebben tussen goud , zilver en brons .

   ![](assets/custom_profile_3.png)

1. Klik op de knop ![](assets/custom_profile_22.png) pictogram om het veld te definiëren.

   ![](assets/custom_profile_12.png)

1. Hier moeten we de toegestane waarden specificeren door te controleren **[!UICONTROL Specify a list of authorized valued]** en maak elke waarde door op **[!UICONTROL Create element]**.

   ![](assets/custom_profile_13.png)

1. Voer de **[!UICONTROL Label]** en **[!UICONTROL Value]** klik vervolgens op **[!UICONTROL Add]**. In dit voorbeeld moeten we de waarde goud, zilver en brons creëren. Klik op **[!UICONTROL Confirm]** wanneer u klaar bent met de configuratie.

   ![](assets/custom_profile_14.png)

1. Selecteer het tabblad **[!UICONTROL Screen definition]**. In de **[!UICONTROL Detail screen configuration]** vervolgkeuzelijst, controleren **[!UICONTROL Add personalized fields]** om een nieuwe sectie in ons profiel te maken.

   ![](assets/custom_profile_4.png)

1. Klik op de knop **[!UICONTROL Add an element]** om uw nieuwe sectie te maken. Selecteer **[!UICONTROL Type]**: **[!UICONTROL Input field]**, **[!UICONTROL Value]** of **[!UICONTROL List]** en vervolgens het veld dat moet worden toegevoegd in deze nieuwe sectie.

   ![](assets/custom_profile_5.png)

1. U kunt ook een titel aan uw sectie toevoegen in het veld **[!UICONTROL Customize the title of the section where the fields will be displayed]**.

   Klikken **[!UICONTROL Save]** wanneer de configuratie is voltooid.

   ![](assets/custom_profile_6.png)

1. Selecteer in het menu Geavanceerd de optie **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** om uw aangepaste bron te publiceren.
1. Klikken **[!UICONTROL Prepare publication]** Klik vervolgens wanneer de voorbereiding is voltooid op de knop **[!UICONTROL Publish]** knop.

   ![](assets/custom_profile_7.png)

Uw nieuwe profielveld kan nu worden gebruikt en geselecteerd door uw ontvangers.

![](assets/custom_profile_8.png)

## Stap 2: De verzendende logboeken uitbreiden met het profielveld {#step-2--extend-the-sending-logs-with-the-profile-field}

Nu uw profielgebied wordt gecreeerd, moeten wij de verzendende logboeken met ons profielgebied uitbreiden om de bijbehorende dimensie van het douaneprofiel in dynamische rapporten tot stand te brengen.

Voordat u het logboek uitbreidt met ons profielveld, controleert u of het PII-venster is geaccepteerd voor toegang tot het **[!UICONTROL Sending logs extension]** tab. Raadpleeg [deze pagina](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) voor meer informatie.

>[!NOTE]
>
>De logboeken kunnen slechts met profielgebieden door beheerder worden uitgebreid.

1. Selecteer in het menu Geavanceerd de optie **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** dan de **[!UICONTROL Profile (profile)]** aangepaste bron.
1. Open de **[!UICONTROL Sending logs extension]** vervolgkeuzelijst.
1. Klik op de knop **[!UICONTROL Create element]**.

   ![](assets/custom_profile_9.png)

1. Selecteer uw eerder gemaakte veld en klik op **[!UICONTROL Confirm]**.
1. Controleren **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** om uw dimensie van het douaneprofiel tot stand te brengen.

   ![](assets/custom_profile_10.png)

   Deze optie is alleen beschikbaar als het PII-venster is geaccepteerd. Raadpleeg [deze pagina](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) voor meer informatie.

1. Klikken **[!UICONTROL Add]** sla uw aangepaste bron op.
1. Omdat de aangepaste bron is gewijzigd, moeten we deze publiceren om de nieuwe wijzigingen te implementeren.

   Selecteer in het menu Geavanceerd de optie **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** om uw aangepaste bron te publiceren.

1. Klikken **[!UICONTROL Prepare publication]** Klik vervolgens wanneer de voorbereiding is voltooid op de knop **[!UICONTROL Publish]** knop.

   ![](assets/custom_profile_7.png)

Uw aangepaste profiel is nu beschikbaar als een aangepaste profieldimensie in uw rapporten.

Nu uw veld is gemaakt en het verzenden van logboeken is uitgebreid met dit profielveld, kunt u zich richten op ontvangers in leveringen.

## Stap 3: Een levering maken voor ontvangers die zijn ingeschreven voor het loyaliteitsprogramma {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

Nadat u het profielveld hebt gepubliceerd, kunt u de levering starten. In dit voorbeeld, willen wij elke ontvanger richten die in het loyaliteitsprogramma wordt ingeschreven.

1. Klik op het tabblad **[!UICONTROL Marketing activities]** op **[!UICONTROL Create]** en selecteer **[!UICONTROL Email]**.
1. Kies een **[!UICONTROL Email type]** Voer vervolgens de eigenschappen van uw e-mail in.
1. Om ontvanger te richten die in het loyaliteitsprogramma wordt ingeschreven, sleep en laat vallen **[!UICONTROL Profiles (attributes)]** activiteit.
1. Selecteer het veld dat u eerder hebt gemaakt in het menu **[!UICONTROL Field]** vervolgkeuzelijst.

   ![](assets/custom_profile_16.png)

1. Selecteer uw **[!UICONTROL Filter conditions]**. Hier willen we ontvangers aanspreken die deel uitmaken van een van de drie niveaus van het loyaliteitsprogramma.

   ![](assets/custom_profile_17.png)

1. Klikken **[!UICONTROL Confirm]** klik vervolgens, wanneer u klaar bent met filteren, op **[!UICONTROL Next]**.
1. Definieer de inhoud van het bericht, de naam van de afzender en het onderwerp en personaliseer deze. Zie deze voor meer informatie over het maken van e-mail [page](../../designing/using/designing-content-in-adobe-campaign.md).

   Klik vervolgens op **[!UICONTROL Create]**.

1. Als u klaar bent, kunt u een voorbeeld van uw bericht bekijken en uw bericht verzenden. Voor meer informatie over het voorbereiden en verzenden van uw bericht raadpleegt u deze [page](../../sending/using/preparing-the-send.md).

Zodra uw e-mail correct naar de geselecteerde ontvangers wordt verzonden, kunt u beginnen uw gegevens te filteren en het succes van uw levering met rapporten te volgen.

## Stap 4: Maak een dynamisch rapport om ontvangers met de dimensie van het aangepaste profiel te filteren {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

Nadat u de levering hebt verzonden, kunt u rapporten afbreken met behulp van de aangepaste profieldimensie van de **[!UICONTROL Profile]** tabel.

1. Van de **[!UICONTROL Reports]** selecteert u een rapport dat buiten de doos valt of klikt u op de knop **[!UICONTROL Create]** om een geheel nieuwe knop te starten.

   ![](assets/custom_profile_18.png)

1. In de **[!UICONTROL Dimensions]** categorie, klikt u op **[!UICONTROL Profile]** en sleep uw aangepaste **Loyaliteitsprogramma** profieldimensie aan uw vrije lijst.

   ![](assets/custom_profile_19.png)

1. Sleep de **[!UICONTROL Processed/Sent]** en **[!UICONTROL Open]** metriek om te beginnen met het filteren van uw gegevens.

   ![](assets/custom_profile_20.png)

1. Sleep indien nodig een visualisatie naar de werkruimte.

   ![](assets/custom_profile_21.png)

**Verwant onderwerp:**

* [Gegevens van aangepaste profielen gebruiken om inzichtelijke rapporten te maken](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
