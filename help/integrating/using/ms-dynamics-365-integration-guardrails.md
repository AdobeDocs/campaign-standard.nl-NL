---
solution: Campaign Standard
product: campaign
title: Integratiehandleidingen voor Microsoft Dynamics 365
description: Microsoft Dynamics 365 met Campaign Standard-integratiehandleidingen
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---


# Integratiegrenzen

## Integratiehandleidingen

Bij het gebruik van deze integratie moet rekening worden gehouden met de volgende instructies. Neem contact op met uw technische vertegenwoordiger van Adobe als u denkt dat u deze instructies overschrijdt.

* U zult het juiste pakket van de Campagne moeten vergunning geven om het ACS motorvraagvolume te steunen dat door de integratie wordt geproduceerd. Het overschrijden van het gelicentieerde aanroepvolume van de motor kan een verslechtering van de campagneprestaties veroorzaken.

   Gebruik het volgende om te helpen het volume van de motorvraag van de integratie schatten:

   * Record wordt ingevoegd (d.w.z. nieuwe record): 1 motoraanroep
   * Opnemen verwijdert: 1 motoraanroep
   * Updates opnemen: 2 motorvraag (slechts 1 vraag als het bestemmingsverslag identiek aan het bronverslag is - d.w.z., als geen verandering in het ACS- verslag)

   Bij het schatten van het totale ACS motorvraagvolume, is het belangrijk om in andere bronnen van motorvraag, met inbegrip van het landen van pagina&#39;s, WebApps, JSSP, APIs, mobiele toepassingsregistraties, enz. rekening te houden.

   Informatie over het pakket Campagne hier weergeven: https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html

* De integratie ondersteunt maximaal 30 miljoen contacten.

* De standaard integratieaanbieding omvat ondersteuning voor maximaal vijf aangepaste entiteiten

* Aangepaste entiteiten met meer dan 500 k records hebben extra consultinguren nodig om een eenmalige (per aangepaste entiteit) eerste op bestanden gebaseerde import uit te voeren via de campagneworkflow (wat extra kosten met zich meebrengt)

* De standaard integratieaanbieding omvat steun voor douaneentiteiten tot 50 kolommen in grootte.

* U moet uw aangepaste bronnen maken en publiceren voordat u de integratie kunt implementeren.

* De maximale tabeldiepte bij het koppelen van tabellen is twee (tabel1->table2->table3)

* Er is beperkte ondersteuning voor dynamische 365 gegevenstypen. Als uw gegevensmodel een gegevenstype buiten eenvoudige gegevenstypes (b.v., koorden, gehelen, decimalen, enz.) bevat, kunt u uw gegevensmodel moeten bijwerken alvorens de integratie te gebruiken.

* Het behouden van bestaande gegevens in aangepaste campagneentiteiten kan extra advieskosten met zich meebrengen om de gegevens voor te bereiden op de integratie.

* Bij het instappen van onderhoudsvensters kan het nodig zijn om tussen Adobe en de klant te bepalen, aangezien initiële invoer vertraging van de campagne kan veroorzaken.

* U wordt aangemoedigd om bekende instanties van significante toename of &quot;pieken&quot;in gebruik van de integratie (b.v., scherpe verhoging van nieuwe of bijgewerkte verslagen) mee te delen, aangezien dit vertraging in gegevenssynchronisatie zou kunnen veroorzaken.

* Als onderdeel van de integratie, zult u de pre-integratieconfiguratiestappen in Microsoft Azure en Dynamics 365 moeten voltooien. Zie de configuratiestappen [op deze pagina](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)

* Verwacht wordt dat u uw Dynamica 365 en de gegevensmodellen van de Campagne aan de integratie zult brengen en hen zult handhaven.

## Integratiegrenzen

De integratie werd ontworpen om het algemene gebruiksgeval van gemeenschappelijke gegevensbeweging tussen Dynamiek 365 en Campagne op te lossen, maar het is niet bedoeld om elk gebruiksgeval te richten specifiek voor elke klant:

* De integratie heeft geen betrekking op het verwijderen van privacy (bijvoorbeeld GDPR). De verantwoordelijkheid voor het voldoen aan de privacyverzoeken van eindgebruikers berust bij de klant; dergelijke verzoeken moeten onafhankelijk van elkaar worden gedaan in de campagne (via de Adobe Experience Platform Privacy Service) en in Dynamics 365. De integratie kan regelmatige schrappingen uitgeven om met gegevenssynchronisatie te helpen, indien gewenst.

* Geen profiel of douaneentiteitsgegevens zullen van Campagne aan Dynamica 365, met uitzondering van opt-out informatie (als gevormd door de klant) worden gesynchroniseerd.

* Abonnementsbeheer voor campagnes (d.w.z. abonnees/unsubscribes) wordt niet native ondersteund.

* Het samenstellen en activeren van campagne-e-mailcampagnes vanuit Dynamics 365 wordt niet ondersteund.

* De integratie zal niet het remodeling van gegevens tussen Dynamiek 365 en de gegevensmodellen van de Campagne steunen. Verwacht wordt dat de integratie één Dynamics 365 tabel synchroniseert met één campagneretabel.

* Er is geen zelfbediening UI met de huidige versie van de integratie.
