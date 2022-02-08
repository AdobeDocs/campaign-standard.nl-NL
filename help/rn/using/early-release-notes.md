---
title: Vroege aanvullende informatie
description: Vroege aanvullende informatie
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 9ab2e49203315e4c31a1bc268cd17bd0351a5349
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 86%

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
<p>Na de update van de release van Apache log4j v2.17.0 in december 2021, hebben we de update intern uitgevoerd en zijn we klaar voor implementatie met deze release, zodat onze klanten niet worden beïnvloed door mogelijke onbedoelde effecten van de introductie van een nieuwe systeemwijziging buiten onze normale releaseplanning.</p>
</td> 
</tr> 
</tbody> 
</table>

**Beveiligingsoplossingen**

* Nieuw URL-handtekeningmechanisme voor tracking opgenomen in deze release. Het vorige mechanisme was uitgeschakeld om een probleem te voorkomen waardoor geldige, ondertekende trackingkoppelingen onjuist werden geblokkeerd nadat ze waren gewijzigd door beveiligingstools van derden. (CAMP-48983)
* Verbeter de beveiliging voor toegang tot toepassings- en serverconfiguratiebestanden: De beveiliging van API&#39;s voor toegang tot JavaScript-bestanden is nu beperkt tot sandboxmappen. (CAMP-49411)

**Verbeteringen**

* Verbeterde verwerking van de rapportagegegevens om overbelasting van het systeem te voorkomen. (CAMP-47578)
* Nadat u uw In-app-berichten hebt verzonden, kunt u er nu voor kiezen om uw levering te deactiveren. Op deze manier kunt u de levering verwijderen zonder rapportgegevens te verliezen. (CAMP-48469)
* Om problemen te voorkomen kunnen gebruikers niet langer dezelfde naam gebruiken voor een aangepaste tabelkolom als de naam die wordt gebruikt voor de automatische primaire sleutel in de database, `"<dataType><resourceName>Id"`. (CAMP-49358)

**Patches**

* Er is een probleem opgelost met de optie **Rapport nu verzenden** in dynamische rapporten: de PDF-generatietaken mislukten bij leveringen met multivarianten. (CAMP-49120)
* Er is een probleem opgelost waarbij gebruikers de content van Adobe Experience Manager (AEM) niet konden vernieuwen of ontkoppelen van hun Adobe Campaign Standard-leveringen wanneer gedupliceerde content in AEM dezelfde sleutel deelde (cq:uuid). (CAMP-49161)
* Er is een fout opgelost bij het openen van een instantie waar pagina&#39;s niet werden geladen, leveringen niet konden worden geopend of eventuele wijzigingen in behandeling niet konden worden opgeslagen. (CAMP-50195)
* Er is een probleem opgelost dat verhinderde dat waarschuwingscriteria voor levering werden geopend als het veld **Leveringsfilter** dat door dit criterium werd toegepast, niet was ingevuld. (CAMP-49093)
* Er is een probleem opgelost bij het bewerken van de knop **Secundair** in In-app-leveringen waardoor er geen rekening kon worden gehouden met wijzigingen. (CAMP-50250)
* Er is een fout opgelost in Japanse instanties waardoor gebruikers Meerdere keren per dag konden kiezen als **Uitvoerfrequentie** in de activiteit **Planner**. (CAMP-50247)
* Er is een probleem opgelost bij het werken in een Japanse gebruikersinterface die een foutbericht weergaf bij het selecteren van een tijd in een Planner-activiteit. (CAMP-49289)
* Er is een fout opgelost met pushmeldingsrapporten waarin afgewezen pushmeldingen werden weergegeven als **Open** in plaats van **Impressie**. (CAMP-45980)
* Er is een probleem opgelost dat tot fouten kon leiden bij het openen van een rapport. (CAMP-49222)
* Er is een probleem opgelost dat ertoe kon leiden dat de e-mailvoorbereiding mislukte nadat een koppeling naar AEM-content was verwijderd. (CAMP-49877)
* Om verschillende problemen op te lossen is het mechanisme voor opnieuw proberen verbeterd voor leveringen met content die is geïmporteerd via een URL. (CAMP-48888)
* Er is een probleem opgelost dat optrad na het maken van een nieuw filter in een aangepaste bron en het vervolgens te gebruiken als een afstemmingssleutel op een landingspagina. Als de aangepaste bron opnieuw is gepubliceerd, is het filter verwijderd uit de lijst met beschikbare afstemmingssleutels voor de landingspagina. (CAMP-49516)
* Er is een probleem opgelost in landingspagina&#39;s bij het gebruik van dynamische voorwaarden met selectievakjes. (CAMP-48604)
* Er is een probleem opgelost dat optrad in een **Query**-activiteit na gebruik van de filtervoorwaarde In of vóór oktober. Bij het werken vanuit een instantie die is ingesteld op een Europese tijdzone, toonde de geselecteerde maand voor het filter september in plaats van oktober, als gevolg van een probleem bij het omrekenen van de tijdzone. (CAMP-48602)
* Voor optimale prestaties worden nu e-mails verzonden met 7-bits codering in plaats van 8-bits. Hierdoor wordt voorkomen dat de DKIM-handtekening door de relais ongeldig wordt gemaakt bij het omzetten van 8 in 7 bits. (CAMP-49016)
* De prestaties bij het dupliceren van audiences zijn verbeterd om problemen bij het werken met grote audiences te voorkomen. (CAMP-49639)
* Er is een probleem opgelost waardoor een aangepast filter de juiste resultaten niet kon weergeven bij gebruik in een **Query**-activiteit. (CAMP-49417)
* Er is een fout opgelost die een foutbericht weergaf bij een poging om een fragment te gebruiken in een levering met een komma in de naam. Het probleem is opgelost. Er kunnen nu komma&#39;s worden gebruikt in de namen van fragmenten. (CAMP-49216)