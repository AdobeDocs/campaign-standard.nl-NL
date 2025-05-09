---
title: E-mailinhoud beheren in Adobe Campaign Standard
description: Leer hoe u de leesbaarheid in Adobe Campaign Standard kunt verbeteren tijdens het bewerken van uw e-mailinhoud.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: debbc70d-4094-44c0-b7cb-c999effda1a6
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 6%

---

# E-mailcontent controleren{#control-email-content}

<!--TO KEEP because specific to Campaign-->

Om ervoor te zorgen dat je e-mailberichten bij je ontvangers terechtkomen en je e-mailsnelheid verbeteren, moeten ze een aantal regels in acht nemen. Anders, kan de inhoud van bepaalde berichten als spam worden ontdekt. Adobe Campaign biedt u verschillende gereedschappen om ervoor te zorgen dat uw inhoud aan deze regels voldoet.

Volg de onderstaande principes bij het ontwerpen van uw berichtinhoud:

* [Naam en adres van de afzender](#sender-name): het adres moet de afzender uitdrukkelijk identificeren. Het domein moet eigendom zijn van en geregistreerd zijn bij de afzender. Het domeinregister mag niet worden geprivatiseerd.
  <!--**Subject**: Avoid excessive capitalization and punctuation, and words that are frequently used by spammers ("Win", "Free", etc.).-->
* [Personalisatie en tijdoptimalisatie](#perso-send-time-optimization): het personaliseren van inhoud en het bepalen van een verzendingstijd per ontvanger verhogen de kansen van uw bericht dat wordt geopend.
* Afbeeldingen en tekst: respecteer een goede verhouding tussen tekst en afbeelding (bijvoorbeeld 60% tekst en 40% afbeeldingen).
* [Koppeling met abonnement opheffen](#opt-out) en landingspagina: de koppeling om het abonnement op te zeggen is essentieel. Het formulier moet zichtbaar en geldig zijn en moet functioneel zijn.
* Voorbeeld: gebruik de gereedschappen van Adobe Campaign om de inhoud van uw e-mail te controleren en te optimaliseren ([Anti-spamanalyse](#anti-spam-analysis), [E-mailrendering](#message-responsiveness)).

Voor meer tips voor het optimaliseren van de leesbaarheid bij het ontwerpen van inhoud raadpleegt u de [Handleiding voor beste praktijken bij de levering van Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/content-best-practices-for-optimal-delivery.html?lang=nl-NL).

>[!NOTE]
>
>Voor meer informatie over het bewerken van e-mailinhoud raadpleegt u de [Overzicht van E-mailDesigner](../../designing/using/designing-content-in-adobe-campaign.md) en de [Aanbevolen werkwijzen voor berichtenontwerp](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices).

## Naam en adres van de afzender {#sender-name}

Bepaalde ISPs controleren de geldigheid van het afzenderadres (**[!UICONTROL From]**) voordat berichten worden geaccepteerd. Een slecht geformuleerd adres kan ertoe leiden dat het door de ontvangende server wordt verworpen.

![](assets/delivery_content_edition16.png)

U moet ervoor zorgen dat een correct adres op instantieniveau of in de het vaakst gebruikte scenario&#39;s wordt gegeven. Neem hiervoor contact op met de beheerder.

Zie voor meer informatie [De e-mailafzender van een e-mailbericht definiëren](../../designing/using/subject-line.md#email-sender).

## Personalisatie en tijdoptimalisatie {#perso-send-time-optimization}

Om de ervaring van uw ontvangers te verbeteren en hen open uw e-mail te maken, laat Adobe Campaign u toe om uw berichten aan te passen. Zie [deze sectie](../../designing/using/personalization.md)voor meer informatie.

Om het openingstarief van uw berichten te verhogen, kunt u een verzendende tijd per ontvanger ook manueel bepalen. Elk profiel ontvangt het bericht op de opgegeven datum en tijd, indien mogelijk. Zie voor meer informatie [De verzendtijd optimaliseren](../../sending/using/optimizing-the-sending-time.md).

## Koppeling en formulier uitschakelen {#opt-out}

Wanneer het bericht wordt geanalyseerd, controleert standaard een typologische regel of een opt-out-koppeling is opgenomen en wordt een waarschuwing gegenereerd als deze ontbreekt. Zie voor meer informatie over het beheren van koppelingen [deze sectie](../../designing/using/links.md).

U moet controleren of de koppeling om te weigeren correct werkt voordat u de koppeling verzendt. Wanneer bijvoorbeeld [de verzending van het bewijs](../../sending/using/sending-proofs.md), controleert u of de koppeling geldig is, of het formulier online is en of het valideren van deze koppeling het **[!UICONTROL No longer contact]** vakken. Deze controle moet u systematisch uitvoeren, omdat een menselijke fout altijd mogelijk is bij het invoeren van de koppeling of bij het wijzigen van het formulier. Zie voor meer informatie over het beheer van opt-in en opt-out [deze sectie](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md).

![](assets/optin_landingpage_3.png)

Als er een probleem wordt vastgesteld met betrekking tot het opzeggen van een abonnement nadat de levering is gestart, is het nog steeds mogelijk om handmatig een abonnement op te zeggen (met behulp van bijvoorbeeld de functie voor het bijwerken van de massa) voor de ontvangers die op de koppeling om te weigeren klikken, zelfs als zij hun keuze niet konden bevestigen.

Als algemene regel geldt dat u niet moet proberen ontvangers die zich willen afmelden te belemmeren door van hen te verlangen dat ze bijvoorbeeld velden invullen zoals hun e-mailadres of naam. De landingspagina voor abonnementen mag slechts één validatieknop hebben.

Het aanvragen van aanvullende bevestiging is niet betrouwbaar: een gebruiker kan twee e-mailadressen hebben die zijn omgeleid naar hetzelfde vak (bijvoorbeeld: firstname.lastname@club.com en firstname.lastname@internet-club.com). Als het profiel alleen het eerste adres kan onthouden en het abonnement wil opzeggen via een bericht dat naar het andere wordt verzonden, wordt dit door het formulier geweigerd omdat de gecodeerde id en het ingevoerde e-mailadres niet overeenkomen.

## Anti-spamanalyse {#anti-spam-analysis}

In de Adobe Campaign-berichteneditor wordt een **Anti-spamanalyse** Dit staat u toe om e-mailberichten te noteren om te bepalen of een bericht het risico loopt om als spam door de anti-anti-spamhulpmiddelen worden beschouwd die op ontvangstbewijs worden gebruikt. Zie voor meer informatie [Berichten voorvertonen](../../sending/using/previewing-messages.md).

Klik in de berichtinhoudseditor op **[!UICONTROL Preview]**. Een bericht waarschuwt u als de anti-anti-spamcontrole een hoog risico voor dit bericht heeft ontdekt. Klikken **[!UICONTROL Anti-spam analysis]** om details weer te geven.

![](assets/sending_anti-spam_analysis.png)

## E-mailweergave {#message-responsiveness}

Voordat u uw bericht verzendt, kunt u de reactiesnelheid van uw bericht testen door te controleren hoe uw bericht eruitziet op verschillende apparaten. Dit is om ervoor te zorgen dat het op een optimale manier op een verscheidenheid van Webcliënten, Webpost en apparaten zal worden getoond.

![](assets/inbox_rendering_report_3.png)

Om dit mogelijk te maken, legt Adobe Campaign de weergave vast en stelt deze beschikbaar in een specifiek rapport. Op deze manier kunt u het voorbeeld van het verzonden bericht bekijken in de verschillende contexten waarin het bericht mogelijk wordt ontvangen.

Zie [E-mail renderen](../../sending/using/email-rendering.md) voor meer informatie.
