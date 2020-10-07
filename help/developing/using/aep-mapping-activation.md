---
title: Toewijzingsactivering
description: Leer hoe u uw gegevenstoewijzing activeert
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 1%

---


# Toewijzingsactivering {#mapping-activation}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector bevindt zich momenteel in bèta, die vaak zonder voorafgaande kennisgeving kan worden bijgewerkt. Klanten moeten op Azure (momenteel alleen in bèta voor Noord-Amerika) worden gehost om toegang te krijgen tot deze mogelijkheden. Neem contact op met de klantenservice van Adobe als u toegang wilt.

Wanneer de toewijzingsdefinitie is voltooid, kunt u de toewijzing publiceren. Na de implementatiestap wordt de gegevensreplicatie tussen Campaign Standard en Adobe Experience Platform automatisch gestart. Op elk ogenblik, kunt u de replicatie tegenhouden door op de **[!UICONTROL Stop]** knoop te klikken.

Afhankelijk van uw toewijzingswijzigingen kunt u ervoor kiezen al uw records opnieuw naar Adobe Experience Platform te sturen.

![](assets/aep_publishmapping.png)

Van de plaatsingstegel, kunt u tot publicatielogboek en de uitvoerlogboeken toegang hebben.

![](assets/aep_publog.png)

Op het **[!UICONTROL Export jobs]** tabblad kunt u de exporttaak voor de gepubliceerde toewijzing controleren.

![](assets/aep_jobstatus.png)

Als u alle taken voor het exporteren van gegevens wilt controleren, gaat u naar **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** .

![](assets/aep_statusmapping.png)

Status van gegevensinvoer:

* **[!UICONTROL Created]**: Er wordt een gegevensinnametaak gemaakt en er worden gegevens ingevoerd.
* **[!UICONTROL Failed]**: Een gegevensinvoertaak is mislukt. Het redengebied beschrijft de reden voor de mislukking. Een fout kan tijdelijk of permanent zijn. In het geval van voorbijgaande mislukkingen, wordt een nieuwe innametaak gecreeerd na een gevormd interval. Als eerste stap aan het oplossen van problemen, kan de gebruiker het redengebied van de mislukking controleren. Als de reden een gebruiker aan Adobe Experience Platform UI opnieuw richt, kan de gebruiker login aan Adobe Experience Platform en de partijstatus in de dataset controleren om nauwkeurige mislukkingsreden te bepalen.
* **[!UICONTROL Uploaded]**: Er wordt eerst een batch gemaakt in Adobe Experience Platform en vervolgens worden gegevens aan de batch toegevoegd. In het veld Batch-id wordt de batch-id voor de batch weergegeven in Adobe Experience Platform. Adobe Experience Platform voert ook een postvalidatie uit op de batch. De batch wordt eerst gemarkeerd als geüpload totdat Adobe Experience Platform de stap voor na de validatie voltooit. Een baan houdt Adobe Experience Platform voor de status van de partij na het uploaden te pollen. Een batch kan worden uitgevoerd in Mislukt of in Successtatus na validatie in Adobe Experience Platform.
* **[!UICONTROL Success]**: Nadat een batch naar Adobe Experience Platform is geüpload, wordt de status van de taak (na validatie op het platform) gecontroleerd na een geconfigureerd interval. Een status &quot;Success&quot; stelde vast dat gegevens met succes werden ingevoerd in Adobe Experience Platform.
