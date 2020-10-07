---
title: Een e-mail maken
description: Voer de volgende stappen uit om een e-mailbericht voor één verzending te maken in Adobe Campaign.
page-status-flag: never-activated
uuid: 74c7ef35-82c0-4bc4-b1f6-8e74fdcaea3c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: email-messages
discoiquuid: b27e0170-e73f-4782-8568-02927fb374f4
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 19%

---


# Een e-mail maken{#creating-an-email}

U kunt een e-mail van een [campagne](../../start/using/marketing-activities.md#creating-a-marketing-activity), van de [homepage](../../start/using/interface-description.md#home-page)van Adobe Campaign, of in de lijst van de [marketing activiteit tot stand brengen](../../start/using/marketing-activities.md#about-marketing-activities). U kunt vanuit een workflow ook eenmalige en terugkerende e-mails maken.

1. Als u eenmaal een marketingactie voor e-mail hebt gestart, selecteert u de sjabloon die u wilt gebruiken.

   Standaard kunt u kiezen uit verschillende sjablonen voor elke marketingactiviteit. Hierdoor kunt u bepaalde parameters vooraf configureren op basis van uw behoeften en ook een merk toewijzen aan uw levering. For more on this, see [Managing templates](../../start/using/marketing-activity-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >Follow-up- en A/B-testsjablonen zijn standaard verborgen. Schakel de selectievakjes links ( **[!UICONTROL Filter]** zijpaneel) in als u deze wilt weergeven.

1. Voer de algemene eigenschappen van de e-mail in. You can enter a name in the **Label** field and edit the ID. Zowel verschijnen de activiteitennaam als zijn identiteitskaart in de interface, maar zij zijn niet zichtbaar aan de berichtontvangers.

   U kunt een beschrijving toevoegen die de gebruiker in de content van de campagne kan zien.

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >U kunt uw e-mail binnen een oudercampagne van de homepage of de lijst van marketing activiteiten tot stand brengen. Selecteer een van de campagnes die al zijn gemaakt.

1. Bepaal het doel van uw bericht dat op uw bedrijfscriteria wordt gebaseerd. See [About profiles](../../audiences/using/about-profiles.md).

   U kunt ook de testprofielen definiëren die het bericht valideren. Zie [Testprofielen beheren](../../audiences/using/managing-test-profiles.md).

   ![](assets/email_creation_3.png)

1. Definieer en pas de inhoud van het bericht, de naam van de afzender en het onderwerp aan met de [e-mailontwerper](../../designing/using/designing-content-in-adobe-campaign.md). Zie [Informatie over ontwerpen](../../designing/using/designing-content-in-adobe-campaign.md)van e-mailinhoud voor meer informatie.

   ![](assets/email_creation_4.png)

   U kunt uw bericht rechtstreeks ontwerpen met een vooraf gedefinieerde inhoudssjabloon of met Dreamweaver of Adobe Experience Manager. Als u zich niet als ontwerper voelt, kunt u een inhoud ook uploaden die voor u, is voorbereid of een bestaande inhoud van een URL invoeren. Zie [Bestaande content selecteren](../../designing/using/using-existing-content.md).

1. Geef een voorvertoning van uw bericht weer. Zie [Berichten voorvertonen](../../sending/using/previewing-messages.md).
1. Bevestig het maken van de e-mail.

   >[!NOTE]
   >
   >Als u uw e-mail wilt opslaan, moet u eerst enkele wijzigingen in de inhoud aanbrengen. Als u op **[!UICONTROL Cancel]** dit punt klikt, wordt de wizard niet voltooid en wordt uw e-mail niet gemaakt.

   Het e-maildashboard wordt vervolgens weergegeven. Hiermee kunt u uw bericht controleren en het verzenden [voorbereiden](../../sending/using/preparing-the-send.md).

   Met de **[!UICONTROL Edit properties]** knop in de rechterbovenhoek kunt u de eigenschappen van het e-mailbericht bewerken. U kunt bijvoorbeeld de e-mail zo configureren dat het label wordt berekend op het moment dat de levering wordt voorbereid.  De beschikbare parameters worden vermeld in [deze sectie](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/delivery_dashboard_2.png)

1. Plan de verzending. Zie [Berichten plannen](../../sending/using/about-scheduling-messages.md).

   ![](assets/delivery_planning.png)

1. Bereid uw bericht voor om zijn doel te analyseren. See [Preparing the send](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >U kunt algemene moeheidsregels tussen kanalen instellen om overvraagde profielen automatisch uit te sluiten van campagnes. Zie [Vermoeidsregels](../../sending/using/fatigue-rules.md)voor meer informatie hierover.

1. Verzend proeven om uw bericht te controleren en te valideren en de weergave ervan in inboxen te controleren. Zie Proef [verzenden](../../sending/using/sending-proofs.md).

   ![](assets/bat_select.png)

1. Verzend het bericht en controleer zijn levering door het berichtdashboard en de logboeken. Zie [Berichten](../../sending/using/confirming-the-send.md)verzenden.

   ![](assets/confirm_delivery.png)

1. Meet het effect van uw bericht met leveringsrapporten. For more on reporting, see [this section](../../reporting/using/about-dynamic-reports.md).

**Verwante onderwerpen**:

* [Een e-mail maken](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/create-email-from-homepage.html) video
* [Een gepersonaliseerde e-mail](https://helpx.adobe.com/nl/campaign/kb/acs-get-started-with-emails.html) stapsgewijze handleiding maken
* [Integratie](https://docs.adobe.com/content/help/nl-NL/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.html) -video Adobe Campaign en Dreamweaver
* [Integreren met Adobe Experience Manager](../../integrating/using/integrating-with-experience-manager.md)
