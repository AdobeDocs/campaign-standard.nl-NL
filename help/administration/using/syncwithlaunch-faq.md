---
title: Synchroniseren met veelgestelde vragen over technische workflow starten
description: Algemene vragen over de technische workflow voor het starten van Adoben
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: aaaceb3a-5e54-47da-9be4-b70747282830
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 1%

---

# Tags in Adobe Experience Platform - veelgestelde vragen over synchronisatie {#syncwithlaunch-faq}

U kunt mobiele eigenschappen van tags importeren naar Adobe Campaign Standard via het dialoogvenster **[!UICONTROL Sync with Launch]** specifieke technische workflow. Raadpleeg deze voor meer informatie [page](../../administration/using/technical-workflows.md)

In de onderstaande sectie worden veelgestelde vragen over deze synchronisatie weergegeven.

## Ik heb een tag-eigenschap gemaakt (niet-beheerder van Org-unit ALL). Mijn toepassing is klaar om staat in Adobe Campaign te vormen maar ik kan het niet openen/vormen. {#configuring-property}

Alleen de beheerder van de organisatie ALL kan mobiele toepassingen configureren in Adobe Campaign Standard. Zodra gevormd, slechts kunnen de gebruikers van de toegewezen organisatorische eenheid de toepassing uitgeven. Raadpleeg voor meer informatie over de organisatorische eenheid [page](../../administration/using/organizational-units.md).

## Ik kan een geconfigureerde mobiele toepassing niet bewerken in Adobe Campaign Standard en mobiele toepassingen zijn alleen-lezen. {#read-mode-mobile-app}

Controleer de organisatorische eenheid van de mobiele toepassing in **[!UICONTROL Access Authorization]** sectie. Alleen gebruikers van de toegewezen organisatie kunnen de mobiele toepassing bewerken.

Raadpleeg voor meer informatie over de organisatorische eenheid [page](../../administration/using/organizational-units.md).

## Ik ben een beheerder met organisatie eenheid ALL in Adobe Campaign Standard maar ik kan mobiele toepassing niet vormen. {#org-unit-mobile}

Een beheerder met de organisatie die eenheid aan ALLE wordt geplaatst zou rechten op alle markering mobiele eigenschappen moeten hebben om de mobiele toepassing te vormen.

Raadpleeg voor meer informatie over de organisatorische eenheid [page](../../administration/using/organizational-units.md).

## Ik heb een tag mobile-eigenschap gemaakt, maar mijn eigenschap is niet zichtbaar in Adobe Campaign Standard. {#visibility-mobile-property}

1. Controleer of de Adobe Campaign Standard-extensie is geïnstalleerd in de mobiele eigenschap in de gebruikersinterface voor gegevensverzameling.

1. Verifieer dat de eindpunten van instantie correct in de uitbreiding worden gevormd.

1. Controleer of &#39;Launch_URL_Campaign&#39; of &#39;NmsServer_URL&#39; correct zijn.

1. Controleer vervolgens of de synchronisatie is voltooid met de **[!UICONTROL syncWithLaunch]** technische workflow.

## Hoe controleert u of de synchronisatie tussen Adobe Campaign en Tags in Adobe Experience Platform is voltooid? {#sync-campaign-launch}

1. Selecteer in Adobe Campaign Standard in het menu Geavanceerd de optie **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Open de **[!UICONTROL syncWithLaunch]** workflow.

1. Controleer of de workflow zonder fout is beëindigd.

1. Controleer in de logboeken of de workflowsynchronisatie is ingeschakeld en voltooid.

## Ik stel de sleutel voor een gevormde markering mobiele toepassing opnieuw in. Hoe te om keykey opnieuw in de Inzameling UI van Gegevens te vormen? {#configuring-pkey}

1. Open het mobiele bezit in de Inzameling UI van Gegevens.

1. Stel een nieuwe URL in de Adobe Campaign Standard-extensie in waarvoor de PKey opnieuw is ingesteld.

1. Sla het bestand op en synchroniseer de workflow.

1. Nadat de synchronisatie is voltooid, opent u de eigenschap mobile in de gebruikersinterface voor gegevensverzameling.

1. Stel de juiste URL in de Adobe Campaign Standard-extensie in waarvoor PKey opnieuw is ingesteld.

1. Sla het bestand op en laat de workflow opnieuw synchroniseren.

1. Alleen dan verschijnt de eigenschap in **[!UICONTROL Ready to Configure]** status in Adobe Campaign en kan nu worden geconfigureerd.

## Ik wil een mobiel bezit in Adobe Campaign vormen. Moet ik wachten tot de technische workflow synchroniseert tussen tags in Adobe Experience Platform en Adobe Campaign?

U kunt de workflow direct uitvoeren:

1. Selecteer in Adobe Campaign Standard in het menu Geavanceerd de optie **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Open de **[!UICONTROL syncWithLaunch]** workflow.

1. Klik op de knop **[!UICONTROL Scheduler]** activiteit en selecteer **[!UICONTROL Immediate execution]**.
