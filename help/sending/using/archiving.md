---
title: Berichten archiveren in Adobe Campaign Standard
description: Leer hoe u e-mailberichten met Adobe Campaign Standard kunt archiveren met een BCC-e-mailadres.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: 7bf380d7-195e-413d-b14e-85e78b07ba8b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 6%

---

# Archiveren met BCC-e-mails{#archiving-emails}

U kunt Adobe Campaign zo configureren dat een kopie van de e-mails die via e-mail BCC van uw platform worden verzonden, bewaard blijft.

Met name als uw organisatie alle uitgaande e-mailberichten moet archiveren voor naleving, kunt u deze mogelijkheid inschakelen. Hiermee kunt u een exacte verborgen kopie van de bijbehorende verzonden berichten verzenden naar een BCC-e-mailadres (onzichtbaar voor de ontvangers van de zending) dat u moet opgeven.

Als deze optie is ingeschakeld, moet u e-mail BCC activeren via de **[!UICONTROL Archive emails]** in de sjabloon voor e-maillevering.

>[!NOTE]
>
>Adobe Campaign zelf beheert gearchiveerde bestanden niet. Het laat u toe om de berichten van uw keus naar een specifiek adres te verzenden, van waar zij kunnen worden verwerkt en worden gearchiveerd gebruikend een extern systeem.

## Recommendations en beperkingen {#recommendations-and-limitations}

* Deze functie is optioneel. Controleer uw licentieovereenkomst en neem contact op met uw accountmanager om deze te activeren.
* Het adres BCC van uw keus moet aan het team van de Adobe worden verstrekt die het voor u zal vormen.
* U kunt slechts één BCC-e-mailadres gebruiken.
* Alleen e-mailberichten die correct zijn verzonden, worden in aanmerking genomen. Bounces niet.
* Om privacyredenen moeten BCC-e-mails worden verwerkt door een archiveringssysteem dat veilig identificeerbare informatie (PII) kan opslaan.
* Bij het maken van een nieuwe leveringssjabloon is E-mail BCC niet standaard ingeschakeld, zelfs niet als de optie is aangeschaft. U moet het manueel in elke leveringsmalplaatje toelaten waar u het wilt gebruiken.

>[!NOTE]
>
>Momenteel worden de gearchiveerde e-mails nog verzonden door de oude archiveringsmodule die een eenvoudig SMTP-relais gebruikt.

## E-mailarchivering activeren {#activating-email-archiving}

Nadat e-mail-BCC is ingeschakeld, wordt deze geactiveerd in het dialoogvenster [e-mailsjabloon](../../start/using/marketing-activity-templates.md)door middel van een specifieke optie:

1. Ga naar **Bronnen** > **Sjablonen** > **Afleveringssjablonen**.
1. De uit-van-de-doos dupliceren **[!UICONTROL Send via email]** sjabloon.
1. Selecteer de gedupliceerde sjabloon.
1. Klik op de knop **[!UICONTROL Edit properties]** om de eigenschappen van de sjabloon te bewerken.
1. Vouw de sectie **[!UICONTROL Send]** uit.
1. Controleer de **[!UICONTROL Archive emails]** doos om een exemplaar van alle verzonden berichten voor elke levering te houden die op dit malplaatje wordt gebaseerd.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>Als de e-mails die naar het BCC-adres worden verzonden worden geopend en als hierop wordt geklikt, wordt hiermee rekening gehouden in het dialoogvenster **[!UICONTROL Total opens]** en **[!UICONTROL Clicks]** van de send analyse, die sommige misberekeningen zou kunnen veroorzaken.
