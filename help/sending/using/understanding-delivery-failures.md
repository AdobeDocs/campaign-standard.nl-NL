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
source-git-commit: d05d2692607117e056c360e81d85b7d64c4077a3
workflow-type: tm+mt
source-wordcount: '1279'
ht-degree: 1%

---


# Leveringsfouten begrijpen{#understanding-delivery-failures}

## Leveringsfouten {#about-delivery-failures}

Wanneer een levering niet naar een profiel kan worden verzonden, verzendt de externe server automatisch een foutbericht dat door het Adobe Campagne-platform wordt opgepakt en dat is gekwalificeerd om te bepalen of het e-mailadres of telefoonnummer al dan niet in quarantaine moet worden geplaatst. Zie [Bounce mail-kwalificatie](#bounce-mail-qualification).

>[!NOTE]
>
>**E-mailfoutberichten** (of &#39;bounces&#39;) worden gekwalificeerd door de Enhanced MTA (synchrone stuitingen) of door het inMail-proces (asynchrone stuitingen).
>
>**SMS** -foutberichten (of &quot;SR&quot; voor &quot;Statusrapport&quot;) worden gekwalificeerd door het MTA-proces.

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

| Foutlabel | Fouttype | Beschrijving |
---------|----------|---------
| **[!UICONTROL User unknown]** | Hard | Het adres bestaat niet. Voor dit profiel worden geen verdere leveringen uitgevoerd. |
| **[!UICONTROL Quarantined address]** | Hard | Het adres is in quarantaine geplaatst. |
| **[!UICONTROL Unreachable]** | Zacht/Hard | Er is een fout opgetreden in de berichtleveringsketen (bijvoorbeeld een tijdelijk onbereikbaar domein). Volgens de fout die door de leverancier is geretourneerd, wordt het adres rechtstreeks naar quarantaine verzonden of wordt de levering opnieuw geprobeerd tot de campagne een fout ontvangt die de quarantainestatus rechtvaardigt of tot het aantal fouten 5 bereikt. |
| **[!UICONTROL Address empty]** | Hard | Het adres is niet gedefinieerd. |
| **[!UICONTROL Mailbox full]** | Zacht | De brievenbus van deze gebruiker is volledig en kan niet meer berichten goedkeuren. Dit adres kan uit de quarantainelijst worden verwijderd om een andere poging te doen. Het wordt automatisch na 30 dagen verwijderd. Om het adres automatisch uit de lijst met in quarantaine geplaatste adressen te verwijderen moet de technische workflow voor **[!UICONTROL Database cleanup]** worden gestart. |
| **[!UICONTROL Refused]** | Zacht/Hard | Het adres is in quarantaine geplaatst toe te schrijven aan een veiligheid terugkoppelt als spamrapport. Volgens de fout die door de leverancier is geretourneerd, wordt het adres rechtstreeks naar quarantaine verzonden of wordt de levering opnieuw geprobeerd tot de campagne een fout ontvangt die de quarantainestatus rechtvaardigt of tot het aantal fouten 5 bereikt. |
| **[!UICONTROL Duplicate]** | Genegeerd | Het adres is reeds ontdekt in de segmentatie. |
| **[!UICONTROL Not defined]** | Zacht | het adres is in kwalificatie omdat de fouten nog niet zijn verhoogd. Dit type fout treedt op wanneer een nieuw foutbericht wordt verzonden door de server: het kan een geïsoleerde fout zijn, maar als het opnieuw voorkomt, zal de foutenteller stijgen, die de technische teams zal waarschuwen. |
| **[!UICONTROL Error ignored]** | Genegeerd | Het adres is in de whitelist en er wordt in elk geval een e-mail naar gestuurd. |
| **[!UICONTROL Blacklisted address]** | Hard | het adres was op het moment van verzending op de zwarte lijst geplaatst. |
| **[!UICONTROL Account disabled]** | Zacht/Hard | Wanneer de Internet Access Provider (IAP) een lange periode van inactiviteit ontdekt, kan het de rekening van de gebruiker sluiten: levering aan het adres van de gebruiker zal dan onmogelijk zijn. Het type Zacht of Hard is afhankelijk van het type ontvangen fout: als de account tijdelijk is uitgeschakeld vanwege een inactiviteit van zes maanden en nog steeds kan worden geactiveerd , **[!UICONTROL Erroneous]** wordt de status toegewezen en wordt de levering opnieuw geprobeerd . Als de ontvangen fout aangeeft dat de account permanent is gedeactiveerd, wordt deze rechtstreeks naar Quarantine verzonden. |
| **[!UICONTROL Not connected]** | Genegeerd | De mobiele telefoon van het profiel is uitgeschakeld of heeft geen verbinding met het netwerk wanneer het bericht wordt verzonden. |
| **[!UICONTROL Invalid domain]** | Zacht | Het domein van het e-mailadres is onjuist of bestaat niet meer. Dit profiel wordt opnieuw geactiveerd tot het aantal fouten 5 is. Hierna wordt de record ingesteld op Quarantine-status en wordt het niet opnieuw geprobeerd. |
| **[!UICONTROL Text too long]** | Genegeerd | Het aantal tekens in het SMS-bericht overschrijdt de limiet. Zie [SMS-codering, -lengte en -transliteratie](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)voor meer informatie. |
| **[!UICONTROL Character not supported by encoding]** | Genegeerd | Het SMS-bericht bevat een of meer tekens die niet door de codering worden ondersteund. &amp;Zie [Tekenlijst - GSM-standaard](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard)voor meer informatie. |

## Retourneert na een tijdelijke leverfout {#retries-after-a-delivery-temporary-failure}

Als een bericht wegens een tijdelijke fout van het **genegeerde** type ontbreekt, zullen de pogingen tijdens de leveringsduur opnieuw worden uitgevoerd. Voor meer over de types van fouten, zie de types en de redenen [van de mislukking van de](#delivery-failure-types-and-reasons)Levering.

Het aantal pogingen (hoeveel pogingen zouden moeten worden uitgevoerd de dag nadat het verzenden is begonnen) en de minimumvertraging tussen pogingen worden nu beheerd door Verbeterde MTA van de Campagne van Adobe, die op hoe goed wordt gebaseerd IP zowel historisch als momenteel bij een bepaald domein presteert. De instellingen voor **Opnieuw** proberen in Campagne worden genegeerd.

Om de duur van een levering te wijzigen, ga naar de geavanceerde parameters van het levering of leveringsmalplaatje, en geef het **[!UICONTROL Delivery duration]** gebied van de sectie van de [Geldigheidsperiode](../../administration/using/configuring-email-channel.md#validity-period-parameters) uit.

>[!IMPORTANT]
>
>**De **[!UICONTROL Delivery duration]**parameter in uw campagneleveringen wordt nu alleen gebruikt als deze is ingesteld op 3,5 dagen of minder.** Als u een waarde definieert die hoger is dan 3,5 dagen, wordt er geen rekening mee gehouden omdat deze waarde nu wordt beheerd door de verbeterde MTA voor Adobe Campagne.

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

Voor de synchrone foutenmeldingen van de leveringsmislukking, bepaalt Verbeterde MTA het stuittype en de kwalificatie, en stuurt die informatie terug naar Campagne.

De asynchrone stuitingen worden nog gekwalificeerd door het inMail proces door de **[!UICONTROL Inbound email]** regels. U opent deze regels door te klikken op het **[!UICONTROL Adobe Campaign]** logo, linksboven, vervolgens te selecteren **[!UICONTROL Administration > Channels > Email > Email processing rules]** en te selecteren **[!UICONTROL Bounce mails]**. Raadpleeg deze [sectie](../../administration/using/configuring-email-channel.md#email-processing-rules)voor meer informatie over deze regel.

>[!NOTE]
>
>De kwalificatie voor stuiterende e-mail wordt nu beheerd door de uitgebreide MTA van de Campagne van Adobe. De stuiterende kwalificaties in de **[!UICONTROL Message qualification]** tabel Campagne worden niet meer gebruikt.

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
