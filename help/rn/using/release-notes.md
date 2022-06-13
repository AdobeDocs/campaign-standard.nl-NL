---
title: Laatste release
description: Op deze pagina vindt u content van de nieuwste release van Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: ht
source-wordcount: '1182'
ht-degree: 100%

---


# Laatste release{#latest-release}

![Configuratiescherm](assets/do-not-localize/cp-icon.png) **Nieuwe release van het configuratiescherm**. [Meer informatie](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=nl){target=&quot;_blank&quot;}.


## Release 22.2 - juni 2022 {#june-2022}

**Verbeteringen**

* **Adobe Notification Service** - Campaign wordt geleverd met Adobe Notification Service waarmee Experience Cloud-oplossingen gebruikers in Experience Cloud kunnen waarschuwen voor activiteiten die belangrijk voor hen zijn om te weten. Vanaf versie 22.2 is de gebruikerservaring verbeterd: meldingen krijgen prioriteit en productgegenereerde meldingen zijn gescheiden van Adobe-statusaankondigingen. Wanneer de notificatie naar een specifieke workflow verwijst, kunt u de bijbehorende workflow nu bovendien rechtstreeks openen via de e-mail of het bericht in het product.  Voor meer informatie over Adobe Campaign-notificaties raadpleegt u [Adobe Campaign-notificaties](../../administration/using/sending-internal-notifications.md).

* **Optimalisatie bij het opstarten van workflows** - Adobe heeft een nieuwe mogelijkheid toegevoegd waarmee het aantal workflows dat rond dezelfde tijd begint, kan worden aangepast. Dit zou CPU-pieken helpen voorkomen die tot serviceonderbrekingen of downtime hadden kunnen leiden. Adobe zou dit inschakelen na de release van 22.2. Er is geen verder actiepunt over de klant met betrekking tot hetzelfde.

* **Toegankelijkheid** - Adobe heeft veel toegankelijkheidsoplossingen gemaakt om het algemene gebruiksgemak van de applicatie te verbeteren. Deze functies zijn momenteel alleen ingeschakeld voor een aantal early adopters en ze zullen in de ACS 22.3-release naar alle klanten worden uitgerold. Voorbeelden van toegankelijkheidsverbeteringen zijn:

   * Ervoor zorgen dat er een zichtbare focusindicator is voor focusbare elementen op elk scherm
   * Paginaoriëntatiepunten maken voor eenvoudigere navigatie
   * De naam, rol, waarde en status toevoegen voor veel besturingselementen
   * Problemen met dynamische focusvolgorde op hoofdschermen corrigeren

**Beveiligingsupgrade**

* Apache Tomcat is geüpgraded van versie 7 naar versie 8.5.

**Patches**

* Er is een probleem opgelost met de technische workflow voor facturering vanwege een dubbele-sleutelfout. (CAMP-51029)
* De ontbrekende Microsoft Edge-browsercategorie is toegevoegd aan trackingrapporten. Ze waren eerder gecategoriseerd met Microsoft Chrome geopend. (CAMP-51165)
* Er is een probleem opgelost met AVG-verzoeken waarbij geen gegevens uit onderliggende tabellen werden verwijderd. (CAMP-48276)
* Er is een probleem opgelost in de e-mailontwerper waardoor de zichtbaarheidsvoorwaarde van een fragment niet werd opgeslagen in een sjabloon voor transactiebericht. (CAMP-50338)
* Er is een probleem opgelost in Campaign-rapporten waardoor geen rekening werd gehouden met het datumbereik. (CAMP-50991)
* Er is een fout verholpen waardoor geplande e-mails mislukten: de bezorgingsanalyse kon niet starten omdat de bezorging nog steeds de status &#39;Opnieuw in behandeling&#39; had. (CAMP-50302)
* Er is een probleem opgelost in de e-mailontwerper bij het bekijken van een voorbeeld van een e-mail met een profielvervanging. (CAMP-49312)
* Er is een probleem opgelost met lege waarde in aangepaste opsommingen: bij het maken van een aangepaste bron met een veld dat een tekstopsomming is en slechts één waarde bevat, wordt deze waarde nu standaard ingesteld, zodat u een query op dit veld kunt maken als een eenvoudig verzoek. (CAMP-50606)



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
<p>Apache log4j heeft de gerapporteerde kwetsbaarheden in de Apache log4j v2.17.1-release verholpen. Adobe Campaign Standard gebruikt Apache log4j en in deze release is deze nieuwste Apache log4j v2.17.1 inbegrepen </p>
</td> 
</tr> 
</tbody> 
</table>

**Beveiligingsoplossingen**

* Nieuw URL-handtekeningmechanisme voor tracking opgenomen in deze release. Het vorige mechanisme was uitgeschakeld om een probleem te voorkomen waardoor geldige, ondertekende trackingkoppelingen onjuist werden geblokkeerd nadat ze waren gewijzigd door beveiligingstools van derden. (CAMP-48983)

**Verbeteringen**

* Verbeterde verwerking van de rapportagegegevens om overbelasting van het systeem te voorkomen. (CAMP-47578)
* Nadat u uw In-app-berichten hebt verzonden, kunt u er nu voor kiezen om uw levering te deactiveren. Op deze manier kunt u de levering verwijderen zonder rapportgegevens te verliezen. (CAMP-48469)
* Om problemen te voorkomen kunnen gebruikers niet langer dezelfde naam gebruiken voor een aangepaste tabelkolom als de naam die wordt gebruikt voor de automatische primaire sleutel in de database, `"<dataType><resourceName>Id"`. (CAMP-49358)
* U kunt nu uw levering bewaken en taaklogboeken volgen met de nieuwe vervolgkeuzelijst **Taakgeschiedenis** van het dashboard van uw berichten. [Meer informatie](../../sending/using/monitoring-a-delivery.md) (CAMP-49840)
* Verbeterde stabiliteit en gezondheid van de database door het verminderen van dode tupels, wanneer een groot aantal berichten in de loop van de tijd over alle kanalen wordt verzonden. (CAMP-49755, CAMP-49792, CAMP-49849)
* Om ervoor te zorgen dat databaseverbindingen automatisch worden vernieuwd in het geval van een databasecrash of opnieuw opstarten, zijn er verbeteringen geïmplementeerd in Campaign Mail Transfer Agent (MTA). (CAMP-48063)
* Een nieuwe trackingoptie **Trackingpixel boven aan de e-mail gebruiken** is toegevoegd aan e-maileigenschappen, zodat u de trackingpixel boven aan de e-mail kunt verplaatsen in plaats van onderaan. (CAMP-49672)

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
* Om verschillende problemen op te lossen is het mechanisme voor opnieuw proberen verbeterd voor leveringen met content die is geïmporteerd via een URL. [Meer informatie](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time) (CAMP-48888)
* Er is een probleem opgelost dat optrad na het maken van een nieuw filter in een aangepaste bron en het vervolgens te gebruiken als een afstemmingssleutel op een landingspagina. Als de aangepaste bron opnieuw is gepubliceerd, is het filter verwijderd uit de lijst met beschikbare afstemmingssleutels voor de landingspagina. (CAMP-49516)
* Er is een probleem opgelost in landingspagina&#39;s bij het gebruik van dynamische voorwaarden met selectievakjes. (CAMP-48604)
* Er is een probleem opgelost dat optrad in een **Query**-activiteit na gebruik van de filtervoorwaarde In of vóór oktober. Bij het werken vanuit een instantie die is ingesteld op een Europese tijdzone, toonde de geselecteerde maand voor het filter september in plaats van oktober, als gevolg van een probleem bij het omrekenen van de tijdzone. (CAMP-48602)
* Adobe Campaign verzendt nu e-mailberichten met 7-bits codering in plaats van 8-bits om de levering te optimaliseren. Hierdoor wordt voorkomen dat tussenliggende relais de DKIM-handtekening ongeldig maken, wat de authenticiteit van de berichten kan beïnvloeden. (CAMP-49016)
* De prestaties bij het dupliceren van audiences zijn verbeterd om problemen bij het werken met grote audiences te voorkomen. (CAMP-49639)
* Er is een probleem opgelost waardoor een aangepast filter de juiste resultaten niet kon weergeven bij gebruik in een **Query**-activiteit. (CAMP-49417)
* Er is een fout opgelost die een foutbericht weergaf bij een poging om een fragment te gebruiken in een levering met een komma in de naam. Het probleem is opgelost. Er kunnen nu komma&#39;s worden gebruikt in de namen van fragmenten. (CAMP-49216)

