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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 15%

---

# De verzending bevestigen{#confirming-the-send}

Nadat u de berichten hebt voorbereid en de goedkeuringsstappen zijn uitgevoerd, kunt u de berichten verzenden. Raadpleeg [De verzending voorbereiden](../../sending/using/preparing-the-send.md) voor meer informatie over het voorbereiden van berichten.

Alleen gebruikers met de **[!UICONTROL Start deliveries]** de rol kan het verzenden bevestigen. Raadpleeg de sectie [Lijst met rollen](../../administration/using/list-of-roles.md) voor meer informatie.

<!--Users without this role will see the following message: 

![](assets/confirm_delivery_2.png)-->

## Het bericht verzenden {#sending-message}

Wanneer de voorbereiding is voltooid, volgt u de onderstaande stappen om uw bericht te verzenden.

1. Klik op de knop **[!UICONTROL Confirm send]** in de actiebalk van het bericht gevonden.

   ![](assets/confirm_delivery.png)

1. De verzending voltooien door op de knop **[!UICONTROL OK]** knop.

   ![](assets/confirm_delivery1.png)

1. Wacht terwijl het bericht wordt verzonden. Het blok **[!UICONTROL Deployment]** toont de voortgang van de verzending.

>[!NOTE]
>
>Als het bericht gepland is, wordt het verzonden wanneer het verzenden van tijd wordt bereikt. Raadpleeg [deze sectie](../../sending/using/about-scheduling-messages.md) voor meer informatie over het plannen van berichten.

Als u een terugkerende levering zonder aggregatieperiode gebruikt, kunt u om bevestiging vragen voordat de levering wordt verzonden. Wanneer het vormen van uw bericht, open **[!UICONTROL Schedule]** blok van het leveringsdashboard en activeer de specifieke optie.

![](assets/confirmation_recurring_deliveries.png)

## Berichtindicatoren {#message-indicators}

Zodra het bericht wordt verzonden naar de contacten, **[!UICONTROL Deployment]** de streek toont uw KPIs (Zeer belangrijke Indicator van Prestaties) gegevens, die omvatten:

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

Als KPIs te lang duurt om bij te werken of niet op de resultaten van het verzenden logboeken wijst, klik **[!UICONTROL Compute stats]** in de **[!UICONTROL Deployment]** venster.

![](assets/sending_delivery7.png)

Het bericht kan worden weergegeven in de geschiedenis van een van de doelprofielen. Zie [Geïntegreerd klantprofiel](../../audiences/using/integrated-customer-profile.md).

Zodra een bericht wordt verzonden, kunt u het gedrag van zijn ontvangers volgen, en het controleren om zijn effect te meten. Raadpleeg deze secties voor meer informatie hierover:

* [Berichten traceren](../../sending/using/tracking-messages.md)
* [Een levering controleren](../../sending/using/monitoring-a-delivery.md)

### Leveringssuccesrapportage {#delivered-status-report}

>[!NOTE]
>
>Deze sectie is alleen van toepassing op e-mailkanalen.

In de **[!UICONTROL Summary]** de weergave van elke e-mail, **[!UICONTROL Delivered]** het percentage begint bij 100% en daalt geleidelijk gedurende de hele levering. [geldigheidsperiode](../../administration/using/configuring-email-channel.md#validity-period-parameters), terwijl de zachte en harde grenzen worden gemeld<!--from the Enhanced MTA to Campaign-->.

Alle berichten worden zelfs als **[!UICONTROL Sent]** in de [verzenden, logbestanden](../../sending/using/monitoring-a-delivery.md#sending-logs) zodra zij met succes van Campagne aan Verbeterde MTA (de Agent van de Overdracht van het Bericht) worden afgelost. Zij blijven deze status behouden, tenzij of totdat [stuiteren](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) voor dat bericht wordt meegedeeld terug van Verbeterde MTA aan Campaign.

Wanneer hard-stuiterende berichten van Verbeterde MTA worden gemeld, verandert hun status van **[!UICONTROL Sent]** tot **[!UICONTROL Failed]** en de **[!UICONTROL Delivered]** het percentage wordt dienovereenkomstig verlaagd.

Wanneer de zachte die berichten terug van Verbeterde MTA worden gemeld, tonen zij nog **[!UICONTROL Sent]** en de **[!UICONTROL Delivered]** percentage is nog niet bijgewerkt. De zachte die berichten van het stuiteren zijn dan [hervat](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure) gedurende de gehele geldigheidsduur van de levering:

* Als een nieuwe poging voor het eind van de geldigheidsperiode succesvol is, blijft de berichtstatus zoals **[!UICONTROL Sent]** en de **[!UICONTROL Delivered]** percentage blijft ongewijzigd.

* Anders verandert de status in **[!UICONTROL Failed]** en de **[!UICONTROL Delivered]** het percentage wordt dienovereenkomstig verlaagd.

Daarom moet u tot het eind van de geldigheidsperiode wachten om het definitieve te zien **[!UICONTROL Delivered]** en het uiteindelijke aantal **[!UICONTROL Sent]** en **[!UICONTROL Failed]** berichten.

### E-mailfeedbackservice (bèta) {#email-feedback-service}

Met de e-mailfeedbackservice (EFS) wordt de status van elke e-mail correct gerapporteerd, omdat feedback rechtstreeks wordt vastgelegd via de Enhanced MTA (Message Transfer Agent).

>[!IMPORTANT]
>
>De e-mailfeedbackservice is momenteel beschikbaar als bètafunctie.

Wanneer de levering is gestart, is er geen wijziging in de **[!UICONTROL Delivered]** percentage wanneer het bericht met succes van Campagne aan Verbeterde MTA wordt afgelost.

![](assets/efs-sending.png)

De leveringslogboeken tonen de **[!UICONTROL Pending]** status voor elk gericht adres.

![](assets/efs-pending.png)

Wanneer de berichtlevering aan de gerichte profielen in echt - tijd van Verbeterde MTA wordt gemeld, tonen de leveringslogboeken **[!UICONTROL Sent]** status voor elk adres dat met succes het bericht ontving. De **[!UICONTROL Delivered]** het percentage wordt dienovereenkomstig verhoogd bij elke succesvolle levering.

Wanneer hard-bouncing berichten terug van Verbeterde MTA worden gemeld, verandert hun logboekstatus van **[!UICONTROL Pending]** tot **[!UICONTROL Failed]** en de **[!UICONTROL Bounces + errors]** het percentage wordt dienovereenkomstig verhoogd.

Wanneer de zachte die berichten terug van Verbeterde MTA worden gemeld, verandert hun logboekstatus ook van **[!UICONTROL Pending]** tot **[!UICONTROL Failed]** en de **[!UICONTROL Bounces + errors]** het percentage wordt dienovereenkomstig verhoogd. De **[!UICONTROL Delivered]** percentage blijft ongewijzigd. De zachte die berichten bewegen worden dan opnieuw geprobeerd door de levering [geldigheidsperiode](../../administration/using/configuring-email-channel.md#validity-period-parameters):

* Als een nieuwe poging is gelukt vóór het einde van de geldigheidsperiode, verandert de berichtstatus in **[!UICONTROL Sent]** en de **[!UICONTROL Delivered]** het percentage wordt dienovereenkomstig verhoogd.

* Anders blijft de status ongewijzigd **[!UICONTROL Failed]**. De **[!UICONTROL Delivered]** en **[!UICONTROL Bounces + errors]** de percentages blijven ongewijzigd.

>[!NOTE]
>
>Zie voor meer informatie over harde en zachte golven [deze sectie](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).
>
>Voor meer informatie over pogingen na een tijdelijke mislukking van de levering, zie [deze sectie](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

<!--Soft-bouncing messages increment an error counter. When the error counter reaches the limit threshold or when the validity period is over, the address goes into quarantine and the status remains as **[!UICONTROL Failed]**. For more on conditions for sending an address to quarantine, see [this section](../../help/sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).-->

### Door EFS ingevoerde wijzigingen {#changes-introduced-by-efs}

De lijsten hieronder tonen de veranderingen in KPIs en het verzenden van logboekstatussen die door het vermogen EFS worden geïntroduceerd.

**Met e-mailfeedbackservice**

| Stap in het verzendende proces | KPI-overzicht | Status van logboeken verzenden |
|--- |--- |--- |
| Het bericht wordt met succes afgelost van Campagne aan Verbeterde MTA | <ul><li>**[!UICONTROL Delivered]** percentage begint bij 0%</li><li>**[!UICONTROL Bounces + errors]** percentage begint bij 0%</li></ul> | In behandeling |
| Fel-stuiterende berichten worden gemeld terug van Verbeterde MTA | <ul><li>Geen wijziging in **[!UICONTROL Delivered]** percentage</li><li>**[!UICONTROL Bounces + errors]** percentage wordt dienovereenkomstig verhoogd</li></ul> | Mislukt |
| De zachte die berichten bewegen worden gemeld terug van Verbeterde MTA | <ul><li>Geen wijziging in **[!UICONTROL Delivered]** percentage</li><li>**[!UICONTROL Bounces + errors]** percentage wordt dienovereenkomstig verhoogd</li></ul> | Mislukt |
| Herhalingen van soft-bouncing berichten zijn succesvol | <ul><li>**[!UICONTROL Delivered]** percentage wordt dienovereenkomstig verhoogd</li><li>**[!UICONTROL Bounces + errors]** percentage wordt dienovereenkomstig verlaagd</li></ul> | Verzonden |
| Herhalingen van soft-bouncing berichten mislukken | <ul><li> Geen wijziging in **[!UICONTROL Delivered]** percentage </li><li> Geen wijziging in **[!UICONTROL Bounces + errors]** percentage </li></ul> | Mislukt |

**Zonder e-mailfeedbackservice**

| Stap in het verzendende proces | KPI-overzicht | Status van logboeken verzenden |
|--- |--- |--- |
| Het bericht wordt met succes afgelost van Campagne aan Verbeterde MTA | <ul><li>**[!UICONTROL Delivered]** percentage begint bij 100%</li><li>**[!UICONTROL Bounces + errors]** percentage begint bij 0%</li></ul> | Verzonden |
| Fel-stuiterende berichten worden gemeld terug van Verbeterde MTA | <ul><li>**[!UICONTROL Delivered]** percentage wordt dienovereenkomstig verlaagd</li><li>**[!UICONTROL Bounces + errors]** percentage wordt dienovereenkomstig verhoogd</li></ul> | Mislukt |
| De zachte die berichten bewegen worden gemeld terug van Verbeterde MTA | <ul><li>Geen wijziging in **[!UICONTROL Delivered]** percentage</li><li>Geen wijziging in **[!UICONTROL Bounces + errors]** percentage</li></ul> | Verzonden |
| Herhalingen van soft-bouncing berichten zijn succesvol | <ul><li>Geen wijziging in **[!UICONTROL Delivered]** percentage</li><li>Geen wijziging in **[!UICONTROL Bounces + errors]** percentage</li></ul> | Verzonden |
| Herhalingen van soft-bouncing berichten mislukken | <ul><li>**[!UICONTROL Delivered]** percentage wordt dienovereenkomstig verlaagd</li><li>**[!UICONTROL Bounces + errors]** percentage wordt dienovereenkomstig verhoogd</li></ul> | Mislukt |
