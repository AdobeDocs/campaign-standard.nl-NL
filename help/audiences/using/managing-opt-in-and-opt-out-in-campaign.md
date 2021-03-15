---
solution: Campaign Standard
product: campaign
title: Opt-in en opt-out beheren in Campaign
description: Begrijp hoe opt-in en opt-out in Adobe Campaign worden beheerd.
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Doelgroepen
role: Zakelijke praktiserer
level: Intermediair
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 8%

---


# Opt-in en opt-out beheren in Campaign{#managing-opt-in-and-opt-out-in-campaign}

## Optie-in en opt-out beheren vanuit een profiel {#managing-opt-in-and-opt-out-from-a-profile}

Gebruikers kunnen door een operator rechtstreeks vanuit het tabblad Profiel worden in- of uitgeschakeld.**[!UICONTROL General]**

In de sectie **[!UICONTROL No longer contact (on denylist)]** komen de geselecteerde selectievakjes overeen met de kanalen waarvan de gebruiker de optie Weigeren heeft gekozen. Selecteer de kanalen op basis van de behoeften van de gebruiker.

![](assets/optin_landingpage_3.png)

## Optie- en opt-out-bestemmingspagina&#39;s instellen {#setting-up-opt-in-and-opt-out-landing-pages}

Als u gebruikers de mogelijkheid wilt geven om in of uit te gaan, moet u een **[!UICONTROL Profile acquisition]**-bestemmingspagina maken en publiceren. Vervolgens kunnen zij de kanalen selecteren op basis van hun behoeften. Volg de onderstaande stappen om dit te doen.

U kunt ook een **[!UICONTROL Denylist]**-bestemmingspagina instellen waarmee gebruikers kunnen afzien van alle leveringen. Raadpleeg [Een landingspagina instellen om te weigeren bij alle leveringen](#setting-up-a-landing-page-to-opt-out-from-all-deliveries) voor meer informatie.

>[!NOTE]
>
>Landingspagina&#39;s kunnen ook worden gebruikt om servicesabonnement in te schakelen. Raadpleeg [deze pagina](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service) voor meer informatie.

1. Maak een **[!UICONTROL Profile acquisition]**-landingspagina (zie [deze sectie](../../channels/using/getting-started-with-landing-pages.md)).
1. Voeg een selectievakje toe in de inhoud van de bestemmingspagina voor elk gewenst kanaal en koppel het vervolgens vanuit de Campagne-database aan het corresponderende veld.

   ![](assets/optin_landingpage_1.png)

1. Sla de openingspagina op en publiceer deze.
1. Op de landingspagina zijn de selectievakjes al geselecteerd op basis van het profiel **[!UICONTROL General]** tabblad. De gebruiker kan de kanalen naar behoefte selecteren of de selectie ervan opheffen en het formulier verzenden.

   ![](assets/optin_landingpage_2.png)

1. Nadat het formulier is verzonden, wordt het tabblad Profiel **[!UICONTROL General]** bijgewerkt op basis van de selectie van de gebruiker.

   ![](assets/optin_landingpage_3.png)

### Een openingspagina instellen om af te zien van alle leveringen {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

Als u gebruikers de mogelijkheid wilt geven om af te zien van alle leveringen, moet u een **[!UICONTROL Denylist]**-bestemmingspagina maken en publiceren. Raadpleeg [deze pagina](../../channels/using/getting-started-with-landing-pages.md) voor meer informatie over het maken van bestemmingspagina&#39;s.

Wanneer een gebruiker op de koppeling naar de bestemmingspagina klikt, wordt de optie **[!UICONTROL No longer contact (by any channel)]** in het profiel automatisch geselecteerd.

![](assets/blocklisting_allchannels.png)

