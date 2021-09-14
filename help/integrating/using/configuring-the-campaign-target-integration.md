---
title: De integratie van Campaign-Target configureren
description: Leer hoe u de Adobe Target-integratie configureert om dynamische inhoud te gaan gebruiken in Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: d382bfdd-418d-46c1-98dd-df8626f85cac
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 4%

---

# De integratie van Campaign-Target configureren{#configuring-the-campaign-target-integration}

Dankzij de integratie tussen Adobe Campaign en Adobe Target kunt u dynamische inhoud in uw levering invoegen.

Een configuratie is eerst nodig in Adobe Campaign om de integratiefuncties met Adobe Target te kunnen gebruiken en moet worden beheerd door de functionele beheerder.

Voor deze procedure zijn de volgende elementen nodig:

* Een Adobe Experience Cloud-huurder
* Een Adobe Target-huurder
* Een Adobe Target-vak opgegeven voor het tot stand brengen van de verbinding met Adobe Campaign

1. Selecteer **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** in het geavanceerde menu via het Adobe Campaign-logo in de linkerbovenhoek.
1. Als u de server- en paderopties voor Adobe Target wilt configureren, vult u de volgende velden dienovereenkomstig in:

   * **[!UICONTROL TNT_TenantName]**: naam van de Adobe Target-huurder. Deze waarde komt overeen met de naam van de Adobe Target **[!UICONTROL Client]**.
   * **[!UICONTROL TNT_EdgeServer]**: Adobe Target-server gebruikt voor integratie. Deze optie is al standaard beschikbaar. Deze waarde komt overeen met de Adobe Target **[!UICONTROL Server Domain]**, gevolgd door de waarde **/m2**. Bijvoorbeeld: **tt.omtrdc.net/m2**.

   ![](assets/tar_options.png)

Uw gebruikers kunnen nu dynamische afbeeldingen toevoegen in een levering met Adobe Target.
