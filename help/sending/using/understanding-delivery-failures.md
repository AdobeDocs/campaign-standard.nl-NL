---
solution: Campaign Standard
product: campaign
title: Leveringsfouten begrijpen
description: Ontdek hoe u leveringsfouten kunt beheren met Campaign.
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Deliverability
role: User
level: Intermediate
exl-id: 92a83400-447a-4d23-b05c-0ea013042ffa
source-git-commit: 7efdb8aa4f931268cf9a0899179819cbc1f86757
workflow-type: tm+mt
source-wordcount: '1303'
ht-degree: 64%

---

# Leveringsfouten begrijpen{#understanding-delivery-failures}

## Leveringsfouten {#about-delivery-failures}

Wanneer een levering niet naar een profiel kan worden verzonden, verzendt de externe server automatisch een foutbericht dat door het Adobe Campaign-platform wordt opgepikt en wordt gekwalificeerd om te bepalen of het e-mailadres of telefoonnummer al dan niet in quarantaine moet worden geplaatst. Zie [Kwalificatie van niet-bezorgde e-mails](#bounce-mail-qualification).

>[!NOTE]
>
>**E-mailfoutberichten** (niet-bezorgde e-mails) worden gekwalificeerd door de Enhanced MTA (synchrone niet-bezorging) of door het inMail-proces (asynchrone niet-bezorging).
>
>**Sms-foutberichten** (of ‘SR’ voor ‘Statusrapport’) worden gekwalificeerd door het MTA-proces.

De berichten kunnen ook tijdens de leveringsvoorbereiding worden uitgesloten als een adres quarantined is of als een profiel op de lijst van gewezen personen is. Uitgesloten berichten worden weergegeven op het tabblad **[!UICONTROL Exclusion logs]** van het leveringsdashboard (zie [deze sectie](../../sending/using/monitoring-a-delivery.md#exclusion-logs)).

![](assets/exclusion_logs.png)

**Verwante onderwerpen:**

* [Werken met quarantainebeheer](../../sending/using/understanding-quarantine-management.md)
* [Informatie over opt-in en opt-out in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
* [Bounces](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#metrics-for-deliverability)

## Leveringsfouten identificeren voor een bericht {#identifying-delivery-failures-for-a-message}

Zodra een levering wordt verzonden, kunt u via het tabblad **[!UICONTROL Sending logs]** (zie [deze sectie](../../sending/using/monitoring-a-delivery.md#sending-logs)) de leveringsstatus voor elk profiel en het bijbehorende fouttype en de reden (zie [Typen leveringsfouten en redenen](#delivery-failure-types-and-reasons)) bekijken.

![](assets/sending_logs.png)

Er is ook een speciaal kant-en-klaar rapport beschikbaar. In dit rapport worden de algemene permanente en tijdelijke fouten beschreven die tijdens de leveringen zijn opgetreden, alsmede de automatische verwerking van niet-bezorgde berichten. Raadpleeg [deze sectie](../../reporting/using/bounce-summary.md) voor meer informatie.

## Typen leveringsfouten en redenen {#delivery-failure-types-and-reasons}

Er zijn drie typen fouten wanneer een levering mislukt:

* **Hard**: Een ‘harde’ of permanente fout wijst op een ongeldig adres. Dit omvat een foutbericht waarin expliciet wordt aangegeven dat het adres ongeldig is, zoals een onbekende gebruiker.
* **Soft**: Dit kan een tijdelijke fout zijn of een fout die niet kan worden gecategoriseerd, zoals een ongeldig domein of een vol postvak.
* **Ignored**: Dit is een fout die doorgaans tijdelijk is, zoals een afwezigheidsbericht of een technische fout, bijvoorbeeld als het afzendertype ‘postmaster’ is.

De mogelijke redenen van een leveringsfout zijn:

| Foutlabel | Fouttype | Beschrijving |
| ---------|----------|---------|
| **[!UICONTROL User unknown]** | Hard | Het adres bestaat niet. Voor dit profiel worden geen verdere leveringen uitgevoerd. |
| **[!UICONTROL Quarantined address]** | Hard | Het adres is in quarantaine geplaatst. |
| **[!UICONTROL Unreachable]** | Zacht/Hard | Er is een fout opgetreden in de berichtleveringsketen (bijvoorbeeld een tijdelijk onbereikbaar domein). Afhankelijk van de fout die door de provider is geretourneerd, wordt het adres rechtstreeks naar quarantaine verzonden of wordt de levering opnieuw geprobeerd totdat Campaign een fout ontvangt die de quarantainestatus rechtvaardigt of tot het aantal fouten 5 bereikt. |
| **[!UICONTROL Address empty]** | Hard | Het adres is niet gedefinieerd. |
| **[!UICONTROL Mailbox full]** | Zacht | De brievenbus van deze gebruiker is volledig en kan niet meer berichten goedkeuren. Dit adres kan uit de quarantainelijst worden verwijderd om een nieuwe poging te doen. Het wordt automatisch na 30 dagen verwijderd. Om het adres automatisch uit de lijst met in quarantaine geplaatste adressen te verwijderen, moet de technische workflow voor **[!UICONTROL Database cleanup]** worden gestart. |
| **[!UICONTROL Refused]** | Zacht/Hard | Het adres is in quarantaine geplaatst toe te schrijven aan een veiligheid terugkoppelt als spamrapport. Afhankelijk van de fout die door de provider is geretourneerd, wordt het adres rechtstreeks naar quarantaine verzonden of wordt de levering opnieuw geprobeerd totdat Campaign een fout ontvangt die de quarantainestatus rechtvaardigt of tot het aantal fouten 5 bereikt. |
| **[!UICONTROL Duplicate]** | Genegeerd | Het adres is reeds ontdekt in de segmentatie. |
| **[!UICONTROL Not defined]** | Zacht | het adres is in kwalificatie omdat de fouten niet zijn verhoogd. | toch. Dit type fout treedt op wanneer een nieuw foutbericht wordt verzonden door de server: het kan een geïsoleerde fout zijn, maar als deze opnieuw voorkomt, zal de foutenteller stijgen en worden de technische teams gewaarschuwd. |
| **[!UICONTROL Error ignored]** | Genegeerd | Het adres staat op de lijst van gewenste personen en er zal in elk geval een e-mail naar worden gestuurd. |
| **[!UICONTROL Address on denylist]** | Hard | Het adres werd toegevoegd aan de lijst van gewezen personen toen het verzenden. |
| **[!UICONTROL Account disabled]** | Zacht/Hard | Wanneer de Internet Access Provider (IAP) een lange periode van inactiviteit ontdekt, kan het de rekening van de gebruiker sluiten: levering aan het adres van de gebruiker zal dan onmogelijk zijn. Het type Soft of Hard is afhankelijk van het type ontvangen fout: als het account tijdelijk is uitgeschakeld vanwege een inactiviteit van zes maanden en nog steeds kan worden geactiveerd, wordt de status **[!UICONTROL Erroneous]** toegewezen en wordt de levering opnieuw geprobeerd. Als de ontvangen fout aangeeft dat het account permanent is gedeactiveerd, wordt de levering rechtstreeks in quarantaine geplaatst. |
| **[!UICONTROL Not connected]** | Genegeerd | De mobiele telefoon van het profiel is uitgeschakeld of heeft geen verbinding met het netwerk wanneer het bericht wordt verzonden. |
| **[!UICONTROL Invalid domain]** | Zacht | Het domein van het e-mailadres is onjuist of bestaat niet meer. Dit profiel wordt opnieuw geactiveerd tot het aantal fouten 5 is. Hierna wordt de record ingesteld op de status Quarantaine en wordt de levering niet opnieuw geprobeerd. |
| **[!UICONTROL Text too long]** | Genegeerd | Het aantal tekens in het SMS-bericht overschrijdt de limiet. Zie [Sms-codering, -lengte en -transliteratie](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) voor meer informatie. |
| **[!UICONTROL Character not supported by encoding]** | Genegeerd | Het SMS-bericht bevat een of meer tekens die niet door de codering worden ondersteund. &amp;Zie [Tabel met tekens - gsm-standaard](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard) voor meer informatie. |


**Verwante onderwerpen:**
* [Harde vlekken](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#hard-bounces)
* [Zachte golven](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#soft-bounces)

## Nieuwe pogingen na een tijdelijke leveringsfout {#retries-after-a-delivery-temporary-failure}

Als een bericht mislukt als gevolg van een tijdelijke fout, worden de pogingen opnieuw uitgevoerd tijdens de leveringsduur. Raadpleeg [Typen leveringsfouten en redenen](#delivery-failure-types-and-reasons) voor meer informatie over de typen fouten.

Het aantal pogingen (hoeveel opnieuw zou moeten worden uitgevoerd de dag nadat verzenden is begonnen) en de minimumvertraging tussen opnieuw probeert is nu<!--managed by the Adobe Campaign Enhanced MTA,--> gebaseerd op hoe goed IP zowel historisch als momenteel bij een bepaald domein uitvoert. De instellingen voor **Retries** in Campaign worden genegeerd.

<!--Please note that Adobe Campaign Enhanced MTA is not available for the Push channel.-->

Om de duur van een levering te wijzigen, gaat u naar de geavanceerde parameters van de levering of de leveringssjabloon en bewerkt u het veld **[!UICONTROL Delivery duration]** in de sectie [Validity period](../../administration/using/configuring-email-channel.md#validity-period-parameters).

>[!IMPORTANT]
>
>**De parameter **[!UICONTROL Delivery duration]**in uw Campaign-leveringen wordt nu alleen gebruikt als deze is ingesteld op 3,5 dagen of minder.** Als u een waarde definieert die hoger is dan 3,5 dagen, wordt hiermee geen rekening gehouden.

Als u bijvoorbeeld opnieuw wilt proberen om een levering na één dag te stoppen, kunt u de leveringsduur instellen op **1d** en worden de berichten in de wachtrij na één dag verwijderd.

>[!NOTE]
>
>Als een bericht maximaal 3,5 dagen in de wachtrij voor opnieuw proberen is geweest en niet is geleverd, wordt de time-out van het bericht vergroot en wordt de status ervan bijgewerkt<!--from **[!UICONTROL Sent]**--> tot **[!UICONTROL Failed]** in de [leveringslogs](../../sending/using/monitoring-a-delivery.md#delivery-logs).

<!--MOVED TO configuring-email-channel.md > LEGACY SETTINGS
The default configuration allows five retries at one-hour intervals, followed by one retry per day for four days. The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template (see [this section](../../administration/using/configuring-email-channel.md#sending-parameters)).-->

## Synchrone en asynchrone fouten {#synchronous-and-asynchronous-errors}

Een levering kan onmiddellijk mislukken (synchrone fout), of later nadat het is verzonden (asynchrone fout).

* **Synchrone fout**: Als de externe server waarmee contact is opgenomen door de Adobe Campaign-leveringsserver onmiddellijk een foutbericht retourneert, mag de levering niet naar de server van het profiel worden verzonden.
* **Asynchrone fout**: Een niet-bezorgde e-mail of een SR is later opnieuw verzonden door de ontvangende server. Asynchrone fouten kunnen optreden tot een week nadat een levering is verzonden.

## Kwalificatie van niet-bezorgde e-mails {#bounce-mail-qualification}

Voor de synchrone foutenmeldingen van de leveringsmislukking, bepaalt Adobe Campaign Verbeterde MTA (de Agent van de Overdracht van het Bericht) het stuittype en de kwalificatie, en stuurt die informatie terug naar Campagne.

>[!NOTE]
>
>De kwalificaties voor niet-bezorging in de tabel **[!UICONTROL Message qualification]** van Campaign worden niet meer gebruikt.

Asynchrone niet-bezorgingen worden nog steeds gekwalificeerd door het inMail-proces aan de hand van de regels voor **[!UICONTROL Inbound email]**. Als u deze regels wilt openen, klikt u op het **Adobe**-logo, linksboven, selecteert u **[!UICONTROL Administration > Channels > Email > Email processing rules]** en selecteert u **[!UICONTROL Bounce mails]**. Voor meer op deze regel, zie [deze sectie](../../administration/using/configuring-email-channel.md#email-processing-rules).

Zie [deze sectie](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#metrics-for-deliverability) voor meer informatie over grenzen en de verschillende soorten grenzen.

<!--MOVED TO configuring-email-channel.md > LEGACY SETTINGS

Bounces can have the following qualification statuses:

* **[!UICONTROL To qualify]**: the bounce mail needs to be qualified. Qualification must be done by the Deliverability team to ensure that the platform deliverability functions correctly. As long as it is not qualified, the bounce mail is not used to enrich the list of email processing rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Update for deliverability** workflow to be compared to existing email processing rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail was qualified but will not be used by the **Update for deliverability** workflow. So it will not be sent to the client instances.

To list the various bounces and their associated error types et reasons, click the **Adobe** logo, in the top left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)-->

## E-mailleverbaarheid optimaliseren met dubbele aanmeldingsprocedure {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

Het dubbele opt-inmechanisme is een best practice voor de verzending van e-mails. Het beveiligt het platform tegen onjuiste of ongeldige e-mailadressen en spambots en voorkomt mogelijke spamklachten.

Het principe is om een e-mail te verzenden om de instemming van bezoekers te bevestigen voordat u deze als profielen in uw Campaign-database opslaat. De bezoeker vult een online landingspagina in, ontvangt een e-mail en moet op de bevestigingskoppeling klikken om zijn inschrijving te voltooien.

Zie [deze sectie](../../channels/using/setting-up-a-double-opt-in-process.md)voor meer informatie.
