---
title: Concepten van datamodellen
description: Leer meer over het datamodel van Adobe Campaign en hoe u dit kunt wijzigen.
page-status-flag: never-activated
uuid: cacd563f-6936-4b3e-83e3-5d4ae31d44e8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 4e0468da-3052-4ce5-8174-45aba1f5c4ed
context-tags: cusResource,overview;eventCusResource,overview
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 84%

---


# Concepten van datamodellen{#data-model-concepts}

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
>Op [deze pagina](../../developing/using/datamodel-introduction.md) ziet u een voorbeeld van een datamodel voor ingebouwde bronnen.

U kunt [de schermnavigatie ook configureren](configuring-the-screen-definition.md) op basis van de bron die u hebt gemaakt.

Zo kunt u aangepaste bronnen **exporteren en importeren**, bijvoorbeeld van een ontwikkelings- naar een productieomgeving. Raadpleeg dit [stapsgewijze gebruiksscenario](../../automating/using/exporting-importing-custom-resources.md) voor meer informatie.

>[!CAUTION]
>
>Alleen functionele [beheerders](../../administration/using/users-management.md#functional-administrators)met **[!UICONTROL Administration]** rol en toegang tot **alle** eenheden hebben toegang tot verzendende logboeken, berichtlogbestanden, trackinglogboeken, uitsluitings- of abonnementlogbestanden. Een gebruiker zonder beheerdersrechten kan zich richten op deze logbestanden, maar begint met een gekoppelde tabel (profielen, levering).
