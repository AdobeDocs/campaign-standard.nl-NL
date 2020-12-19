---
solution: Campaign Standard
product: campaign
title: Actieve profielen
description: U kunt tot een specifiek rapport over klantenmetriek toegang hebben en actieve profielen in uw gegevensbestand van de Campagne visualiseren.
audience: audiences
content-type: reference
topic-tags: managing-profiles
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 1%

---


# Actieve profielen{#active-profiles}

Adobe Campaign geeft een rapport weer waarin het aantal actieve profielen wordt weergegeven. Dit rapport is slechts informatief, het heeft geen directe invloed op het factureren. Alleen beheerders hebben toegang tot dit rapport onder **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_active_profiles1.png)

>[!NOTE]
>
>Als u op AWS wordt ontvangen en Campaign Standard van bouwstijl 10368 gebruikt, kunt u het aantal actieve profielen ook controleren die op uw instanties direct van het Controlebord worden gebruikt. Raadpleeg de [documentatie van het Configuratiescherm](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html) voor meer informatie.
>
>Merk op dat de metrische waarde van de Actieve profielen voor **Instanties van de Marketing** slechts beschikbaar en relevant is. Het is niet van toepassing noch beschikbaar voor uitvoeringsinstanties, die instanties MID (mid sourcing) en RT (Message Center/Real-time messaging) betekent.


Er wordt geen rekening gehouden met de profielen die tijdens de voorbereiding van de levering zijn uitgesloten (typologische regels, quarantaine, controlegroepen). Een profiel dat voor meerdere leveringen is bestemd, wordt slechts eenmaal meegeteld. Onder aan het rapport vindt u de lijst met actieve profielen voor elke doeldimensie.

Dit rapport wordt elke maand geproduceerd door de **[!UICONTROL Billing]** technische werkschema. Het bevat het aantal actieve profielen die tijdens de laatste 12 maanden rolperiode werden gericht.

Er wordt geen rekening gehouden met de profielen die tijdens de voorbereiding van de levering zijn uitgesloten (typologische regels, quarantaine). Bovendien wordt een profiel dat voor meerdere leveringen is bestemd, slechts eenmaal meegeteld.

![](assets/audience_active_profiles2.png)

Onder aan het rapport ziet u de lijst met actieve profielen die zijn verwerkt door de factureringsworkflow:

* De bron **[!UICONTROL NmsRecipient]** omvat alle klanten die met informatie van hun profiel van de Campaign Standard werden gecontacteerd.

* Klanten die alleen op basis van specifieke informatie (e-mailadres, telefoonnummer) zijn aangewezen, en die geen relatie hebben met hun campagneprofiel, vallen onder de **[!UICONTROL anonymous]**-bron.
