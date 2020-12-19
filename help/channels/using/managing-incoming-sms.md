---
solution: Campaign Standard
product: campaign
title: Binnenkomende sms'en beheren
description: Leer hoe u STOP SMS beheert en inkomende SMS opslaat in Adobe Campaign.
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: delivery,smsContent,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 7%

---


# Binnenkomende sms&#39;en beheren{#managing-incoming-sms}

## STOP-SMS beheren {#managing-stop-sms}

Wanneer een profiel een sms-bericht beantwoordt dat via Campaign is verzonden, kunt u berichten configureren die automatisch naar het profiel worden teruggestuurd, evenals de actie die moet worden uitgevoerd.

Deze configuratie wordt bepaald in **[!UICONTROL Automatic reply sent to the MO]** sectie van [SMS die externe rekening ](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) verplettert. MO staat voor &#39;Mobiele oorsprong&#39;, wat betekent dat u een automatisch antwoord kunt configureren voor de mobiele gebruiker die het SMS heeft verzonden.

Dit doet u als volgt:

1. Selecteer **[!UICONTROL Administration > Application settings > External accounts]** in het geavanceerde menu via het Adobe Campaign-logo en vervolgens de externe account **[!UICONTROL SMS routing via SMPP]**.
1. Klik onder de categorie **[!UICONTROL Automatic reply sent to the MO]** op **[!UICONTROL Create element]** om uw automatische reactie te configureren.

   ![](assets/sms_mo_1.png)

1. Kies het trefwoord dat dit automatische antwoord activeert. De trefwoorden zijn niet hoofdlettergevoelig. Als ontvangers bijvoorbeeld het trefwoord &quot;STOP&quot; verzenden, ontvangen ze de automatische reactie.

   Laat deze kolom leeg als u hetzelfde antwoord wilt verzenden, ongeacht het trefwoord.

   ![](assets/sms_mo_2.png)

1. Geef in het veld **[!UICONTROL Short code]** een getal op dat gewoonlijk wordt gebruikt om leveringen te verzenden en dat als naam van de afzender zal dienen. U kunt ook besluiten om de **[!UICONTROL Short code]** kolom leeg te verlaten, om het zelfde antwoord te verzenden ongeacht wat de korte code.

   ![](assets/sms_mo_4.png)

1. Typ het antwoord dat u naar uw ontvangers wilt verzenden in het veld **[!UICONTROL Reply]**.

   Als u een actie wilt uitvoeren zonder een antwoord te verzenden, laat u de kolom **[!UICONTROL Reply]** leeg. Zo kunt u bijvoorbeeld het telefoonnummer van een gebruiker die met een ander bericht dan &quot;STOP&quot; reageert, uit quarantaine verwijderen.

   ![](assets/sms_mo_3.png)

1. Koppel in het veld **[!UICONTROL Additional action]** een handeling aan uw automatische antwoord:

   * De actie **[!UICONTROL Send to quarantine]** plaatst automatisch het aantal van de profieltelefoon in quarantines.
   * De actie **[!UICONTROL Remove from quarantine]** verwijdert het aantal van de profieltelefoon uit quarantaine.
   * Met de handeling **[!UICONTROL None]** kunt u alleen het bericht verzenden naar uw ontvangers zonder een handeling te hoeven uitvoeren.

   Bijvoorbeeld, in de configuratie hieronder, als de ontvangers het sleutelwoord &quot;STOP&quot;verzenden, zullen zij automatisch een unsubscription bevestiging ontvangen en hun telefoonaantal zal naar quarantaine met de status **[!UICONTROL On denylist]** worden verzonden. Deze status verwijst alleen naar het telefoonnummer. Het profiel is zodanig dat de gebruiker e-mailberichten blijft ontvangen.

   ![](assets/sms_mo.png)

De ontvangers kunnen nu automatisch het abonnement op uw berichten opzeggen en naar quarantaine worden verzonden met dit automatische antwoord. De in quarantaine geplaatste ontvangers worden vermeld in de **[!UICONTROL Addresses]**-tabel die beschikbaar is via het menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]**. Voor meer informatie over quarantines, verwijs naar dit [sectie](../../sending/using/understanding-quarantine-management.md).

Deze inkomende SMS kan indien nodig worden opgeslagen. Raadpleeg voor meer informatie hierover deze [sectie](#storing-incoming-sms).

## Binnenkomende SMS {#storing-incoming-sms} opslaan

In **[!UICONTROL SMS routing via SMPP]** externe rekening, kunt u verkiezen om inkomende berichten op te slaan, bijvoorbeeld wanneer een abonnee &quot;STOP&quot;aan een SMS- bericht antwoordt om van uw ontvankelijke lijsten te worden verwijderd.

![](assets/sms_config_mo_1.png)

Door **[!UICONTROL Store incoming MO in the database]** in de **[!UICONTROL SMPP channel settings]** categorie te controleren, zal al SMS in de inSMS lijst worden opgeslagen en kan via een vraagactiviteit in een werkschema worden teruggewonnen.

Dit doet u als volgt:

1. Schakel **[!UICONTROL Store incoming MO in the database]** in het veld **[!UICONTROL SMPP channel settings]** in.

   ![](assets/sms_config_mo_2.png)

1. Klik op het tabblad **[!UICONTROL Marketing activities]** op **[!UICONTROL Create]** en selecteer **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. Selecteer het type workflow.
1. Bewerk de eigenschappen van de workflow en klik op **[!UICONTROL Create]**. Raadpleeg dit [gedeelte](../../automating/using/building-a-workflow.md) voor meer informatie over het maken van workflows.
1. Sleep een **[!UICONTROL Query]**-activiteit en dubbelklik op de activiteit.
1. Kies **[!UICONTROL Incoming SMS (inSMS)]** in het veld **[!UICONTROL Resource]** op het tabblad **[!UICONTROL Properties]** van de query.

   ![](assets/sms_config_mo_4.png)

1. Vervolgens sleept u de **[!UICONTROL Incoming SMS attributes]**-regel op de tab **[!UICONTROL Target]**.

   ![](assets/sms_config_mo_5.png)

1. Hier, willen wij elk inkomend bericht van de dag daarvoor richten. Selecteer **[!UICONTROL Creation date (created)]** in de categorie **[!UICONTROL Field]**.
1. Selecteer **[!UICONTROL Filter type]** en kies **[!UICONTROL Day]** in **[!UICONTROL Level of precision]**.**[!UICONTROL Relative]**

   ![](assets/sms_config_mo_6.png)

1. Vervolgens kunt u kiezen of u gegevens wilt ophalen van vandaag, de dag ervoor of de laatste dagen. Klik **[!UICONTROL Confirm]** wanneer uw vraag wordt gevormd.

Deze vraag zal elk die STOP bericht terugwinnen afhankelijk van de gekozen tijdwaaier wordt ontvangen.

De activiteit staat u bijvoorbeeld toe om een bevolking te bouwen en uw leveringen beter te personaliseren.
