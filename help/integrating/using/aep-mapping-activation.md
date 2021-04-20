---
solution: Campaign Standard
product: campaign
title: Toewijzingsactivering
description: Leer hoe u uw gegevenstoewijzing activeert
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 0%

---


# Toewijzingsactivering {#mapping-activation}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector bevindt zich momenteel in bèta, die vaak zonder voorafgaande kennisgeving kan worden bijgewerkt. Klanten moeten op Azure (momenteel alleen in bèta voor Noord-Amerika) worden gehost om toegang te krijgen tot deze mogelijkheden. Neem contact op met de klantenservice van Adobe als u toegang wilt.

Wanneer de toewijzingsdefinitie is voltooid, kunt u de toewijzing publiceren. Na de implementatiestap wordt de gegevensreplicatie tussen Campaign Standard en Adobe Experience Platform automatisch gestart. Op elk ogenblik, kunt u de replicatie tegenhouden door op **[!UICONTROL Stop]** knoop te klikken.

Afhankelijk van uw toewijzingswijzigingen kunt u ervoor kiezen al uw records opnieuw naar Adobe Experience Platform te sturen.

![](assets/aep_publishmapping.png)

Van de plaatsingstegel, kunt u tot publicatielogboek en de uitvoerlogboeken toegang hebben.

![](assets/aep_publog.png)

Op het tabblad **[!UICONTROL Export jobs]** kunt u de exporttaak voor de gepubliceerde toewijzing controleren.

![](assets/aep_jobstatus.png)

Als u alle taken voor gegevensexport wilt controleren, gaat u naar **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** menu.

![](assets/aep_statusmapping.png)

De statussen van gegevensinvoer zijn:

* **[!UICONTROL Created]**: Er wordt een gegevensinnametaak gemaakt en er worden gegevens ingevoerd.
* **[!UICONTROL Failed]**: Een gegevensinvoertaak is mislukt. Het redengebied beschrijft de reden voor de mislukking. Een fout kan tijdelijk of permanent zijn. In het geval van voorbijgaande mislukkingen, wordt een nieuwe innametaak gecreeerd na een gevormd interval. Als eerste stap aan het oplossen van problemen, kan de gebruiker het redengebied van de mislukking controleren. Als de reden een gebruiker aan Adobe Experience Platform UI opnieuw richt, kan de gebruiker login aan Adobe Experience Platform en de partijstatus in de dataset controleren om nauwkeurige mislukkingsreden te bepalen.
* **[!UICONTROL Uploaded]**: Er wordt eerst een batch gemaakt in Adobe Experience Platform en vervolgens worden gegevens aan de batch toegevoegd. In het veld Batch-id wordt de batch-id voor de batch weergegeven in Adobe Experience Platform. Adobe Experience Platform voert ook een postvalidatie uit op de batch. De batch wordt eerst gemarkeerd als geüpload totdat Adobe Experience Platform de stap voor na de validatie voltooit. Een baan houdt Adobe Experience Platform voor de status van de partij na het uploaden te pollen. Een batch kan worden uitgevoerd in Mislukt of in Successtatus na validatie in Adobe Experience Platform.
* **[!UICONTROL Success]**: Nadat een batch naar Adobe Experience Platform is geüpload, wordt de status van de taak (na validatie op het platform) gecontroleerd na een geconfigureerd interval. Een status &quot;Success&quot; stelde vast dat gegevens met succes werden ingevoerd in Adobe Experience Platform.

In sommige gevallen krijgt u de onderstaande validatiefout bij het publiceren van uw toewijzing.

![](assets/aep_datamapping_ccpa.png)

Dit gebeurt wanneer het XDM-schema dat u gebruikt, niet is bijgewerkt met het nieuwste XDM-veld voor privacybeheer en nog steeds het vervangen XDM-veld &quot;ccpa&quot; bevat.

Ga als volgt te werk om het XDM-schema bij te werken:

1. Ga naar de dataset op Adobe Experience Platform gebruikend de verbinding aanwezig op de XDM toewijzingspagina.

1. Navigeer naar uw XDM-schema.

1. Voeg de **[!UICONTROL Profile Privacy]** mix aan het schema toe.

   ![](assets/aep_datamapping_privacyfield.png)

1. Sla het schema op en publiceer de toewijzing opnieuw. De publicatie moet nu overgaan.

   ![](assets/aep_save_mapping.png)
