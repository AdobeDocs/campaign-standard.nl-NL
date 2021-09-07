---
solution: Campaign Standard
product: campaign
title: Werken met quarantainebeheer
description: Leer hoe u leveringen kunt optimaliseren met quarantainebeheer.
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Deliverability
role: User
level: Intermediate
exl-id: ed269751-78ab-4189-89d9-116bf42c0c90
source-git-commit: 084838ff5ff369aaaa7715f5bec87a5133093750
workflow-type: tm+mt
source-wordcount: '1268'
ht-degree: 30%

---

# Werken met quarantainebeheer{#understanding-quarantine-management}

## Quarantaine {#about-quarantines}

Een e-mailadres of telefoonnummer kan bijvoorbeeld in quarantaine worden geplaatst, wanneer de brievenbus volledig is of als het adres niet bestaat.

In alle gevallen voldoet de quarantaineprocedure aan de specifieke regels van deze [sectie](#conditions-for-sending-an-address-to-quarantine).

### Uw levering optimaliseren via quarantaine {#optimizing-your-delivery-through-quarantines}

De profielen waarvan de e-mailadressen of telefoonnummers in quarantaine zijn geplaatst, worden automatisch uitgesloten tijdens de voorbereiding van berichten (zie [In quarantaine geplaatste adressen voor een levering identificeren](#identifying-quarantined-addresses-for-a-delivery)). Hierdoor wordt de levering versneld, omdat het foutenpercentage een belangrijk effect heeft op de leveringssnelheid.

Sommige internetproviders beschouwen e-mails automatisch als spam als het aantal ongeldige adressen te hoog is. Met quarantaine kunt u dus voorkomen dat u door deze providers aan de lijst van gewezen personen wordt toegevoegd.

Bovendien zijn de verzendkosten voor sms-berichten lager doordat onjuiste telefoonnummers van de levering worden uitgesloten.

Raadpleeg [deze pagina](../../sending/using/delivery-best-practices.md) voor meer informatie over de best practices voor het beveiligen en optimaliseren van uw leveringen.

### Quarantine versus Lijst van gewezen personen {#quarantine-vs-denylist}

Quarantaine en lijst van gewezen personen zijn niet van toepassing op hetzelfde object:

* **** Quarantineis slechts op een  **adres**  (of telefoonaantal, enz.), niet op het profiel zelf van toepassing. Een profiel waarvan het e-mailadres in quarantaine is geplaatst, kan bijvoorbeeld zijn profiel bijwerken en een nieuw adres invoeren. Dit profiel kan dan opnieuw worden geactiveerd door leveringsacties. Eveneens, als twee profielen gebeuren om het zelfde telefoonaantal te hebben, zullen zij allebei worden beïnvloed als het aantal quarantined is.

   De quarantined adressen of telefoonaantallen worden getoond in [uitsluitingslogboeken](identifying-quarantined-addresses-for-a-delivery) (voor een levering) of in [quarantainelijst](#identifying-quarantined-addresses-for-the-entire-platform) (voor het volledige platform).

* Als u daarentegen op de **lijst van gewezen personen** staat, wordt het **profiel** niet meer gericht op de levering, bijvoorbeeld na een abonnement (opt-out), voor een bepaald kanaal. Als een profiel op de lijst van gewezen personen voor het e-mailkanaal bijvoorbeeld twee e-mailadressen heeft, worden beide adressen van levering uitgesloten. Raadpleeg [Informatie over opt-in en opt-out in Campagne](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md) voor meer informatie over de lijst van gewezen personen.

   U kunt controleren of een profiel op de lijst van gewezen personen voor één of meerdere kanalen in de **[!UICONTROL No longer contact (on denylist)]** sectie van de **[!UICONTROL General]** tabel van het profiel is. Zie [deze sectie](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

>[!NOTE]
>
>Quarantaine bevat de status **Op lijst van gewezen personen**. Deze status is van toepassing wanneer ontvangers uw bericht melden als spam of op een SMS-bericht reageren met een trefwoord zoals &quot;STOP&quot;. In dat geval wordt het betreffende adres of telefoonnummer van het profiel naar quarantaine verzonden met de status **[!UICONTROL On denylist]**. Zie [deze sectie](../../channels/using/managing-incoming-sms.md#managing-stop-sms) voor meer informatie over het beheren van SMS-berichten van STOP.

<!--When a user replies to an SMS message with a keyword such as STOP in order to opt-out from SMS deliveries, his profile is not added to the denylist like in the email opt-out process. Instead, the profile's phone number is sent to quarantine with the **[!UICONTROL On denylist]** status. This status refers to the phone number only, meaning that the profile will continue receiving email messages.<!-- Also, if the profile has another phone number, he can still receive SMS messages on the other number. For more on this, refer to [this section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).-->

## In quarantaine geplaatste adressen identificeren {#identifying-quarantined-addresses}

De gekwalificeerde adressen kunnen voor een specifieke levering of voor het volledige platform worden getoond.

<!--
If you need to remove an address from quarantine, contact your technical administrator.
-->

### In quarantaine geplaatste adressen voor een levering identificeren {#identifying-quarantined-addresses-for-a-delivery}

Bij adressen die voor een specifieke levering in quarantaine worden geplaatst, gebeurt dit tijdens de voorbereidingsfase van de levering, via het tabblad **[!UICONTROL Exclusion logs]** van het leveringsdashboard (zie [deze sectie](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). Raadpleeg [deze sectie](../../sending/using/preparing-the-send.md) voor meer informatie over het voorbereiden van leveringen.

![](assets/exclusion_logs.png)

### In quarantaine geplaatste adressen voor het volledige platform identificeren {#identifying-quarantined-addresses-for-the-entire-platform}

Beheerders hebben via het menu **[!UICONTROL Administration > Channels > Quarantines > Addresses]** toegang tot de gedetailleerde lijst met e-mailadressen in quarantaine voor het gehele platform.

<!--
This menu lists quarantined elements for **Email**, **SMS** and **Push notification** channels.
-->

![](assets/quarantines1.png)

>[!NOTE]
>
>De toename van het aantal quarantaine is een normaal effect dat verband houdt met de &quot;slijtage&quot; van de database. Als de levensduur van een e-mailadres wordt beschouwd als drie jaar en de lijst met ontvangers jaarlijks met 50% groeit, kan de verhoging van het aantal quarantaines als volgt worden berekend: Einde van jaar 1: (1*0,33)/(1+0,5)=22%. Einde van jaar 2: ((1,22*0,33)+0,33)/(1,5+0,75)=32,5%.

Er zijn filters beschikbaar waarmee u door de lijst kunt bladeren. U kunt filteren op het adres, de status en/of het kanaal.

![](assets/quarantines-filters.png)

U kunt elk item bewerken of [verwijderen en nieuwe maken.](#removing-a-quarantined-address)

Als u een item wilt bewerken, klikt u op de desbetreffende rij en wijzigt u de velden naar wens.

![](assets/quarantines-edit.png)

Als u handmatig een nieuw item wilt toevoegen, gebruikt u de knop **[!UICONTROL Create]**.

![](assets/quarantines-create-button.png)

Definieer het adres (of telefoonnummer, enz.) en kanaaltype. U kunt een status instellen om in de quarantainelijst te staan en een reden voor een fout. U kunt ook de datum aangeven waarop de fout is opgetreden, het aantal fouten en de fouttekst invoeren. Selecteer zo nodig de laatste levering die naar het adres is verzonden in de vervolgkeuzelijst.

![](assets/quarantines-create-last-delivery.png)

### Het verwijderen van een quarantined adres {#removing-a-quarantined-address}

Indien nodig, kunt u een adres uit de quarantainelijst manueel verwijderen. Daarnaast worden adressen die overeenkomen met specifieke voorwaarden automatisch uit de quarantainelijst verwijderd door de workflow **[!UICONTROL Database cleanup]**. (Zie [deze sectie](../../administration/using/technical-workflows.md#list-of-technical-workflows) voor meer informatie over technische workflows.)

Als u een adres handmatig uit de quarantainelijst wilt verwijderen, voert u een van de onderstaande handelingen uit.

>[!IMPORTANT]
Als u handmatig een e-mailadres uit quarantaine verwijdert, betekent dit dat u opnieuw gaat leveren aan dit adres. Dientengevolge, kan dit ernstige gevolgen op uw leverbaarheid en IP reputatie hebben, die uiteindelijk tot uw IP adres of verzendend domein zou kunnen leiden die worden geblokkeerd. Ga extra voorzichtig te werk wanneer u overweegt een adres uit quarantaine te verwijderen. Neem in geval van twijfel contact op met een leverancier.

* Selecteer het adres in de lijst **[!UICONTROL Administration > Channels > Quarantines > Addresses]** en selecteer **[!UICONTROL Delete element]**.

   ![](assets/quarantine-delete-address.png)

* Selecteer een adres en verander **[!UICONTROL Status]** in **[!UICONTROL Valid]**.

   ![](assets/quarantine-valid-status.png)

   U kunt ook de status wijzigen in **[!UICONTROL On allowlist]**. In dit geval blijft het adres op de quarantainelijst staan, maar het wordt systematisch als doel gebruikt, zelfs als er een fout optreedt.

De adressen worden automatisch verwijderd uit de quarantainelijst in de volgende gevallen:

* Adressen in een status **[!UICONTROL Erroneous]** zullen uit de quarantainelijst na succesvolle levering worden verwijderd.
* Adressen in een status **[!UICONTROL Erroneous]** worden uit de quarantainelijst verwijderd als de laatste zachte stuit meer dan 10 dagen geleden plaatsvond. Zie [deze sectie](#soft-error-management) voor meer informatie over softerror management.
* Adressen in een status **[!UICONTROL Erroneous]** die met de fout **[!UICONTROL Mailbox full]** zijn verworpen zullen na 30 dagen uit de quarantainelijst worden verwijderd.

Hun status verandert dan in **[!UICONTROL Valid]**.

>[!IMPORTANT]
Ontvangers met een adres in de status **[!UICONTROL Quarantine]** of **[!UICONTROL On denylist]** worden nooit automatisch verwijderd, zelfs niet als ze een e-mail ontvangen.

Het maximumaantal uit te voeren pogingen in het geval van **[!UICONTROL Erroneous]** status en de minimumvertraging tussen pogingen zijn nu gebaseerd op hoe goed IP zowel historisch als momenteel bij een bepaald domein uitvoert.

## Voorwaarden voor het in quarantaine plaatsen van een adres {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign beheert quarantaine op basis van leveringsfouten en de reden die wordt toegewezen bij de kwalificatie van foutmeldingen (zie [Fouttypen en redenen voor foute leveringen](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) en [Kwalificatie voor niet-bezorgde mail](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)).

* **Genegeerde fout**: bij genegeerde fouten wordt een adres niet in quarantaine geplaatst.
* **Harde fout**: het desbetreffende e-mailadres wordt onmiddellijk in quarantaine geplaatst.
* **Zachte fout**: bij zachte fouten wordt het adres niet direct in quarantaine geplaatst, maar neemt het aantal fouten op de foutenteller toe. Zie [Zwak foutenbeheer](#soft-error-management) voor meer informatie.

   <!--
  When the error counter reaches the limit threshold, the address goes into quarantine. In the default configuration, the threshold is set at five errors, where two errors are significant if they occur at least 24 hours apart. The address is placed in quarantine at the fifth error. The error counter threshold can be modified. For more on this, refer to this [page](../../administration/using/configuring-email-channel.md#email-channel-parameters).
  When a delivery is successful after a retry, the error counter of the address which was prior to that quarantined is reinitialized. The address status changes to **[!UICONTROL Valid]** and it is deleted from the list of quarantines after two days by the **[!UICONTROL Database cleanup]** workflow.
  -->

Als een gebruiker een e-mail als spam ([terugkoppelt lijn](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops)) kwalificeert, wordt het bericht automatisch opnieuw gericht naar een technische brievenbus die door Adobe wordt geleid. Het e-mailadres van de gebruiker wordt vervolgens automatisch in quarantaine geplaatst met de status **[!UICONTROL On denylist]**. Deze status verwijst alleen naar het adres, het profiel staat niet op de lijst van gewezen personen, zodat de gebruiker SMS-berichten en pushberichten blijft ontvangen.

>[!NOTE]
Quarantaine in Adobe Campaign is hoofdlettergevoelig. Zorg dat u de e-mailadressen in kleine letters importeert, zodat ze later niet opnieuw worden getarget.

In de lijst met adressen in quarantaine (zie [In quarantaine geplaatste adressen voor het volledige platform identificeren](#identifying-quarantined-addresses-for-the-entire-platform)) geeft het veld **[!UICONTROL Error reason]** aan waarom het geselecteerde adres in quarantaine werd geplaatst.

![](assets/quarantines2.png)

### Beheer van zachte fouten {#soft-error-management}

In tegenstelling tot harde fouten, verzenden de zachte fouten onmiddellijk geen adres naar quarantaine, maar zij verhogen in plaats daarvan een foutenteller.

Opnieuw proberen wordt uitgevoerd tijdens de [leveringsduur](../../administration/using/configuring-email-channel.md#validity-period-parameters). Wanneer de foutenteller de grenswaarde bereikt, wordt het adres in quarantaine geplaatst. Voor meer op dit, verwijs naar [Opnieuw na een levering tijdelijke mislukking](understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

<!--In the default configuration, the threshold is set at five errors, where two errors are significant if they occur at least 24 hours apart. The address is placed in quarantine at the fifth error.
The error counter threshold can be modified.-->

De foutenteller wordt opnieuw geïnitialiseerd als de laatste significante fout meer dan 10 dagen geleden voorkwam. De adresstatus verandert dan in **Geldig** en het wordt geschrapt uit de lijst van quarantines door **Opschonen van het Gegevensbestand** werkschema. (Zie [deze sectie](../../administration/using/technical-workflows.md#list-of-technical-workflows) voor meer informatie over technische workflows.)
