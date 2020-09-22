---
title: Indicatoren berekenen
description: Begrijp de resultaten van uw rapporten met een lijst van elke metrische formule.
page-status-flag: never-activated
uuid: dfbc9d7e-62db-4e77-bb8e-0ac826ec7333
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: about-reporting
discoiquuid: 45b11631-6b32-4074-8c8d-affd06407810
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1b1fb4a0dc0f7881e24e10f8ac171feab2ac8cba
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 2%

---


# Indicatoren berekenen{#indicator-calculation}

>[!NOTE]
>
>Om hoge volumes en real-time analyses beter te verwerken en te beheren, gebruikt de dynamische rapportering benaderende aggregaties voor verschillende telramingen. De geschatte samenvoegingen bieden een beperkt geheugengebruik en zijn vaak sneller dan nauwkeurige berekeningen.

De onderstaande tabellen bevatten een lijst met indicatoren die in de verschillende verslagen worden gebruikt en de berekeningsformule, afhankelijk van het leveringstype.

## E-maillevering {#email-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Label</strong> <br /> </th> 
   <th> <strong>Veldnaam</strong> <br /> </th> 
   <th> <strong>Indicatorberekeningsformule</strong> <br /> </th> 
   <th> <strong>Opmerkingen</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Account uitgeschakeld<br /> </td> 
   <td> @disabled<br /> </td> 
   <td> count(@failureReason=4)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Op lijst van afgewezen personen<br /> </td> 
   <td> @blacklist<br /> </td> 
   <td> count(@failureReason=8, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Lijst van afgewezen personen<br /> </td> 
   <td> @rateBlacklist<br /> </td> 
   <td> @blacklist/@sent<br /> </td> 
   <td> De noemer voor de berekening van de rente is gebaseerd op het aantal verzonden (Geleverd + Bounces).<br /> </td> 
  </tr> 
  <tr> 
   <td> Bounces + fouten<br /> </td> 
   <td> @bounces<br /> </td> 
   <td> count(@status=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Stuiteren + foutenfrequentie<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> @bounces/@sent<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Klik op<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> count(@trackingUrlType=1, 10 of 11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Klikken tot snelheid<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> @uniqueclicks/@bezorgd<br /> </td> 
   <td> De noemer voor de berekening van het tarief is gebaseerd op slechts Geleverd.<br /> </td> 
  </tr> 
  <tr> 
   <td> Geleverd<br /> </td> 
   <td> @loaded<br /> </td> 
   <td> count(@status=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Afgeleverde rente<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> @delivery/@sent<br /> </td> 
   <td> De noemer voor de berekening van de rente is gebaseerd op het aantal verzonden (Geleverd + Bounces).<br /> </td> 
  </tr> 
  <tr> 
   <td> Harde vlekken<br /> </td> 
   <td> @hardBounces<br /> </td> 
   <td> count(@failureType=2 EN @failureReason=8)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Fel-stallatiesnelheid<br /> </td> 
   <td> @rateHardBounces<br /> </td> 
   <td> @hardBounces/@sent<br /> </td> 
   <td> De noemer voor de berekening van de rente is gebaseerd op het aantal verzonden (Geleverd + Bounces).<br /> </td> 
  </tr> 
  <tr> 
   <td> Ongeldig domein<br /> </td> 
   <td> @invalidDomain<br /> </td> 
   <td> count(@failureReason=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Postbus vol<br /> </td> 
   <td> @mailBoxFull<br /> </td> 
   <td> count(@failureReason=5)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Pagina spiegelen<br /> </td> 
   <td> @mirrorPage<br /> </td> 
   <td> count(@trackingUrlType=6)<br /> </td> 
   <td> De noemer voor de berekening van het tarief is gebaseerd op slechts Geleverd.<br /> </td> 
  </tr> 
  <tr> 
   <td> Paginasnelheid spiegelen<br /> </td> 
   <td> @rateMirrorPage<br /> </td> 
   <td> @mirrorPage/@loaded<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Niet verbonden<br /> </td> 
   <td> @notConnected<br /> </td> 
   <td> count(@failureReason=6)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Open<br /> </td> 
   <td> @uniqueOpens<br /> </td> 
   <td> count(@trackingUrlType=2 + unique(@trackingUrlType=1,2,3,6,10,11) - unique(@trackingUrlType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Open rate<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> @open/@loaded<br /> </td> 
   <td> De noemer voor de berekening van het tarief is gebaseerd op slechts Geleverd.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quarantine<br /> </td> 
   <td> @quarantaine<br /> </td> 
   <td> isQuarantine=true<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Quarantaine<br /> </td> 
   <td> @rateQuarantine<br /> </td> 
   <td> @quarantaine/@verzonden<br /> </td> 
   <td> De noemer voor de berekening van de rente is gebaseerd op het aantal verzonden (Geleverd + Bounces).<br /> </td> 
  </tr>
  <tr> 
   <td> Geweigerd<br /> </td> 
   <td> @geweigerd<br /> </td> 
   <td> count(@failureReason=20, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Geweigerde snelheid<br /> </td> 
   <td> @rateRejected<br /> </td> 
   <td> @geweigerd/@verzonden<br /> </td> 
   <td> De noemer voor de berekening van de rente is gebaseerd op het aantal verzonden (Geleverd + Bounces).<br /> </td> 
  </tr> 
  <tr> 
   <td> Verwerkt/verzonden<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @delivery + @bounces<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Zachte stuit<br /> </td> 
   <td> @softBounces<br /> </td> 
   <td> count(@failureType=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Zachte stuitsnelheid<br /> </td> 
   <td> @rateSoftBounces<br /> </td> 
   <td> @softBounces/@sent<br /> </td> 
   <td> De noemer voor de berekening van de rente is gebaseerd op het aantal verzonden (Geleverd + Bounces).<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke klikken<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> De unieke kliks wordt berekend gebruikend de concepten van de Schets. For more on this, refer to this <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">example</a>.<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Unieke openingen<br /> </td> 
   <td> @uniqueOpenen<br /> </td> 
   <td> unique(@trackingUrlType=1,2,3,6,10,11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Onbereikbaar <br /> </td> 
   <td> @onbereikbaar<br /> </td> 
   <td> count(@failureReason=3)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Abonnement opzeggen<br /> </td> 
   <td> @unsubscribes<br /> </td> 
   <td> count(@trackingUrlType=3)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Abonnement opzeggen<br /> </td> 
   <td> @rateUnsubscribes<br /> </td> 
   <td> @unsubscribes/@loaded<br /> </td> 
   <td> De noemer voor de berekening van het tarief is gebaseerd op slechts Geleverd.<br /> </td> 
  </tr> 
  <tr> 
   <td> Gebruiker onbekend<br /> </td> 
   <td> @unknownUser<br /> </td> 
   <td> count(@failureReason=1)<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

## Levering via pushmelding {#push-notification-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Label</strong> <br /> </th> 
   <th> <strong>Veldnaam</strong> <br /> </th> 
   <th> <strong>Indicatorberekeningsformule</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Verwerkt/verzonden<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
  </tr> 
  <tr> 
   <td> Geleverd<br /> </td> 
   <td> @loaded<br /> </td> 
   <td> @count(status=bezorgd)<br /> </td> 
  </tr> 
  <tr> 
   <td> Afgeleverde rente<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> (@bezorgd/@verzonden)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Stuiteren + foutenfrequentie<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> (@bezorgd/@verzonden)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Open<br /> </td> 
   <td> @opens<br /> </td> 
   <td> @count(status=open)<br /> </td> 
  </tr> 
  <tr> 
   <td> Open rate<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> (@opent/@bezorgd)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke openingen<br /> </td> 
   <td> @uniqueOpenen<br /> </td> 
   <td> Unieke opent wordt berekend gebruikend de concepten van Schets van unieke RecipientIds. For more on this, refer to this <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">example</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressies<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=bezorgd)<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke afbeeldingen<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view)<br /> </td> 
  </tr> 
  <tr> 
   <td> Klik op<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> @count(status=interact)<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke klikken<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> De unieke kliks wordt berekend gebruikend de concepten van de Schets. For more on this, refer to this <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">example</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Klikken tot snelheid<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> (@interact/@bezorgd)*100<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Levering in de app {#in-app-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Label</strong> <br /> </th> 
   <th> <strong>Veldnaam</strong> <br /> </th> 
   <th> <strong>Indicatorberekeningsformule</strong> <br /> </th> 
   <th> <strong>Opmerkingen</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Verwerkt/verzonden<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
   <td> sent=delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Geleverd<br /> </td> 
   <td> @loaded<br /> </td> 
   <td> @count(status=bezorgd)<br /> </td> 
   <td> delivery=sent<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressies<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=view) of @count(status=knop 1 klik + knop 2 klik + ontslag)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Unieke afbeeldingen<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view)<br /> </td> 
   <td> Voor <span class="uicontrol">doelgebruikers die zijn gebaseerd op hun sjabloon Campagneprofiel (inAppProfile)</span> , is gebruiker = Ontvangersidentiteitskaart<br /> Voor <span class="uicontrol">Doel: alle gebruikers van een mobiele app (inAppBroadcast)</span> en <span class="uicontrol">doelgebruikers op basis van hun sjablonen voor hun mobiele profiel (inApp)</span> . Dit is de gebruiker = MC-id of equivalent die een unieke combinatie van gebruiker, mobiele app en apparaat vertegenwoordigt.<br /> </td> 
  </tr> 
  <tr> 
   <td> In-app klikken <br /> </td> 
   <td> @inappclicks<br /> </td> 
   <td> @count (status=klikken)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Unieke muisklikken in de app<br /> </td> 
   <td> @uniqueinapp<br /> </td> 
   <td> @unique(@count (status=click)<br /> </td> 
   <td> Voor <span class="uicontrol">doelgebruikers die zijn gebaseerd op hun sjabloon Campagneprofiel (inAppProfile)</span> , is gebruiker = Ontvangersidentiteitskaart<br /> Voor <span class="uicontrol">Doel: alle gebruikers van een mobiele app (inAppBroadcast)</span> en <span class="uicontrol">doelgebruikers op basis van hun sjablonen voor hun mobiele profiel (inApp)</span> . Dit is de gebruiker = MC-id of equivalent die een unieke combinatie van gebruiker, mobiele app en apparaat vertegenwoordigt.<br /> </td> 
  </tr> 
  <tr> 
   <td> In-app klikfrequentie<br /> </td> 
   <td> @inappclickthrough<br /> </td> 
   <td> De totale kliks op Knoop 1 of Knoop 2/totale beelden*100<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Ontslag in de app<br /> </td> 
   <td> @dismission<br /> </td> 
   <td> @count (status=close)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Unieke ontslagen in de app<br /> </td> 
   <td> @uniquedismission<br /> </td> 
   <td> @unique(@count (status=close)<br /> </td> 
   <td> Voor <span class="uicontrol">doelgebruikers die zijn gebaseerd op hun sjabloon Campagneprofiel (inAppProfile)</span> , is gebruiker = Ontvangersidentiteitskaart<br /> Voor <span class="uicontrol">Doel: alle gebruikers van een mobiele app (inAppBroadcast)</span> en <span class="uicontrol">doelgebruikers op basis van hun sjablonen voor hun mobiele profiel (inApp)</span> . Dit is de gebruiker = MC-id of equivalent die een unieke combinatie van gebruiker, mobiele app en apparaat vertegenwoordigt.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ontslagfrequentie in de app<br /> </td> 
   <td> @dismissalrate<br /> </td> 
   <td> Totaal aantal close/total-impressions*100<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

