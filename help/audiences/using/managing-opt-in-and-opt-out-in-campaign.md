---
title: Opt-in en opt-out beheren in Campaign
description: Begrijp hoe opt-in en opt-out in Adobe Campaign worden beheerd.
page-status-flag: never-activated
uuid: aa1801ec-562b-420e-8d79-c07d066b7b1a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
discoiquuid: 6b5680f2-bba9-453e-a0d5-8ca69dd02001
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1b1fb4a0dc0f7881e24e10f8ac171feab2ac8cba
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 6%

---


# Opt-in en opt-out beheren in Campaign{#managing-opt-in-and-opt-out-in-campaign}

## Optie en opt-out beheren voor een profiel {#managing-opt-in-and-opt-out-from-a-profile}

Gebruikers kunnen door een operator rechtstreeks vanuit het **[!UICONTROL General]** tabblad Profiel in- of uitschakelen.

In de **[!UICONTROL No longer contact (on denylist)]** sectie komen de geselecteerde selectievakjes overeen met de kanalen waarvan de gebruiker de optie Weigeren heeft gekozen. Selecteer de kanalen op basis van de behoeften van de gebruiker.

![](assets/optin_landingpage_3.png)

## Optie- en opt-out-bestemmingspagina&#39;s instellen {#setting-up-opt-in-and-opt-out-landing-pages}

Als u gebruikers de mogelijkheid wilt geven om in of uit te gaan, moet u een **[!UICONTROL Profile acquisition]** bestemmingspagina maken en publiceren. Vervolgens kunnen zij de kanalen selecteren op basis van hun behoeften. Volg de onderstaande stappen om dit te doen.

U kunt ook een **[!UICONTROL Denylist]** openingspagina instellen waarmee gebruikers zich kunnen afmelden voor alle leveringen. Raadpleeg voor meer informatie een [bestemmingspagina instellen om te weigeren van alle leveringen](#setting-up-a-landing-page-to-opt-out-from-all-deliveries).

>[!NOTE]
>
>Landingspagina&#39;s kunnen ook worden gebruikt om servicesabonnement in te schakelen. For more on this, refer to [this page](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service).

1. Maak een **[!UICONTROL Profile acquisition]** openingspagina (zie [deze sectie](../../channels/using/getting-started-with-landing-pages.md)).
1. Voeg een selectievakje toe in de inhoud van de bestemmingspagina voor elk gewenst kanaal en koppel het vervolgens vanuit de Campagne-database aan het corresponderende veld.

   ![](assets/optin_landingpage_1.png)

1. Sla de openingspagina op en publiceer deze.
1. Op de openingspagina zijn de selectievakjes al geselecteerd op basis van het **[!UICONTROL General]** tabblad Profiel. De gebruiker kan de kanalen naar behoefte selecteren of de selectie ervan opheffen en het formulier verzenden.

   ![](assets/optin_landingpage_2.png)

1. Nadat het formulier is verzonden, wordt het tabblad Profiel **[!UICONTROL General]** bijgewerkt op basis van de selectie van de gebruiker.

   ![](assets/optin_landingpage_3.png)

### Een landingspagina instellen om af te zien van alle leveringen {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

Als u gebruikers de mogelijkheid wilt geven zich af te melden voor alle leveringen, moet u een **[!UICONTROL Denylist]** bestemmingspagina maken en publiceren. Raadpleeg [deze pagina](../../channels/using/getting-started-with-landing-pages.md)voor meer informatie over het maken van bestemmingspagina&#39;s.

Wanneer een gebruiker op de koppeling naar de bestemmingspagina klikt, wordt de **[!UICONTROL No longer contact (by any channel)]** optie in het profiel automatisch geselecteerd.

![](assets/blocklisting_allchannels.png)

