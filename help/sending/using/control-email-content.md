---
title: E-mailinhoud beheren in Adobe Campaign Standard
description: Leer hoe u de leesbaarheid in Adobe Campaign Standard kunt verbeteren tijdens het bewerken van uw e-mailinhoud.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 7%

---


# E-mailcontent beheren{#control-email-content}

Om de e-mailleverbaarheid te verbeteren en ervoor te zorgen dat de e-mails bij de ontvangers terechtkomen, moet het e-mailbericht aan een aantal regels voldoen.

* **Naam en adres** van de afzender: Het adres moet de afzender uitdrukkelijk identificeren. Het domein moet eigendom zijn van en geregistreerd zijn bij de afzender. Het domeinregister mag niet worden geprivatiseerd.
* **Betreft**: Voorkom buitensporige kapitalisatie en leestekens en woorden die vaak door spammers worden gebruikt (&quot;Win&quot;, &quot;Free&quot;, enz.).
* **Personaliseer uw e-mail**: Als je de e-mail personaliseert, wordt de kans groter dat je bericht wordt geopend.
* **Afbeeldingen en tekst**: Een goede verhouding tussen tekst en afbeelding respecteren (bijvoorbeeld 60% tekst en 40% afbeeldingen).
* **Koppeling en openingspagina** voor abonnement opzeggen: De koppeling om uw abonnement op te zeggen is essentieel. Het formulier moet zichtbaar en geldig zijn en moet functioneel zijn.
* **Gebruik de tools** die Adobe Campaign aanbiedt om de inhoud van uw e-mail te optimaliseren (leveringsanalyse, anti-spamanalyse).

Raadpleeg voor meer informatie over het bewerken van e-mailinhoud het overzicht [van de](../../designing/using/designing-content-in-adobe-campaign.md) e-mailontwerper en de aanbevolen procedures [voor het ontwerpen van](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices)berichten.

## Naam en adres van de afzender {#sender-name}

Bepaalde ISPs controleert de geldigheid van het afzenderadres (van) alvorens berichten goed te keuren. Een slecht geformuleerd adres kan ertoe leiden dat het door de ontvangende server wordt verworpen. U moet ervoor zorgen dat een correct adres op instantieniveau of in de het vaakst gebruikte scenario&#39;s wordt gegeven. Neem contact op met de beheerder.

![](assets/delivery_content_edition16.png)

Zie [De naam](../../designing/using/personalization.md#personalizing-the-sender)van de afzender aanpassen voor meer informatie.

## Onderwerpregel {#subject-line}

Wanneer u een e-mailbericht bewerkt, kunt u verschillende onderwerpregel uitproberen en een schatting krijgen van de openstaande frequentie voordat u het bericht verzendt. Zie [De onderwerpregel van een e-mail](../../sending/using/testing-subject-line-email.md)testen voor meer informatie.

![](assets/predictive_subject_line_example.png)

Zie [deze sectie](../../designing/using/subject-line.md)voor meer informatie over het definiëren van de onderwerpregel van een e-mail.

## Send time optimization {#send-time-optimization}

Om het succestarief van uw berichten te verbeteren, kunt u een verzendende tijd per ontvanger manueel bepalen. Elk profiel ontvangt het bericht dan op de opgegeven datum en tijd, indien mogelijk.

Voor meer op dit, zie het [Optimaliseren van de verzendende tijd](../../sending/using/optimizing-the-sending-time.md).

## Koppeling en formulier uitschakelen {#opt-out}

Wanneer het bericht wordt geanalyseerd, controleert standaard een typologische regel of een opt-out-koppeling is opgenomen en wordt een waarschuwing gegenereerd als deze ontbreekt.

U moet controleren of de koppeling om te weigeren correct werkt voordat u de koppeling verzendt. Wanneer u bijvoorbeeld de proefdruk verzendt, controleert u of de koppeling geldig is, of het formulier online is en of bij validatie hiervan de waarde van de contactvakken Niet meer worden ingeschakeld. Deze controle moet u systematisch uitvoeren, omdat een menselijke fout altijd mogelijk is bij het invoeren van de koppeling of bij het wijzigen van het formulier.

Als er een probleem wordt vastgesteld met betrekking tot het opzeggen van een abonnement nadat de levering is gestart, is het nog steeds mogelijk om handmatig een abonnement op te zeggen (met behulp van bijvoorbeeld de functie voor het bijwerken van de massa) voor de ontvangers die op de koppeling om te weigeren klikken, zelfs als zij hun keuze niet konden bevestigen.

Als algemene regel geldt dat u ontvangers die zich willen afmelden, niet in de weg wilt staan door van hen te verlangen dat ze bijvoorbeeld velden invullen zoals hun e-mailadres of naam. De landingspagina voor abonnementen mag slechts één validatieknop hebben. Aanvullende bevestiging aanvragen is niet betrouwbaar: een gebruiker kan twee e-mailadressen naar hetzelfde vak hebben omgeleid (bijvoorbeeld: firstname.lastname@club.com en firstname.lastname@internet-club.com). Als het profiel alleen het eerste adres kan onthouden en het abonnement wil opzeggen via een bericht dat naar het andere wordt verzonden, wordt dit door het formulier geweigerd omdat de gecodeerde id en het ingevoerde e-mailadres niet overeenkomen.

## Anti-spamanalyse {#anti-spam-analysis}

De het berichtredacteur van Adobe Campaign integreert een **anti-spamanalyse** die u toestaat om e-mail te scoren om te bepalen of een bericht het risico loopt om als spam door de anti-anti-spamhulpmiddelen worden beschouwd die op ontvangstbewijs worden gebruikt. For more on this, see [Previewing messages](../../sending/using/previewing-messages.md).

Klik in de berichtinhoudseditor op **[!UICONTROL Preview]**. Een bericht waarschuwt u als de anti-anti-spamcontrole een hoog risico voor dit bericht heeft ontdekt. Klik **[!UICONTROL Anti-spam analysis]** om details weer te geven.

![](assets/sending_anti-spam_analysis.png)

## De reactiesnelheid van berichten controleren {#message-responsiveness}

Voordat u uw bericht verzendt, kunt u controleren hoe uw bericht eruitziet op verschillende apparaten. Dit is om ervoor te zorgen dat het op een optimale manier op een verscheidenheid van Webcliënten, Webpost en apparaten zal worden getoond.

Om dit mogelijk te maken, legt Adobe Campaign de weergave vast en stelt deze beschikbaar in een specifiek rapport. Op deze manier kunt u het voorbeeld van het verzonden bericht bekijken in de verschillende contexten waarin het bericht mogelijk wordt ontvangen.

Zie [E-mail renderen](../../sending/using/email-rendering.md) voor meer informatie.

![](assets/inbox_rendering_report_3.png)
