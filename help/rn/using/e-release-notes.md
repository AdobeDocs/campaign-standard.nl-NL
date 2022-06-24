---
title: Vroege aanvullende informatie
description: Vroege aanvullende informatie
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 66aed3668dc0eb2041312dcbaebe7c36f54b13a5
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---

# Vroege aanvullende informatie {#new-release}

Op deze pagina worden nieuwe functies, verbeteringen en oplossingen beschreven die in de volgende release van Campaign Standard zijn opgenomen.

>[!CAUTION]
>
> Deze content kan zonder voorafgaande kennisgeving worden gewijzigd tot de upgradedatum van de werkgebiedomgevingen. Meer informatie vindt u op de [releaseplanningspagina](../../rn/using/release-planning.md).

## Release 22.2 - juni 2022 {#rn-2022}

**Verbeteringen**

* **Adobe Notification Service** - Campaign wordt geleverd met Adobe Notification Service waarmee Experience Cloud-oplossingen gebruikers in Experience Cloud kunnen waarschuwen voor activiteiten die belangrijk voor hen zijn om te weten. Vanaf versie 22.2 is de gebruikerservaring verbeterd: meldingen krijgen prioriteit en productgegenereerde meldingen zijn gescheiden van Adobe-statusaankondigingen. Wanneer de notificatie naar een specifieke workflow verwijst, kunt u de bijbehorende workflow nu bovendien rechtstreeks openen via de e-mail of het bericht in het product.  Voor meer informatie over Adobe Campaign-notificaties raadpleegt u [Adobe Campaign-notificaties](../../administration/using/sending-internal-notifications.md).

* **Optimalisatie bij het opstarten van workflows** - Adobe heeft een nieuwe mogelijkheid toegevoegd waarmee het aantal workflows dat rond dezelfde tijd begint, kan worden aangepast. Dit zou CPU-pieken helpen voorkomen die tot serviceonderbrekingen of downtime hadden kunnen leiden. Adobe zou dit inschakelen na de release van 22.2. Er is geen verder actiepunt over de klant met betrekking tot hetzelfde.

* **Toegankelijkheid** - Adobe heeft veel toegankelijkheidsoplossingen gemaakt om het algemene gebruiksgemak van de applicatie te verbeteren. Deze functies zijn momenteel alleen ingeschakeld voor een aantal early adopters en ze zullen in de ACS 22.3-release naar alle klanten worden uitgerold. Voorbeelden van toegankelijkheidsverbeteringen zijn:

   * Ervoor zorgen dat er een zichtbare focusindicator is voor focusbare elementen op elk scherm
   * Paginaoriëntatiepunten maken voor eenvoudigere navigatie
   * De naam, rol, waarde en status toevoegen voor veel besturingselementen
   * Problemen met dynamische focusvolgorde op hoofdschermen corrigeren


**Patches**

* Er is een probleem opgelost met de technische workflow voor facturering vanwege een dubbele-sleutelfout. (CAMP-51029)
* De ontbrekende Microsoft Edge-browsercategorie is toegevoegd aan trackingrapporten. Ze waren eerder gecategoriseerd met Microsoft Chrome geopend. (CAMP-51165)
* Er is een probleem opgelost met AVG-verzoeken waarbij geen gegevens uit onderliggende tabellen werden verwijderd. (CAMP-48276)
* Er is een probleem opgelost in de e-mailontwerper waardoor de zichtbaarheidsvoorwaarde van een fragment niet werd opgeslagen in een sjabloon voor transactiebericht. (CAMP-50338)
* Er is een probleem opgelost in Campaign-rapporten waardoor geen rekening werd gehouden met het datumbereik. (CAMP-50991)
* Er is een fout verholpen waardoor geplande e-mails mislukten: de bezorgingsanalyse kon niet starten omdat de bezorging nog steeds de status &#39;Opnieuw in behandeling&#39; had. (CAMP-50302)
* Er is een probleem opgelost in de e-mailontwerper bij het bekijken van een voorbeeld van een e-mail met een profielvervanging. (CAMP-49312)
* Er is een probleem opgelost met lege waarde in aangepaste opsommingen: bij het maken van een aangepaste bron met een veld dat een tekstopsomming is en slechts één waarde bevat, wordt deze waarde nu standaard ingesteld, zodat u een query op dit veld kunt maken als een eenvoudig verzoek. (CAMP-50606)
