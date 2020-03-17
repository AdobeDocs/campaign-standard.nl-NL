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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5f3bf4c2d0bba095182194ac28b3107eae2c54a6

---


# Toewijzingsactivering {#mapping-activation}

>[!IMPORTANT]
>
>De dienst van de Gegevens van de Standaard van de campagne is momenteel in bèta, die aan regelmatige updates zonder bericht kan worden onderworpen. Klanten moeten op Azure (momenteel alleen in bèta voor Noord-Amerika) worden gehost om toegang te krijgen tot deze mogelijkheden. Neem contact op met de klantenservice van Adobe als u toegang wilt.

Wanneer de toewijzingsdefinitie is voltooid, kunt u de toewijzing publiceren. Na de implementatiestap wordt de gegevensreplicatie tussen Campagnestandaard en Adobe Experience Platform automatisch gestart. Op elk ogenblik, kunt u de replicatie tegenhouden door op de **[!UICONTROL Stop]** knoop te klikken.

Afhankelijk van uw toewijzingswijzigingen kunt u ervoor kiezen al uw records opnieuw te verzenden naar het Adobe Experience Platform.

![](assets/aep_publishmapping.png)

Van de plaatsingstegel, kunt u tot publicatielogboek en de uitvoerlogboeken toegang hebben.

![](assets/aep_publog.png)

Op het **[!UICONTROL Export jobs]** tabblad kunt u de exporttaak voor de gepubliceerde toewijzing controleren.

![](assets/aep_jobstatus.png)

Als u alle taken voor het exporteren van gegevens wilt controleren, gaat u naar **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** .

![](assets/aep_statusmapping.png)

Status van gegevensinvoer:

* **[!UICONTROL Created]**: Er wordt een gegevensinnametaak gemaakt en er worden gegevens ingevoerd.
* **[!UICONTROL Failed]**: Een gegevensinvoertaak is mislukt. Het redengebied beschrijft de reden voor de mislukking. Een fout kan tijdelijk of permanent zijn. In het geval van voorbijgaande mislukkingen, wordt een nieuwe innametaak gecreeerd na een gevormd interval. Als eerste stap aan het oplossen van problemen, kan de gebruiker het redengebied van de mislukking controleren. Als de reden een gebruiker omleidt naar de gebruikersinterface van het Adobe Experience Platform, kan de gebruiker zich aanmelden bij het Adobe Experience Platform en de batchstatus in de gegevensset controleren om de exacte reden voor de fout te bepalen.
* **[!UICONTROL Uploaded]**: Er wordt eerst een batch gemaakt in het Adobe Experience Platform en er worden vervolgens gegevens in de batch ingevoerd. In het veld Batch-id wordt de batch-id voor de batch weergegeven in het Adobe Experience Platform. Adobe Experience Platform voert ook een postvalidatie uit op de batch. De batch wordt eerst gemarkeerd als geüpload totdat Adobe Experience Platform de stap voor de validatie na de validatie heeft voltooid. Een taak houdt het opiniepeilen van het Platform van de Ervaring voor de status van de partij na het uploaden. Een batch kan worden uitgevoerd in Niet geslaagd of in Successtatus na validatie in het Adobe Experience Platform.
* **[!UICONTROL Success]**: Nadat een batch naar het Adobe Experience Platform is geüpload, wordt de status van de taak (na validatie op het platform) gecontroleerd na een geconfigureerd interval. Met de status &quot;Success&quot; is vastgesteld dat gegevens met succes zijn ingevoerd in het Adobe Experience Platform.
