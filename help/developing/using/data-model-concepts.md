---
solution: Campaign Standard
product: campaign
title: Concepten van datamodellen
description: Leer meer over het datamodel van Adobe Campaign en hoe u dit kunt wijzigen.
audience: developing
content-type: reference
topic-tags: about-custom-resources
context-tags: cusResource,overview;eventCusResource,overview
feature: Gegevensmodel
role: Ontwikkelaar
level: Ervaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 78%

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
>U kunt een datamodel vertegenwoordiging voor de ingebouwde middelen in [deze pagina](../../developing/using/datamodel-introduction.md) vinden.

U kunt [de schermnavigatie ook configureren](configuring-the-screen-definition.md) op basis van de bron die u hebt gemaakt.

Zo kunt u aangepaste bronnen **exporteren en importeren**, bijvoorbeeld van een ontwikkelings- naar een productieomgeving. Raadpleeg dit [stapsgewijze gebruiksscenario](../../automating/using/exporting-importing-custom-resources.md) voor meer informatie.

>[!CAUTION]
>
>Alleen functionele [beheerders](../../administration/using/users-management.md#functional-administrators), met **[!UICONTROL Administration]** rol en toegang tot **Alle** eenheden hebben toegang tot verzendende logboeken, berichtlogboeken, trackinglogboeken, uitsluitings- of abonnementlogboeken. Een gebruiker zonder beheerdersrechten kan zich richten op deze logbestanden, maar begint met een gekoppelde tabel (profielen, levering).
