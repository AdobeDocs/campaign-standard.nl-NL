---
title: Over toegangsbeheer
description: Beheer uw Adobe Campaign-operatoren met behulp van rollen, groepen en organisatorische eenheden.
page-status-flag: never-activated
uuid: 4f538452-cc67-4e03-9e2f-2d9eecc081c7
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 54028f63-c9ca-4397-a079-e27e0cfdebf6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d0a0c59763af8babc9701206cc39fe41b98e0cd4
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 0%

---


# veelgestelde vragen over de technische workflow voor SyncWithLaunch {#syncwithlaunch-faq}

Met de **[!UICONTROL Sync with Launch]** workflow kunt u alle mobiele eigenschappen van Adobe Launch automatisch importeren in Adobe Campaign Standard.

Raadpleeg deze [pagina](../../administration/using/technical-workflows.md)voor meer informatie hierover.

>[!NOTE]
>
>U moet een ticket naar de klantenservice van Adobe verzenden (rechtstreeks of via uw Adobe-contactpersoon) om de **[!UICONTROL syncWithLaunch]** technische workflow in uw Campagne-instantie in te schakelen.

## Ik heb een eigenschap gemaakt in [!DNL Launch] (niet-admin van Org-unit ALL). Mijn toepassing is klaar om staat in Adobe Campaign te vormen maar ik kan het niet openen/vormen. {#configuring-property}

Alleen de beheerder van de organisatie ALL kan mobiele toepassingen configureren in Adobe Campaign Standard. Zodra gevormd, slechts kunnen de gebruikers van de toegewezen organisatorische eenheid de toepassing uitgeven. Raadpleeg deze [pagina](../../administration/using/organizational-units.md)voor meer informatie over de organisatie-eenheid.

## Ik kan een geconfigureerde mobiele toepassing niet bewerken in Adobe Campaign Standard en mobiele toepassingen zijn alleen-lezen. {#read-mode-mobile-app}

Controleer de organisatorische eenheid van de mobiele toepassing in de **[!UICONTROL Access Authorization ]** sectie. Alleen gebruikers van de toegewezen organisatie kunnen de mobiele toepassing bewerken.

Raadpleeg deze [pagina](../../administration/using/organizational-units.md)voor meer informatie over de organisatie-eenheid.

## Ik ben een beheerder met organisatie eenheid ALL in Adobe Campaign Standard maar ik kan mobiele toepassing niet vormen. {#org-unit-mobile}

Een beheerder met organisatie die aan ALLE wordt geplaatst zou rechten op alle mobiele eigenschappen moeten hebben binnen [!DNL Launch] om de mobiele toepassing te vormen.

Raadpleeg deze [pagina](../../administration/using/organizational-units.md)voor meer informatie over de organisatie-eenheid.

## Ik heb een eigenschap voor mobiele apparaten gemaakt in [!DNL Launch] maar mijn eigenschap is niet zichtbaar in Adobe Campaign Standard. {#visibility-mobile-property}

1. Controleer of de extensie Adobe Campaign Standard is geïnstalleerd in de eigenschap mobile in [!DNL Launch].

1. Verifieer dat de eindpunten van instantie correct in de uitbreiding worden gevormd.

1. Controleer of &#39;Launch_URL_Campaign&#39; of &#39;NmsServer_URL&#39; correct zijn.

1. Controleer vervolgens of de synchronisatie tussen [!DNL Launch] en Adobe Campaign is voltooid met de **[!UICONTROL syncWithLaunch]** technische workflow.

## Hoe controleert u of de synchronisatie tussen Adobe Campaign en Launch is voltooid? {#sync-campaign-launch}

1. Kies in Adobe Campaign Standard in het menu Geavanceerd **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

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

1. Alleen dan wordt de eigenschap in **[!UICONTROL Ready to Configure]** status weergegeven in Adobe Campaign en kan deze nu worden geconfigureerd.

## Ik wil een eigenschap voor mobiele apparaten configureren in Adobe Campaign. Moet ik wachten tot de technische workflow synchroniseert tussen Adobe Launch en Adobe Campaign?

U kunt de workflow direct uitvoeren:

1. Kies in Adobe Campaign Standard in het menu Geavanceerd **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Open de **[!UICONTROL syncWithLaunch]** workflow.

1. Klik op de **[!UICONTROL Scheduler]** activiteit en selecteer **[!UICONTROL Immediate execution]**.
