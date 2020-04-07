---
title: Berichten bijhouden
description: Leer hoe u het gedrag van de ontvangers van de levering kunt bijhouden.
page-status-flag: never-activated
uuid: c3721647-0663-4614-a9c9-3b3a40af328a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
discoiquuid: 6fa50f0d-3dcf-4a9e-bccc-1ecda2bfb449
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2926b916ac8e8a2605694758407c48b1db359c60

---


# Berichten bijhouden{#tracking-messages}

## Over bijhouden {#about-tracking}

Dankzij de trackingfuncties van Adobe Campaign kunt u het gedrag van de ontvangers bijhouden. Hiervoor gebruikt Adobe Campaign sessiecookies en permanente cookies.

U kunt gebruikers laten weten dat uw sites zijn uitgerust met webtraceringsprogramma&#39;s via een verzoek om toestemming (bijvoorbeeld via de pagina) met een selectievakje waarmee het gebruik van cookies wordt toegestaan, of u kunt een banner toevoegen boven aan de eerste pagina waarop ze landen, enzovoort. Pop-upvensters moeten worden vermeden omdat ze vaak worden geblokkeerd door browsers.

Trackinggegevens zijn beschikbaar voor elk contact van uw database met **[!UICONTROL integrated customer profiles]**. For more on this, refer to [this section](../../audiences/using/integrated-customer-profile.md).

Adobe Campaign gebruikt twee soorten cookies:

* Een sessiecookie (ongeldig). Dit bevat het herkenningsteken van e-mail die naar het contact (broadlogId) wordt verzonden en herkenningsteken van het berichtmalplaatje (deliveryId). Deze wordt toegevoegd wanneer de contactpersoon op een URL klikt die is opgenomen in een e-mailbericht dat is verzonden door Adobe Campaign. Hiermee kunt u het gedrag van de contactpersoon op het web volgen. Deze sessiecookie wordt automatisch gewist wanneer de browser wordt gesloten. De contactpersoon kan zijn browser configureren om cookies te weigeren.
* Een cookie die wordt gedeeld tussen Adobe Experience Cloud-oplossingen. Op deze manier kunt u de gebruikers identificeren die met de Experience Cloud-oplossingen werken wanneer ze een website bezoeken. De beschrijving van deze cookie is hier beschikbaar: [https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html).

Als u opvolgt met de Adobe Campaign Standard, hebt u toegang tot de volgende functies:

<table>
<tr>
    <td valign="top">
        <a href="../../administration/using/configuring-email-channel.md#tracking-parameters"><img width="60px" alt="voorwaarden" src="assets/icon_email_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="https://helpx.adobe.com/campaign/kb/push-tracking.html"><img width="60px" alt="voorwaarden" src="assets/icon_push_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="../../designing/using/links.md#about-tracked-urls"><img width="60px" alt="voorwaarden" src="assets/icon_url.png"/></a>
    </td>
        <td valign="top">
          <a href="../../sending/using/tracking-messages.md#tracking-logs"><img width="60px" alt="voorwaarden" src="assets/icon_log.png"/></a>
    </td>
    </td>
    <td valign="top">
          <a href="../../reporting/using/tracking-indicators.md"><img width="60px" alt="voorwaarden" src="assets/icon_report.png"/></a>

</tr>
<tr>
<td>E-mailtracking</td>
<td>Push tracking</td>
<td>Bijgehouden URL's</td>
<td>Logboeken bijhouden</td>
<td>Trackingrapport</td>
</tr>

</table>

## Logboeken bijhouden {#tracking-logs}

Op het **[!UICONTROL Tracking logs]** tabblad vindt u de volggeschiedenis voor deze levering. Op dit tabblad wordt de informatie over het bijhouden van de verzonden berichten weergegeven, zoals alle URL&#39;s die door Adobe Campaign zijn bijgehouden. De trackinggegevens op dit tabblad worden elke 10 minuten bijgewerkt.

>[!NOTE]
>
>Als &#39;tracking&#39; niet is ingeschakeld voor levering, wordt dit tabblad niet weergegeven. Logbestanden voor bijhouden zijn alleen beschikbaar voor **e-mail** - en **pushmeldingen** .

![](assets/tracking_logs.png)

In het bovenstaande voorbeeld:

* Open het bericht.
* Klik op de aangepaste koppeling &quot;MEER INFORMATIE&quot;.
* Klik op de koppeling Abonnement opzeggen en de spiegel.

In de **[!UICONTROL Type]** kolom zijn de mogelijke waarden:

* **[!UICONTROL Email click]**: de ontvangers hebben op een aangepaste koppeling geklikt.
* **[!UICONTROL Mirror page]**: de ontvanger klikte op een verbinding aan de spiegelpagina.
* **[!UICONTROL Open]**: de ontvanger heeft de e-mail geopend.
* **[!UICONTROL Opt-out]**: de ontvanger klikte op een unsubscription verbinding.

>[!NOTE]
>
>Voor het **pushmeldingskanaal** worden alleen de mobiele meldingen bijgehouden. In dat geval is de waarde **[!UICONTROL Click on mobile notification]**.

Raadpleeg [deze pagina](../../designing/using/links.md#inserting-a-link)voor meer informatie over het invoegen van koppelingen voor reeksspatiëring.

## Bijgehouden URL&#39;s {#tracked-urls}

Op het **[!UICONTROL Tracked URLs]** tabblad worden de URL&#39;s in het verzonden bericht opnieuw gegroepeerd, inclusief hun URL-type en hun bron-URL.

![](assets/sending_delivery6.png)

For more on tracking links, refer to [this section](../../designing/using/links.md#about-tracked-urls).
