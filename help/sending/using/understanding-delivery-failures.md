---
title: Leveringsfouten begrijpen
description: Leer hoe u leveringsfouten kunt beheren met Campagne.
page-status-flag: never-activated
uuid: 2735aa05-7b6f-47c9-98c4-a15cc33be39d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: 38452841-4cd4-4f92-a5c3-1dfdd54ff6f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f1db8c886e560fe3f57d589b7fc2f2c2c1656f76

---


# Leveringsfouten begrijpen{#understanding-delivery-failures}

## Leveringsfouten {#about-delivery-failures}

Wanneer een levering niet naar een profiel kan worden verzonden, verzendt de externe server automatisch een foutbericht dat door het Adobe Campagne-platform wordt opgepakt en dat is gekwalificeerd om te bepalen of het e-mailadres of telefoonnummer al dan niet in quarantaine moet worden geplaatst. Zie [Bounce mail-kwalificatie](#bounce-mail-qualification).

>[!NOTE]
>
>**E-mailfoutberichten** (of &#39;bounces&#39;) worden gekwalificeerd door de Enhanced MTA (synchrone stuitingen) of door het inMail-proces (asynchrone stuitingen). **SMS** -foutberichten (of &quot;SR&quot; voor &quot;Statusrapport&quot;) worden gekwalificeerd door het MTA-proces.

Berichten kunnen ook tijdens de voorbereiding van de levering worden uitgesloten als een adres in quarantaine is geplaatst of als een profiel op een zwarte lijst staat. Uitgesloten berichten worden vermeld op het **[!UICONTROL Exclusion logs]** tabblad van het leveringsdashboard (zie [deze sectie](../../sending/using/monitoring-a-delivery.md#exclusion-logs)).

![](assets/exclusion_logs.png)

**Verwante onderwerpen:**

* [Werken met quarantainebeheer](../../sending/using/understanding-quarantine-management.md)
* [Zwarte lijst beheren in campagne](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## Leveringsfouten identificeren voor een bericht {#identifying-delivery-failures-for-a-message}

Zodra een levering wordt verzonden, staat het **[!UICONTROL Sending logs]** lusje (zie [deze sectie](../../sending/using/monitoring-a-delivery.md#sending-logs)) u toe om de leveringsstatus voor elk profiel en het bijbehorende mislukkingstype en de reden (zie de types en de redenen [van de mislukking van de](#delivery-failure-types-and-reasons)Levering) te bekijken.

![](assets/sending_logs.png)

Er is ook een speciaal rapport beschikbaar dat niet in de doos kan worden weergegeven. In dit rapport worden de algemene harde en zachte fouten beschreven die tijdens de leveringen zijn opgetreden, alsmede de automatische verwerking van steunbedragen. For more on this, refer to [this section](../../reporting/using/bounce-summary.md).

## Typen leveringsfouten en redenen {#delivery-failure-types-and-reasons}

Er zijn drie soorten fouten wanneer een levering mislukt:

* **Hard**: Een &quot;harde&quot;fout wijst op een ongeldig adres. Dit omvat een foutbericht waarin expliciet wordt aangegeven dat het adres ongeldig is, zoals: &quot;Onbekende gebruiker&quot;.
* **Zacht**: Dit kan een tijdelijke fout zijn of een fout die niet kan worden gecategoriseerd, zoals: &quot;Ongeldig domein&quot; of &quot;Brievenbus vol&quot;.
* **Genegeerd**: Dit is een fout die als tijdelijk, zoals &quot;uit bureau&quot;bekend is, of een technische fout, bijvoorbeeld als het afzendertype &quot;postmaster&quot;is.

De mogelijke oorzaken van een mislukking van de levering zijn:

* **[!UICONTROL User unknown]** (Hard type): het adres bestaat niet. Voor dit profiel worden geen verdere leveringen uitgevoerd.
* **[!UICONTROL Quarantined address]** (Hard type): het adres is in quarantaine geplaatst.
* **[!UICONTROL Unreachable]** (Zacht/Hard type): er is een fout opgetreden in de berichtleveringsketen (bijvoorbeeld een tijdelijk onbereikbaar domein). Volgens de fout die door de leverancier is geretourneerd, wordt het adres rechtstreeks naar quarantaine verzonden of wordt de levering opnieuw geprobeerd tot de campagne een fout ontvangt die de quarantainestatus rechtvaardigt of tot het aantal fouten 5 bereikt.
* **[!UICONTROL Address empty]** (Hard type): het adres is niet gedefinieerd.
* **[!UICONTROL Mailbox full]** (Zachte tekst): de brievenbus van deze gebruiker is volledig en kan niet meer berichten goedkeuren. Dit adres kan uit de quarantainelijst worden verwijderd om een andere poging te doen. Het wordt automatisch na 30 dagen verwijderd.

   Om het adres automatisch uit de lijst met in quarantaine geplaatste adressen te verwijderen moet de technische workflow voor **[!UICONTROL Database cleanup]** worden gestart.

* **[!UICONTROL Refused]** (Zacht/Hard type): het adres is in quarantaine geplaatst wegens veiligheidsterugkoppelen als spamrapport. Volgens de fout die door de leverancier is geretourneerd, wordt het adres rechtstreeks naar quarantaine verzonden of wordt de levering opnieuw geprobeerd tot de campagne een fout ontvangt die de quarantainestatus rechtvaardigt of tot het aantal fouten 5 bereikt.
* **[!UICONTROL Duplicate]**: het adres is reeds ontdekt in de segmentatie.
* **[!UICONTROL Not defined]** (Zachte tekst): het adres is in kwalificatie omdat de fouten nog niet zijn verhoogd.

   Dit type fout treedt op wanneer een nieuw foutbericht wordt verzonden door de server: het kan een geïsoleerde fout zijn, maar als het opnieuw voorkomt, zal de foutenteller stijgen, die de technische teams zal waarschuwen.

* **[!UICONTROL Error ignored]**: het adres bevindt zich in de whitelist en er zal in ieder geval een e-mail naar worden gestuurd .
* **[!UICONTROL Blacklisted address]**: het adres was op het moment van verzending op de zwarte lijst geplaatst.
* **[!UICONTROL Account disabled]** (Zacht/Hard type): wanneer de Internet Access Provider (IAP) een lange periode van inactiviteit ontdekt, kan het de rekening van de gebruiker sluiten: levering aan het adres van de gebruiker zal dan onmogelijk zijn. Het type Zacht of Hard is afhankelijk van het type ontvangen fout: als de account tijdelijk is uitgeschakeld vanwege een inactiviteit van zes maanden en nog steeds kan worden geactiveerd , **[!UICONTROL Erroneous]** wordt de status toegewezen en wordt de levering opnieuw geprobeerd . Als de ontvangen fout aangeeft dat de account permanent is gedeactiveerd, wordt deze rechtstreeks naar Quarantine verzonden.
* **[!UICONTROL Not connected]**: de mobiele telefoon van het profiel is uitgeschakeld of heeft geen verbinding met het netwerk wanneer het bericht wordt verzonden.
* **[!UICONTROL Invalid domain]** (Zachte tekst): het domein van het e-mailadres is onjuist of bestaat niet meer. Dit profiel wordt opnieuw geactiveerd tot het aantal fouten 5 is. Hierna wordt de record ingesteld op Quarantine-status en wordt het niet opnieuw geprobeerd.
* **[!UICONTROL Text too long]**: het aantal tekens in het SMS-bericht overschrijdt de limiet. Zie [SMS-codering, -lengte en -transliteratie](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)voor meer informatie.
* **[!UICONTROL Character not supported by encoding]**: het SMS-bericht bevat een of meer tekens die niet door de codering worden ondersteund. &amp;Zie [Tekenlijst - GSM-standaard](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard)voor meer informatie.

## Retourneert na een tijdelijke leverfout {#retries-after-a-delivery-temporary-failure}

Als een bericht wegens een tijdelijke fout van het **genegeerde** type ontbreekt, zullen de pogingen tijdens de leveringsduur opnieuw worden uitgevoerd. Voor meer over de types van fouten, zie de types en de redenen [van de mislukking van de](#delivery-failure-types-and-reasons)Levering.

Nadat de upgrade naar de [Adobe Campagne Enhanced MTA](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)is uitgevoerd, worden de instellingen voor **Opnieuw proberen** in Campagne genegeerd. Het aantal pogingen (hoeveel pogingen zouden moeten worden uitgevoerd de dag nadat verzenden is begonnen) en de minimumvertraging tussen pogingen worden beheerd door Verbeterde MTA, gebaseerd op hoe goed IP zowel historisch als momenteel bij een bepaald domein uitvoert.

Om de duur van een levering te wijzigen, ga naar de geavanceerde parameters van het levering of leveringsmalplaatje, en geef het **[!UICONTROL Delivery duration]** gebied van de sectie van de [Geldigheidsperiode](../../administration/using/configuring-email-channel.md#validity-period-parameters) uit.

>[!IMPORTANT]
>
>Zodra de upgrade naar de [Adobe Campagne Enhanced MTA](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)is uitgevoerd, wordt de **[!UICONTROL Delivery duration]** parameter in uw campagneleveringen alleen gebruikt als deze op 3,5 dagen of minder is ingesteld. Als u een waarde definieert die hoger is dan 3,5 dagen, wordt hiermee geen rekening gehouden.

Bijvoorbeeld, als u herpogingen voor een levering na één dag wilt ophouden, kunt u de leveringsduur aan **1d** plaatsen, en Verbeterde MTA zal dat het plaatsen door berichten in de herprobeer rij na één dag te verwijderen respecteren.

>[!NOTE]
>
>Zodra een bericht in de Verbeterde MTA rij 3.5 dagen is geweest en niet heeft geleverd, zal het uit tijd en zijn status van **[!UICONTROL Sent]** aan **[!UICONTROL Failed]** in de [leveringslogboeken](../../sending/using/monitoring-a-delivery.md#delivery-logs)worden bijgewerkt.

<!--The default configuration allows five retries at one-hour intervals, followed by one retry per day for four days. The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template (see [this section](../../administration/using/configuring-email-channel.md#sending-parameters)).-->

## Synchrone en asynchrone fouten {#synchronous-and-asynchronous-errors}

Een levering kan onmiddellijk (synchrone fout), of later op ontbreken, nadat het is verzonden (asynchrone fout).

* **Synchrone fout**: Als de externe server waarmee contact is opgenomen door de Adobe Campaign-leveringsserver onmiddellijk een foutbericht heeft geretourneerd, mag de levering niet naar de server van het profiel worden verzonden.
* **Asynchrone fout**: een stuiterende post of een SR werd later opnieuw toegestuurd door de ontvangende server. Asynchrone fouten kunnen optreden tot een week nadat een levering is verzonden.

## Bounce mail-kwalificatie {#bounce-mail-qualification}

<!--Delivery failure error messages (or "SMTP bounce responses") are picked up by the Adobe Campaign platform and then processed and qualified as **Hard**, **Soft**, or **Ignored** using the **[!UICONTROL Delivery log qualification]** database.

//Delivery failure error messages (or "bounces") are picked up by the Adobe Campaign platform and qualified by the inMail process to enrich the list of email management rules.(applies to asynchronous (out-of-band) bounces)

This list is available to administrators only and contains all the rules used by Adobe Campaign to qualify delivery failures.-->

>[!IMPORTANT]
>
>Zodra bijgewerkt naar de verbeterde MTA, worden de stuiterende kwalificaties in de **[!UICONTROL Message qualification]** lijst van de Campagne niet meer gebruikt.

Voor de synchrone foutenmeldingen van de leveringsmislukking, bepaalt Verbeterde MTA het stuittype en de kwalificatie, en stuurt die informatie terug naar Campagne. Raadpleeg dit [document](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)voor meer informatie over de verbeterde MTA voor Adobe-campagne.

De asynchrone stuitingen worden nog gekwalificeerd door het inMail proces door de **[!UICONTROL Inbound email]** regels. U opent deze regels door te klikken op het **[!UICONTROL Adobe Campaign]** logo, linksboven, vervolgens te selecteren **[!UICONTROL Administration > Channels > Email > Email processing rules]** en te selecteren **[!UICONTROL Bounce mails]**. Raadpleeg deze [sectie](../../administration/using/configuring-email-channel.md#email-processing-rules)voor meer informatie over deze regel.

<!--Bounces can have the following qualification statuses:

* **[!UICONTROL To qualify]**: the bounce mail needs to be qualified. Qualification must be done by the Deliverability team to ensure that the platform deliverability functions correctly. As long as it is not qualified, the bounce mail is not used to enrich the list of email processing rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Update for deliverability** workflow to be compared to existing email processing rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail was qualified but will not be used by the **Update for deliverability** workflow. So it will not be sent to the client instances.

To list the various bounces and their associated error types et reasons, click the **[!UICONTROL Adobe Campaign]** logo, in the top left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)-->

## De postleverbaarheid van het optimaliseren met dubbel opt-in mechanisme {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

Dubbele aanmeldingsprocedure is een beste manier om e-mails te verzenden. Het beveiligt het platform tegen onjuiste of ongeldige e-mailadressen, spambots, en voorkomt mogelijke spamklachten.

Het principe is om een e-mail te verzenden om de overeenkomst van de bezoeker te bevestigen alvorens hen als &quot;profielen&quot;in uw gegevensbestand van de Campagne op te slaan: de bezoeker vult een online bestemmingspagina in, ontvangt een e-mail en moet in de bevestigingsverbinding klikken om zijn abonnement te voltooien.

For more on this, refer to [this section](../../channels/using/setting-up-a-double-opt-in-process.md).
