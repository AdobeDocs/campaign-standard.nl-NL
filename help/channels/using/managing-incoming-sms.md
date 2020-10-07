---
title: Binnenkomende sms'en beheren
description: Leer hoe u STOP SMS beheert en inkomende SMS opslaat in Adobe Campaign.
page-status-flag: never-activated
uuid: f063052b-96ef-41b6-bf1b-4006de73f0b9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: ee1970e6-1ced-46e0-94e6-8337768300ee
delivercontext-tags: delivery,smsContent,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 7%

---


# Binnenkomende sms&#39;en beheren{#managing-incoming-sms}

## STOP SMS beheren {#managing-stop-sms}

Wanneer een profiel een sms-bericht beantwoordt dat via Campaign is verzonden, kunt u berichten configureren die automatisch naar het profiel worden teruggestuurd, evenals de actie die moet worden uitgevoerd.

Deze configuratie wordt bepaald in de **[!UICONTROL Automatic reply sent to the MO]** sectie van [SMS die externe rekening](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)verplettert. MO staat voor &#39;Mobiele oorsprong&#39;, wat betekent dat u een automatisch antwoord kunt configureren voor de mobiele gebruiker die het SMS heeft verzonden.

Dit doet u als volgt:

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration > Application settings > External accounts]** then the **[!UICONTROL SMS routing via SMPP]** external account.
1. Klik onder de **[!UICONTROL Automatic reply sent to the MO]** categorie **[!UICONTROL Create element]** om de automatische reactie te configureren.

   ![](assets/sms_mo_1.png)

1. Kies het trefwoord dat dit automatische antwoord activeert. De trefwoorden zijn niet hoofdlettergevoelig. Als ontvangers bijvoorbeeld het trefwoord &quot;STOP&quot; verzenden, ontvangen ze de automatische reactie.

   Laat deze kolom leeg als u hetzelfde antwoord wilt verzenden, ongeacht het trefwoord.

   ![](assets/sms_mo_2.png)

1. Geef in het **[!UICONTROL Short code]** veld een nummer op dat gewoonlijk wordt gebruikt om leveringen te verzenden en dat als naam van de afzender zal fungeren. U kunt ook besluiten om de **[!UICONTROL Short code]** kolom leeg te laten, om het zelfde antwoord te verzenden ongeacht wat de korte code.

   ![](assets/sms_mo_4.png)

1. Typ in het veld het antwoord dat u naar de ontvangers wilt verzenden **[!UICONTROL Reply]**.

   Als u een actie wilt uitvoeren zonder een antwoord te verzenden, laat u de **[!UICONTROL Reply]** kolom leeg. Zo kunt u bijvoorbeeld het telefoonnummer van een gebruiker die met een ander bericht dan &quot;STOP&quot; reageert, uit quarantaine verwijderen.

   ![](assets/sms_mo_3.png)

1. Koppel een handeling in het **[!UICONTROL Additional action]** veld aan uw automatische antwoord:

   * De **[!UICONTROL Send to quarantine]** actie plaatst automatisch het aantal van de profieltelefoon in quarantines.
   * De **[!UICONTROL Remove from quarantine]** actie verwijdert het aantal van de profieltelefoon uit quarantaine.
   * Met de **[!UICONTROL None]** handeling kunt u alleen het bericht naar de ontvangers verzenden zonder een handeling uit te voeren.

   Bijvoorbeeld, in de configuratie hieronder, als de ontvangers het sleutelwoord &quot;STOP&quot;verzenden, zullen zij automatisch een unsubscription bevestiging ontvangen en hun telefoonaantal zal naar quarantaine met de **[!UICONTROL On denylist]** status worden verzonden. Deze status verwijst alleen naar het telefoonnummer. Het profiel is zodanig dat de gebruiker e-mailberichten blijft ontvangen.

   ![](assets/sms_mo.png)

De ontvangers kunnen nu automatisch het abonnement op uw berichten opzeggen en naar quarantaine worden verzonden met dit automatische antwoord. De in quarantaine geplaatste ontvangers worden vermeld in de **[!UICONTROL Addresses]** lijst beschikbaar door **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** menu. For more information on quarantines, refer to this [section](../../sending/using/understanding-quarantine-management.md).

Deze inkomende SMS kan indien nodig worden opgeslagen. For more information on this, refer to this [section](#storing-incoming-sms).

## Binnenkomende SMS opslaan {#storing-incoming-sms}

In de **[!UICONTROL SMS routing via SMPP]** externe account kunt u ervoor kiezen inkomende berichten op te slaan, bijvoorbeeld wanneer een abonnee &quot;STOP&quot; antwoordt op een SMS-bericht om uit uw lijst met ontvangers te worden verwijderd.

![](assets/sms_config_mo_1.png)

Door **[!UICONTROL Store incoming MO in the database]** in de **[!UICONTROL SMPP channel settings]** categorie te controleren, zal al SMS in de inSMS lijst worden opgeslagen en kan via een vraagactiviteit in een werkschema worden teruggewonnen.

Dit doet u als volgt:

1. In the **[!UICONTROL SMPP channel settings]** field, check **[!UICONTROL Store incoming MO in the database]**.

   ![](assets/sms_config_mo_2.png)

1. In the **[!UICONTROL Marketing activities]** tab, click **[!UICONTROL Create]** then select **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. Selecteer het type workflow.
1. Bewerk de eigenschappen van de workflow en klik op **[!UICONTROL Create]**. For more on workflows creation, refer to this [section](../../automating/using/building-a-workflow.md).
1. Drag and drop a **[!UICONTROL Query]** activity and double-click the activity.
1. Kies op het **[!UICONTROL Properties]** tabblad van de query de optie **[!UICONTROL Incoming SMS (inSMS)]** in het **[!UICONTROL Resource]** veld.

   ![](assets/sms_config_mo_4.png)

1. Vervolgens sleept u de **[!UICONTROL Target]** regel op het **[!UICONTROL Incoming SMS attributes]** tabblad.

   ![](assets/sms_config_mo_5.png)

1. Hier, willen wij elk inkomend bericht van de dag daarvoor richten. In the **[!UICONTROL Field]** category, select **[!UICONTROL Creation date (created)]**.
1. Selecteer vervolgens **[!UICONTROL Filter type]** in **[!UICONTROL Relative]** , kies **[!UICONTROL Level of precision]****[!UICONTROL Day]**.

   ![](assets/sms_config_mo_6.png)

1. Vervolgens kunt u kiezen of u gegevens wilt ophalen van vandaag, de dag ervoor of de laatste dagen. Klik **[!UICONTROL Confirm]** wanneer uw vraag wordt gevormd.

Deze vraag zal elk die STOP bericht terugwinnen afhankelijk van de gekozen tijdwaaier wordt ontvangen.

De activiteit staat u bijvoorbeeld toe om een bevolking te bouwen en uw leveringen beter te personaliseren.
