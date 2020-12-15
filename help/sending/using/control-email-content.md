---
solution: Campaign Standard
product: campaign
title: E-mailinhoud beheren in Adobe Campaign Standard
description: Leer hoe u de leesbaarheid in Adobe Campaign Standard kunt verbeteren tijdens het bewerken van uw e-mailinhoud.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 1e7359db2de1a9c420af33ac85c0597c098ae3f8
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 8%

---


# E-mailcontent beheren{#control-email-content}

Om de e-mailleverbaarheid te verbeteren en ervoor te zorgen dat de e-mails bij de ontvangers terechtkomen, moet het e-mailbericht aan een aantal regels voldoen.

* **Naam en adres** van de afzender: Het adres moet de afzender uitdrukkelijk identificeren. Het domein moet eigendom zijn van en geregistreerd zijn bij de afzender. Het domeinregister mag niet worden geprivatiseerd.
* **Betreft**: Voorkom buitensporige kapitalisatie en leestekens en woorden die vaak door spammers worden gebruikt (&quot;Win&quot;, &quot;Free&quot;, enz.).
* **Personaliseer uw e-mail**: Als je de e-mail personaliseert, wordt de kans groter dat je bericht wordt geopend.
* **Afbeeldingen en tekst**: Een goede verhouding tussen tekst en afbeelding respecteren (bijvoorbeeld 60% tekst en 40% afbeeldingen).
* **Koppeling en openingspagina** voor abonnement opzeggen: De koppeling om uw abonnement op te zeggen is essentieel. Het formulier moet zichtbaar en geldig zijn en moet functioneel zijn.
* **Gebruik de** gereedschappen van Adobe Campaign om de inhoud van uw e-mail te optimaliseren (leveringsanalyse, anti-spamanalyse).

Voor meer informatie over het bewerken van e-mailinhoud raadpleegt u het [e-mailDesigner-overzicht](../../designing/using/designing-content-in-adobe-campaign.md) en de [Beste werkwijzen bij het ontwerpen van berichten](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices).

## Naam en adres van de afzender {#sender-name}

Bepaalde ISPs controleert de geldigheid van het afzenderadres (van) alvorens berichten goed te keuren. Een slecht geformuleerd adres kan ertoe leiden dat het door de ontvangende server wordt verworpen. U moet ervoor zorgen dat een correct adres op instantieniveau of in de het vaakst gebruikte scenario&#39;s wordt gegeven. Neem contact op met de beheerder.

![](assets/delivery_content_edition16.png)

Zie [De naam van de afzender aanpassen](../../designing/using/personalization.md#personalizing-the-sender) voor meer informatie.

## Optimalisatie van tijd verzenden {#send-time-optimization}

Om het succestarief van uw berichten te verbeteren, kunt u een verzendende tijd per ontvanger manueel bepalen. Elk profiel ontvangt het bericht dan op de opgegeven datum en tijd, indien mogelijk.

Zie [De verzendtijd optimaliseren](../../sending/using/optimizing-the-sending-time.md) voor meer informatie.

## Koppeling en formulier {#opt-out} uitschakelen

Wanneer het bericht wordt geanalyseerd, controleert standaard een typologische regel of een opt-out-koppeling is opgenomen en wordt een waarschuwing gegenereerd als deze ontbreekt.

U moet controleren of de koppeling om te weigeren correct werkt voordat u de koppeling verzendt. Wanneer u bijvoorbeeld de proefdruk verzendt, controleert u of de koppeling geldig is, of het formulier online is en of bij validatie hiervan de waarde van de contactvakken Niet meer worden ingeschakeld. Deze controle moet u systematisch uitvoeren, omdat een menselijke fout altijd mogelijk is bij het invoeren van de koppeling of bij het wijzigen van het formulier.

Als er een probleem wordt vastgesteld met betrekking tot het opzeggen van een abonnement nadat de levering is gestart, is het nog steeds mogelijk om handmatig een abonnement op te zeggen (met behulp van bijvoorbeeld de functie voor het bijwerken van de massa) voor de ontvangers die op de koppeling om te weigeren klikken, zelfs als zij hun keuze niet konden bevestigen.

Als algemene regel geldt dat u ontvangers die zich willen afmelden, niet in de weg wilt staan door van hen te verlangen dat ze bijvoorbeeld velden invullen zoals hun e-mailadres of naam. De landingspagina voor abonnementen mag slechts één validatieknop hebben. Aanvullende bevestiging aanvragen is niet betrouwbaar: een gebruiker kan twee e-mailadressen naar hetzelfde vak hebben omgeleid (bijvoorbeeld: firstname.lastname@club.com en firstname.lastname@internet-club.com). Als het profiel alleen het eerste adres kan onthouden en het abonnement wil opzeggen via een bericht dat naar het andere wordt verzonden, wordt dit door het formulier geweigerd omdat de gecodeerde id en het ingevoerde e-mailadres niet overeenkomen.

## Anti-spamanalyse {#anti-spam-analysis}

De het berichtredacteur van Adobe Campaign integreert een **anti-spamanalyse** die u toestaat om e-mail te scoren om te bepalen of een bericht het risico loopt om als spam door de anti-anti-spamhulpmiddelen worden beschouwd die op ontvangstbewijs worden gebruikt. Zie [Berichten voorvertonen](../../sending/using/previewing-messages.md) voor meer informatie.

In de redacteur van de berichtinhoud, klik **[!UICONTROL Preview]**. Een bericht waarschuwt u als de anti-anti-spamcontrole een hoog risico voor dit bericht heeft ontdekt. Klik **[!UICONTROL Anti-spam analysis]** om details te bekijken.

![](assets/sending_anti-spam_analysis.png)

## Het controleren van de berichtontvankelijkheid {#message-responsiveness}

Voordat u uw bericht verzendt, kunt u controleren hoe uw bericht eruitziet op verschillende apparaten. Dit is om ervoor te zorgen dat het op een optimale manier op een verscheidenheid van Webcliënten, Webpost en apparaten zal worden getoond.

Om dit mogelijk te maken, legt Adobe Campaign de weergave vast en stelt deze beschikbaar in een specifiek rapport. Op deze manier kunt u het voorbeeld van het verzonden bericht bekijken in de verschillende contexten waarin het bericht mogelijk wordt ontvangen.

Zie [E-mail renderen](../../sending/using/email-rendering.md) voor meer informatie.

![](assets/inbox_rendering_report_3.png)
