---
solution: Campaign Standard
product: campaign
title: Informatie over opt-in en opt-out in Campaign
description: Uitschakelen heeft tot gevolg dat een profiel niet langer wordt gericht op levering of op leveringen van een specifiek kanaal.
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Beginner
exl-id: ccb35aeb-2b32-4444-969b-50021111a0d6
source-git-commit: 6b293db5bc8f299a3237aa83c003339f0e697c6f
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 9%

---

# Informatie over opt-in en opt-out in Campaign{#about-opt-in-and-opt-out-in-campaign}

Uitschakelen heeft tot gevolg dat een profiel niet langer wordt gericht op levering of op leveringen van een specifiek kanaal.

Als u profielen de mogelijkheid wilt geven om in of uit te schakelen, moet u een specifieke bestemmingspagina maken. Raadpleeg [Optie-in- en opt-out-bestemmingspagina&#39;s instellen](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages) voor meer informatie.

Profielen kunnen ook handmatig door een operator worden in- of uitgeschakeld. Raadpleeg [Optie-in en opt-out beheren van een profiel](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile) voor meer informatie.

Opt-outprofielen worden automatisch uitgesloten tijdens de leveringsanalyse om leveringen te versnellen (het foutenpercentage heeft een significant effect op leveringssnelheid).

>[!NOTE]
>
>Uitschakelen is van toepassing op **Profielen**, in tegenstelling tot quarantaine die is gekoppeld aan een **e-mailadres** of **telefoonnummer**. Als u een profiel uitschakelt, worden dus alle adressen waaraan het profiel is gekoppeld, van de levering uitgesloten. Als een gebruiker echter twee profielen in de database heeft, worden de leveringen nog steeds op hem gericht, omdat slechts een van zijn profielen is uitgeschakeld. Om ervoor te zorgen al zijn adressen worden uitgesloten, voeg hen aan de quarantined adressen toe. Raadpleeg [deze pagina](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform) voor meer informatie.

Raadpleeg [deze pagina](../../audiences/using/about-subscriptions.md) voor meer informatie over abonnementen op services.
