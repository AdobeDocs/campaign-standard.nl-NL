---
title: Logboeken exporteren
description: Loggegevens, of ze nu betrekking hebben op leveringen of op abonnementen, kunnen via een eenvoudige workflow worden geëxporteerd.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
old-role: Data Architect
role: Developer
level: Experienced
exl-id: d74e2a2c-3ce1-44d6-a058-67b0600360ca
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 14%

---

# Logboeken exporteren{#exporting-logs}

Loggegevens, of ze nu betrekking hebben op leveringen of op abonnementen, kunnen via een eenvoudige workflow worden geëxporteerd. Hiermee kunt u de resultaten van uw campagnes analyseren in uw eigen rapportage- of BI-programma.

>[!CAUTION]
>
>Slechts kunnen de Functionele [ beheerders ](../../administration/using/users-management.md#functional-administrators), met **[!UICONTROL Administration]** rol en toegang tot **Alle** eenheden tot het verzenden van logboeken, berichtlogboeken, het volgen logboeken, uitsluiting of abonnementlogboeken toegang hebben. Een gebruiker zonder beheerdersrechten kan zich richten op deze logbestanden, maar begint met een gekoppelde tabel (profielen, levering).

Als u een **[!UICONTROL Incremental query]** gebruikt die alleen nieuwe logbestanden ophaalt wanneer de workflow wordt uitgevoerd en een eenvoudige **[!UICONTROL Extract file]** -activiteit gebruikt om de uitvoerkolommen te definiëren, kunt u een bestand ophalen met de indeling en alle gegevens die u nodig hebt. Gebruik vervolgens een **[!UICONTROL Transfer file]** -activiteit om het uiteindelijke bestand op te halen. Elke werkstroomuitvoering wordt gepland door een **[!UICONTROL Scheduler]** .

De bewerking voor het exporteren van logbestanden kan worden uitgevoerd door standaardgebruikers. De privé middelen zoals: de uitzendingen, het volgen logboeken, de logboeken van het uitsluitingslogboekabonnement en de abonnementsgeschiedenis logboeken op **Profielen** kunnen slechts door functionele beheerder worden beheerd.

1. Creeer een nieuw werkschema zoals gedetailleerd in [ deze sectie ](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Voeg een **[!UICONTROL Scheduler]** activiteit toe en plaats het op uw behoeften. Hieronder ziet u een voorbeeld van een maandelijkse uitvoering.

   ![](assets/export_logs_scheduler.png)

1. Voeg een **[!UICONTROL Incremental query]** activiteit toe en vorm het zodat het de logboeken selecteert u wenst. Bijvoorbeeld, om alle nieuwe of bijgewerkte uitzendingen (de logboeken van de profiellevering te selecteren):

   * In het **[!UICONTROL Properties]** lusje, verander het doelmiddel in **Logboeken van de Levering** (wideLogRcp).

     ![](assets/export_logs_query_properties.png)

   * Stel op het tabblad **[!UICONTROL Target]** een voorwaarde in om alle leveringslogboeken op te halen die overeenkomen met leveringen die in 2016 of daarna zijn verzonden. Voor meer informatie, verwijs naar [ het Uitgeven vragen ](../../automating/using/editing-queries.md#creating-queries) sectie.

     ![](assets/export_logs_query_target.png)

   * Op het **[!UICONTROL Processed data]** lusje, selecteer **[!UICONTROL Use a date field]** en kies het **lastModified** gebied. Bij de volgende uitvoeringen van de workflow worden alleen logboeken opgehaald die na de laatste uitvoering zijn gewijzigd of gemaakt.

     ![](assets/export_logs_query_processeddata.png)

     Na de eerste uitvoering van de workflow ziet u op dit tabblad de laatste uitvoeringsdatum die wordt gebruikt voor de volgende uitvoering. Deze wordt automatisch steeds bijgewerkt wanneer de workflow wordt uitgevoerd. U kunt deze waarde ook overschrijven door handmatig een nieuwe waarde in te voeren die beter aan uw behoeften voldoet.

1. Voeg een **[!UICONTROL Extract file]** -activiteit toe die de gevraagde gegevens in een bestand exporteert:

   * Geef op het tabblad **[!UICONTROL Extraction]** de naam van het bestand op.

     Als u de optie **[!UICONTROL Add date and time to the file name]** selecteert, wordt deze naam automatisch aangevuld met de datum van het exporteren om ervoor te zorgen dat alle geëxtraheerde bestanden uniek zijn. Selecteer de kolommen die u in het bestand wilt exporteren. U kunt hier gegevens selecteren die afkomstig zijn uit gerelateerde bronnen, zoals leverings- of profielgegevens.

     >[!NOTE]
     >
     >Als u een unieke id voor elk logboek wilt exporteren, selecteert u het element **[!UICONTROL Delivery log ID]** .

     U kunt een sortering toepassen om het uiteindelijke bestand te ordenen. Bijvoorbeeld op de logboekdatum, zoals aangetoond in het voorbeeld hieronder.

     ![](assets/export_logs_extractfile_extraction.png)

   * Definieer op het tabblad **[!UICONTROL File structure]** de indeling van het uitvoerbestand zodat dit aan uw wensen voldoet.

     Schakel de optie **[!UICONTROL Export labels instead of internal values of enumerations]** in als u opsommingswaarden exporteert. Hiermee kunt u kortere labels ophalen die gemakkelijker zijn te begrijpen dan id&#39;s.

1. Voeg een **[!UICONTROL Transfer file]** -activiteit toe en configureer deze om het nieuwe bestand van de Adobe Campaign-server over te brengen naar een andere locatie waar u toegang tot het bestand hebt, zoals een SFTP-server.

   * Selecteer op het tabblad **[!UICONTROL General]** **[!UICONTROL File upload]** omdat het bestand van Adobe Campaign naar een andere server moet worden verzonden.
   * In het **[!UICONTROL Protocol]** lusje, specificeer de overdrachtsparameters en selecteer de [ externe rekening ](../../administration/using/external-accounts.md#creating-an-external-account) aan gebruik.

1. Voeg een **[!UICONTROL End]** activiteit toe om ervoor te zorgen het behoorlijk beëindigt en uw werkschema bewaart.

   ![](assets/export_logs_example_workflow.png)

U kunt nu de workflow uitvoeren en het uitvoerbestand op uw externe server ophalen.

**Verwant onderwerp:**

[Workflows](../../automating/using/get-started-workflows.md)
