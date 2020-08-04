---
title: Werken met quarantainebeheer
description: Leer hoe u leveringen kunt optimaliseren met quarantainebeheer.
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
ht-degree: 81%

---


# Werken met quarantainebeheer{#understanding-quarantine-management}

## Quarantaine {#about-quarantines}

Een e-mailadres of telefoonnummer kan bijvoorbeeld in quarantaine worden geplaatst, wanneer de brievenbus volledig is of als het adres niet bestaat.

In alle gevallen voldoet de quarantaineprocedure aan de specifieke regels van deze [sectie](#conditions-for-sending-an-address-to-quarantine).

### Uw levering optimaliseren via quarantaine {#optimizing-your-delivery-through-quarantines}

De profielen waarvan de e-mailadressen of telefoonnummers in quarantaine zijn geplaatst, worden automatisch uitgesloten tijdens de voorbereiding van berichten (zie [In quarantaine geplaatste adressen voor een levering identificeren](#identifying-quarantined-addresses-for-a-delivery)). Hierdoor wordt de levering versneld, omdat het foutenpercentage een belangrijk effect heeft op de leveringssnelheid.

Sommige internetproviders beschouwen e-mails automatisch als spam als het aantal ongeldige adressen te hoog is. Met quarantaine kunt u dus voorkomen dat u door deze providers aan een lijst van afgewezen personen wordt toegevoegd.

Bovendien zijn de verzendkosten voor sms-berichten lager doordat onjuiste telefoonnummers van de levering worden uitgesloten.

Raadpleeg [deze pagina](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html) voor meer informatie over de best practices voor het beveiligen en optimaliseren van uw leveringen.

### Quarantine versus lijst van afgewezen personen {#quarantine-vs-block-list}

**Quarantaine** is alleen van toepassing op een adres, niet op het profiel zelf. Wanneer twee profielen hetzelfde e-mailadres hebben, worden ze dus allebei beïnvloed als het adres in quarantaine wordt geplaatst.

Op dezelfde manier kan een profiel waarvan het e-mailadres in quarantaine is geplaatst, zijn profiel bijwerken en een nieuw adres invoeren. Dit profiel kan dan opnieuw worden getarget door leveringsacties.

Being on the **block list**, on the other hand, will result in the profile no longer being targeted by any delivery, for example after an unsubscription (opt-out). Raadpleeg [Info over opt-in en opt-out in Campagne voor meer informatie over het proces voor](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)lijsten van afgewezen personen.

>[!NOTE]
>
>Wanneer een gebruiker op een SMS-bericht reageert met een trefwoord zoals &quot;STOP&quot; om zich af te melden voor SMS-leveringen, wordt dit profiel niet aan de lijst van afgewezen personen toegevoegd, zoals in het e-mailuitschakelproces. Het profieltelefoonnummer wordt in quarantaine geplaatst met de status **[!UICONTROL On block list]**. Deze status verwijst alleen naar het telefoonnummer, het profiel bevindt zich niet op de lijst van afgewezen personen zodat de gebruiker e-mailberichten blijft ontvangen. Raadpleeg [deze sectie](../../channels/using/managing-incoming-sms.md#managing-stop-sms) voor meer informatie hierover.

## In quarantaine geplaatste adressen identificeren {#identifying-quarantined-addresses}

Adressen kunnen in quarantaine worden geplaatst voor een specifieke levering of voor het volledige platform.

>[!NOTE]
>
>Als u een adres uit quarantaine moet halen, neemt u contact op met uw technische beheerder.

### In quarantaine geplaatste adressen voor een levering identificeren {#identifying-quarantined-addresses-for-a-delivery}

Bij adressen die voor een specifieke levering in quarantaine worden geplaatst, gebeurt dit tijdens de voorbereidingsfase van de levering, via het tabblad **[!UICONTROL Exclusion logs]** van het leveringsdashboard (zie [deze sectie](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). Raadpleeg [deze sectie](../../sending/using/preparing-the-send.md) voor meer informatie over het voorbereiden van leveringen.

![](assets/exclusion_logs.png)

### In quarantaine geplaatste adressen voor het volledige platform identificeren {#identifying-quarantined-addresses-for-the-entire-platform}

Vanuit het menu **[!UICONTROL Administration > Channels > Quarantines > Addresses]** kunnen beheerders ook adressen voor het gehele platform in quarantaine plaatsen.

>[!NOTE]
>
>Dit menu bevat quarantaine-elementen voor **e-mail**-, **sms**- en **pushberichtkanalen**.

![](assets/quarantines1.png)

>[!NOTE]
>
>De toename van het aantal quarantaines is een normaal effect dat verband houdt met de &quot;veroudering&quot; van de database. Als de levensduur van een e-mailadres wordt beschouwd als drie jaar en de lijst met ontvangers jaarlijks met 50% groeit, kan de verhoging van het aantal quarantaines als volgt worden berekend: Einde van jaar 1: (1*0,33)/(1+0,5)=22%. Einde van jaar 2: ((1,22*0,33)+0,33)/(1,5+0,75)=32,5%.

## Voorwaarden voor het in quarantaine plaatsen van een adres {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign beheert quarantaine op basis van leveringsfouten en de reden die wordt toegewezen bij de kwalificatie van foutmeldingen (zie [Fouttypen en redenen voor foute leveringen](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) en [Kwalificatie voor niet-bezorgde mail](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)).

* **Genegeerde fout**: bij genegeerde fouten wordt een adres niet in quarantaine geplaatst.
* **Harde fout**: het desbetreffende e-mailadres wordt onmiddellijk in quarantaine geplaatst.
* **Zachte fout**: bij zachte fouten wordt het adres niet direct in quarantaine geplaatst, maar neemt het aantal fouten op de foutenteller toe. Wanneer de foutenteller de grenswaarde bereikt, wordt het adres in quarantaine geplaatst. In de standaardconfiguratie is de drempel ingesteld op vijf fouten, waarbij twee fouten significant worden bij een tussenliggende periode van minstens 24 uur. Het adres wordt bij de vijfde fout in quarantaine geplaatst. De drempelwaarde voor de foutenteller kan worden gewijzigd. Raadpleeg [deze pagina](../../administration/using/configuring-email-channel.md#email-channel-parameters) voor meer informatie.

   Wanneer een levering bij een nieuwe poging succesvol is, wordt de foutenteller voor het adres dat in quarantaine stond, opnieuw geïnitialiseerd. De adresstatus verandert in **[!UICONTROL Valid]** en wordt na twee dagen door de **[!UICONTROL Database cleanup]**-workflow uit de quarantainelijst verwijderd.

Als een gebruiker een e-mail kwalificeert als spam (**Feedbacklus**), wordt het bericht automatisch doorgestuurd naar een technisch postvak dat door Campaign wordt beheerd. Het e-mailadres van de gebruiker wordt vervolgens automatisch in quarantaine geplaatst met de status **[!UICONTROL On block list]**. Deze status verwijst alleen naar het adres, het profiel bevindt zich niet op de lijst van afgewezen personen, zodat de gebruiker SMS-berichten en pushberichten blijft ontvangen.

>[!NOTE]
Quarantaine in Adobe Campaign is hoofdlettergevoelig. Zorg dat u de e-mailadressen in kleine letters importeert, zodat ze later niet opnieuw worden getarget.

In de lijst met adressen in quarantaine (zie [In quarantaine geplaatste adressen voor het volledige platform identificeren](#identifying-quarantined-addresses-for-the-entire-platform)) geeft het veld **[!UICONTROL Error reason]** aan waarom het geselecteerde adres in quarantaine werd geplaatst.

![](assets/quarantines2.png)

