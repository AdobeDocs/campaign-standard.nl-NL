---
title: Logboeken exporteren
description: Loggegevens, of ze nu betrekking hebben op leveringen of op abonnementen, kunnen via een eenvoudige workflow worden geëxporteerd.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
exl-id: d74e2a2c-3ce1-44d6-a058-67b0600360ca
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 14%

---

# Logboeken exporteren{#exporting-logs}

Loggegevens, of ze nu betrekking hebben op leveringen of op abonnementen, kunnen via een eenvoudige workflow worden geëxporteerd. Hiermee kunt u de resultaten van uw campagnes analyseren in uw eigen rapportage- of BI-programma.

>[!CAUTION]
>
>Alleen functionele [beheerders](../../administration/using/users-management.md#functional-administrators), met **[!UICONTROL Administration]** rol en toegang tot **Alle** eenheden hebben toegang tot verzendende logboeken, berichtlogboeken, trackinglogboeken, uitsluitings- of abonnementlogboeken. Een gebruiker zonder beheerdersrechten kan zich richten op deze logbestanden, maar begint met een gekoppelde tabel (profielen, levering).

Door een **[!UICONTROL Incremental query]** te gebruiken die slechts nieuwe logboeken terugwint telkens als het werkschema wordt uitgevoerd en een eenvoudige **[!UICONTROL Extract file]** activiteit om de outputkolommen te bepalen, kunt u een dossier met het formaat en alle gegevens krijgen u nodig hebt. Dan gebruik **[!UICONTROL Transfer file]** activiteit om het definitieve dossier terug te winnen. Elke werkstroomuitvoering wordt gepland door een **[!UICONTROL Scheduler]**.

De bewerking voor het exporteren van logbestanden kan worden uitgevoerd door standaardgebruikers. Particuliere middelen zoals: de uitzendingen, het volgen logboeken, de logboeken van het uitsluitingslogboeken van het abonnement en de abonnementsgeschiedenis het programma **Profiles** kunnen slechts door functionele beheerder worden beheerd.

1. Maak een nieuwe workflow zoals beschreven in [deze sectie](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Voeg een **[!UICONTROL Scheduler]** activiteit toe en plaats het op uw behoeften. Hieronder ziet u een voorbeeld van een maandelijkse uitvoering.

   ![](assets/export_logs_scheduler.png)

1. Voeg een **[!UICONTROL Incremental query]** activiteit toe en vorm het zodat het de logboeken selecteert u wenst. Bijvoorbeeld, om alle nieuwe of bijgewerkte uitzendingen (de logboeken van de profiellevering te selecteren):

   * Wijzig op het tabblad **[!UICONTROL Properties]** de doelbron in **Delivery logs** (wideLogRcp).

      ![](assets/export_logs_query_properties.png)

   * Stel op het tabblad **[!UICONTROL Target]** een voorwaarde in om alle leveringslogboeken op te halen die overeenkomen met leveringen die in 2016 of daarna zijn verzonden. Voor meer informatie, verwijs naar [het Uitgeven van vragen](../../automating/using/editing-queries.md#creating-queries) sectie.

      ![](assets/export_logs_query_target.png)

   * Selecteer op het tabblad **[!UICONTROL Processed data]** **[!UICONTROL Use a date field]** en kies het veld **lastModified**. Bij de volgende uitvoeringen van de workflow worden alleen logboeken opgehaald die na de laatste uitvoering zijn gewijzigd of gemaakt.

      ![](assets/export_logs_query_processeddata.png)

      Na de eerste uitvoering van de workflow ziet u op dit tabblad de laatste uitvoeringsdatum die wordt gebruikt voor de volgende uitvoering. Deze wordt automatisch steeds bijgewerkt wanneer de workflow wordt uitgevoerd. U kunt deze waarde ook overschrijven door handmatig een nieuwe waarde in te voeren die beter aan uw behoeften voldoet.

1. Voeg een **[!UICONTROL Extract file]** activiteit toe die de gevraagde gegevens in een dossier zal uitvoeren:

   * Geef op het tabblad **[!UICONTROL Extraction]** de naam van het bestand op.

      Als u de optie **[!UICONTROL Add date and time to the file name]** selecteert, wordt deze naam automatisch aangevuld met de datum van het exporteren om ervoor te zorgen dat alle geëxtraheerde bestanden uniek zijn. Selecteer de kolommen die u in het bestand wilt exporteren. U kunt hier gegevens selecteren die afkomstig zijn uit gerelateerde bronnen, zoals leverings- of profielgegevens.

      >[!NOTE]
      >
      >Als u een unieke id voor elk log wilt exporteren, selecteert u het element **[!UICONTROL Delivery log ID]**.

      U kunt een sortering toepassen om het uiteindelijke bestand te ordenen. Bijvoorbeeld op de logboekdatum, zoals aangetoond in het voorbeeld hieronder.

      ![](assets/export_logs_extractfile_extraction.png)

   * Definieer op het tabblad **[!UICONTROL File structure]** de indeling van het uitvoerbestand zodat dit aan uw wensen voldoet.

      Schakel de optie **[!UICONTROL Export labels instead of internal values of enumerations]** in als u opsommingswaarden exporteert. Hiermee kunt u kortere labels ophalen die gemakkelijker zijn te begrijpen dan id&#39;s.

1. Voeg een **[!UICONTROL Transfer file]** activiteit toe en vorm het om het nieuwe dossier van de server van Adobe Campaign naar een andere plaats over te brengen waar u tot het kunt toegang hebben, zoals een server SFTP.

   * Selecteer **[!UICONTROL General]** op het tabblad **[!UICONTROL File upload]** als doel het bestand van Adobe Campaign naar een andere server te verzenden.
   * Geef op het tabblad **[!UICONTROL Protocol]** de overdrachtsparameters op en selecteer de [externe account](../../administration/using/external-accounts.md#creating-an-external-account) die u wilt gebruiken.

1. Voeg een **[!UICONTROL End]** activiteit toe om ervoor te zorgen het behoorlijk beëindigt en uw werkschema bewaart.

   ![](assets/export_logs_example_workflow.png)

U kunt nu de workflow uitvoeren en het uitvoerbestand op uw externe server ophalen.

**Verwant onderwerp:**

[Workflows](../../automating/using/get-started-workflows.md)
