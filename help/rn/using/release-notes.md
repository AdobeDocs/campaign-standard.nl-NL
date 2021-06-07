---
solution: Campaign Standard
product: campaign
title: Laatste release
description: Op deze pagina vindt u content van de nieuwste release van Campaign Standard
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overzicht
role: Business Practitioner
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: e492009166ba94cdd27613f2391229179ba9f8a4
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 6%

---

# Laatste release{#latest-release}

## Release 21.2 - juni 2021 {#release-21-2---june-2021}

De nieuwe functies, verbeteringen en oplossingen die zijn opgenomen in de volgende release van Campaign Standard worden hieronder weergegeven.

**Verbeteringen**

* Bij het ontwerpen van een landingspagina kunt u nu een verplicht selectievakje toevoegen dat profielen moeten selecteren voordat het formulier wordt verzonden. Raadpleeg de [gedetailleerde documentatie](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox) voor meer informatie.

* Voor de integratie van Triggers is het foutbericht dat wordt weergegeven wanneer er geen afstemmingsgegevens in de lading van de trigger komen, verbeterd: &quot;Alias data missing from payload&quot;.

* De prestaties voor het ophalen van pushberichten uit de wachtrij zijn verbeterd.

**Overige wijzigingen**

* Het URL-handtekeningmechanisme voor het bijhouden van koppelingen is uitgeschakeld om te voorkomen dat er een probleem is opgetreden waardoor bepaalde geldige, ondertekende koppelingen voor het bijhouden van koppelingen onjuist werden geblokkeerd nadat deze waren gewijzigd door beveiligingsprogramma&#39;s van derden.

* Bij leveringen met meerdere varianten kunnen gebruikers niet langer taalkopieën maken als de standaardvariant is verwijderd. Er wordt nu een bericht weergegeven tijdens het maken van een taalkopie. (CAMP-48235)

* Het proces voor het verwijderen van profielen in twee stappen (verouderde versie van Campagne 19.4) is nu standaard uitgeschakeld. Eerder moest het manueel van de interface van de Campagne worden onbruikbaar gemaakt alvorens de Dienst van de Kern van de Privacy te gebruiken. Als u dit niet doet, blijven aanvragen voor verwijderen in behandeling zonder ze te voltooien.

* Er is een nieuwe statistische functie &#39;StringAgg&#39; geïntroduceerd om de waarden van een kolom met het type tekenreeks samen te voegen. (CAMP-47077) [Meer informatie](../../automating/using/list-of-functions.md#aggregates)

* In Dynamische rapporten, is het **segment van het Bewijs van de Uitsluiting** verwijderd. (CAMP-46161)

* Er is een nieuw waarschuwingsbericht toegevoegd om de gebruiker te waarschuwen wanneer een iOS-certificaat zonder de waarde platformPrincipal in de Campagne-toepassing wordt geüpload.

* De maximale grootte van een e-mailbericht is nu standaard ingesteld op 100 MB. Met deze limiet kunt u fouten voorkomen die een e-mailbericht oneindig groter kunnen maken. Dit kan ertoe leiden dat het systeem vastloopt. (CAMP-47445) [Meer informatie](../../sending/using/design-and-personalize.md#email-size)

* De integratie van de Asset Core-service met de e-mailontwerper kan nu worden gebruikt door standaardgebruikers.

* Er is een nieuw bericht toegevoegd ter bevestiging van een geslaagde migratie van een v4-pushtoepassing naar een v5-pushtoepassing.

* Tijdens het creëren van Tokens JSONWeb om aan Campaign Standard API voor authentiek te verklaren, zijn de productprofielen nu **overwogen**. Dit betekent dat de organisatorische eenheden en rollen die zijn toegewezen aan de beveiligingsgroep (die overeenkomt met het productprofiel op AdobeIO) worden toegepast op de technische IMS-account die nodig is voor aanroepen van de Campaign Standard Rest API. (CAMP-47479)

**Patches**

* Probleem verholpen waardoor de afloopoptie voor de logtabel van het batchproces (**xtkjoblog**) niet kon worden toegepast. Hierdoor is de tabel niet correct gewist.

* Probleem verholpen waardoor u de volgorde van filters in een **Segmentatie**-workflowactiviteit niet kon wijzigen. (CAMP-48357)

* Probleem verholpen waarbij een regressie van 20.4 resulteerde in een fout met de waarde null. (CAMP-48591)

* Probleem verholpen waarbij u een rapport niet kon verzenden via **Share** > **Rapport nu verzenden** of **Rapport verzenden in Schema** menu. (CAMP-47798)

* Oplossing voor een regressie die tot onjuiste open tarieven voor Gmail als gevolg van het filtreren van het volgen van gebeurtenissen kon leiden die van rekeningen Gmail werden ontvangen. (CAMP-46504)

* Verschillende problemen die tot gegevensdiscrepantie tussen rapporten in Adobe Campaign Standard en rapporten in Adobe Analytics leidden, zijn opgelost. (CAMP-47671, CAMP-47296)

* Probleem verholpen waardoor u geen toegang meer kreeg tot de leveringslogboeken nadat de voorbereiding was mislukt. (CAMP-48296)

* Probleem verholpen waarbij een foutbericht kon worden weergegeven wanneer werd geprobeerd een aangepast rapport te bewerken, te verwijderen of te verzenden. (CAMP-47789, CAMP-47798)

* Probleem verholpen waarbij APIs-aanroepen mislukten wanneer een nieuwe aangepaste bron werd gemaakt en de optie **Niet synchroniseren** werd ingeschakeld. (CAMP-48014)

* Probleem verholpen waarbij aangepaste bronnen met de optie **Niet synchroniseren** ingeschakeld konden verwijzen naar een schema dat opnieuw was geformuleerd of verwijderd. Dit probleem heeft een fout veroorzaakt bij het publiceren van de aangepaste bronnen.

* Probleem verholpen waarbij een SMS-optie werd uitgeschakeld bij het gebruik van meerdere korte codes op dezelfde externe account.

* Probleem verholpen waardoor u geen toegang kreeg tot een nieuw leveringswaarschuwingscriterium (&quot;de bron u probeert toegang te krijgen is onbereikbaar&quot;) na publicatie van de database. (CAMP-48221)

* Probleem verholpen waarbij trackinglogboeken in sommige campagneinstanties met dynamische rapportage ontbraken. Er is een nieuwe [technische workflow](../../administration/using/technical-workflows.md) toegevoegd om deze logbestanden voor bijhouden te herstellen. (CAMP-47885)

* Probleem verholpen waarbij geen leveringsgegevens werden weergegeven in dynamische rapporten. De rapporten zijn ingesteld op 0. (CAMP-47480)

* Probleem verholpen waardoor de Server JavaScript HTTP Client geen verbinding kon maken met externe URL.

* Probleem verholpen waarbij een **Incrementele query** activiteit opnieuw werd ingesteld nadat de interne naam van de workflow was gewijzigd. Dit gebeurde wanneer een datumveld werd gebruikt als incrementele modus. (CAMP-47674)

* Probleem verholpen waarbij de voorvertoningsminiatuur niet kon worden weergegeven in het leveringsoverzicht bij het maken van een meertalige e-mail met Adobe Experience Manager-integratie. Dit probleem is opgetreden bij het gebruik van de knop **Taalkopie maken** om de e-mailvarianten te maken. (CAMP-47810)

* Probleem verholpen waardoor gebruikers geen toegang kregen tot de bovenliggende levering via e-mail of SMS. (CAMP-47986)

* Probleem verholpen waarbij het CPU- en geheugenverbruik te hoog zou kunnen zijn bij het verzenden van transactieberichten via de REST API met een ontbrekende aangepaste gebeurtenis. (CAMP-47147)

* Oplossing voor een fout met de API voor Transactieberichten waardoor realtime berichten soms niet konden worden verzonden.

* Probleem verholpen waarbij geen rapporten werden ontvangen na het gebruik van de optie **Rapport verzenden volgens schema**. (CAMP-48583, CAMP-47786)

* Probleem verholpen waarbij rapporten die werden ontvangen na het gebruik van de optie **Rapport nu verzenden** onvolledig waren en gegevens ontbraken. (CAMP-48583)

* Probleem verholpen met de e-mailontwerper waarbij de afmetingen van een afbeelding tijdens het uploaden van een afbeelding werden verkleind. (CAMP-47017)

* Probleem verholpen waarbij elke beschikbare sjabloon voor Experience Managers niet kon worden weergegeven bij het maken van een levering. (CAMP-48132)

* Probleem verholpen waardoor de koppeling Campagne in de overzichtspagina van een verzonden levering de gebruikers niet kon doorsturen naar de gerelateerde campagne. (CAMP-48012)

* Probleem verholpen in de e-mailontwerper waarbij de integratie van de Asset Core-service bleef mislukken bij het selecteren van middelen. (CAMP-47446)

* Probleem verholpen waarbij sommige Journey Orchestration-leveringen werden geblokkeerd vanwege campagne die geen tijdstempels met een exacte waarde ondersteunt (dat wil zeggen eindigend met 00) die door gebeurtenissen van Journey Orchestration werden verzonden.
