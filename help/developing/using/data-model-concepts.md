---
title: Concepten van datamodellen
description: Leer meer over het datamodel van Adobe Campaign en hoe u dit kunt wijzigen.
audience: developing
content-type: reference
topic-tags: about-custom-resources
context-tags: cusResource,overview;eventCusResource,overview
feature: Data Model
role: Developer
level: Experienced
exl-id: 6e9e016a-473b-4a51-8bd6-c23c7b3d3610
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 79%

---

# Concepten van gegevensmodellen{#data-model-concepts}

Adobe Campaign bevat een vooraf gedefinieerd datamodel. Dit datamodel kan worden gewijzigd door [beheerders](../../administration/using/users-management.md#functional-administrators) die nieuwe bronnen of uitbreidingen aan bestaande bronnen kunnen toevoegen.

>[!CAUTION]
>
>Het maken en wijzigen van bronnen zijn gevoelige verrichtingen die alleen door deskundige gebruikers moeten worden uitgevoerd.

Via het menu **[!UICONTROL Administration]** > **[!UICONTROL Development]**, dat u kunt openen via het logo van Adobe Campaign, kunt u uw **aangepaste bronnen** beheren, **publiceren** en **toegang krijgen tot de diagnostische tools**.

De data die door Adobe Campaign worden gebruikt, zijn gedefinieerd via verschillende bronnen. U kunt **de bestaande datasjabloon verrijken** door uw eigen aangepaste bronnen te maken, zoals aankoop- of producttabellen.

Ingebouwde bronnen (zoals campagnes, e-mails of doelgroepen) kunnen niet worden gewijzigd. Maar aangepaste bronnen kunnen wel worden uitgebreid om nieuwe velden toe te voegen.

Extensievelden krijgen een voorvoegsel, zodat ze nooit een conflict veroorzaken met de ingebouwde velden.

>[!NOTE]
>
>U kunt een datamodel vertegenwoordiging voor de ingebouwde middelen in vinden [deze pagina](../../developing/using/datamodel-introduction.md).

U kunt [de schermnavigatie ook configureren](configuring-the-screen-definition.md) op basis van de bron die u hebt gemaakt.

Zo kunt u aangepaste bronnen **exporteren en importeren**, bijvoorbeeld van een ontwikkelings- naar een productieomgeving. Raadpleeg dit [stapsgewijze gebruiksscenario](../../automating/using/exporting-importing-custom-resources.md) voor meer informatie.

>[!CAUTION]
>
>Alleen functioneel [beheerders](../../administration/using/users-management.md#functional-administrators), met **[!UICONTROL Administration]** rol en toegang tot **Alles** eenheden hebben toegang tot verzendende logboeken, berichtenlogboeken, trackinglogboeken, uitsluitings- of abonnementlogboeken. Een gebruiker zonder beheerdersrechten kan zich richten op deze logbestanden, maar begint met een gekoppelde tabel (profielen, levering).
