---
title: Vroege aanvullende informatie
description: Vroege aanvullende informatie
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 5435e1dbfbe08399c488322320ac5bb8e681a79d
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 10%

---

# Vroege aanvullende informatie {#new-release}

Op deze pagina worden nieuwe functies, verbeteringen en oplossingen beschreven die in de volgende release van Campaign Standard zijn opgenomen.

>[!CAUTION]
>
> Deze content kan zonder voorafgaande kennisgeving worden gewijzigd tot de upgradedatum van de werkgebiedomgevingen. Meer informatie vindt u op de [releaseplanningspagina](../../rn/using/release-planning.md).

## Release 22.1 - februari 2022 {#feb-2022}


**Nieuwe functies**


<table> 
<thead> 
<tr> 
<th> <strong>Beveiligingsupdate voor beveiligingskwetsbaarheden van Apache Log4j</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Apache log4j heeft de geïdentificeerde kwetsbaarheden in Apache log4j v2.17.1-release verholpen. Adobe Campaign Standard gebruikt Apache log4j en in deze release is deze nieuwste Apache log4j v2.17.1 inbegrepen </p>
</td> 
</tr> 
</tbody> 
</table>

**Beveiligingsoplossingen**

* Nieuw URL-handtekeningmechanisme voor bijhouden opgenomen in deze release. Het vorige mechanisme was uitgeschakeld om te voorkomen dat een probleem zou ontstaan dat ertoe leidde dat bepaalde geldige, ondertekende koppelingen voor bijhouden onjuist werden geblokkeerd nadat deze waren gewijzigd door beveiligingsprogramma&#39;s van derden. (CAMP-48983)

**Verbeteringen**

* Verbeterde verwerking van de rapportagegegevens om overbelasting van het systeem te voorkomen. (CAMP-47578)
* Nadat u uw In-App-berichten hebt verzonden, kunt u de levering nu deactiveren. Op deze manier kunt u de levering verwijderen zonder rapportgegevens te verliezen. (CAMP-48469)
* Om problemen te voorkomen, kunnen gebruikers niet langer dezelfde naam voor een aangepaste tabelkolom gebruiken als de naam die wordt gebruikt voor de automatische primaire sleutel in de database. `"<dataType><resourceName>Id"`. (CAMP-49358)
* U kunt nu uw levering controleren en taaklogboeken bijhouden met de nieuwe **Taakgeschiedenis** vervolgkeuzelijst van het dashboard van uw berichten. (CAMP-49840)
* Verbeterde stabiliteit en databasegezondheid door dode beginselen te verminderen, wanneer een groot aantal berichten over alle kanalen in de loop der tijd wordt verzonden. (CAMP-49755, CAMP-49792, CAMP-49849)
* Om ervoor te zorgen dat de databaseverbindingen automatisch worden vernieuwd in het geval van een database die vastloopt of opnieuw wordt opgestart, zijn verbeteringen geïmplementeerd in de Campagne Mail Transfer Agent (MTA). (CAMP-48063)


**Patches**

* Probleem verholpen met de **Rapport nu verzenden** optie in dynamische rapporten: de PDF-generatietaken mislukten met leveringen, inclusief multivarianten. (CAMP-49120)
* Probleem verholpen waarbij gebruikers Adobe Experience Manager-inhoud (AEM) niet konden vernieuwen of loskoppelen van hun Adobe Campaign Standard-leveringen wanneer een gedupliceerde inhoud in AEM dezelfde sleutel deelde (cq:uuid). (CAMP-49161)
* Probleem verholpen bij het openen van een instantie waarbij pagina&#39;s niet werden geladen, leveringen niet konden worden geopend of hangende wijzigingen niet konden worden opgeslagen. (CAMP-50195)
* Probleem verholpen waardoor waarschuwingscriteria voor levering niet konden worden geopend in het veld **Aflevering, filter** niet is voldaan. (CAMP-49093)
* Probleem verholpen tijdens het bewerken van het dialoogvenster **Secundair** knop in In-App-leveringen waardoor geen rekening kon worden gehouden met wijzigingen. (CAMP-50250)
* Correctie van een fout in Japanse instanties waardoor gebruikers meerdere keren per dag niet konden kiezen **Uitvoerfrequentie** in de **Planner** activiteit. (CAMP-50247)
* Probleem verholpen tijdens het werken in een Japanse gebruikersinterface die een foutbericht weergaf bij het selecteren van een tijd in een planningsactiviteit. (CAMP-49289)
* Probleem verholpen met pushberichtrapporten waarin verwijderde pushberichten werden weergegeven als **Openen** in plaats van **Impressie**. (CAMP-45980)
* Probleem opgelost dat tot fouten bij het openen van een rapport kon leiden. (CAMP-49222)
* Probleem opgelost waarbij de e-mailvoorbereiding mislukte nadat een koppeling naar AEM inhoud was verwijderd. (CAMP-49877)
* Om verschillende problemen op te lossen, is het mechanisme voor opnieuw proberen verbeterd voor leveringen, waaronder inhoud die is geïmporteerd vanaf een URL. (CAMP-48888)
* Probleem verholpen die optrad na het maken van een nieuw filter in een aangepaste bron en het vervolgens gebruiken als een combinatietoets op een bestemmingspagina. Als de aangepaste bron opnieuw is gepubliceerd, is het filter verwijderd uit de lijst met beschikbare afstemmingssleutels voor de landingspagina. (CAMP-49516)
* Probleem verholpen in bestemmingspagina&#39;s bij gebruik van dynamische omstandigheden met selectievakjes. (CAMP-48604)
* Probleem verholpen dat zich voordeed in een **Query** activiteit bij gebruik van de filtervoorwaarde &quot;Op of vóór oktober&quot;. Wanneer u werkt van een instantie die is ingesteld op een Europese tijdzone, heeft de geselecteerde maand voor het filter september in plaats van oktober getoond vanwege een probleem bij het omzetten van de tijdzone. (CAMP-48602)
* Adobe Campaign verzendt nu e-mailberichten met 7-bits codering in plaats van 8-bits om de prestaties te optimaliseren. Hierdoor wordt voorkomen dat tussenliggende relais de DKIM-handtekening ongeldig maakt, wat de authenticiteit van de berichten kan beïnvloeden. (CAMP-49016)
* De prestaties bij het dupliceren van het publiek zijn verbeterd om problemen bij het werken met een groot publiek te voorkomen. (CAMP-49639)
* Probleem verholpen waarbij een aangepast filter niet de juiste resultaten kon weergeven bij gebruik in een **Query** activiteit. (CAMP-49417)
* Probleem verholpen waarbij een foutbericht werd weergegeven bij een poging een fragment te gebruiken in een levering met een komma in de naam. Het probleem is opgelost. Er kunnen nu komma&#39;s worden gebruikt in de namen van fragmenten. (CAMP-49216)