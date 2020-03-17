---
title: De integratie Campagne-Target configureren
description: Leer hoe u de integratie met Adobe Target configureert om dynamische inhoud te gebruiken in Adobe Campaign.
page-status-flag: never-activated
uuid: 0df5701c-dc26-4c30-9af9-ebf92815d90c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
discoiquuid: f7fb2084-dd6f-4aa2-940f-e48713146635
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# De integratie Campagne-Target configureren{#configuring-the-campaign-target-integration}

Dankzij de integratie tussen Adobe Campaign en Adobe Target kunt u dynamische inhoud in uw levering invoegen.

In Adobe Campaign is eerst een configuratie nodig om de integratiefuncties van Adobe Target te kunnen gebruiken. Deze configuratie moet door de functionele beheerder worden beheerd.

Voor deze procedure zijn de volgende elementen nodig:

* Een Adobe Experience Cloud-gebruiker
* Adobe Target-gebruiker
* Een Adobe Target-rawbox die is opgegeven om de verbinding met Adobe Campagne tot stand te brengen

1. Kies in het geavanceerde menu linksboven via het Adobe Campagne-logo **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.
1. Als u de server- en paderopties voor Adobe Target wilt configureren, vult u de volgende velden dienovereenkomstig in:

   * **[!UICONTROL TNT_TenantName]**: naam van de Adobe Target-gebruiker. Deze waarde komt overeen met de naam van Adobe Target **[!UICONTROL Client]**.
   * **[!UICONTROL TNT_EdgeServer]**: Adobe Target-server gebruikt voor integratie. Deze optie is al standaard beschikbaar. Deze waarde komt overeen met Adobe Target **[!UICONTROL Server Domain]**, gevolgd door de waarde **/m2** . Bijvoorbeeld: **tt.omtrdc.net/m2**.
   ![](assets/tar_options.png)

Uw gebruikers kunnen nu dynamische afbeeldingen in een levering toevoegen met Adobe Target.
