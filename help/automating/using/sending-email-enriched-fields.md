---
title: Een e-mail met verrijkte velden verzenden
description: In het onderstaande voorbeeld ziet u hoe u een e-mail verzendt met behulp van aanvullende gegevens die via het laden van het bestand zijn opgehaald uit een extern bestand.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileImport,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 5ca7571d-d4d2-4b59-86d4-4f1f3a620b54
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 68%

---

# Een e-mail met verrijkte velden verzenden {#sending-email-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](example-2-email-with-enriched-fields)-->

Met de activiteit voor het laden van een bestand kunt u ook een e-mail verzenden die is verrijkt met aanvullende data van een extern bestand in dezelfde workflow.

In het onderstaande voorbeeld ziet u hoe u een e-mail verzendt met behulp van aanvullende data die via de activiteit voor het laden van het bestand zijn opgehaald uit een extern bestand. In dit voorbeeld bevat het externe bestand een lijst met profielen met het bijbehorende accountnummer. U wilt deze data importeren om een e-mail te verzenden naar elk profiel met het bijbehorende accountnummer.

![](assets/load_file_workflow_ex2.png)

Voer de volgende stappen uit om de workflow te maken:

1. Sleep een [Query](../../automating/using/query.md) in uw werkstroom en open het om het belangrijkste doel te bepalen.

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. Sleep een [Bestand laden](../../automating/using/load-file.md) activiteit om sommige gegevens aan een profiel toe te wijzen. In dit voorbeeld laadt u een bestand met accountnummers die overeenkomen met bepaalde profielen van de database.

   ![](assets/load_file_activity.png)

1. Sleep een [Verrijking](../../automating/using/enrichment.md) in uw werkstroom en koppel het ladingsdossier en vraagactiviteiten aan het.

1. Selecteer op het tabblad **[!UICONTROL Advanced relations]** van de activiteit voor het verrijken de optie **[!UICONTROL 0 or 1 cardinality simple link]** en definieer de velden die moeten worden gebruikt voor afstemming. Hier gebruiken we de achternaam om de data af te stemmen op de databaseprofielen.

   ![](assets/load_file_enrichment_relation.png)

1. Selecteer op het tabblad **[!UICONTROL Additional data]** de elementen die u in de e-mail wilt gebruiken. Hier selecteert u Account number (kolom uit het bestand dat u hebt opgehaald via de activiteit voor het laden van een bestand).

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   Zie de sectie [Verrijking](../../automating/using/enrichment.md) voor meer informatie.

1. Sleep een [Segmentering](../../automating/using/segmentation.md) in uw werkstroom en open het om het belangrijkste doel te verfijnen.

   ![](assets/load_file_segmentation.png)

   Zie de sectie [Segmentatie](../../automating/using/segmentation.md) voor meer informatie.

1. Sleep een [E-maillevering](../../automating/using/email-delivery.md) in uw werkstroom te openen.

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. Voeg een personalisatieveld toe en selecteer de aanvullende data die in de activiteit voor het verrijken (hier Account number) zijn gedefinieerd vanaf het knooppunt **[!UICONTROL Additional data (targetData)]**. Hiermee kunt u het accountnummer van elk profiel in de e-mailcontent op een dynamische manier ophalen.

   ![](assets/load_file_perso_field.png)

1. Sla de e-mail op en start de workflow.

De e-mail wordt naar het doel verzonden. Elk profiel ontvangt de e-mail met het overeenkomstige accountnummer.

![](assets/load_file_email.png)
