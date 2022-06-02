---
title: Vroege aanvullende informatie
description: Vroege aanvullende informatie
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 75bc042701ac29d2e525884dc929063147c1cdce
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 37%

---

# Vroege aanvullende informatie {#new-release}

Op deze pagina worden nieuwe functies, verbeteringen en oplossingen beschreven die in de volgende release van Campaign Standard zijn opgenomen.

>[!CAUTION]
>
> Deze content kan zonder voorafgaande kennisgeving worden gewijzigd tot de upgradedatum van de werkgebiedomgevingen. Meer informatie vindt u op de [releaseplanningspagina](../../rn/using/release-planning.md).

## Release 22.2 - juni 2022 {#rn-2022}

**Verbetering**

* **Adobe Notification Service** - Campaign wordt geleverd met Adobe Notification Service waarmee Experience Cloud-oplossingen gebruikers in Experience Cloud kunnen waarschuwen voor activiteiten die belangrijk voor hen zijn om te weten. Vanaf versie 22.2 is de gebruikerservaring verbeterd: meldingen krijgen prioriteit en productgegenereerde meldingen zijn gescheiden van Adobe-statusaankondigingen. Wanneer de notificatie naar een specifieke workflow verwijst, kunt u de bijbehorende workflow nu bovendien rechtstreeks openen via de e-mail of het bericht in het product.  Voor meer informatie over Adobe Campaign-notificaties raadpleegt u [Adobe Campaign-notificaties](../../administration/using/sending-internal-notifications.md).

* **Optimalisatie bij opstarten van workflow** - Adobe heeft een nieuwe functie toegevoegd die het aantal werkstromen kan afstemmen die rond dezelfde tijd beginnen. Dit zou helpen cpu pieken verhinderen die tot de dienstonderbrekingen of onderbreking konden leiden. Adobe zou het na 22.2 versie toelaten. Er is geen verder actiepunt voor de klant met betrekking tot hetzelfde.

**Beveiligingsupgrade**

* Apache Tomcat is geüpgraded van versie 7 naar versie 8.5.

**Patches**

* Probleem opgelost met betrekking tot de technische workflow voor facturering als gevolg van een dubbele toetsfout. (CAMP-51029)
* De ontbrekende Microsoft Edge-browsercategorie is toegevoegd bij het bijhouden van rapporten. Ze waren eerder gecategoriseerd met Microsoft Chrome wordt geopend. (CAMP-51165)
* Probleem verholpen met GDPR-verzoeken die geen gegevens uit onderliggende tabellen verwijderen. (CAMP-48276)
* Probleem verholpen in de e-mailontwerper die ertoe leidde dat de zichtbaarheidsvoorwaarde van een fragment niet werd opgeslagen in een transactiemalplaatje voor berichten. (CAMP-50338)
* Probleem verholpen in campagnerapporten waarbij geen rekening werd gehouden met het datumbereik. (CAMP-50991)
* Probleem verholpen waarbij geplande e-mailberichten mislukten: de leveringanalyse kon niet worden gestart omdat de levering nog steeds de status &#39;Opnieuw in behandeling&#39; had. (CAMP-50302)
* Probleem verholpen in de e-mailontwerper tijdens het voorvertonen van een e-mailbericht met een vervangend profiel. (CAMP-49312)
* Probleem verholpen met lege waarde in aangepaste opsommingen: Wanneer u een aangepaste bron maakt met een veld dat een tekstopsomming is en slechts één waarde bevat, wordt deze waarde standaard ingesteld, zodat u een query voor dit veld kunt maken als een eenvoudige aanvraag. (CAMP-50606)
