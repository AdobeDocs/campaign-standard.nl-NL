---
title: Uitvoerfouten
description: Leer hoe u leveringsfouten kunt beheren met Campagne.
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Deliverability
role: User
level: Intermediate
exl-id: 92a83400-447a-4d23-b05c-0ea013042ffa
source-git-commit: ac925ec5f59f1bb57b56b430fd175a27b08c3bfe
workflow-type: tm+mt
source-wordcount: '1281'
ht-degree: 0%

---

# Uitvoerfouten{#understanding-delivery-failures}

## Leveringsfouten {#about-delivery-failures}

Wanneer een levering niet naar een profiel kan worden verzonden, verzendt de externe server automatisch een foutbericht dat door het Adobe Campaign-platform wordt opgepakt en dat is gekwalificeerd om te bepalen of het e-mailadres of telefoonnummer al dan niet in quarantaine moet worden geplaatst. Zie [&#x200B; de postkwalificatie van de Stuiteren &#x200B;](#bounce-mail-qualification).

>[!NOTE]
>
>**E-mail** foutenmeldingen (of &quot;stuitingen&quot;) worden gekwalificeerd door Verbeterde MTA (synchrone stuitingen) of door het proces InMail (asynchrone stuitingen).
>
>**SMS** foutenmeldingen (of &quot;SR&quot;voor &quot;Rapport van de Status&quot;) worden gekwalificeerd door het MTA proces.

De berichten kunnen ook tijdens de leveringsvoorbereiding worden uitgesloten als een adres quarantined is of als een profiel op de lijst van gewezen personen is. De uitgesloten berichten zijn vermeld in het **[!UICONTROL Exclusion logs]** lusje van het leveringsdashboard (zie [&#x200B; deze sectie &#x200B;](../../sending/using/monitoring-a-delivery.md#exclusion-logs)).

![](assets/exclusion_logs.png)

**Verwante onderwerpen:**

* [quarantainebeheer](../../sending/using/understanding-quarantine-management.md)
* [Over opt-in en opt-out in campagne](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
* [&#x200B; Bounces &#x200B;](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#metrics-for-deliverability)

## Leveringsfouten identificeren voor een bericht {#identifying-delivery-failures-for-a-message}

Zodra een levering wordt verzonden, staat het **[!UICONTROL Sending logs]** lusje (zie [&#x200B; deze sectie &#x200B;](../../sending/using/monitoring-a-delivery.md#sending-logs)) u toe om de leveringsstatus voor elk profiel en het bijbehorende mislukkingstype en de reden (zie [&#x200B; de mislukkingstypes en redenen van de Levering &#x200B;](#delivery-failure-types-and-reasons)) te bekijken.

![](assets/sending_logs.png)

Er is ook een speciaal rapport beschikbaar dat niet in de doos kan worden weergegeven. In dit rapport worden de algemene harde en zachte fouten beschreven die tijdens de leveringen zijn opgetreden, alsmede de automatische verwerking van steunbedragen. Voor meer op dit, verwijs naar [&#x200B; deze sectie &#x200B;](../../reporting/using/bounce-summary.md).

## Typen leveringsfouten en redenen {#delivery-failure-types-and-reasons}

Er zijn drie soorten fouten wanneer een levering mislukt:

* **Vast**: Een &quot;harde&quot;fout wijst op een ongeldig adres. Dit omvat een foutbericht waarin expliciet wordt aangegeven dat het adres ongeldig is, zoals: &quot;Onbekende gebruiker&quot;.
* **Zacht**: Dit zou een tijdelijke fout kunnen zijn, of één die niet kon worden gecategoriseerd, zoals: &quot;Ongeldig domein&quot;of &quot;Brievenbus volledig&quot;.
* **Genegeerd**: Dit is een fout die om tijdelijk, zoals &quot;uit bureau&quot;bekend is, of een technische fout, bijvoorbeeld als het afzendertype &quot;postmaster&quot;is.

De mogelijke oorzaken van een mislukking van de levering zijn:

| Foutlabel | Fouttype | Beschrijving |
| ---------|----------|---------|
| **[!UICONTROL User unknown]** | Hard | Het adres bestaat niet. Voor dit profiel worden geen verdere leveringen uitgevoerd. |
| **[!UICONTROL Quarantined address]** | Hard | Het adres is in quarantaine geplaatst. |
| **[!UICONTROL Unreachable]** | Zacht/Hard | Er is een fout opgetreden in de berichtleveringsketen (bijvoorbeeld een tijdelijk onbereikbaar domein). Volgens de fout die door de leverancier is geretourneerd, wordt het adres rechtstreeks naar quarantaine verzonden of wordt de levering opnieuw geprobeerd tot de campagne een fout ontvangt die de quarantainestatus rechtvaardigt of tot het aantal fouten 5 bereikt. |
| **[!UICONTROL Address empty]** | Hard | Het adres is niet gedefinieerd. |
| **[!UICONTROL Mailbox full]** | Zacht | De brievenbus van deze gebruiker is volledig en kan niet meer berichten goedkeuren. Dit adres kan uit de quarantainelijst worden verwijderd om een andere poging te doen. Het wordt automatisch na 30 dagen verwijderd. Als u wilt dat het adres automatisch uit de lijst met in quarantaine geplaatste adressen wordt verwijderd, moet de **[!UICONTROL Database cleanup]** technische workflow worden gestart. |
| **[!UICONTROL Refused]** | Zacht/Hard | Het adres is in quarantaine geplaatst toe te schrijven aan een veiligheid terugkoppelt als spamrapport. Volgens de fout die door de leverancier is geretourneerd, wordt het adres rechtstreeks naar quarantaine verzonden of wordt de levering opnieuw geprobeerd tot de campagne een fout ontvangt die de quarantainestatus rechtvaardigt of tot het aantal fouten 5 bereikt. |
| **[!UICONTROL Duplicate]** | Genegeerd | Het adres is reeds ontdekt in de segmentatie. |
| **[!UICONTROL Not defined]** | Zacht | het adres is in kwalificatie omdat de fouten nog niet zijn verhoogd. Dit type van fout komt voor wanneer een nieuw foutenbericht door de server wordt verzonden: het kan een geïsoleerde fout zijn, maar als het opnieuw voorkomt, stijgt de foutenteller, die de technische teams zal waarschuwen. |
| **[!UICONTROL Error ignored]** | Genegeerd | Het adres staat op de lijst van gewenste personen en er zal in elk geval een e-mail naar worden gestuurd. |
| **[!UICONTROL Address on denylist]** | Hard | Het adres werd toegevoegd aan de lijst van gewezen personen op het tijdstip van verzending. |
| **[!UICONTROL Account disabled]** | Zacht/Hard | Wanneer de Internet Access Provider (IAP) een lange periode van inactiviteit detecteert, kan deze de account van de gebruiker sluiten: de levering aan het adres van de gebruiker is dan onmogelijk. Het type Zacht of Hard is afhankelijk van het type ontvangen fout: als de account tijdelijk is uitgeschakeld vanwege een inactiviteit van zes maanden en nog steeds kan worden geactiveerd, wordt de status **[!UICONTROL Erroneous]** toegewezen en wordt de levering opnieuw geprobeerd. Als de ontvangen fout aangeeft dat de account permanent is gedeactiveerd, wordt deze rechtstreeks naar Quarantine verzonden. |
| **[!UICONTROL Not connected]** | Genegeerd | De mobiele telefoon van het profiel is uitgeschakeld of heeft geen verbinding met het netwerk wanneer het bericht wordt verzonden. |
| **[!UICONTROL Invalid domain]** | Zacht | Het domein van het e-mailadres is onjuist of bestaat niet meer. Dit profiel wordt opnieuw geactiveerd tot het aantal fouten 5 is. Hierna wordt de record ingesteld op Quarantine-status en wordt het niet opnieuw geprobeerd. |
| **[!UICONTROL Text too long]** | Genegeerd | Het aantal tekens in het SMS-bericht overschrijdt de limiet. Voor meer op dit, zie [&#x200B; het coderen van SMS, lengte en transliteratie &#x200B;](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration). |
| **[!UICONTROL Character not supported by encoding]** | Genegeerd | Het SMS-bericht bevat een of meer tekens die niet door de codering worden ondersteund. &amp;Voor meer op dit, zie [&#x200B; Lijst van karakters - GSM Standaard &#x200B;](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard). |


**Verwante onderwerpen:**
* [&#x200B; Harde grenzen &#x200B;](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#hard-bounces)
* [&#x200B; Zachte grenzen &#x200B;](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#soft-bounces)

## Retourneert na een tijdelijke leverfout {#retries-after-a-delivery-temporary-failure}

Als een bericht mislukt als gevolg van een tijdelijke fout, worden de pogingen opnieuw uitgevoerd tijdens de leveringsduur. Voor meer op de types van fouten, zie [&#x200B; de mislukkingstypes van de Levering en redenen &#x200B;](#delivery-failure-types-and-reasons).

Het aantal pogingen (hoeveel opnieuw zou moeten worden uitgevoerd de dag nadat verzendt is begonnen) en de minimumvertraging tussen opnieuw probeert is nu <!--managed by the Adobe Campaign Enhanced MTA,--> gebaseerd op hoe goed IP zowel historisch als momenteel bij een bepaald domein uitvoert. **probeert opnieuw** montages in Campagne wordt genegeerd.

<!--Please note that Adobe Campaign Enhanced MTA is not available for the Push channel.-->

Om de duur van een levering te wijzigen, ga naar de geavanceerde parameters van het levering of leveringsmalplaatje, en geef het **[!UICONTROL Delivery duration]** gebied van de [&#x200B; sectie van de Geldigheidsperiode &#x200B;](../../administration/using/configuring-email-channel.md#validity-period-parameters) uit.

>[!IMPORTANT]
>
>**de &#x200B;** [!UICONTROL Delivery duration]&#x200B;**parameter in uw levering van de Campagne wordt nu slechts gebruikt als reeks aan 3.5 dagen of minder.** Als u een waarde definieert die hoger is dan 3,5 dagen, wordt hiermee geen rekening gehouden.

Bijvoorbeeld, als u opnieuw voor een levering wilt stoppen na één dag, kunt u de leveringsduur aan **1d** plaatsen, en de berichten in de hertry rij zullen na één dag worden verwijderd.

>[!NOTE]
>
>Zodra een bericht in de herpogingsrij voor een maximum van 3.5 dagen is geweest en heeft nagelaten te leveren, zal het uit tijd en zijn status <!--from **[!UICONTROL Sent]**--> aan **[!UICONTROL Failed]** in [&#x200B; leveringslogboeken &#x200B;](../../sending/using/monitoring-a-delivery.md#delivery-logs) worden bijgewerkt.

<!--
MOVED TO configuring-email-channel.md > LEGACY SETTINGS
The default configuration allows five retries at one-hour intervals, followed by one retry per day for four days. The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template (see [this section](../../administration/using/configuring-email-channel.md#sending-parameters)).
-->

## Synchrone en asynchrone fouten {#synchronous-and-asynchronous-errors}

Een levering kan onmiddellijk (synchrone fout), of later op ontbreken, nadat het is verzonden (asynchrone fout).

* **Synchrone fout**: de verre server die door de leverings server van Adobe Campaign wordt gecontacteerd kwam onmiddellijk een foutenmelding terug, wordt de levering niet toegestaan om naar de server van het profiel worden verzonden.
* **Asynchrone fout**: een stuiterende post of een SR werd opnieuw verstuurd later door de ontvangende server. Asynchrone fouten kunnen optreden tot een week nadat een levering is verzonden.

## Bounce mail-kwalificatie {#bounce-mail-qualification}

Voor de synchrone foutenmeldingen van de leveringsmislukking, bepaalt Adobe Campaign Verbeterde MTA (de Agent van de Overdracht van het Bericht) het stuittype en de kwalificatie, en stuurt die informatie terug naar Campagne.

>[!NOTE]
>
>De stuiterende kwalificaties in de tabel Campagne **[!UICONTROL Message qualification]** worden niet meer gebruikt.

Asynchrone stuiteringen worden nog steeds gekwalificeerd door het inMail-proces via de **[!UICONTROL Inbound email]** -regels. Om tot deze regels toegang te hebben, klik het **Adobe** embleem, bij top-left, dan selecteren **[!UICONTROL Administration > Channels > Email > Email processing rules]** en selecteren **[!UICONTROL Bounce mails]**. Voor meer op deze regel, zie [&#x200B; deze sectie &#x200B;](../../administration/using/configuring-email-channel.md#email-processing-rules).

Voor meer op stuitingen en de verschillende soorten stuitingen, zie [&#x200B; deze sectie &#x200B;](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#metrics-for-deliverability).

<!--
MOVED TO configuring-email-channel.md > LEGACY SETTINGS

Bounces can have the following qualification statuses:

* **[!UICONTROL To qualify]**: the bounce mail needs to be qualified. Qualification must be done by the Deliverability team to ensure that the platform deliverability functions correctly. As long as it is not qualified, the bounce mail is not used to enrich the list of email processing rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Update for deliverability** workflow to be compared to existing email processing rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail was qualified but will not be used by the **Update for deliverability** workflow. So it will not be sent to the client instances.

To list the various bounces and their associated error types et reasons, click the **Adobe** logo, in the top-left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)
-->

## E-mailleverbaarheid optimaliseren met dubbele aanmeldingsprocedure {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

Dubbele aanmeldingsprocedure is een beste manier om e-mails te verzenden. Het beveiligt het platform tegen onjuiste of ongeldige e-mailadressen, spambots, en voorkomt mogelijke spamklachten.

Het principe is om een e-mail te verzenden ter bevestiging van de overeenkomst van de bezoeker voordat deze als &#39;profielen&#39; worden opgeslagen in uw Campagne-database: de bezoeker vult een online bestemmingspagina in, ontvangt vervolgens een e-mail en moet op de bevestigingskoppeling klikken om zijn abonnement af te ronden.

Voor meer op dit, zie [&#x200B; deze sectie &#x200B;](../../channels/using/setting-up-a-double-opt-in-process.md).
