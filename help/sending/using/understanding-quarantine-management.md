---
title: Werken met quarantainebeheer
description: Leer hoe u leveringen kunt optimaliseren met quarantainebeheer.
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Deliverability
role: User
level: Intermediate
exl-id: ed269751-78ab-4189-89d9-116bf42c0c90
source-git-commit: 449187bba167f9ce00e644d44a124b36030ba001
workflow-type: tm+mt
source-wordcount: '1430'
ht-degree: 22%

---

# Werken met quarantainebeheer{#understanding-quarantine-management}

## Informatie over quarantines {#about-quarantines}

Een e-mailadres of telefoonnummer kan bijvoorbeeld in quarantaine worden geplaatst, wanneer de brievenbus volledig is of als het adres niet bestaat.

In alle gevallen voldoet de quarantaineprocedure aan de specifieke regels van deze [sectie](#conditions-for-sending-an-address-to-quarantine).

### De levering optimaliseren via quarantines {#optimizing-your-delivery-through-quarantines}

De profielen waarvan de e-mailadressen of telefoonnummers in quarantaine zijn geplaatst, worden automatisch uitgesloten tijdens de voorbereiding van berichten (zie [In quarantaine geplaatste adressen voor een levering identificeren](#identifying-quarantined-addresses-for-a-delivery)). Hierdoor wordt de levering versneld, omdat het foutenpercentage een belangrijk effect heeft op de leveringssnelheid.

Sommige internetproviders beschouwen e-mails automatisch als spam als het aantal ongeldige adressen te hoog is. Met quarantaine kunt u dus voorkomen dat deze providers aan de lijst van gewezen personen worden toegevoegd.

Bovendien zijn de verzendkosten voor sms-berichten lager doordat onjuiste telefoonnummers van de levering worden uitgesloten.

Raadpleeg [deze pagina](../../sending/using/delivery-best-practices.md) voor meer informatie over de best practices voor het beveiligen en optimaliseren van uw leveringen.

### Quarantine versus Lijst van gewezen personen {#quarantine-vs-denylist}

Quarantaine en lijst van gewezen personen zijn niet van toepassing op hetzelfde object:

* **quarantaine** is slechts op een **adres** (of telefoonaantal, enz.), niet op het profiel zelf van toepassing. Een profiel waarvan het e-mailadres in quarantaine is geplaatst, kan bijvoorbeeld zijn profiel bijwerken en een nieuw adres invoeren. Dit profiel kan dan opnieuw worden geactiveerd door leveringsacties. Eveneens, als twee profielen gebeuren om het zelfde telefoonaantal te hebben, zullen zij allebei worden beïnvloed als het aantal quarantined is.

  De quarantined adressen of telefoonaantallen worden getoond in [ uitsluitingslogboeken ](#identifying-quarantined-addresses-for-a-delivery) (voor een levering) of in de [ quarantainelijst ](#identifying-quarantined-addresses-for-the-entire-platform) (voor het volledige platform).

* Het zijn op de **lijst van gewezen personen**, anderzijds, zal in het **profiel** resulteren niet meer door de levering, zoals na een unsubscription (opt-out), voor een bepaald kanaal wordt gericht. Als een profiel op de lijst van gewezen personen voor het e-mailkanaal bijvoorbeeld twee e-mailadressen heeft, worden beide adressen van levering uitgesloten. Voor meer op het proces van de lijst van gewezen personen, verwijs naar [ Ongeveer opt-in en opt-out in Campagne ](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

  In de sectie **[!UICONTROL No longer contact (on denylist)]** van het tabblad **[!UICONTROL General]** van het profiel kunt u controleren of er zich op de lijst van gewezen personen een of meer kanalen bevinden in de sectie  van het profiel. Zie [deze sectie](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

>[!NOTE]
>
>De quarantaine omvat een **op de status van de lijst van gewezen personen**, die van toepassing is wanneer de ontvangers uw bericht als spam melden of op een bericht van SMS met een sleutelwoord zoals &quot;STOP&quot;antwoorden. In dat geval wordt het betreffende adres of telefoonnummer van het profiel naar quarantaine verzonden met de status **[!UICONTROL On denylist]** . Voor meer bij het beheren van STOP SMS berichten, verwijs naar [ deze sectie ](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

&lt;!—Wanneer een gebruiker op een SMS-bericht reageert met een trefwoord zoals STOP om te weigeren van SMS-leveringen, wordt dit profiel niet toegevoegd aan de lijst van gewezen personen, zoals in het e-mailuitschakelproces. In plaats daarvan wordt het telefoonnummer van het profiel naar quarantaine verzonden met de status **[!UICONTROL On denylist]** . Deze status verwijst alleen naar het telefoonnummer, wat betekent dat het profiel e-mailberichten blijft ontvangen.<!-- Also, if the profile has another phone number, he can still receive SMS messages on the other number. For more on this, refer to [this section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).-->

## In quarantaine geplaatste adressen identificeren {#identifying-quarantined-addresses}

De gekwalificeerde adressen kunnen voor een specifieke levering of voor het volledige platform worden getoond.

<!--
If you need to remove an address from quarantine, contact your technical administrator.
-->

### Het identificeren van quarantined adressen voor een levering {#identifying-quarantined-addresses-for-a-delivery}

Bij adressen die voor een specifieke levering in quarantaine worden geplaatst, gebeurt dit tijdens de voorbereidingsfase van de levering, via het tabblad **[!UICONTROL Exclusion logs]** van het leveringsdashboard (zie [deze sectie](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). Raadpleeg [deze sectie](../../sending/using/preparing-the-send.md) voor meer informatie over het voorbereiden van leveringen.

![](assets/exclusion_logs.png)

### Het identificeren van quarantined adressen voor het volledige platform {#identifying-quarantined-addresses-for-the-entire-platform}

Beheerders hebben via het menu **[!UICONTROL Administration > Channels > Quarantines > Addresses]** toegang tot de gedetailleerde lijst met e-mailadressen in quarantaine voor het gehele platform.

<!--
This menu lists quarantined elements for **Email**, **SMS** and **Push notification** channels.
-->

![](assets/quarantines1.png)

>[!NOTE]
>
>De toename van het aantal quarantaine is een normaal effect dat verband houdt met de &quot;slijtage&quot; van de database. Bijvoorbeeld, als het leven van een e-mailadres wordt beschouwd als drie jaar en de ontvankelijke lijst stijgt met 50% elk jaar, kan de verhoging in quarantines als volgt worden berekend: Eind van Jaar 1: (1 &#42; 0.33)/(1+0.5)=22%. Eind van Jaar 2: (1.22 &#42; 0.33) + 0.33)/(1.5+0.75)=32.5%.

Er zijn filters beschikbaar waarmee u door de lijst kunt bladeren. U kunt filteren op adres, status en/of kanaal.

![](assets/quarantines-filters.png)

U kunt uitgeven of [ schrappen ](#removing-a-quarantined-address) elke ingang, evenals nieuwe degenen creëren.

Als u een item wilt bewerken, klikt u op de desbetreffende rij en wijzigt u de velden naar wens.

![](assets/quarantines-edit.png)

Als u handmatig een nieuwe vermelding wilt toevoegen, gebruikt u de knop **[!UICONTROL Create]** .

![](assets/quarantines-create-button.png)

Definieer het adres (of telefoonnummer, enz.) en kanaaltype. U kunt een status instellen om in de quarantainelijst te staan en een reden voor een fout. U kunt ook de datum aangeven waarop de fout is opgetreden, het aantal fouten en de fouttekst invoeren. Selecteer zo nodig de laatste levering die naar het adres is verzonden in de vervolgkeuzelijst.

![](assets/quarantines-create-last-delivery.png)

## Een adres uit quarantaine verwijderen {#removing-a-quarantined-address}

### Automatische updates {#unquarantine-auto}

Adressen die specifieke voorwaarden aanpassen worden automatisch geschrapt uit de quarantainelijst door het opschoonwerkschema van het Gegevensbestand. Leer meer over technische werkschema&#39;s, zie [ deze sectie ](../../administration/using/technical-workflows.md#list-of-technical-workflows).

De adressen worden automatisch verwijderd uit de quarantainelijst in de volgende gevallen:

* Adressen in de status **[!UICONTROL Erroneous]** worden na een geslaagde levering uit de quarantainelijst verwijderd.
* Adressen in een status **[!UICONTROL Erroneous]** worden uit de quarantainelijst verwijderd als de laatste zachte stuit meer dan 10 dagen geleden plaatsvond. Voor meer op softfoutenbeheer, zie [ deze sectie ](#soft-error-management).
* Adressen in een **[!UICONTROL Erroneous]** -status die met de **[!UICONTROL Mailbox full]** -fout zijn gemarkeerd, worden na 30 dagen uit de quarantainelijst verwijderd.

De status verandert vervolgens in **[!UICONTROL Valid]** .

Het maximumaantal uit te voeren pogingen in het geval van **[!UICONTROL Erroneous]** status en de minimumvertraging tussen pogingen zijn nu gebaseerd op hoe goed IP zowel historisch als momenteel bij een bepaald domein uitvoert.


>[!IMPORTANT]
>
>Ontvangers met een adres in de status **[!UICONTROL Quarantine]** of **[!UICONTROL Denylisted]** worden nooit verwijderd, zelfs niet als ze een e-mail ontvangen.


### Handmatige updates {#unquarantine-manual}

U kunt een adres ook handmatig uit de quarantaine verwijderen.  Als u een adres handmatig uit de quarantainelijst wilt verwijderen, kunt u het uit de quarantainelijst verwijderen of de status ervan wijzigen in **[!UICONTROL Valid]** .

* Selecteer het adres in de lijst **[!UICONTROL Administration > Channels > Quarantines > Addresses]** en selecteer **[!UICONTROL Delete element]** .

  ![](assets/quarantine-delete-address.png)

* Selecteer een adres en wijzig **[!UICONTROL Status]** in **[!UICONTROL Valid]** .

  ![](assets/quarantine-valid-status.png)


### Bulkupdates {#unquarantine-bulk}

U zou bulkupdates op de quarantainelijst, bijvoorbeeld in het geval van een ISP stroomonderbreking kunnen moeten uitvoeren. In dat geval worden e-mails ten onrechte als bonnen gemarkeerd omdat ze niet met succes aan de ontvanger kunnen worden bezorgd. Deze adressen moeten uit de quarantainelijst worden verwijderd.

Om dit te doen, creeer een werkschema en voeg een **[!UICONTROL Query]** activiteit op uw quarantainetabel toe om alle beïnvloede ontvangers uit te filteren. Als deze eenmaal zijn geïdentificeerd, kunnen ze uit de quarantainelijst worden verwijderd en worden opgenomen in toekomstige e-mailleveringen voor campagnes.

Gebaseerd op het tijdkader van het incident, hieronder zijn de geadviseerde richtlijnen voor deze vraag.

* **de tekst van de Fout (quarantainetekst)** bevat &quot;550-5.1.1&quot;EN **Tekst van de Fout (quarantainetekst)** bevat &quot;support.ISP.com&quot;

  waar &quot;support.ISP.com&quot; kan zijn: bijvoorbeeld &quot;support.apple.com&quot; of &quot;support.google.com&quot;

* **status van de Update (@lastModified)** op of na `MM/DD/YYYY HH:MM:SS AM`
* **status van de Update (@lastModified)** op of vóór `MM/DD/YYYY HH:MM:SS PM`

Als u de lijst met betrokken ontvangers hebt, voegt u een **[!UICONTROL Update data]** -activiteit toe om de status van hun e-mailadres in te stellen op **[!UICONTROL Valid]** , zodat ze uit de quarantainelijst worden verwijderd via de **[!UICONTROL Database cleanup]** -workflow. U kunt ze ook gewoon uit de quarantainetabel verwijderen.

## Voorwaarden voor verzending van een adres naar quarantaine {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign beheert quarantaine op basis van leveringsfouten en de reden die wordt toegewezen bij de kwalificatie van foutmeldingen (zie [Fouttypen en redenen voor foute leveringen](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) en [Kwalificatie voor niet-bezorgde mail](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)).

* **Genegeerde fout**: bij genegeerde fouten wordt een adres niet in quarantaine geplaatst.
* **Harde fout**: het desbetreffende e-mailadres wordt onmiddellijk in quarantaine geplaatst.
* **Zachte fout**: bij zachte fouten wordt het adres niet direct in quarantaine geplaatst, maar neemt het aantal fouten op de foutenteller toe. Voor meer op dit, zie [ Zacht foutenbeheer ](#soft-error-management).

  <!--
  When the error counter reaches the limit threshold, the address goes into quarantine. In the default configuration, the threshold is set at five errors, where two errors are significant if they occur at least 24 hours apart. The address is placed in quarantine at the fifth error. The error counter threshold can be modified. For more on this, refer to this [page](../../administration/using/configuring-email-channel.md#email-channel-parameters).
  When a delivery is successful after a retry, the error counter of the address which was prior to that quarantined is reinitialized. The address status changes to **[!UICONTROL Valid]** and it is deleted from the list of quarantines after two days by the **[!UICONTROL Database cleanup]** workflow.
  -->

Als een gebruiker een e-mail als spam ([ kwalificeert koppelt lijn ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops)), wordt het bericht automatisch opnieuw gericht naar een technische brievenbus die door Adobe wordt geleid. Het e-mailadres van de gebruiker wordt vervolgens automatisch in quarantaine geplaatst met de status **[!UICONTROL On denylist]**. Deze status verwijst alleen naar het adres, het profiel staat niet op de lijst van gewezen personen, zodat de gebruiker SMS-berichten en pushberichten blijft ontvangen.

>[!NOTE]
>
>Quarantaine in Adobe Campaign is hoofdlettergevoelig. Zorg dat u de e-mailadressen in kleine letters importeert, zodat ze later niet opnieuw worden getarget.

In de lijst met adressen in quarantaine (zie [In quarantaine geplaatste adressen voor het volledige platform identificeren](#identifying-quarantined-addresses-for-the-entire-platform)) geeft het veld **[!UICONTROL Error reason]** aan waarom het geselecteerde adres in quarantaine werd geplaatst.

![](assets/quarantines2.png)

### Beheer van zachte fouten {#soft-error-management}

In tegenstelling tot harde fouten, verzenden de zachte fouten onmiddellijk geen adres naar quarantaine, maar zij verhogen in plaats daarvan een foutenteller.

De pogingen zullen tijdens de [ leveringsduur ](../../administration/using/configuring-email-channel.md#validity-period-parameters) worden uitgevoerd. Wanneer de foutenteller de grenswaarde bereikt, wordt het adres in quarantaine geplaatst. Voor meer op dit, verwijs naar [ probeert na een tijdelijke mislukking van de levering ](understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

<!--In the default configuration, the threshold is set at five errors, where two errors are significant if they occur at least 24 hours apart. The address is placed in quarantine at the fifth error.
The error counter threshold can be modified.-->

De foutenteller wordt opnieuw geïnitialiseerd als de laatste significante fout meer dan 10 dagen geleden voorkwam. De adresstatus verandert dan in **Geldig** en het wordt geschrapt van de lijst van quarantines door het **schoonmaakbeurt van het Gegevensbestand** werkschema. (Voor meer op technische werkschema&#39;s, zie [ deze sectie ](../../administration/using/technical-workflows.md#list-of-technical-workflows).)
