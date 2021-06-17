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
source-git-commit: 887396a0871a8ed93642c55a49c8737f5c98bfc2
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 98%

---


# Laatste release{#latest-release}

## Release 21.2 - juni 2021 {#release-21-2---june-2021}

De nieuwe functies, verbeteringen en oplossingen die zijn opgenomen in de volgende release van Campaign Standard worden hieronder weergegeven. De nieuwe functies, verbeteringen en oplossingen die zijn opgenomen in deze release van Campaign Standard, worden hieronder weergegeven.

**Verbeteringen**

* Bij het ontwerpen van een landingspagina kunt u nu een verplicht selectievakje toevoegen dat profielen moeten selecteren voordat het formulier wordt verzonden. Raadpleeg de [gedetailleerde documentatie](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox) voor meer informatie.

* Voor de integratie van Triggers is het foutbericht dat wordt weergegeven wanneer er geen afstemmingsgegevens in de lading van de trigger komen, verbeterd: &#39;Aliasgegevens ontbreken in de lading&#39;.

* De prestaties voor het ophalen van pushmeldingen uit de wachtrij zijn verbeterd.

**Overige wijzigingen**

* Het URL-handtekeningmechanisme voor het bijhouden van koppelingen is uitgeschakeld om te voorkomen dat er een probleem optrad waardoor bepaalde geldige, ondertekende trackingskoppelingen ten onrechte werden geblokkeerd nadat deze waren gewijzigd door beveiligingstools van derden.

* Bij leveringen met meerdere varianten kunnen gebruikers niet langer taalkopieën maken als de standaardvariant is verwijderd. Er wordt nu een bericht weergegeven tijdens het maken van een taalkopie. (CAMP-48235)

* Het proces in twee stappen voor het verwijderen van profielen (verouderde versie van Campaign 19.4) is nu standaard uitgeschakeld. Eerder moest het handmatig in de interface van Campaign worden uitgeschakeld alvorens de Privacy Core-service te gebruiken. Als u dit niet deed, bleven aanvragen voor verwijderen in behandeling zonder ze te voltooien.

* In Dynamische rapporten is het segment van het **Bewijs van uitsluiting** verwijderd. (CAMP-46161)

* Er is een nieuw waarschuwingsbericht toegevoegd om de gebruiker te waarschuwen wanneer een iOS-certificaat zonder de waarde platformPrincipal in de Campaign-applicatie wordt geüpload.

* De maximale grootte van een e-mailbericht is nu standaard ingesteld op 100 MB. Met deze limiet kunt u fouten voorkomen die een e-mailbericht oneindig groter kunnen maken, waardoor het systeem kan vastlopen. (CAMP-47445) [Meer informatie](../../sending/using/design-and-personalize.md#email-size)

* De integratie van de Asset Core-service met de e-mailontwerper kan nu worden gebruikt door standaardgebruikers.

* Er is een nieuw bericht toegevoegd ter bevestiging van een geslaagde migratie van een v4-pushapplicatie naar een v5-pushapplicatie.

* Tijdens het maken van JSONWeb-tokens om te verifiëren bij de Campaign Standard-API voor authentiek te verklaren, zijn nu de productprofielen **overwogen**. Dit betekent dat de organisatorische eenheden en rollen die zijn toegewezen aan de beveiligingsgroep (die overeenkomt met het productprofiel op AdobeIO), worden toegepast op de technische IMS-account die nodig is voor oproepen van de Campaign Standard Rest-API. (CAMP-47479)

**Patches**

* Probleem verholpen waardoor de verloopoptie voor de logtabel van het batchproces (**xtkjoblog**) niet kon worden toegepast. Hierdoor kon de tabel niet correct worden gewist.

* Probleem verholpen waardoor u de volgorde van filters in een **Segmentatie**-workflowactiviteit niet kon wijzigen. (CAMP-48357)

* Probleem verholpen waarbij een regressie van 20.4 resulteerde in een fout met de waarde null. (CAMP-48591)

* Probleem verholpen waarbij u een rapport niet kon verzenden via de menu&#39;s **Delen** > **Rapport nu verzenden** of **Rapport volgens planning verzenden**. (CAMP-47798)

* Probleem verholpen waarbij een regressie werd gecorrigeerd die kon leiden tot onjuiste openingspercentages voor Gmail wegens het filteren van trackinggebeurtenissen die van Gmail-accounts werden ontvangen. (CAMP-46504)

* Verschillende problemen verholpen die leidde tot gegevensdiscrepanties tussen rapporten in Adobe Campaign Standard en rapporten in Adobe Analytics. (CAMP-47671, CAMP-47296)

* Probleem verholpen waardoor u geen toegang meer kreeg tot de leveringslogboeken nadat de voorbereiding was mislukt. (CAMP-48296)

* Probleem verholpen waarbij een foutbericht kon worden weergegeven wanneer werd geprobeerd een aangepast rapport te bewerken, te verwijderen of te verzenden. (CAMP-47789, CAMP-47798)

* Probleem verholpen waarbij oproepen van API&#39;s mislukten wanneer een nieuwe aangepaste bron werd gemaakt en de optie **Niet synchroniseren** werd ingeschakeld. (CAMP-48014)

* Probleem verholpen waarbij aangepaste bronnen met de ingeschakelde optie **Niet synchroniseren** konden verwijzen naar een schema dat opnieuw was geformuleerd of verwijderd. Dit probleem veroorzaakte een fout bij het publiceren van de aangepaste bronnen.

* Probleem verholpen met een sms-opt-out bij het gebruik van meerdere korte codes op hetzelfde externe account.

* Probleem verholpen waardoor u geen toegang kreeg tot een nieuw leveringswaarschuwingscriterium (&quot;de bron die u probeert te bereiken is onbereikbaar&quot;) na publicatie van de database. (CAMP-48221)

* Probleem verholpen waarbij trackinglogboeken in sommige Campaign-instanties met dynamische rapportage ontbraken. Er is een nieuwe [technische workflow](../../administration/using/technical-workflows.md) toegevoegd om deze trackinglogboeken te herstellen. (CAMP-47885)

* Probleem verholpen waarbij geen leveringsdata in dynamische rapporten werden weergegeven. De rapporten zijn ingesteld op 0. (CAMP-47480)

* Probleem verholpen waardoor de Server JavaScript HTTP Client geen verbinding kon maken met externe URL.

* Probleem verholpen waarbij een **Incrementele query**-activiteit werd hersteld nadat de interne naam van de workflow werd gewijzigd. Dit gebeurde wanneer een datumveld werd gebruikt als incrementele modus. (CAMP-47674)

* Probleem verholpen waarbij de voorvertoningsminiatuur niet kon worden weergegeven in het leveringsoverzicht bij het maken van een meertalige e-mail met de integratie van Adobe Experience Manager. Dit probleem trad op bij het gebruik van de knop **Taalkopie maken** om de e-mailvarianten te maken. (CAMP-47810)

* Probleem verholpen waardoor gebruikers geen toegang kregen tot de bovenliggende levering via onderliggende levering van e-mail of sms. (CAMP-47986)

* Probleem verholpen waarbij het CPU- en geheugenverbruik te hoog zou kunnen zijn bij het verzenden van transactieberichten via de REST-API met een ontbrekende aangepaste gebeurtenis. (CAMP-47147)

* Probleem verholpen met de API voor Transactieberichten waardoor realtimeberichten soms niet konden worden verzonden.

* Probleem verholpen waarbij geen rapporten werden ontvangen na het gebruik van de optie **Rapport volgens planning verzenden**. (CAMP-48583, CAMP-47786)

* Probleem verholpen waarbij rapporten die werden ontvangen na het gebruik van de optie **Rapport nu verzenden**, onvolledig waren en gegevens ontbraken. (CAMP-48583)

* Probleem verholpen met de e-mailontwerper waarbij de afmetingen van een afbeelding tijdens het uploaden van een afbeelding werden verkleind. (CAMP-47017)

* Probleem verholpen waarbij elke beschikbare sjabloon van Experience Manager niet kon worden weergegeven bij het maken van een levering. (CAMP-48132)

* Probleem verholpen waardoor de koppeling Campaign in de overzichtspagina van een verzonden levering de gebruikers niet kon doorsturen naar de gerelateerde campagne. (CAMP-48012)

* Probleem verholpen in de e-mailontwerper waarbij de integratie van de Asset Core-service bleef mislukken bij het selecteren van een asset. (CAMP-47446)

* Probleem verholpen waarbij sommige Journey Orchestration-leveringen werden geblokkeerd doordat Campaign geen tijdstempels met een exacte waarde ondersteunde (dat wil zeggen eindigend met 00) die door gebeurtenissen van Journey Orchestration werden verzonden.
