---
solution: Campaign Standard
product: campaign
title: Actieve profielen voor campagnes
description: Leer hoe u toegang krijgt tot maatgegevens van klanten en actieve profielen
feature: Profielen
role: Business Practitioner
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
source-git-commit: d2fcf2ca22bb5fe3632280f922dfed0972f6eb09
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 1%

---

# Metingen van klanten {#customer-metrics}

Functionele beheerders van campagnes hebben toegang tot het **[!UICONTROL Customer metrics]**-rapport van **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_active_profiles1.png)

Dit rapport wordt weergegeven:

* de Experience Cloud-id
* IMS-organisatie-id
* het aantal **actieve profielen**
* de lijst van doelmaten die in de zaak beschikbaar zijn

Dit rapport wordt elke maand geproduceerd door de **[!UICONTROL Billing]** technische werkschema.

## Actieve profielen{#active-profiles}

Volgens uw contract wordt elk van uw campagneexemplaren voorzien van een specifiek aantal actieve profielen. Raadpleeg de licentieovereenkomst voor informatie over het aantal aangeschafte actieve profielen.

>[!NOTE]
>
>Als Admin-gebruiker kunt u het aantal actieve profielen dat op uw instanties wordt gebruikt, ook rechtstreeks vanuit het Configuratiescherm controleren. Raadpleeg de [documentatie van het Configuratiescherm](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html) voor meer informatie.


Een &quot;Profiel&quot;is een verslag van informatie die een eindklant, vooruitzicht, of lood vertegenwoordigt. Profielen worden als **actief** beschouwd als zij door een levering van de Campagne binnen de afgelopen 12 maanden via om het even welk kanaal zijn gericht. Er wordt geen rekening gehouden met de profielen die tijdens de bereiding van de levering zijn uitgesloten (bijvoorbeeld naar typologische regels of quarantainemechanisme). Een profiel dat voor meerdere leveringen is bestemd, wordt slechts eenmaal meegeteld. Dit rapport is slechts informatief, het heeft geen directe invloed op het factureren.

![](assets/audience_active_profiles2.png)

Onder aan het rapport vindt u de lijst met actieve profielen voor elke doeldimensie. Het toont het aantal actieve profielen die tijdens de laatste 12 maanden rolperiode werden gericht.

* De bron **[!UICONTROL NmsRecipient]** bevat alle profielen waarmee contact is opgenomen via informatie uit het profiel Campaign Standard.

* De klant **[!UICONTROL anonymous]**-bron geeft het aantal profielen weer dat als doel is ingesteld met alleen een bepaald gegeven (e-mailadres, telefoonnummer), zonder dat dit verband houdt met het campagneprofiel.
