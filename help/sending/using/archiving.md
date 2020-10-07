---
title: Berichten archiveren in Adobe Campaign Standard
description: Leer hoe u e-mailberichten met Adobe Campaign Standard kunt archiveren met een BCC-e-mailadres.
page-status-flag: never-activated
uuid: c3721647-0663-4614-a9c9-3b3a40af328a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
discoiquuid: 6fa50f0d-3dcf-4a9e-bccc-1ecda2bfb449
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 6%

---


# Archiveren met Email BCC{#archiving-emails}

U kunt Adobe Campaign zo configureren dat een kopie van de e-mails die via e-mail BCC van uw platform worden verzonden, bewaard blijft.

Met name als uw organisatie alle uitgaande e-mailberichten moet archiveren voor naleving, kunt u deze mogelijkheid inschakelen. Hiermee kunt u een exacte verborgen kopie van de bijbehorende verzonden berichten verzenden naar een BCC-e-mailadres (onzichtbaar voor de ontvangers van de zending) dat u moet opgeven.

Als deze optie eenmaal is ingeschakeld, moet u de e-mail BCC activeren via de **[!UICONTROL Archive emails]** optie in de sjabloon voor het verzenden van e-mail.

>[!NOTE]
>
>Adobe Campaign zelf beheert gearchiveerde bestanden niet. Het laat u toe om de berichten van uw keus naar een specifiek adres te verzenden, van waar zij kunnen worden verwerkt en worden gearchiveerd gebruikend een extern systeem.

## Recommendations en beperkingen {#recommendations-and-limitations}

* Deze functie is optioneel. Controleer uw licentieovereenkomst en neem contact op met uw accountmanager om deze te activeren.
* Het adres BCC van uw keus moet aan het team van Adobe worden verstrekt die het voor u zal vormen.
* U kunt slechts één BCC-e-mailadres gebruiken.
* Alleen e-mailberichten die correct zijn verzonden, worden in aanmerking genomen. Bounces niet.
* Om privacyredenen moeten BCC-e-mails worden verwerkt door een archiveringssysteem dat veilig identificeerbare informatie (PII) kan opslaan.
* Bij het maken van een nieuwe leveringssjabloon is de optie BCC via e-mail niet standaard ingeschakeld, zelfs niet als de optie is aangeschaft. U moet het manueel in elke leveringsmalplaatje toelaten waar u het wilt gebruiken.

>[!NOTE]
>
>De gearchiveerde e-mails kunnen momenteel niet worden verzonden met de verbeterde MTA van Adobe Campaign, zelfs niet als u al bent geüpgraded naar de verbeterde MTA.

## E-mailarchivering activeren {#activating-email-archiving}

Nadat e-mail-BCC is ingeschakeld, wordt deze geactiveerd in de [e-mailsjabloon](../../start/using/marketing-activity-templates.md)via een speciale optie:

1. Ga naar **Bronnen** > **Sjablonen** > **Leveringssjablonen**.
1. Dupliceer de out-of-box **[!UICONTROL Send via email]** sjabloon.
1. Selecteer de gedupliceerde sjabloon.
1. Click the **[!UICONTROL Edit properties]** button to edit the template&#39;s properties.
1. Vouw de sectie **[!UICONTROL Send]** uit.
1. Schakel het **[!UICONTROL Archive emails]** selectievakje in om een kopie van alle verzonden berichten te bewaren voor elke levering die op deze sjabloon is gebaseerd.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>Als de e-mails die naar het BCC-adres worden verzonden worden geopend en doorgeklikt, wordt hiermee rekening gehouden in de analyse **[!UICONTROL Total opens]** en **[!UICONTROL Clicks]** de verzendanalyse, wat tot onjuiste berekeningen kan leiden.