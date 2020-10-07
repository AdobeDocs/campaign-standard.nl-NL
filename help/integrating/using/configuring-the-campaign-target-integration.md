---
title: De integratie van Campaign en Target configureren
description: Leer hoe u de Adobe Target-integratie configureert om dynamische inhoud te gaan gebruiken in Adobe Campaign.
page-status-flag: never-activated
uuid: 0df5701c-dc26-4c30-9af9-ebf92815d90c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
discoiquuid: f7fb2084-dd6f-4aa2-940f-e48713146635
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 4%

---


# De integratie van Campaign en Target configureren{#configuring-the-campaign-target-integration}

Dankzij de integratie tussen Adobe Campaign en Adobe Target kunt u dynamische inhoud in uw levering invoegen.

Een configuratie is eerst nodig in Adobe Campaign om de integratiefuncties met Adobe Target te kunnen gebruiken en moet worden beheerd door de functionele beheerder.

Voor deze procedure zijn de volgende elementen nodig:

* Een Adobe Experience Cloud-huurder
* Een Adobe Target-huurder
* Een Adobe Target-vak opgegeven voor het tot stand brengen van de verbinding met Adobe Campaign

1. Selecteer in het geavanceerde menu via het Adobe Campaign-logo in de linkerbovenhoek **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.
1. Als u de server- en paderopties voor Adobe Target wilt configureren, vult u de volgende velden dienovereenkomstig in:

   * **[!UICONTROL TNT_TenantName]**: naam van de Adobe Target-huurder. Deze waarde komt overeen met de naam van de Adobe Target **[!UICONTROL Client]**.
   * **[!UICONTROL TNT_EdgeServer]**: Adobe Target-server gebruikt voor integratie. Deze optie is al standaard beschikbaar. Deze waarde komt overeen met de Adobe Target **[!UICONTROL Server Domain]**, gevolgd door de waarde **/m2** . Bijvoorbeeld: **tt.omtrdc.net/m2**.

   ![](assets/tar_options.png)

Uw gebruikers kunnen nu dynamische afbeeldingen toevoegen in een levering met Adobe Target.
