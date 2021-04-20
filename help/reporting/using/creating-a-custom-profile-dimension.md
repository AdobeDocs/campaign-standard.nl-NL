---
solution: Campaign Standard
product: campaign
title: Een aangepaste profieldimensie maken
description: Leer hoe u een aangepaste profieldimensie maakt op basis van aangepaste profielgegevens.
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 5%

---


# Een aangepaste profieldimensie maken{#creating-a-custom-profile-dimension}

Rapporten kunnen ook worden gemaakt en beheerd op basis van aangepaste profielgegevens die zijn gemaakt tijdens de uitbreiding van de aangepaste profielbron.

In dit voorbeeld, willen wij het gebied van het douaneprofiel **Loyalty programma&#39;s** tot stand brengen die in drie niveaus zullen worden verdeeld: goud, zilver en brons. Dit aangepaste profiel wordt vervolgens uitgebreid zodat het kan worden gebruikt als een aangepaste profieldimensie in dynamische rapporten.

* [Stap 1: Een nieuw profielveld maken](#step-1--create-a-new-profile-field)
* [Stap 2: De verzendende logboeken uitbreiden met het profielveld](#step-2--extend-the-sending-logs-with-the-profile-field)
* [Stap 3: Een levering maken voor ontvangers die zijn ingeschreven voor het loyaliteitsprogramma](#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [Stap 4: Maak een dynamisch rapport om ontvangers met de dimensie van het aangepaste profiel te filteren](#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## Stap 1: Een nieuw profielveld maken {#step-1--create-a-new-profile-field}

We moeten eerst het nieuwe profielveld **Loyalty program** maken dat het loyaliteitsniveau aan onze ontvangers toewijst: goud, zilver of brons.

>[!NOTE]
>
>De middelen van de douane kunnen slechts door een beheerder worden beheerd.

Dit doet u als volgt:

1. Selecteer in het geavanceerde menu **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** en vervolgens de **[!UICONTROL Profile (profile)]** aangepaste bron.

   ![](assets/custom_profile_1.png)

1. Klik op het tabblad **[!UICONTROL Data structure]** in de categorie **[!UICONTROL Fields]** op de knop **[!UICONTROL Add field]**.

   ![](assets/custom_profile_2.png)

1. Voer **[!UICONTROL Label]**, **[!UICONTROL ID]** in en selecteer de aangepaste bron **[!UICONTROL Type]**. Hier hebben we **[!UICONTROL Text]** geselecteerd omdat ontvangers de keuze zullen hebben tussen goud, zilver en brons.

   ![](assets/custom_profile_3.png)

1. Klik op het pictogram ![](assets/custom_profile_22.png) om het veld te definiëren.

   ![](assets/custom_profile_12.png)

1. Hier, moeten wij de geoorloofde waarden specificeren door **[!UICONTROL Specify a list of authorized valued]** te controleren en elke waarde tot stand te brengen door **[!UICONTROL Create element]** te klikken.

   ![](assets/custom_profile_13.png)

1. Voer **[!UICONTROL Label]** en **[!UICONTROL Value]** in en klik vervolgens **[!UICONTROL Add]**. In dit voorbeeld moeten we de waarde goud, zilver en brons creëren. Klik **[!UICONTROL Confirm]** wanneer gereed.

   ![](assets/custom_profile_14.png)

1. Selecteer het tabblad **[!UICONTROL Screen definition]**. Schakel in de vervolgkeuzelijst **[!UICONTROL Detail screen configuration]** de sectie **[!UICONTROL Add personalized fields]** in om een nieuwe sectie in ons profiel te maken.

   ![](assets/custom_profile_4.png)

1. Klik op de knop **[!UICONTROL Add an element]** om de nieuwe sectie te maken. Selecteer **[!UICONTROL Type]**: **[!UICONTROL Input field]**, **[!UICONTROL Value]** of **[!UICONTROL List]**, dan het gebied om in deze nieuwe sectie toe te voegen.

   ![](assets/custom_profile_5.png)

1. U kunt ook een titel aan uw sectie toevoegen in het veld **[!UICONTROL Customize the title of the section where the fields will be displayed]**.

   Klik **[!UICONTROL Save]** wanneer de configuratie wordt gedaan.

   ![](assets/custom_profile_6.png)

1. Selecteer **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** in het geavanceerde menu om uw aangepaste bron te publiceren.
1. Klik **[!UICONTROL Prepare publication]** dan wanneer de voorbereiding wordt gedaan, klik **[!UICONTROL Publish]** knoop.

   ![](assets/custom_profile_7.png)

Uw nieuwe profielveld kan nu worden gebruikt en geselecteerd door uw ontvangers.

![](assets/custom_profile_8.png)

## Stap 2: De verzendende logboeken uitbreiden met het profielveld {#step-2--extend-the-sending-logs-with-the-profile-field}

Nu uw profielgebied wordt gecreeerd, moeten wij de verzendende logboeken met ons profielgebied uitbreiden om de bijbehorende dimensie van het douaneprofiel in dynamische rapporten tot stand te brengen.

Voordat u het logbestand uitbreidt met ons profielveld, controleert u of het PII-venster is geaccepteerd voor toegang tot het tabblad **[!UICONTROL Sending logs extension]**. Raadpleeg [deze pagina](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) voor meer informatie.

>[!NOTE]
>
>De logboeken kunnen slechts met profielgebieden door beheerder worden uitgebreid.

1. Selecteer in het geavanceerde menu **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** en vervolgens de **[!UICONTROL Profile (profile)]** aangepaste bron.
1. Open de vervolgkeuzelijst **[!UICONTROL Sending logs extension]**.
1. Klik op de knop **[!UICONTROL Create element]**.

   ![](assets/custom_profile_9.png)

1. Selecteer het eerder gemaakte veld en klik op **[!UICONTROL Confirm]**.
1. Schakel **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** in om uw aangepaste profieldimensie te maken.

   ![](assets/custom_profile_10.png)

   Deze optie is alleen beschikbaar als het PII-venster is geaccepteerd. Raadpleeg [deze pagina](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) voor meer informatie.

1. Klik **[!UICONTROL Add]** dan sparen uw douanemiddel.
1. Omdat de aangepaste bron is gewijzigd, moeten we deze publiceren om de nieuwe wijzigingen te implementeren.

   Selecteer **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** in het geavanceerde menu om uw aangepaste bron te publiceren.

1. Klik **[!UICONTROL Prepare publication]** dan wanneer de voorbereiding wordt gedaan, klik **[!UICONTROL Publish]** knoop.

   ![](assets/custom_profile_7.png)

Uw aangepaste profiel is nu beschikbaar als een aangepaste profieldimensie in uw rapporten.

Nu uw veld is gemaakt en het verzenden van logboeken is uitgebreid met dit profielveld, kunt u zich richten op ontvangers in leveringen.

## Stap 3: Een levering maken voor ontvangers die zijn ingeschreven voor het loyaliteitsprogramma {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

Nadat u het profielveld hebt gepubliceerd, kunt u de levering starten. In dit voorbeeld, willen wij elke ontvanger richten die in het loyaliteitsprogramma wordt ingeschreven.

1. Klik op het tabblad **[!UICONTROL Marketing activities]** op **[!UICONTROL Create]** en selecteer **[!UICONTROL Email]**.
1. Kies een **[!UICONTROL Email type]** en voer vervolgens de eigenschappen van uw e-mail in.
1. Om ontvanger te richten die in het loyaliteitsprogramma wordt ingeschreven, sleep en laat vallen de **[!UICONTROL Profiles (attributes)]** activiteit.
1. Selecteer het eerder gemaakte veld in de vervolgkeuzelijst **[!UICONTROL Field]**.

   ![](assets/custom_profile_16.png)

1. Selecteer uw **[!UICONTROL Filter conditions]**. Hier willen we ontvangers aanspreken die deel uitmaken van een van de drie niveaus van het loyaliteitsprogramma.

   ![](assets/custom_profile_17.png)

1. Klik **[!UICONTROL Confirm]** dan wanneer gedaan het filtreren, klik **[!UICONTROL Next]**.
1. Definieer de inhoud van het bericht, de naam van de afzender en het onderwerp en personaliseer deze. Raadpleeg deze [pagina](../../designing/using/designing-content-in-adobe-campaign.md) voor meer informatie over het maken van e-mail.

   Klik vervolgens op **[!UICONTROL Create]**.

1. Als u klaar bent, kunt u een voorbeeld van uw bericht bekijken en uw bericht verzenden. Voor meer informatie over hoe te om uw bericht voor te bereiden en te verzenden, verwijs naar deze [pagina](../../sending/using/preparing-the-send.md).

Zodra uw e-mail correct naar de geselecteerde ontvangers wordt verzonden, kunt u beginnen uw gegevens te filteren en het succes van uw levering met rapporten te volgen.

## Stap 4: Een dynamisch rapport maken om ontvangers met de aangepaste profieldimensie te filteren{#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

Nadat u de levering hebt verzonden, kunt u rapporten splitsen aan de hand van uw aangepaste profieldimensie in de tabel **[!UICONTROL Profile]**.

1. Selecteer op het tabblad **[!UICONTROL Reports]** een rapport uit de doos of klik op de knop **[!UICONTROL Create]** om een rapport helemaal opnieuw te beginnen.

   ![](assets/custom_profile_18.png)

1. Klik in de categorie **[!UICONTROL Dimensions]** op **[!UICONTROL Profile]** en sleep uw aangepaste **Loyalty-programma**-profieldimensie naar uw vrije-vormtabel.

   ![](assets/custom_profile_19.png)

1. Sleep de **[!UICONTROL Processed/Sent]** en **[!UICONTROL Open]** metriek om te beginnen uw gegevens te filtreren.

   ![](assets/custom_profile_20.png)

1. Sleep indien nodig een visualisatie naar de werkruimte.

   ![](assets/custom_profile_21.png)

**Verwant onderwerp:**

* [Gegevens van aangepaste profielen gebruiken om inzichtelijke rapporten te maken](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
