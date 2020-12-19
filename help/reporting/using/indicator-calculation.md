---
solution: Campaign Standard
product: campaign
title: Indicatoren berekenen
description: Begrijp de resultaten van uw rapporten met een lijst van elke metrische formule.
audience: reporting
content-type: reference
topic-tags: about-reporting
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
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
   <td> Lijst van afgewezen personen snelheid<br /> </td> 
   <td> @rateBlacklist<br /> </td> 
   <td> @blacklist/@sent<br /> </td> 
   <td> De noemer voor het berekenen van het tarief is gebaseerd op Verzonden telling (Geleverd + Stemmen).<br /> </td> 
  </tr> 
  <tr> 
   <td> Stuiterwaarden + fouten<br /> </td> 
   <td> @bounces<br /> </td> 
   <td> count(@status=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Bounce + foutenfrequentie<br /> </td> 
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
   <td> Klikken door frequentie<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> @uniqueclicks/@delivery<br /> </td> 
   <td> De noemer voor tariefberekening is gebaseerd op slechts Geleverd.<br /> </td> 
  </tr> 
  <tr> 
   <td> Afgeleverd<br /> </td> 
   <td> @levering<br /> </td> 
   <td> count(@status=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Afgeleverde snelheid<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> @levering/@sent<br /> </td> 
   <td> De noemer voor het berekenen van het tarief is gebaseerd op Verzonden telling (Geleverd + Stemmen).<br /> </td> 
  </tr> 
  <tr> 
   <td> Harde grenzen<br /> </td> 
   <td> @hardBounces<br /> </td> 
   <td> count(@failureType=2 EN @failureReason=8)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Harde-stuiteringsfrequentie<br /> </td> 
   <td> @rateHardBounces<br /> </td> 
   <td> @hardBounces/@sent<br /> </td> 
   <td> De noemer voor het berekenen van het tarief is gebaseerd op Verzonden telling (Geleverd + Stemmen).<br /> </td> 
  </tr> 
  <tr> 
   <td> Ongeldig domein<br /> </td> 
   <td> @invalidDomain<br /> </td> 
   <td> count(@failureReason=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Mailbox full<br /> </td> 
   <td> @mailBoxFull<br /> </td> 
   <td> count(@failureReason=5)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Pagina spiegelen<br /> </td> 
   <td> @mirrorPage<br /> </td> 
   <td> count(@trackingUrlType=6)<br /> </td> 
   <td> De noemer voor tariefberekening is gebaseerd op slechts Geleverd.<br /> </td> 
  </tr> 
  <tr> 
   <td> Bezig met spiegelen van paginasnelheid<br /> </td> 
   <td> @rateMirrorPage<br /> </td> 
   <td> @mirrorPage/@delivery<br /> </td> 
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
   <td> count(@trackingUrlType=2 + unique(@trackingUrlType=1,2,3,6,10,11) - unique(@trackingUrlType=2))<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Open rate<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> @Opent/@bezorgd<br /> </td> 
   <td> De noemer voor tariefberekening is gebaseerd op slechts Geleverd.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quarantine<br /> </td> 
   <td> @quarantaine<br /> </td> 
   <td> isQuarantine=true<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Quarantaine rate<br /> </td> 
   <td> @rateQuarantine<br /> </td> 
   <td> @quarantaine/@sent<br /> </td> 
   <td> De noemer voor het berekenen van het tarief is gebaseerd op Verzonden telling (Geleverd + Stemmen).<br /> </td> 
  </tr>
  <tr> 
   <td> Afgewezen<br /> </td> 
   <td> @removed<br /> </td> 
   <td> count(@failureReason=20, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Afgewezen snelheid<br /> </td> 
   <td> @rateRejected<br /> </td> 
   <td> @geweigerd/@sent<br /> </td> 
   <td> De noemer voor het berekenen van het tarief is gebaseerd op Verzonden telling (Geleverd + Stemmen).<br /> </td> 
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
   <td> De noemer voor het berekenen van het tarief is gebaseerd op Verzonden telling (Geleverd + Stemmen).<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke klikken<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> De unieke kliks wordt berekend gebruikend de concepten van de Schets. Voor meer op dit, verwijs naar dit <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">example</a>.<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Uniek wordt geopend<br /> </td> 
   <td> @uniqueopened<br /> </td> 
   <td> unique(@trackingUrlType=1,2,3,6,10,11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Onbereikbaar <br /> </td> 
   <td> @unbereikable<br /> </td> 
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
   <td> @unsubscribes/@delivery<br /> </td> 
   <td> De noemer voor tariefberekening is gebaseerd op slechts Geleverd.<br /> </td> 
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
   <td> Afgeleverd<br /> </td> 
   <td> @levering<br /> </td> 
   <td> @count(status=bezorgd)<br /> </td> 
  </tr> 
  <tr> 
   <td> Afgeleverde snelheid<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> (@delivery/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Bounce + foutenfrequentie<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> (@delivery/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Open<br /> </td> 
   <td> @open<br /> </td> 
   <td> @count(status=open)<br /> </td> 
  </tr> 
  <tr> 
   <td> Open rate<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> (@opent/@bezorgd)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Uniek wordt geopend<br /> </td> 
   <td> @uniqueopened<br /> </td> 
   <td> Unieke opent wordt berekend gebruikend de concepten van Schets van unieke RecipientIds. Voor meer op dit, verwijs naar dit <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">example</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressies<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=bezorgd)<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke afbeeldingen<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
  </tr> 
  <tr> 
   <td> Klik op<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> @count(status=interact)<br /> </td> 
  </tr> 
  <tr> 
   <td> Unieke klikken<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> De unieke kliks wordt berekend gebruikend de concepten van de Schets. Voor meer op dit, verwijs naar dit <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">example</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Klikken door frequentie<br /> </td> 
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
   <td> Afgeleverd<br /> </td> 
   <td> @levering<br /> </td> 
   <td> @count(status=bezorgd)<br /> </td> 
   <td> bezorgd=sent<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressies<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=view) of @count(status=button 1 klik + knoop 2 klik + ontslagmiddelen)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Unieke afbeeldingen<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
   <td> Voor <span class="uicontrol">Doelgebruikers die op hun profiel van de Campagne (inAppProfile)</span> malplaatje worden gebaseerd, gebruiker = Ontvangersidentiteitskaart<br /> Voor  <span class="uicontrol">Doel: alle gebruikers van een mobiele app (inAppBroadcast)</span> en  <span class="uicontrol">doelgebruikers op basis van hun mobiele-profielsjablonen (inApp)</span> voor de gebruiker = MC-id of equivalent die een unieke combinatie van gebruiker, mobiele app en apparaat vertegenwoordigt.<br /> </td> 
  </tr> 
  <tr> 
   <td> In-app klikt <br /> </td> 
   <td> @inappclicks<br /> </td> 
   <td> @count (status=click)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Unieke klik in de app<br /> </td> 
   <td> @uniqueinapp<br /> </td> 
   <td> @unique(@count (status=click))<br /> </td> 
   <td> Voor <span class="uicontrol">Doelgebruikers die op hun profiel van de Campagne (inAppProfile)</span> malplaatje worden gebaseerd, gebruiker = Ontvangersidentiteitskaart<br /> Voor  <span class="uicontrol">Doel: alle gebruikers van een mobiele app (inAppBroadcast)</span> en  <span class="uicontrol">doelgebruikers op basis van hun mobiele-profielsjablonen (inApp)</span> voor de gebruiker = MC-id of equivalent die een unieke combinatie van gebruiker, mobiele app en apparaat vertegenwoordigt.<br /> </td> 
  </tr> 
  <tr> 
   <td> In-app klik door tarief<br /> </td> 
   <td> @inappclickthrough<br /> </td> 
   <td> Het totaal klikt op Knoop 1 of Knoop 2/totale drukken*100<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> In-app ontslag<br /> </td> 
   <td> @dismission<br /> </td> 
   <td> @count (status=close)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Unieke ontslagen in de app<br /> </td> 
   <td> @uniquedismission<br /> </td> 
   <td> @unique(@count (status=close))<br /> </td> 
   <td> Voor <span class="uicontrol">Doelgebruikers die op hun profiel van de Campagne (inAppProfile)</span> malplaatje worden gebaseerd, gebruiker = Ontvangersidentiteitskaart<br /> Voor  <span class="uicontrol">Doel: alle gebruikers van een mobiele app (inAppBroadcast)</span> en  <span class="uicontrol">doelgebruikers op basis van hun mobiele-profielsjablonen (inApp)</span> voor de gebruiker = MC-id of equivalent die een unieke combinatie van gebruiker, mobiele app en apparaat vertegenwoordigt.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ontslagfrequentie in de app<br /> </td> 
   <td> @dismissalrate<br /> </td> 
   <td> Totaal aantal close/total-impressions*100<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

