---
title: Concepten van gegevensmodellen
description: Leer meer over het gegevensmodel van de Campagne van Adobe en hoe te om het te wijzigen.
page-status-flag: never-activated
uuid: cacd563f-6936-4b3e-83e3-5d4ae31d44e8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 4e0468da-3052-4ce5-8174-45aba1f5c4ed
context-tags: cusResource,overview;eventCusResource,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

---


# Concepten van gegevensmodellen{#data-model-concepts}

Adobe Campagne wordt geleverd met een vooraf gedefinieerd gegevensmodel. Dit gegevensmodel kan worden gewijzigd door [beheerders](../../administration/using/users-management.md#functional-administrators) die nieuwe middelen of uitbreidingen aan bestaande middelen kunnen toevoegen.

>[!CAUTION]
>
>Het creëren van en het wijzigen van middelen zijn gevoelige verrichtingen die door deskundige slechts gebruikers moeten worden uitgevoerd.

Via het menu **[!UICONTROL Administration]** > **[!UICONTROL Development]** , dat u kunt openen via het logo van Adobe Campagne, kunt u uw **aangepaste bronnen** beheren, **publiceren** en **toegang krijgen tot de diagnostische gereedschappen**.

De gegevens die door Adobe Campaign worden gebruikt, worden via verschillende bronnen gedefinieerd. U kunt het gegevensmalplaatje **** verrijken dat door uw eigen douanemiddelen, zoals aankoop of productlijsten wordt verstrekt te creëren.

Ingebouwde bronnen (zoals campagnes, e-mails of publiek) kunnen niet worden gewijzigd. Aangepaste bronnen kunnen echter worden uitgebreid om nieuwe velden toe te voegen.

Extensievelden worden gegenereerd met een voorvoegsel, zodat ze nooit een conflict veroorzaken met de ingebouwde velden.

>[!NOTE]
>
>U kunt een datamodel-vertegenwoordiging voor de ingebouwde middelen in [deze pagina](../../developing/using/datamodel-introduction.md)vinden.

U kunt de navigatie [in de schermen ook](configuring-the-screen-definition.md) vormen die aan het gecreeerde middel beantwoorden.

Het is mogelijk aangepaste bronnen te **exporteren en te importeren** , bijvoorbeeld van een ontwikkeling naar een productieomgeving. Raadpleeg deze [stapsgewijze gebruiksaanwijzing](../../automating/using/exporting-importing-custom-resources.md)voor meer informatie.
