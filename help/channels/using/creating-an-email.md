---
title: Een e-mail maken
description: Voer de volgende stappen uit om een e-mailbericht voor één verzending te maken in Adobe Campaign.
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: User
level: Beginner
exl-id: 4483e469-0a2b-494d-b768-950168759727
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 16%

---

# Een e-mail maken{#creating-an-email}

U kunt een e-mailbericht maken op basis van een [campagne](../../start/using/marketing-activities.md#creating-a-marketing-activity), van Adobe Campaign [homepage](../../start/using/interface-description.md#home-page)of in de [lijst met marketingactiviteiten](../../start/using/marketing-activities.md#about-marketing-activities). U kunt vanuit een workflow ook eenmalige en terugkerende e-mails maken.

![](assets/do-not-localize/how-to-video.png) [Ontdek deze functie in video](#video)

1. Als u eenmaal een marketingactie voor e-mail hebt gestart, selecteert u de sjabloon die u wilt gebruiken.

   Standaard kunt u kiezen uit verschillende sjablonen voor elke marketingactiviteit. Hierdoor kunt u bepaalde parameters vooraf configureren op basis van uw behoeften en ook een merk toewijzen aan uw levering. Zie voor meer informatie [Sjablonen beheren](../../start/using/marketing-activity-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >Follow-up- en A/B-testsjablonen zijn standaard verborgen. Schakel de selectievakjes links in ( **[!UICONTROL Filter]** (zijpaneel) als u ze wilt weergeven.

1. Voer de algemene eigenschappen van de e-mail in. U kunt een naam invoeren in het dialoogvenster **Label** en bewerk de id.

   >[!NOTE]
   >
   >Zowel verschijnen de activiteitennaam als zijn identiteitskaart in de interface, maar zij zijn niet zichtbaar aan de berichtontvangers.
   >
   >Zorg ervoor dat het veld Id geen lege ruimte bevat om discrepanties te voorkomen, bijvoorbeeld bij integratie met Adobe Analytics.

   U kunt een beschrijving toevoegen die de gebruiker in de content van de campagne kan zien.

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >U kunt uw e-mail binnen een oudercampagne van de homepage of de lijst van marketing activiteiten tot stand brengen. Selecteer een van de campagnes die al zijn gemaakt.

1. Bepaal het doel van uw bericht dat op uw bedrijfscriteria wordt gebaseerd. Zie [Profielen](../../audiences/using/about-profiles.md).

   U kunt ook de testprofielen definiëren die het bericht valideren. Zie [Testprofielen beheren](../../audiences/using/managing-test-profiles.md).

   ![](assets/email_creation_3.png)

1. De inhoud van het bericht, de naam van de afzender en het onderwerp definiëren en aanpassen met de opdracht [E-mailontwerper](../../designing/using/designing-content-in-adobe-campaign.md). Zie voor meer informatie [Over het ontwerpen van e-mailinhoud](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/email_creation_4.png)

   U kunt uw bericht rechtstreeks ontwerpen met een vooraf gedefinieerde inhoudssjabloon of met Dreamweaver of Adobe Experience Manager. Als u zich niet als ontwerper voelt, kunt u een inhoud ook uploaden die voor u, is voorbereid of een bestaande inhoud van een URL invoeren. Zie [Bestaande content selecteren](../../designing/using/using-existing-content.md).

1. Geef een voorvertoning van uw bericht weer. Zie [Berichten voorvertonen](../../sending/using/previewing-messages.md).
1. Bevestig het maken van de e-mail.

   >[!NOTE]
   >
   >Als u uw e-mail wilt opslaan, moet u eerst enkele wijzigingen in de inhoud aanbrengen. Als u op **[!UICONTROL Cancel]** op dit moment kunt u de wizard niet voltooien en wordt uw e-mail niet gemaakt.

   Het e-maildashboard wordt vervolgens weergegeven. Hiermee kunt u uw bericht controleren en [de verzending voorbereiden](../../sending/using/preparing-the-send.md).

   De **[!UICONTROL Edit properties]** in de rechterbovenhoek kunt u de eigenschappen van het e-mailbericht bewerken. U kunt bijvoorbeeld de e-mail zo configureren dat het label wordt berekend op het moment dat de levering wordt voorbereid.  Beschikbare parameters worden vermeld in [deze sectie](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/delivery_dashboard_2.png)

1. Plan de verzending. Zie [Berichten plannen](../../sending/using/about-scheduling-messages.md).

   ![](assets/delivery_planning.png)

1. Bereid uw bericht voor om zijn doel te analyseren. Zie [De verzending voorbereiden](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >U kunt algemene moeheidsregels tussen kanalen instellen om overvraagde profielen automatisch uit te sluiten van campagnes. Zie voor meer informatie [Vermogensregels](../../sending/using/fatigue-rules.md).

1. Verzend proeven om uw bericht te controleren en te valideren en de weergave ervan in inboxen te controleren. Zie [Bewijs verzenden](../../sending/using/sending-proofs.md).

   ![](assets/bat_select.png)

1. Verzend het bericht en controleer zijn levering door het berichtdashboard en de logboeken. Zie [Berichten verzenden](../../sending/using/confirming-the-send.md).

   ![](assets/confirm_delivery.png)

1. Meet het effect van uw bericht met leveringsrapporten. Zie voor meer informatie over rapportage [deze sectie](../../reporting/using/about-dynamic-reports.md).

**Verwante onderwerpen**:

* [Een persoonlijke e-mail maken](../../channels/using/key-steps-to-send-a-message.md) stapsgewijze handleiding
* [Integratie van Adobe Campaign en Dreamweaver](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)
* [Integreren met Adobe Experience Manager](../../integrating/using/integrating-with-experience-manager.md)

## Video over zelfstudie {#video}

In deze video wordt getoond hoe u een e-mail kunt maken.

>[!VIDEO](https://video.tv.adobe.com/v/23721?quality=12)

Er zijn aanvullende Campaign Standard-hoe-kan-video&#39;s beschikbaar [hier](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=nl).
