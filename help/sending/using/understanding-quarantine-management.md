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
source-git-commit: 21bcc9818b881212985988ef3377687069a1dbea
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

* **Quarantine** is alleen van toepassing op een **adres** (of telefoonnummer, enz.), niet naar het profiel zelf. Een profiel waarvan het e-mailadres in quarantaine is geplaatst, kan bijvoorbeeld zijn profiel bijwerken en een nieuw adres invoeren. Dit profiel kan dan opnieuw worden geactiveerd door leveringsacties. Eveneens, als twee profielen gebeuren om het zelfde telefoonaantal te hebben, zullen zij allebei worden beïnvloed als het aantal quarantined is.

  De in quarantaine geplaatste adressen of telefoonaantallen worden getoond in [uitsluitingslogboeken](#identifying-quarantined-addresses-for-a-delivery) (voor levering) of in de [quarantainelijst](#identifying-quarantined-addresses-for-the-entire-platform) (voor het gehele platform).

* Aan de slag **lijst van gewezen personen** anderzijds zal **profiel** niet langer het doelwit is van de levering, bijvoorbeeld na een abonnement (opt-out), voor een bepaald kanaal. Als een profiel op de lijst van gewezen personen voor het e-mailkanaal bijvoorbeeld twee e-mailadressen heeft, worden beide adressen van levering uitgesloten. Voor meer informatie over het proces van de lijst van gewezen personen, verwijs naar [Over opt-in en opt-out in campagne](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

  U kunt controleren of een profiel op de lijst van gewezen personen voor een of meer kanalen in het dialoogvenster **[!UICONTROL No longer contact (on denylist)]** van het profiel **[!UICONTROL General]** tab. Zie [deze sectie](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

>[!NOTE]
>
>Quarantine bevat een **Op lijst van gewezen personen** status, die van toepassing is wanneer ontvangers uw bericht melden als spam of op een SMS-bericht reageren met een trefwoord zoals &quot;STOP&quot;. In dat geval wordt het betreffende adres of telefoonnummer van het profiel verzonden naar quarantaine met de **[!UICONTROL On denylist]** status. Voor meer informatie over het beheren van SMS-berichten van STOP raadpleegt u [deze sectie](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

&lt;!—Wanneer een gebruiker op een SMS-bericht reageert met een trefwoord zoals STOP om te weigeren van SMS-leveringen, wordt dit profiel niet toegevoegd aan de lijst van gewezen personen, zoals in het e-mailuitschakelproces. In plaats daarvan wordt het telefoonnummer van het profiel verzonden naar quarantaine met de **[!UICONTROL On denylist]** status. Deze status verwijst alleen naar het telefoonnummer, wat betekent dat het profiel e-mailberichten blijft ontvangen.<!-- Also, if the profile has another phone number, he can still receive SMS messages on the other number. For more on this, refer to [this section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).-->

## In quarantaine geplaatste adressen identificeren {#identifying-quarantined-addresses}

De gekwalificeerde adressen kunnen voor een specifieke levering of voor het volledige platform worden getoond.

<!--
If you need to remove an address from quarantine, contact your technical administrator.
-->

### Het identificeren van quarantined adressen voor een levering {#identifying-quarantined-addresses-for-a-delivery}

Bij adressen die voor een specifieke levering in quarantaine worden geplaatst, gebeurt dit tijdens de voorbereidingsfase van de levering, via het tabblad **[!UICONTROL Exclusion logs]** van het leveringsdashboard (zie [deze sectie](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). Raadpleeg [deze sectie](../../sending/using/preparing-the-send.md) voor meer informatie over het voorbereiden van leveringen.

![](assets/exclusion_logs.png)

### Het identificeren van quarantined adressen voor het volledige platform {#identifying-quarantined-addresses-for-the-entire-platform}

Beheerders hebben vanuit het **[!UICONTROL Administration > Channels > Quarantines > Addresses]** -menu.

<!--
This menu lists quarantined elements for **Email**, **SMS** and **Push notification** channels.
-->

![](assets/quarantines1.png)

>[!NOTE]
>
>De toename van het aantal quarantaine is een normaal effect dat verband houdt met de &quot;slijtage&quot; van de database. Bijvoorbeeld, als de levensduur van een e-mailadres wordt beschouwd als drie jaar en de ontvankelijke lijst met 50% elk jaar stijgt, kan de verhoging van quarantines als volgt worden berekend: Eind van Jaar 1: (1&#42;0,33)/(1+0,5)=22%. Einde van jaar 2: (1.22&#42;0,33)+0,33)/(1,5+0,75)=32,5%.

Er zijn filters beschikbaar waarmee u door de lijst kunt bladeren. U kunt filteren op adres, status en/of kanaal.

![](assets/quarantines-filters.png)

U kunt [delete](#removing-a-quarantined-address) elke ingang, en creeer nieuwe.

Als u een item wilt bewerken, klikt u op de desbetreffende rij en wijzigt u de velden naar wens.

![](assets/quarantines-edit.png)

Als u handmatig een nieuw item wilt toevoegen, gebruikt u de opdracht **[!UICONTROL Create]** knop.

![](assets/quarantines-create-button.png)

Definieer het adres (of telefoonnummer, enz.) en kanaaltype. U kunt een status instellen om in de quarantainelijst te staan en een reden voor een fout. U kunt ook de datum aangeven waarop de fout is opgetreden, het aantal fouten en de fouttekst invoeren. Selecteer zo nodig de laatste levering die naar het adres is verzonden in de vervolgkeuzelijst.

![](assets/quarantines-create-last-delivery.png)

## Een adres uit quarantaine verwijderen {#removing-a-quarantined-address}

### Automatische updates {#unquarantine-auto}

Adressen die specifieke voorwaarden aanpassen worden automatisch geschrapt uit de quarantainelijst door het opschoonwerkschema van het Gegevensbestand. Meer informatie over technische workflows vindt u op [deze sectie](../../administration/using/technical-workflows.md#list-of-technical-workflows).

De adressen worden automatisch verwijderd uit de quarantainelijst in de volgende gevallen:

* Adressen in een **[!UICONTROL Erroneous]** de status wordt na een geslaagde levering uit de quarantainelijst verwijderd .
* Adressen in een **[!UICONTROL Erroneous]** de status wordt uit de quarantainelijst verwijderd als de laatste zachte stuit meer dan tien dagen geleden heeft plaatsgevonden . Zie voor meer informatie over softerror management [deze sectie](#soft-error-management).
* Adressen in een **[!UICONTROL Erroneous]** status die met de **[!UICONTROL Mailbox full]** De fout wordt na 30 dagen uit de quarantainelijst verwijderd.

Hun status verandert vervolgens in **[!UICONTROL Valid]**.

Het maximumaantal pogingen dat moet worden uitgevoerd in het geval van **[!UICONTROL Erroneous]** status en de minimumvertraging tussen pogingen zijn nu gebaseerd op hoe goed IP zowel historisch als momenteel bij een bepaald domein presteert.


>[!IMPORTANT]
>
Ontvangers met een adres in een **[!UICONTROL Quarantine]** of **[!UICONTROL Denylisted]** de status wordt nooit verwijderd, zelfs niet als ze een e-mail ontvangen.


### Handmatige updates {#unquarantine-manual}

U kunt een adres ook handmatig uit de quarantaine verwijderen.  Als u een adres handmatig uit de quarantainelijst wilt verwijderen, kunt u het uit de quarantainelijst verwijderen of de status ervan wijzigen in **[!UICONTROL Valid]**.

* Selecteer het adres in het menu **[!UICONTROL Administration > Channels > Quarantines > Addresses]** lijst en selecteer **[!UICONTROL Delete element]**.

  ![](assets/quarantine-delete-address.png)

* Een adres selecteren en het adres wijzigen **[!UICONTROL Status]** tot **[!UICONTROL Valid]**.

  ![](assets/quarantine-valid-status.png)


### Bulkupdates {#unquarantine-bulk}

U zou bulkupdates op de quarantainelijst, bijvoorbeeld in het geval van een ISP stroomonderbreking kunnen moeten uitvoeren. In dat geval worden e-mails ten onrechte als bonnen gemarkeerd omdat ze niet met succes aan de ontvanger kunnen worden bezorgd. Deze adressen moeten uit de quarantainelijst worden verwijderd.

Om dit te doen, creeer een werkschema en voeg toe **[!UICONTROL Query]** activiteit op uw quarantainetabel om alle getroffen ontvangers uit te filteren. Als deze eenmaal zijn geïdentificeerd, kunnen ze uit de quarantainelijst worden verwijderd en worden opgenomen in toekomstige e-mailleveringen voor campagnes.

Gebaseerd op het tijdkader van het incident, hieronder zijn de geadviseerde richtlijnen voor deze vraag.

* **Fouttekst (quarantainetekst)** bevat &quot;550-5.1.1&quot; EN **Fouttekst (quarantainetekst)** bevat &quot;support.ISP.com&quot;

  waar &quot;support.ISP.com&quot; kan zijn: bijvoorbeeld &quot;support.apple.com&quot; of &quot;support.google.com&quot;

* **Status bijwerken (@lastModified)** op of na `MM/DD/YYYY HH:MM:SS AM`
* **Status bijwerken (@lastModified)** op of voor  `MM/DD/YYYY HH:MM:SS PM`

Als u de lijst met betrokken ontvangers hebt, voegt u een **[!UICONTROL Update data]** activiteit om hun e-mailadresstatus in te stellen op **[!UICONTROL Valid]** zodat zij uit de quarantainelijst worden verwijderd door **[!UICONTROL Database cleanup]** workflow. U kunt ze ook gewoon uit de quarantainetabel verwijderen.

## Voorwaarden voor verzending van een adres naar quarantaine {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign beheert quarantaine op basis van leveringsfouten en de reden die wordt toegewezen bij de kwalificatie van foutmeldingen (zie [Fouttypen en redenen voor foute leveringen](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) en [Kwalificatie voor niet-bezorgde mail](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)).

* **Genegeerde fout**: bij genegeerde fouten wordt een adres niet in quarantaine geplaatst.
* **Harde fout**: het desbetreffende e-mailadres wordt onmiddellijk in quarantaine geplaatst.
* **Zachte fout**: bij zachte fouten wordt het adres niet direct in quarantaine geplaatst, maar neemt het aantal fouten op de foutenteller toe. Zie voor meer informatie [Beheer van zachte fouten](#soft-error-management).

  <!--
  When the error counter reaches the limit threshold, the address goes into quarantine. In the default configuration, the threshold is set at five errors, where two errors are significant if they occur at least 24 hours apart. The address is placed in quarantine at the fifth error. The error counter threshold can be modified. For more on this, refer to this [page](../../administration/using/configuring-email-channel.md#email-channel-parameters).
  When a delivery is successful after a retry, the error counter of the address which was prior to that quarantined is reinitialized. The address status changes to **[!UICONTROL Valid]** and it is deleted from the list of quarantines after two days by the **[!UICONTROL Database cleanup]** workflow.
  -->

Als een gebruiker een e-mailbericht kwalificeert als spam ([feedbacklus](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops)), wordt het bericht automatisch opnieuw gericht naar een technische brievenbus die door Adobe wordt beheerd. Het e-mailadres van de gebruiker wordt vervolgens automatisch in quarantaine geplaatst met de status **[!UICONTROL On denylist]**. Deze status verwijst alleen naar het adres, het profiel staat niet op de lijst van gewezen personen, zodat de gebruiker SMS-berichten en pushberichten blijft ontvangen.

>[!NOTE]
>
Quarantaine in Adobe Campaign is hoofdlettergevoelig. Zorg dat u de e-mailadressen in kleine letters importeert, zodat ze later niet opnieuw worden getarget.

In de lijst met adressen in quarantaine (zie [In quarantaine geplaatste adressen voor het volledige platform identificeren](#identifying-quarantined-addresses-for-the-entire-platform)) geeft het veld **[!UICONTROL Error reason]** aan waarom het geselecteerde adres in quarantaine werd geplaatst.

![](assets/quarantines2.png)

### Beheer van zachte fouten {#soft-error-management}

In tegenstelling tot harde fouten, verzenden de zachte fouten onmiddellijk geen adres naar quarantaine, maar zij verhogen in plaats daarvan een foutenteller.

Opnieuw proberen wordt uitgevoerd tijdens de [leveringstijd](../../administration/using/configuring-email-channel.md#validity-period-parameters). Wanneer de foutenteller de grenswaarde bereikt, wordt het adres in quarantaine geplaatst. Raadpleeg voor meer informatie hierover [Retourneert na een tijdelijke leverfout](understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

<!--In the default configuration, the threshold is set at five errors, where two errors are significant if they occur at least 24 hours apart. The address is placed in quarantine at the fifth error.
The error counter threshold can be modified.-->

De foutenteller wordt opnieuw geïnitialiseerd als de laatste significante fout meer dan 10 dagen geleden voorkwam. De adresstatus verandert vervolgens in **Geldig** en wordt door de **Database opschonen** workflow. (Zie voor meer informatie over technische workflows [deze sectie](../../administration/using/technical-workflows.md#list-of-technical-workflows).)
