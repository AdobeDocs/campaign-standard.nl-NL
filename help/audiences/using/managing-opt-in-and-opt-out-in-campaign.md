---
title: Opt-in en opt-out beheren in Campaign
description: Begrijp hoe opt-in en opt-out in Adobe Campaign worden beheerd.
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Intermediate
exl-id: 4aeb90c5-f5b5-4cfe-93fb-2fd01fb8d70e
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 8%

---

# Opt-in en opt-out beheren in Campaign{#managing-opt-in-and-opt-out-in-campaign}

## Optie en opt-out beheren voor een profiel {#managing-opt-in-and-opt-out-from-a-profile}

Gebruikers kunnen door een operator rechtstreeks vanuit het profiel in- of uitschakelen **[!UICONTROL General]** tab.

In de **[!UICONTROL No longer contact (on denylist)]** , komen de geselecteerde selectievakjes overeen met de kanalen waarvan de gebruiker de optie Weigeren heeft gekozen. Selecteer de kanalen op basis van de behoeften van de gebruiker.

![](assets/optin_landingpage_3.png)

## Optie- en opt-out-bestemmingspagina&#39;s instellen {#setting-up-opt-in-and-opt-out-landing-pages}

Als u gebruikers de mogelijkheid wilt geven zich aan te melden of te weigeren, moet u een **[!UICONTROL Profile acquisition]** openingspagina. Vervolgens kunnen zij de kanalen selecteren op basis van hun behoeften. Volg de onderstaande stappen om dit te doen.

U kunt ook een **[!UICONTROL Denylist]** landingspagina waarmee gebruikers kunnen afzien van alle leveringen. Raadpleeg voor meer informatie hierover [Een landingspagina instellen om af te zien van alle leveringen](#setting-up-a-landing-page-to-opt-out-from-all-deliveries).

>[!NOTE]
>
>Landingspagina&#39;s kunnen ook worden gebruikt om servicesabonnement in te schakelen. Raadpleeg [deze pagina](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service) voor meer informatie.

1. Een **[!UICONTROL Profile acquisition]** openingspagina (zie [deze sectie](../../channels/using/getting-started-with-landing-pages.md)).
1. Voeg een selectievakje toe in de inhoud van de bestemmingspagina voor elk gewenst kanaal en koppel het vervolgens vanuit de Campagne-database aan het corresponderende veld.

   ![](assets/optin_landingpage_1.png)

1. Sla de openingspagina op en publiceer deze.
1. Op de bestemmingspagina zijn de selectievakjes al geselecteerd volgens het profiel **[!UICONTROL General]** tab. De gebruiker kan de kanalen naar behoefte selecteren of de selectie ervan opheffen en het formulier verzenden.

   ![](assets/optin_landingpage_2.png)

1. Zodra het formulier is verzonden, wordt het profiel **[!UICONTROL General]** wordt bijgewerkt op basis van de selectie van de gebruiker.

   ![](assets/optin_landingpage_3.png)

### Een landingspagina instellen om af te zien van alle leveringen {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

Als u gebruikers de mogelijkheid wilt geven zich af te melden voor alle leveringen, moet u een **[!UICONTROL Denylist]** openingspagina. Voor meer informatie over het maken van bestemmingspagina&#39;s raadpleegt u [deze pagina](../../channels/using/getting-started-with-landing-pages.md).

Wanneer een gebruiker op de koppeling naar de bestemmingspagina klikt, wordt de **[!UICONTROL No longer contact (by any channel)]** in het profiel wordt automatisch geselecteerd.

![](assets/blocklisting_allchannels.png)
