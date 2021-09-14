---
title: Overzicht van niet-bezorging
description: Met het overzicht van de Stuiteren uit-van-de-doos rapport, leer over de status van uw verzonden campagnes en fouten zij kunnen hebben ontmoet.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: bounceReport,main;campaignCirculationReport,main;programCirculationReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 03ea2f20-959c-497e-bd71-4e77132d712e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 1%

---

# Overzicht van niet-bezorging{#bounce-summary}

In dit rapport worden de algemene harde en zachte fouten beschreven die tijdens leveringen zijn aangetroffen, evenals de automatische verwerking van steunkleuren (zie [Inzicht in leveringsfouten](../../sending/using/understanding-delivery-failures.md)).

![](assets/campaign_reports_bounces.png)

Elke tabel wordt aangegeven met een overzichtsnummer en een overzicht van de diagrammen. U kunt wijzigen hoe de details worden weergegeven in de respectievelijke visualisatie-instellingen.

**Flop 5** repartitioneert de vijf leveringen met het hoogste aantal quarantines:

De **Bounce reason**-tabel bevat de beschikbare gegevens voor de typen fouten die stuitingen hebben veroorzaakt voor elke levering:

* **[!UICONTROL User unknown]**: Het type fout dat wordt gegenereerd wanneer een levering naar een ongeldig e-mailadres wordt verzonden.
* **[!UICONTROL Invalid domain]**: Het type fout dat wordt gegenereerd wanneer een levering wordt verzonden naar een e-mailadres waarvan het domein onjuist is of niet meer bestaat.
* **[!UICONTROL Unreachable]**: Het type van fout die in het koord van de berichtlevering wordt ontmoet, zoals domein tijdelijk onbereikbaar.
* **[!UICONTROL Account disabled]**: Het type fout dat wordt gegenereerd wanneer een levering wordt verzonden naar een e-mailadres dat niet meer bestaat.
* **[!UICONTROL Mailbox full]**: Het type fout dat wordt gegenereerd wanneer het Postvak IN van de ontvanger vol is. Er zijn vijf pogingen om het bericht te leveren alvorens deze fout wordt geproduceerd.
* **[!UICONTROL Not connected]**: Het type fout dat wordt gegenereerd wanneer de mobiele telefoon van de ontvanger is uitgeschakeld of wanneer de ontvanger niet is verbonden met een netwerk op het moment dat het bericht wordt verzonden.

   >[!NOTE]
   >
   >Dit type fout heeft alleen betrekking op leveringen op mobiele kanalen.

* **[!UICONTROL Refused]**: Het type van fout produceerde wanneer een adres door de dienstverlener van Internet (ISP) wordt geweigerd. Bijvoorbeeld, wanneer een veiligheidsregel door anti-Spam software is toegepast.

In de tabel **Domeinrepartitie** worden de algemene problemen weergegeven die tijdens de leveringen zijn ondervonden, afhankelijk van het ontvangende domein.
