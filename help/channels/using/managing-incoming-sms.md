---
title: Binnenkomende sms'en beheren
description: Leer hoe u STOP SMS beheert en inkomende SMS opslaat in Adobe Campaign.
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: delivery,smsContent,back
feature: SMS
role: User
level: Intermediate
exl-id: 86cb6f4c-a5a7-4d9d-bbfd-4a70af38cf3a
source-git-commit: 30d0c2552bea3a7cbd8500be4e8c0c74e5a40a99
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---

# Binnenkomende sms&#39;en beheren{#managing-incoming-sms}

## STOP SMS beheren {#managing-stop-sms}

Wanneer een profiel op een SMS-bericht reageert dat via Campagne is verzonden, kunt u berichten configureren die automatisch naar hen worden teruggestuurd, evenals de actie die moet worden uitgevoerd.

Deze configuratie is gedefinieerd in het dialoogvenster **[!UICONTROL Automatic reply sent to the MO]** van de [SMS-routering externe account](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing). MO staat voor &#39;Mobiele oorsprong&#39;, wat betekent dat u een automatisch antwoord kunt configureren voor de mobiele gebruiker die het SMS heeft verzonden.

Dit doet u als volgt:

1. Selecteer in het geavanceerde menu via het Adobe Campaign-logo de optie **[!UICONTROL Administration > Application settings > External accounts]** dan de **[!UICONTROL SMS routing via SMPP]** externe rekening.
1. Onder de **[!UICONTROL Automatic reply sent to the MO]** categorie, klikt u op **[!UICONTROL Create element]** om te beginnen uw automatisch antwoord te vormen.

   ![](assets/sms_mo_1.png)

1. Kies het trefwoord dat dit automatische antwoord activeert. De trefwoorden zijn niet hoofdlettergevoelig. Als ontvangers bijvoorbeeld het trefwoord &quot;STOP&quot; verzenden, ontvangen ze de automatische reactie.

   Laat deze kolom leeg als u hetzelfde antwoord wilt verzenden, ongeacht het trefwoord.

   >[!IMPORTANT]
   >
   >Alleen alfanumerieke tekens zijn toegestaan.

   ![](assets/sms_mo_2.png)

1. In de **[!UICONTROL Short code]** Geef een nummer op dat gewoonlijk wordt gebruikt om leveringen te verzenden en dat als naam van de afzender zal fungeren. U kunt ook besluiten om de **[!UICONTROL Short code]** kolom leeg, om het zelfde antwoord te verzenden geen kwestie wat de korte code.

   ![](assets/sms_mo_4.png)

1. Typ in het veld het antwoord dat u naar de ontvangers wilt verzenden **[!UICONTROL Reply]**.

   Als u een actie wilt uitvoeren zonder een antwoord te verzenden, laat u de **[!UICONTROL Reply]** kolom leeg. Zo kunt u bijvoorbeeld het telefoonnummer van een gebruiker die met een ander bericht dan &quot;STOP&quot; reageert, uit quarantaine verwijderen.

   ![](assets/sms_mo_3.png)

1. In de **[!UICONTROL Additional action]** veld, een handeling koppelen aan uw automatische antwoord:

   * De **[!UICONTROL Send to quarantine]** De actie plaatst automatisch het aantal van de profieltelefoon in quarantines.
   * De **[!UICONTROL Remove from quarantine]** de actie verwijdert het aantal van de profieltelefoon uit quarantaine.
   * De **[!UICONTROL None]** kunt u het bericht alleen naar de ontvangers verzenden zonder een handeling uit te voeren.

   Als ontvangers in de onderstaande configuratie bijvoorbeeld het trefwoord STOP verzenden, ontvangen ze automatisch een bevestiging van het abonnement en wordt hun telefoonnummer verzonden naar quarantaine met de **[!UICONTROL On denylist]** status. Deze status verwijst alleen naar het telefoonnummer. Het profiel is zodanig dat de gebruiker e-mailberichten blijft ontvangen.

   ![](assets/sms_mo.png)

1. Klik op **[!UICONTROL Save]**.

1. Van de **[!UICONTROL Advanced parameters]** van je SMS-verzending **[!UICONTROL Properties]** kunt u een specifieke **[!UICONTROL Short code]** om automatisch ontvangers uit te sluiten die hebben gekozen. Raadpleeg voor meer informatie hierover [deze sectie](../../administration/using/configuring-sms-channel.md#configuring-sms-properties).

De ontvangers kunnen nu automatisch het abonnement op uw berichten opzeggen en naar quarantaine worden verzonden met dit automatische antwoord. De in quarantaine geplaatste ontvangers worden vermeld in de **[!UICONTROL Addresses]** tabel beschikbaar via **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** -menu. Voor meer informatie over quarantines, verwijs naar dit [sectie](../../sending/using/understanding-quarantine-management.md).

Deze inkomende SMS kan indien nodig worden opgeslagen. Raadpleeg voor meer informatie hierover [sectie](#storing-incoming-sms).

## Binnenkomende SMS opslaan {#storing-incoming-sms}

In de **[!UICONTROL SMS routing via SMPP]** externe account, kunt u ervoor kiezen inkomende berichten op te slaan, bijvoorbeeld wanneer een abonnee &quot;STOP&quot; antwoordt op een SMS-bericht om uit uw lijst met ontvangers te worden verwijderd.

![](assets/sms_config_mo_1.png)

Door te controleren **[!UICONTROL Store incoming MO in the database]** in de **[!UICONTROL SMPP channel settings]** categorie, wordt al SMS opgeslagen in de inSMS-tabel en kan worden opgehaald via een queryactiviteit in een workflow.

Dit doet u als volgt:

1. In de **[!UICONTROL SMPP channel settings]** veld, controleren **[!UICONTROL Store incoming MO in the database]**.

   ![](assets/sms_config_mo_2.png)

1. In de **[!UICONTROL Marketing activities]** tabblad, klikt u op **[!UICONTROL Create]** Selecteer vervolgens **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. Selecteer het type workflow.
1. Bewerk de eigenschappen van de workflow en klik vervolgens op **[!UICONTROL Create]**. Raadpleeg de volgende secties voor meer informatie over het maken van workflows [sectie](../../automating/using/building-a-workflow.md).
1. Sleep een **[!UICONTROL Query]** en dubbelklik op de activiteit.
1. In de **[!UICONTROL Properties]** tabblad van de query, kiest u **[!UICONTROL Incoming SMS (inSMS)]** in de **[!UICONTROL Resource]** veld.

   ![](assets/sms_config_mo_4.png)

1. Dan, in **[!UICONTROL Target]** tabblad, slepen en neerzetten **[!UICONTROL Incoming SMS attributes]** regel.

   ![](assets/sms_config_mo_5.png)

1. Hier, willen wij elk inkomend bericht van de dag daarvoor richten. In de **[!UICONTROL Field]** categorie, selecteert u **[!UICONTROL Creation date (created)]**.
1. In **[!UICONTROL Filter type]**, selecteert u **[!UICONTROL Relative]** dan in **[!UICONTROL Level of precision]**, kiest u **[!UICONTROL Day]**.

   ![](assets/sms_config_mo_6.png)

1. Vervolgens kunt u kiezen of u gegevens wilt ophalen van vandaag, de dag ervoor of de laatste dagen. Klikken **[!UICONTROL Confirm]** wanneer uw vraag wordt gevormd.

Deze vraag zal elk die STOP bericht terugwinnen afhankelijk van de gekozen tijdwaaier wordt ontvangen.

De activiteit staat u bijvoorbeeld toe om een bevolking te bouwen en uw leveringen beter te personaliseren.
