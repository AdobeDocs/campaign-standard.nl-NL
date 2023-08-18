---
title: Probleem met handtekening van bijgehouden URL's
description: Probleem met handtekening van bijgehouden URL's
hidefromtoc: true
hide: true
exl-id: 8c2725a8-2c3a-448a-8c04-c0c2a5950574
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 100%

---

# Probleem met handtekening van bijgehouden URL&#39;s {#tracked-urls}

Na recente wijzigingen kunnen door Campaign verzonden bijgehouden URL&#39;s mislukken. De impact van het probleem verschilt per e-mailaccount. Sommige bedrijven hebben namelijk specifieke beveiligingstools die verbindingen kunnen beïnvloeden en het URL-handtekeningmechanisme kunnen veranderen.

Adobe heeft daarom besloten het handtekeningmechanisme voor trackingkoppelingen uit te schakelen. Op deze manier worden alle trackingkoppelingen hersteld.

Afmeldkoppelingen kunnen net als andere koppelingen mislukken. De frequentie verschilt van host tot host, maar is minder dan 1%.

**Heeft dit gevolgen voor u?**

Dit heeft gevolgen voor sommige gebruikers van Campaign Standard aangezien het handtekeningmechanisme voor trackingkoppelingen in e-mails in oktober 2020 is geïntroduceerd in [Campaign Standard 20.4](release-notes-2020.md#release-20-4---october-2020) en standaard voor alle klanten is ingeschakeld.

**Hoe kan ik bijwerken?**

Adobe gaat binnenkort samen met u uw configuratie bijwerken. U ontvangt een e-mail met de tijdlijn van de upgrade.

**Wat is de impact?**

De uitvaltijd voor onderhoud bedraagt maximaal 25 minuten en tijdens deze periode werken alle verzendingen, trackingkoppelingen en API-aanroepen niet.

Zodra de update is uitgevoerd, werken alle koppelingen weer naar behoren.

>[!NOTE]
>
>Voor vragen over deze wijzigingen neemt u contact op met de [Adobe-klantenservice](https://helpx.adobe.com/nl/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).
>
