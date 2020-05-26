---
title: Profielen maken
description: Leer hoe u profielen maakt en gegevens verzamelt op uw contactpersonen, met behulp van API's, importmogelijkheden, online aankopen, automatische of handmatige updates.
page-status-flag: never-activated
uuid: a5f5a58a-e798-400f-8648-05dc843d5557
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: 4ab8a984-f898-4fff-ad8c-ed8f95362f96
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 0%

---


# Profielen maken{#creating-profiles}

In Adobe Campagne, worden de profielen gebruikt door gebrek om het belangrijkste doel van berichten te bepalen.

Als u een profiel wilt maken of bijwerken in Campagne, kunt u:

* Een profiellijst importeren vanuit een bestand via een [workflow](../../automating/using/creating-import-workflow-templates.md)
* Gegevens online verzamelen via [bestemmingspagina&#39;s](../../channels/using/getting-started-with-landing-pages.md)
* Bulk maken via [REST API](../../api/using/get-started-apis.md)
* Profielen synchroniseren met [Microsoft Dynamics](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* Gegevens invoeren met de grafische interfaceschermen, zoals hieronder wordt uitgelegd

Voer bijvoorbeeld de volgende stappen uit om een nieuw profiel rechtstreeks in de gebruikersinterface te maken:

1. Klik op de startpagina van Adobe Campagne op de **Klantenprofielkaart** of op het tabblad **Profielen** om de lijst met profielen te openen.

   ![](assets/profile_creation_1.png)

1. Klik vervolgens **[!UICONTROL Create]**.

   ![](assets/profile_creation.png)

1. Voer de profielgegevens in.

   ![](assets/profile_creation1.png)

   * De contactgegevens, zoals voornaam, achternaam, geslacht, geboortedatum, foto, voorkeurstaal (voor [meertalige e-mails](../../channels/using/creating-a-multilingual-email.md)), helpen de leveringen beter te personaliseren.
   * Het profiel **[!UICONTROL Time zone]** wordt gebruikt om leveringen in de tijdzone van het profiel te verzenden. For more on this, refer to this [section](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).
   * In de **[!UICONTROL Channels]** categorie met het e-mailadres, het mobiele telefoonnummer en de optie om te weigeren, kunt u zien welk kanaal het profiel kan worden bereikt.
   * De **[!UICONTROL No longer contact]** categorie wordt bijgewerkt zodra het profiel zich afmeldt bij een kanaal.
   * De **[!UICONTROL Address]** categorie bevat het postadres dat moet worden ingevuld en de **[!UICONTROL Address specified]** optie om [direct mail](../../channels/using/about-direct-mail.md) naar dit profiel te verzenden. Als de **[!UICONTROL Address specified]** optie niet is ingeschakeld, wordt dit profiel uitgesloten van elke direct-maillevering.
   * De **[!UICONTROL Access authorization]** categorie geeft de organisatie-eenheden van het profiel aan (voor het [beheren van machtigingen](../../administration/using/about-access-management.md)). Zie ook [Partitioneringsprofielen](../../administration/using/organizational-units.md#partitioning-profiles).
   * De **[!UICONTROL Traceability]** categorie wordt automatisch bijgewerkt met informatie over de gebruiker die het profiel heeft gemaakt of gewijzigd.

1. Klik **[!UICONTROL Create]** om het profiel op te slaan.

Het profiel wordt nu in de lijst weergegeven.

>[!NOTE]
>
>Het is ook mogelijk profielen te maken met de standaard-API van Adobe Campagne. Raadpleeg de [desbetreffende documentatie](../../api/using/creating-profiles.md)voor meer informatie hierover.

Profielen kunnen ook worden gepartitioneerd op basis van hun organisatie-eenheden. Raadpleeg de sectie [Partitioneringsprofielen](../../administration/using/organizational-units.md#partitioning-profiles) voor informatie over het toevoegen van organisatorische velden aan uw profielen.

>[!NOTE]
>
>Het voorkeurstaalveld wordt gebruikt om de taal te selecteren bij het verzenden van meertalige berichten. Voor meer informatie over de meertalige berichten [verwijs naar deze pagina](../../channels/using/creating-a-multilingual-email.md).

**Verwante onderwerpen:**

* [Stapsgewijze handleiding voor het landen van pagina](../../channels/using/getting-started-with-landing-pages.md) &#39;s
* [Video over het importeren van profielen](https://video.tv.adobe.com/v/24993?captions=dut)
