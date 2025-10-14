---
title: De verzending bevestigen
description: Leer hoe u de berichtvoorbereiding voltooit.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
context-tags: delivery,deployment,back
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: 0a0fe969-cdfd-4b0c-a746-081038424d86
source-git-commit: 058c59136c28e7fce2a79686919f900f410e324a
workflow-type: tm+mt
source-wordcount: '982'
ht-degree: 15%

---

# De verzending bevestigen{#confirming-the-send}

Nadat u de berichten hebt voorbereid en de goedkeuringsstappen zijn uitgevoerd, kunt u de berichten verzenden. Raadpleeg [De verzending voorbereiden](../../sending/using/preparing-the-send.md) voor meer informatie over het voorbereiden van berichten.

Alleen gebruikers met de rol **[!UICONTROL Start deliveries]** kunnen het verzenden bevestigen. Raadpleeg de sectie [Lijst met rollen](../../administration/using/list-of-roles.md) voor meer informatie.

<!--Users without this role will see the following message: 

![](assets/confirm_delivery_2.png)-->

## Het bericht verzenden {#sending-message}

Wanneer de voorbereiding is voltooid, volgt u de onderstaande stappen om uw bericht te verzenden.

1. Klik op de knop **[!UICONTROL Confirm send]** op de actiebalk van het bericht.

   ![](assets/confirm_delivery.png)

1. Voltooi de verzending door op de knop **[!UICONTROL OK]** te klikken.

   ![](assets/confirm_delivery1.png)

1. Wacht terwijl het bericht wordt verzonden. Het blok **[!UICONTROL Deployment]** toont de voortgang van de verzending.

>[!NOTE]
>
>Als het bericht gepland is, wordt het verzonden wanneer het verzenden van tijd wordt bereikt. Raadpleeg [deze sectie](../../sending/using/about-scheduling-messages.md) voor meer informatie over het plannen van berichten.

Als u een terugkerende levering zonder aggregatieperiode gebruikt, kunt u om bevestiging vragen voordat de levering wordt verzonden. Wanneer het vormen van uw bericht, open het **[!UICONTROL Schedule]** blok van het leveringsdashboard en activeer de specifieke optie.

![](assets/confirmation_recurring_deliveries.png)

## Berichtindicatoren {#message-indicators}

>[!NOTE]
>
> Het **dashboard van de Plaatsing** verstrekt gegevens voor snelle verwijzing, die niet de aantallen in Dynamische rapporten kan aanpassen. Voor nauwkeurige en betrouwbare informatie, adviseren wij het gebruiken van de Dynamische rapportering als bron van waarheid. [Meer informatie](../../reporting/using/get-started-reporting.md)

Zodra het bericht wordt verzonden naar de contacten, toont de **[!UICONTROL Deployment]** streek uw gegevens van KPIs (de Zeer belangrijke Indicator van Prestaties), die omvatten:

* Het aantal te leveren berichten
* Het aantal verzonden berichten
* Het percentage geleverde berichten
* Het percentage niet-bezorgbare berichten en fouten
* Het percentage geopende berichten
* Het percentage klikken in de berichten (voor e-mails)

  >[!NOTE]
  >
  >De waarden van **[!UICONTROL Open rate]** en **[!UICONTROL Click-through rate]** worden elk uur bijgewerkt.

![](assets/sending_delivery.png)

Als de KPI&#39;s te lang duren om bij te werken of als ze de resultaten van de verzendende logboeken niet weerspiegelen, klikt u op de knop **[!UICONTROL Compute stats]** in het **[!UICONTROL Deployment]** -venster.

![](assets/sending_delivery7.png)

Het bericht kan worden weergegeven in de geschiedenis van een van de doelprofielen. Zie [Geïntegreerd klantprofiel](../../audiences/using/integrated-customer-profile.md).

Zodra een bericht wordt verzonden, kunt u het gedrag van zijn ontvangers volgen, en het controleren om zijn effect te meten. Raadpleeg deze secties voor meer informatie hierover:

* [Berichten traceren](../../sending/using/tracking-messages.md)
* [Een levering controleren](../../sending/using/monitoring-a-delivery.md)

### Leveringssuccesrapportage {#delivered-status-report}

>[!NOTE]
>
>Deze sectie is alleen van toepassing op e-mailkanalen.

In de **[!UICONTROL Summary]** mening van elke e-mail, begint het **[!UICONTROL Delivered]** percentage bij 100% en gaat dan progressief door de levering [&#x200B; geldigheidsperiode &#x200B;](../../administration/using/configuring-email-channel.md#validity-period-parameters), aangezien de zachte en harde grenzen worden gemeld terug <!--from the Enhanced MTA to Campaign-->.

Sterker nog, tonen alle berichten als **[!UICONTROL Sent]** in [&#x200B; verzendend logboeken &#x200B;](../../sending/using/monitoring-a-delivery.md#sending-logs) zodra zij met succes van Campagne aan Verbeterde MTA (de Agent van de Overdracht van het Bericht) worden afgelost. Zij blijven in die status tenzij of tot a [&#x200B; stuiteren &#x200B;](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) voor dat bericht terug van Verbeterde MTA aan Campagne wordt meegedeeld.

Wanneer hard-bouncing berichten van Verbeterde MTA worden gemeld, verandert hun status van **[!UICONTROL Sent]** in **[!UICONTROL Failed]** en **[!UICONTROL Delivered]** percentage wordt dienovereenkomstig verminderd.

Wanneer soft-bouncing berichten terug van Verbeterde MTA worden gemeld, tonen zij nog steeds als **[!UICONTROL Sent]** en het **[!UICONTROL Delivered]** percentage wordt nog niet bijgewerkt. De soft-bouncing berichten worden dan [&#x200B; opnieuw geprobeerd &#x200B;](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure) door de periode van de leveringsgeldigheid:

* Als het opnieuw proberen is gelukt vóór het einde van de geldigheidsperiode, blijft de status van het bericht behouden als **[!UICONTROL Sent]** en blijft het percentage **[!UICONTROL Delivered]** ongewijzigd.

* Anders verandert de status in **[!UICONTROL Failed]** en wordt het percentage **[!UICONTROL Delivered]** dienovereenkomstig verlaagd.

Daarom moet u wachten tot het einde van de geldigheidsperiode om het uiteindelijke **[!UICONTROL Delivered]** percentage en het uiteindelijke aantal **[!UICONTROL Sent]** - en **[!UICONTROL Failed]** -berichten weer te geven.

### E-mailfeedbackservice (bèta) {#email-feedback-service}

Met de e-mailfeedbackservice (EFS) wordt de status van elke e-mail correct gerapporteerd, omdat feedback rechtstreeks wordt vastgelegd via de Enhanced MTA (Message Transfer Agent).

>[!IMPORTANT]
>
>De e-mailfeedbackservice is momenteel beschikbaar als bètafunctie.

Zodra de levering is begonnen, is er geen verandering in het **[!UICONTROL Delivered]** percentage wanneer het bericht met succes van Campagne aan Verbeterde MTA wordt afgelost.

![](assets/efs-sending.png)

In de leveringslogboeken wordt de status **[!UICONTROL Pending]** voor elk doeladres weergegeven.

![](assets/efs-pending.png)

Wanneer de berichtlevering aan de gerichte profielen in echt - tijd van Uitgebreide MTA wordt gemeld, tonen de leveringslogboeken de **[!UICONTROL Sent]** status voor elk adres dat met succes het bericht ontving. Het percentage **[!UICONTROL Delivered]** wordt dienovereenkomstig verhoogd bij elke succesvolle levering.

Wanneer hard-bouncing berichten van Verbeterde MTA worden gemeld, verandert hun logboekstatus van **[!UICONTROL Pending]** in **[!UICONTROL Failed]** en **[!UICONTROL Bounces + errors]** percentage wordt dienovereenkomstig verhoogd.

Wanneer soft-bouncing berichten van Verbeterde MTA worden gemeld, verandert hun logboekstatus ook van **[!UICONTROL Pending]** in **[!UICONTROL Failed]** en **[!UICONTROL Bounces + errors]** percentage wordt dienovereenkomstig verhoogd. Het percentage **[!UICONTROL Delivered]** blijft ongewijzigd. De soft-bouncing berichten worden dan opnieuw geprobeerd door de levering [&#x200B; geldigheidsperiode &#x200B;](../../administration/using/configuring-email-channel.md#validity-period-parameters):

* Als het opnieuw proberen is gelukt vóór het einde van de geldigheidsperiode, verandert de berichtstatus in **[!UICONTROL Sent]** en wordt het **[!UICONTROL Delivered]** percentage dienovereenkomstig verhoogd.

* Anders blijft de status als **[!UICONTROL Failed]** . De percentages **[!UICONTROL Delivered]** en **[!UICONTROL Bounces + errors]** blijven ongewijzigd.

>[!NOTE]
>
>Voor meer op harde en zachte grenzen, zie [&#x200B; deze sectie &#x200B;](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).
>
>Voor meer op herpogingen na een tijdelijke mislukking van de levering, zie [&#x200B; deze sectie &#x200B;](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

<!--Soft-bouncing messages increment an error counter. When the error counter reaches the limit threshold or when the validity period is over, the address goes into quarantine and the status remains as **[!UICONTROL Failed]**. For more on conditions for sending an address to quarantine, see [this section](../../help/sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).-->

### Door EFS ingevoerde wijzigingen {#changes-introduced-by-efs}

De lijsten hieronder tonen de veranderingen in KPIs en het verzenden van logboekstatussen die door het vermogen EFS worden geïntroduceerd.

**met de dienst van de Terugkoppeling E-mail**

| Stap in het verzendende proces | KPI-overzicht | Status van logboeken verzenden |
|--- |--- |--- |
| Het bericht wordt met succes afgelost van Campagne aan Verbeterde MTA | <ul><li>**[!UICONTROL Delivered]** percentage begint bij 0%</li><li>**[!UICONTROL Bounces + errors]** percentage begint bij 0%</li></ul> | In behandeling |
| Fel-stuiterende berichten worden gemeld terug van Verbeterde MTA | <ul><li>Geen wijziging in **[!UICONTROL Delivered]** percentage</li><li>**[!UICONTROL Bounces + errors]** percentage wordt dienovereenkomstig verhoogd</li></ul> | Mislukt |
| De zachte die berichten bewegen worden gemeld terug van Verbeterde MTA | <ul><li>Geen wijziging in **[!UICONTROL Delivered]** percentage</li><li>**[!UICONTROL Bounces + errors]** percentage wordt dienovereenkomstig verhoogd</li></ul> | Mislukt |
| Herhalingen van soft-bouncing berichten zijn succesvol | <ul><li>**[!UICONTROL Delivered]** percentage wordt dienovereenkomstig verhoogd</li><li>**[!UICONTROL Bounces + errors]** percentage is dienovereenkomstig verlaagd</li></ul> | Verzonden |
| Herhalingen van soft-bouncing berichten mislukken | <ul><li> Geen wijziging in **[!UICONTROL Delivered]** percentage </li><li> Geen wijziging in **[!UICONTROL Bounces + errors]** percentage </li></ul> | Mislukt |

**zonder de dienst van de Terugkoppeling E-mail**

| Stap in het verzendende proces | KPI-overzicht | Status van logboeken verzenden |
|--- |--- |--- |
| Het bericht wordt met succes afgelost van Campagne aan Verbeterde MTA | <ul><li>**[!UICONTROL Delivered]** percentage begint bij 100%</li><li>**[!UICONTROL Bounces + errors]** percentage begint bij 0%</li></ul> | Verzonden |
| Fel-stuiterende berichten worden gemeld terug van Verbeterde MTA | <ul><li>**[!UICONTROL Delivered]** percentage is dienovereenkomstig verlaagd</li><li>**[!UICONTROL Bounces + errors]** percentage wordt dienovereenkomstig verhoogd</li></ul> | Mislukt |
| De zachte die berichten bewegen worden gemeld terug van Verbeterde MTA | <ul><li>Geen wijziging in **[!UICONTROL Delivered]** percentage</li><li>Geen wijziging in **[!UICONTROL Bounces + errors]** percentage</li></ul> | Verzonden |
| Herhalingen van soft-bouncing berichten zijn succesvol | <ul><li>Geen wijziging in **[!UICONTROL Delivered]** percentage</li><li>Geen wijziging in **[!UICONTROL Bounces + errors]** percentage</li></ul> | Verzonden |
| Herhalingen van soft-bouncing berichten mislukken | <ul><li>**[!UICONTROL Delivered]** percentage is dienovereenkomstig verlaagd</li><li>**[!UICONTROL Bounces + errors]** percentage wordt dienovereenkomstig verhoogd</li></ul> | Mislukt |
