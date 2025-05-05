---
title: Berichten traceren
description: Leer hoe u het gedrag van de ontvangers van de levering kunt bijhouden.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: fac29bc2-57fa-40f9-a160-cd75f695b91e
source-git-commit: affd4f9716235a283df20de5539e43c4832762f7
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 21%

---

# Berichten traceren{#tracking-messages}

## Over bijhouden {#about-tracking}

Dankzij de trackingfuncties van Adobe Campaign kunt u het gedrag van de ontvangers van de levering volgen. Hiervoor gebruikt Adobe Campaign sessiecookies en permanente cookies.

U kunt gebruikers laten weten dat uw sites zijn uitgerust met webtraceringsprogramma&#39;s via een verzoek om toestemming (bijvoorbeeld via de pagina) met een selectievakje waarmee het gebruik van cookies wordt toegestaan, of u kunt een banner toevoegen boven aan de eerste pagina waarop ze landen, enzovoort. Pop-upvensters moeten worden vermeden omdat ze vaak worden geblokkeerd door browsers.

Trackinggegevens zijn beschikbaar voor elke contactpersoon van uw database naar **[!UICONTROL integrated customer profiles]**. Raadpleeg [deze sectie](../../audiences/using/integrated-customer-profile.md) voor meer informatie.

Adobe Campaign gebruikt twee soorten cookies:

* Een sessiecookie (ongeldig). Dit bevat het herkenningsteken van e-mail die naar het contact (broadlogId) wordt verzonden en herkenningsteken van het berichtmalplaatje (deliveryId). Deze wordt toegevoegd wanneer de contactpersoon op een URL klikt die is opgenomen in een e-mail die door Adobe Campaign wordt verzonden. Hiermee kunt u het gedrag van de contactpersoon op het web volgen. Deze sessiecookie wordt automatisch gewist wanneer de browser wordt gesloten. De contactpersoon kan zijn browser configureren om cookies te weigeren.
* Een cookie die wordt gedeeld tussen Adobe Experience Cloud-oplossingen. Hierdoor kunt u de gebruikers identificeren die met de oplossingen van het Experience Cloud communiceren wanneer zij een website bezoeken. De beschrijving van deze cookie is beschikbaar [hier](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-mc.html?lang=nl-NL).

Als u opvolgt met de Adobe Campaign Standard, hebt u toegang tot de volgende functies:

<table>
<tr>
    <td valign="top">
        <a href="../../administration/using/configuring-email-channel.md#tracking-parameters"><img width="60px" alt="voorwaarden" src="assets/icon_email_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="../../administration/using/push-tracking.md"><img width="60px" alt="voorwaarden" src="assets/icon_push_parameters.png"/></a>
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

De **[!UICONTROL Tracking logs]** wordt de volggeschiedenis voor deze levering weergegeven. Op dit tabblad wordt de informatie over het bijhouden van de verzonden berichten weergegeven, zoals alle URL&#39;s die door Adobe Campaign zijn bijgehouden. De trackinggegevens op dit tabblad worden elke 10 minuten bijgewerkt.

>[!NOTE]
>
>Als &#39;tracking&#39; niet is ingeschakeld voor levering, wordt dit tabblad niet weergegeven. Logbestanden voor bijhouden zijn beschikbaar voor de **email** en **pushmelding** alleen kanalen.

![](assets/tracking_logs.png)

In het bovenstaande voorbeeld:

* Open het bericht.
* Klik op de koppeling spiegel.
* Klik op de aangepaste koppeling MEER INFORMATIE.

In de **[!UICONTROL Type]** kolom, de mogelijke waarden zijn:

* **[!UICONTROL Email click]**: de ontvangers hebben op een aangepaste koppeling geklikt.
* **[!UICONTROL Mirror page]**: de ontvanger klikte op een verbinding aan de spiegelpagina.
* **[!UICONTROL Open]**: de ontvanger heeft de e-mail geopend.
* **[!UICONTROL Opt-out]**: de ontvanger klikte op een koppeling zonder abonnement.

>[!NOTE]
>
>Voor de **pushmelding** kanaal, worden alleen kliks op mobiele meldingen bijgehouden. In dat geval wordt de waarde **[!UICONTROL Click on mobile notification]**.

Raadpleeg voor meer informatie over het invoegen van koppelingen voor reeksspatiëring [deze pagina](../../designing/using/links.md#inserting-a-link).

De **[!UICONTROL Tracking indicators]** het rapport bevat de belangrijkste indicatoren voor het volgen van gedrag nadat de e-mailberichten worden ontvangen. Raadpleeg [deze pagina](../../reporting/using/tracking-indicators.md) voor meer informatie.

## Bijgehouden URL&#39;s {#tracked-urls}

De **[!UICONTROL Tracked URLs]** wordt de URL&#39;s in het verzonden bericht opnieuw gegroepeerd, inclusief hun URL-type en hun bron-URL.

![](assets/sending_delivery6.png)

Raadpleeg voor meer informatie over het bijhouden van koppelingen [deze sectie](../../designing/using/links.md#about-tracked-urls).
