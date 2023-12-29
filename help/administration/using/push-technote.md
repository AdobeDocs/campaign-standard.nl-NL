---
title: Aanstaande wijzigingen in het kanaal voor pushmeldingen
description: Aanstaande wijzigingen in het kanaal voor pushmeldingen
audience: channels
feature: Push
role: Admin
level: Experienced
exl-id: e273b443-7c43-482b-8f86-60ada4b57cbf
source-git-commit: 1d8baca669235be10d373d985ea62f6f014c16f8
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 12%

---

# Aanstaande wijzigingen in het kanaal voor pushmeldingen {#push-upgrade}

Met Campagne kunt u pushmeldingen verzenden op Android- en iOS-apparaten. Om dit te doen, baseert de Campagne zich op de specifieke abonnementsdiensten. In 2024 komt er een versie met enkele belangrijke wijzigingen voor de service FCM (Android Firebase Cloud Messaging). Deze zullen van invloed zijn op uw Adobe Campaign-implementatie. Daarnaast wijzigt de Adobe voor iOS-toepassingen de manier waarop beheerders certificaten kunnen configureren.

## Wat is er veranderd? {#push-changes}

### Android {#push-android}

Als onderdeel van de voortdurende inspanningen van Google om haar diensten te verbeteren, zullen de bestaande FCM API&#39;s worden stopgezet op **20 juni 2024**. Meer informatie over het HTTP-protocol voor Firebase Cloud Messaging vindt u in [Google Firebase-documentatie](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

Adobe Campaign Standard gebruikt momenteel de verouderde HTTP-API&#39;s om Android Push Notification Messages te verzenden. In de komende maanden wordt een upgrade naar de v1-API&#39;s van HTTP uitgevoerd.

### iOS {#push-ios}

De Adobe zal ook Adobe Campaign Standard voor het Kanaal van het Push Bericht van iOS bevorderen en de manier veranderen wij Beheerders toestaan om certificaten voor hun toepassingen van iOS te vormen. Beheerders moeten nu de iOS-certificaten uploaden via de Adobe Campaign Standard-gebruikersinterface.

## Heb je invloed op? {#push-impact}

Als gebruiker van het Campaign Standard, als u pushberichten naar uw publiek verzendt, wordt u beïnvloed.

## Hoe migreren? {#push-migration}

Deze updates vereisen een Campaign Standard bouwt verbetering, aangezien zij de mobiele kanaalconfiguratie en het toestemmingsbeheer beïnvloeden.

Er zullen binnenkort gedetailleerde instructies worden gegeven om een soepel overgangsproces te vergemakkelijken.

Ons klantenondersteuningsteam zal beschikbaar zijn om u tijdens deze overgang bij te staan. We kunnen ook webinars en machtigingssessies organiseren om de technische aspecten en beste praktijken voor de overgang te behandelen.

In de tussentijd is het raadzaam om deze keer uw huidige configuratie en aanpassing in Adobe Campaign Standard te herzien zodat u bereid bent om indien nodig noodzakelijke wijzigingen aan te brengen.

Als u directe zorgen hebt of vragen hebt, aarzel dan niet om contact op te nemen met ons ondersteuningsteam.
