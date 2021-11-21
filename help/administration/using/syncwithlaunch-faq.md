---
title: Synchroniseren met veelgestelde vragen over technische workflow starten
description: Algemene vragen over de technische workflow van Starten.
audience: administration
content-type: reference
topic-tags: users-and-security
feature: Instance Settings
role: Admin
level: Experienced
exl-id: aaaceb3a-5e54-47da-9be4-b70747282830
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 0%

---

# Veelgestelde vragen over de synchronisatie van Adobe Launch {#syncwithlaunch-faq}

U kunt Adobe Launch mobile-eigenschappen importeren in Adobe Campaign Standard via het dialoogvenster **[!UICONTROL Sync with Launch]** specifieke technische workflow. Raadpleeg deze voor meer informatie [page](../../administration/using/technical-workflows.md)

In de onderstaande sectie worden veelgestelde vragen over deze synchronisatie weergegeven.

## Ik heb een eigenschap gemaakt in [!DNL Launch] (niet-beheerder van Org-unit ALL). Mijn toepassing is klaar om staat in Adobe Campaign te vormen maar ik kan het niet openen/vormen. {#configuring-property}

Alleen de beheerder van de organisatie ALL kan mobiele toepassingen configureren in Adobe Campaign Standard. Zodra gevormd, slechts kunnen de gebruikers van de toegewezen organisatorische eenheid de toepassing uitgeven. Raadpleeg voor meer informatie over de organisatorische eenheid [page](../../administration/using/organizational-units.md).

## Ik kan een geconfigureerde mobiele toepassing niet bewerken in Adobe Campaign Standard en mobiele toepassingen zijn alleen-lezen. {#read-mode-mobile-app}

Controleer de organisatorische eenheid van de mobiele toepassing in **[!UICONTROL Access Authorization]** sectie. Alleen gebruikers van de toegewezen organisatie kunnen de mobiele toepassing bewerken.

Raadpleeg voor meer informatie over de organisatorische eenheid [page](../../administration/using/organizational-units.md).

## Ik ben een beheerder met organisatie eenheid ALL in Adobe Campaign Standard maar ik kan mobiele toepassing niet vormen. {#org-unit-mobile}

Een beheerder met een organisatie-eenheid ingesteld op ALL moet rechten hebben op alle mobiele eigenschappen in [!DNL Launch] om de mobiele toepassing te configureren.

Raadpleeg voor meer informatie over de organisatorische eenheid [page](../../administration/using/organizational-units.md).

## Ik heb een mobiele eigenschap gemaakt in [!DNL Launch] maar mijn eigenschap is niet zichtbaar in Adobe Campaign Standard. {#visibility-mobile-property}

1. Controleer of de extensie Adobe Campaign Standard is geïnstalleerd in de eigenschap mobile in [!DNL Launch].

1. Verifieer dat de eindpunten van instantie correct in de uitbreiding worden gevormd.

1. Controleer of &#39;Launch_URL_Campaign&#39; of &#39;NmsServer_URL&#39; correct zijn.

1. Controleer vervolgens of de synchronisatie tussen [!DNL Launch] en Adobe Campaign is voltooid met de **[!UICONTROL syncWithLaunch]** technische workflow.

## Hoe controleert u of de synchronisatie tussen Adobe Campaign en Launch is voltooid? {#sync-campaign-launch}

1. Selecteer in Adobe Campaign Standard in het menu Geavanceerd de optie **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Open de **[!UICONTROL syncWithLaunch]** workflow.

1. Controleer of de workflow zonder fout is beëindigd.

1. Controleer in de logboeken of de workflowsynchronisatie is ingeschakeld en voltooid.

## Ik stel de sleutel voor een gevormde mobiele toepassing in Lancering terug. Hoe te om pkey opnieuw in Lancering te vormen? {#configuring-pkey}

1. Open de eigenschap mobile in Adobe Launch.

1. Stel een nieuwe URL in de Adobe Campaign Standard-extensie in waarvoor de PKey opnieuw is ingesteld.

1. Sla het bestand op en laat de workflow synchroniseren tussen Adobe Campaign en [!DNL Launch].

1. Nadat de synchronisatie is voltooid, opent u de eigenschap mobile in [!DNL Launch].

1. Stel de juiste URL in de Adobe Campaign Standard-extensie in waarvoor PKey opnieuw is ingesteld.

1. Sla het bestand op en laat de workflow opnieuw synchroniseren.

1. Alleen dan verschijnt de eigenschap in **[!UICONTROL Ready to Configure]** status in Adobe Campaign en kan nu worden geconfigureerd.

## Ik wil een eigenschap voor mobiele apparaten configureren in Adobe Campaign. Moet ik wachten tot de technische workflow synchroniseert tussen Adobe Launch en Adobe Campaign?

U kunt de workflow direct uitvoeren:

1. Selecteer in Adobe Campaign Standard in het menu Geavanceerd de optie **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Open de **[!UICONTROL syncWithLaunch]** workflow.

1. Klik op de knop **[!UICONTROL Scheduler]** activiteit en selecteer **[!UICONTROL Immediate execution]**.
