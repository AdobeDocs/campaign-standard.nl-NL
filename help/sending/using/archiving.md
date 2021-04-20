---
solution: Campaign Standard
product: campaign
title: Berichten archiveren in Adobe Campaign Standard
description: Leer hoe u e-mailberichten met Adobe Campaign Standard kunt archiveren met een BCC-e-mailadres.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
feature: Performance Monitoring
role: Business Practitioner
level: Intermediate
exl-id: 7bf380d7-195e-413d-b14e-85e78b07ba8b
translation-type: tm+mt
source-git-commit: f7d77f524a6c141066056e53fc8616f35189fc39
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 7%

---

# Archiveren met Email BCC{#archiving-emails}

U kunt Adobe Campaign zo configureren dat een kopie van de e-mails die via e-mail BCC van uw platform worden verzonden, bewaard blijft.

Met name als uw organisatie alle uitgaande e-mailberichten moet archiveren voor naleving, kunt u deze mogelijkheid inschakelen. Hiermee kunt u een exacte verborgen kopie van de bijbehorende verzonden berichten verzenden naar een BCC-e-mailadres (onzichtbaar voor de ontvangers van de zending) dat u moet opgeven.

Als deze optie eenmaal is ingeschakeld, moet u de optie BCC via e-mail activeren via de optie **[!UICONTROL Archive emails]** in de sjabloon voor het verzenden van e-mail.

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
>Momenteel worden de gearchiveerde e-mails nog verzonden door de oude archiveringsmodule die een eenvoudig SMTP-relais gebruikt.

## E-mailarchivering {#activating-email-archiving} activeren

Nadat e-mail BCC is ingeschakeld, wordt deze geactiveerd in de [e-mailsjabloon](../../start/using/marketing-activity-templates.md) via een speciale optie:

1. Ga naar **Bronnen** > **Sjablonen** > **Leveringssjablonen**.
1. Dupliceer de uit-van-doos **[!UICONTROL Send via email]** malplaatje.
1. Selecteer de gedupliceerde sjabloon.
1. Klik op de knop **[!UICONTROL Edit properties]** om de eigenschappen van de sjabloon te bewerken.
1. Vouw de sectie **[!UICONTROL Send]** uit.
1. Schakel het selectievakje **[!UICONTROL Archive emails]** in om een kopie van alle verzonden berichten te bewaren voor elke levering die op deze sjabloon is gebaseerd.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>Als de e-mails die naar het BCC-adres worden verzonden, worden geopend en doorgeklikt, wordt hiermee rekening gehouden in de **[!UICONTROL Total opens]** en **[!UICONTROL Clicks]** van de verzendanalyse, wat tot onjuiste berekeningen kan leiden.
