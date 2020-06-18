---
title: Werken met quarantainebeheer
description: Leer hoe u uw prestaties kunt optimaliseren met quarantainebeheer.
page-status-flag: never-activated
uuid: 3c287865-1ada-4351-b205-51807ff9f7ed
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: de3a50b6-ea8f-4521-996b-c49cc1f3c946
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 121ec37cef6193d3a7085b6d0296b6a2e7cafa06
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 0%

---


# Werken met quarantainebeheer{#understanding-quarantine-management}

## Informatie over quarantines {#about-quarantines}

Een e-mailadres of een telefoonaantal kunnen in quarantined worden, bijvoorbeeld, wanneer de brievenbus volledig is of als het adres niet bestaat.

In elk geval voldoet de quarantaineprocedure aan de specifieke voorschriften van deze [sectie](#conditions-for-sending-an-address-to-quarantine).

### De levering optimaliseren via quarantines {#optimizing-your-delivery-through-quarantines}

De profielen waarvan e-mailadressen of telefoonaantal in quarantaine zijn worden automatisch uitgesloten tijdens berichtvoorbereiding (zie het [identificeren van quarantined adressen voor een levering](#identifying-quarantined-addresses-for-a-delivery)). Dit zal leveranties versnellen, aangezien het foutenpercentage een significant effect op leveringssnelheid heeft.

Sommige internetproviders beschouwen e-mails automatisch als spam als de snelheid van ongeldige adressen te hoog is. Met quarantaine kunt u dus voorkomen dat deze providers aan een bloklijst worden toegevoegd.

Bovendien helpen quarantines de verzendkosten van SMS te verminderen door onjuiste telefoonaantallen van leveringen uit te sluiten.

Raadpleeg [deze pagina](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html)voor meer informatie over tips en trucs voor het beveiligen en optimaliseren van leveringen.

### Quarantine versus block list {#quarantine-vs-block-list}

**Quarantaine** is alleen van toepassing op een adres, niet op het profiel zelf. Dit betekent dat twee profielen met hetzelfde e-mailadres worden beïnvloed als het adres in quarantaine wordt geplaatst.

Op dezelfde manier kan een profiel waarvan het e-mailadres in quarantaine is geplaatst, zijn profiel bijwerken en een nieuw adres invoeren. Dit profiel kan vervolgens opnieuw worden geactiveerd door leveringsacties.

Als het profiel op de **bloklijst** staat, wordt het profiel echter niet meer gericht op levering, bijvoorbeeld na een abonnement (opt-out). Raadpleeg [Info over opt-in en opt-out in Campagne voor meer informatie over het bloklijstproces](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

>[!NOTE]
>
>Wanneer een gebruiker op een SMS-bericht reageert met een trefwoord zoals &quot;STOP&quot; om zich af te melden voor SMS-leveringen, wordt dit profiel niet toegevoegd aan de bloklijst, zoals in het e-mailuitschakelproces. Het profieltelefoonnummer wordt naar quarantaine met de **[!UICONTROL On block list]** status verzonden. Deze status verwijst alleen naar het telefoonnummer. Het profiel staat niet in de bloklijst, zodat de gebruiker e-mailberichten blijft ontvangen. For more on this, refer to [this section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

## In quarantaine geplaatste adressen identificeren {#identifying-quarantined-addresses}

De gekwalificeerde adressen kunnen voor een specifieke levering of voor het volledige platform worden vermeld.

>[!NOTE]
>
>Als u een adres uit quarantaine moet verwijderen, contacteer uw technische beheerder.

### Het identificeren van quarantined adressen voor een levering {#identifying-quarantined-addresses-for-a-delivery}

Gegarandeerde adressen voor een specifieke levering zijn vermeld tijdens de leveringsvoorbereidingsfase, op het **[!UICONTROL Exclusion logs]** lusje van het leveringsdashboard (zie [deze sectie](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). For more on delivery preparation, refer to [this section](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### Het identificeren van quarantined adressen voor het volledige platform {#identifying-quarantined-addresses-for-the-entire-platform}

Beheerders kunnen de adressen in quarantaine weergeven voor het gehele platform vanuit het **[!UICONTROL Administration > Channels > Quarantines > Addresses]** menu.

>[!NOTE]
>
>Dit menu bevat quarantaine-elementen voor **e-mail**-, **SMS** - en **pushberichtkanalen** .

![](assets/quarantines1.png)

>[!NOTE]
>
>De toename van het aantal quarantines is een normaal effect dat verband houdt met de &quot;slijtage&quot; van de database. Bijvoorbeeld, als de levensduur van een e-mailadres wordt beschouwd als drie jaar en de ontvankelijke lijst met 50% elk jaar stijgt, kan de verhoging van quarantines als volgt worden berekend: Einde van jaar 1: (1*0,33)/(1+0,5)=22%. Einde van jaar 2: (1,22*0,33)+0,33)/(1,5+0,75)=32,5%.

## Voorwaarden voor verzending van een adres naar quarantaine {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign beheert quarantaine volgens het type van de leveringsmislukking en de reden die tijdens de kwalificatie van foutenmeldingen wordt toegewezen (zie de types van de mislukking van de [Levering en de redenen](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) en de [kwalificatie](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)van de Stuitse post).

* **Genegeerde fout**: genegeerde fouten sturen geen adres naar quarantaine.
* **Harde fout**: het desbetreffende e-mailadres wordt onmiddellijk naar quarantaine verzonden.
* **Zachte fout**: de zachte fouten verzenden onmiddellijk geen adres naar quarantaine, maar zij verhogen een foutenteller. Wanneer de foutenteller de grensdrempel bereikt, gaat het adres in quarantaine. In de standaardconfiguratie is de drempel ingesteld op vijf fouten, waarbij twee fouten significant zijn als ze zich op een afstand van minstens 24 uur bevinden. Het adres wordt in quarantaine geplaatst bij de vijfde fout. De drempelwaarde voor de foutteller kan worden gewijzigd. Raadpleeg deze [pagina](../../administration/using/configuring-email-channel.md#email-channel-parameters)voor meer informatie.

   Wanneer een levering succesvol na opnieuw probeert, wordt de foutenteller van het adres dat voorafgaand aan die quarantined was opnieuw geïnitialiseerd. De adresstatus verandert in **[!UICONTROL Valid]** en wordt na twee dagen door de **[!UICONTROL Database cleanup]** workflow verwijderd uit de lijst met quarantines.

Als een gebruiker een e-mail als spam (**Terugkoppeling lijn**) kwalificeert, wordt het bericht automatisch opnieuw gericht naar een technische brievenbus die door Campagne wordt geleid. Het e-mailadres van de gebruiker wordt vervolgens automatisch naar quarantaine verzonden met de **[!UICONTROL On block list]** status. Deze status verwijst alleen naar het adres, het profiel staat niet op de bloklijst, zodat de gebruiker SMS-berichten en pushberichten blijft ontvangen.

>[!NOTE]
Quarantine in Adobe Campaign is hoofdlettergevoelig. Importeer e-mailadressen in kleine letters, zodat ze later niet opnieuw worden toegewezen.

In de lijst van quarantined adressen (zie het [identificeren van quarantined adressen voor het volledige platform](#identifying-quarantined-addresses-for-the-entire-platform)), wijst het **[!UICONTROL Error reason]** gebied erop waarom het geselecteerde adres in quarantaine werd geplaatst.

![](assets/quarantines2.png)

