---
title: Laatste release
description: Deze pagina bevat een overzicht van alle recente releases van Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 1cf2e40c-beca-43db-8261-a1820ee86ad3
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 5c7bfb74-4002-4ffe-87e8-bddb41d34b41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 66e480e957d12275d2ce5575c99b0808462588f9

---


# Laatste release{#latest-release}

[Release-planning](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) | [Release](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) van het regelpaneel| [Documentatiebijwerkingen](../../rn/using/documentation-updates.md) | [Opmerkingen bij](../../rn/using/release-notes-2019.md) vorige release| [Verouderde functies](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)

[Klik hier](http://amc-mkt-prod1-t.adobe-campaign.com/lp/LP25?service=%40rZ5cqp2DgNzrgz0alKPInakNbPSTeJYozZYnS7Wbs802u4GlISkHZX4omtK00nAU6xzZ6luEWQzr7kQ9pkCwJYumWkU) om u te abonneren op de release-meldingen en informatie over de nieuwste Adobe Experience Cloud-releases direct in uw Postvak IN op te halen.

## Release 20.2 - april 2020 {#release-20-2---april-2020}

**Wat is nieuw?**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Azure Blob Integration</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>De Azure Blob-opslagconnector kan nu worden gebruikt voor het importeren of exporteren van gegevens naar Adobe Campagne met behulp van een workflowactiviteit voor het <strong>overdragen van bestanden</strong> . </p>
    <p>Raadpleeg de <a href="../../administration/using/external-accounts.md#microsoft-azure-external-account">gedetailleerde documentatie</a>voor meer informatie.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Testen via e-mail met doelprofielen</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Naast testprofielen kunt u nu uw e-mails testen op echte doelprofielen. Zo kunt u een exacte weergave krijgen van het bericht dat het profiel ontvangt: aangepaste velden, dynamische en persoonlijke gegevens, inclusief aanvullende gegevens van workflows, enz. </p>
    <p>Raadpleeg de <a href="../../sending/using/testing-messages-using-target.md">gedetailleerde documentatie</a> en de <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html">zelfstudie-video</a>voor meer informatie. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Nieuwe mogelijkheden worden in april beschikbaar gesteld in het Configuratiescherm van Campagne, waaronder Google TXT-recordbeheer, bewaking van de databaseruimte en e-mailwaarschuwingen. Raadpleeg de Opmerking bij de release van het [Configuratiescherm voor meer informatie over deze functies](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html).

**Verbeteringen**

* De transnationale overseinengebruikerservaring is verbeterd en de interfaceconsistentie werd verbeterd. [Meer informatie](../../channels/using/about-transactional-messaging.md)
* Met de campagnestandaard kunt u nu proefdrukken naar testprofielen verzenden met behulp van aanvullende gegevens uit workflows.
* De handleidingen voor de externe API-activiteit zijn bijgewerkt. [Meer informatie](../../automating/using/external-api.md)

**Verbeteringen voor e-mailontwerper**

* Probleem verholpen dat invloed had op escape wanneer meerdere keren op een gepersonaliseerde afbeelding werd geklikt.
* Probleem verholpen bij het dupliceren van dynamische tekstcomponenten die kunnen leiden tot het dupliceren van de lange lijn. (CAMP-41249)
* Probleem met opvulling in Outlook verholpen bij het definiëren van opvulling op tabelniveau in plaats van op div-niveau.
* Probleem verholpen waarbij de breedte van een afbeelding werd gewijzigd wanneer naar de HTML-modus werd overgeschakeld. (CAMP-41116)
* Probleem verholpen waarbij de component sociale media niet toegankelijk was wanneer alternatieve tekst voor de pictogrammen wordt aangeboden. (CAMP-41345)
* Probleem verholpen waarbij zichtbare `<br>` tags werden weergegeven bij gebruik van kopiëren plakken in e-mailontwerper.
* Probleem verholpen waarbij HTML-tags in de e-mail werden weergegeven nadat er van HTML-inhoud naar normale tekst was overgeschakeld. (CAMP-41138)
* Probleem verholpen waarbij het renderen van knoppen met slechts één rand werd voorkomen.
* Probleem verholpen in HTML-inspringing waardoor de voettekst van e-mailberichten in Microsoft Outlook naar links werd verplaatst. (CAMP-40987)
* Probleem verholpen waarbij aanpassingsvelden die verwijzen naar een verzamelingskenmerk dat is gedefinieerd in HTML, in de normale tekstinhoud werden gekopieerd wanneer naar de modus Onbewerkte tekst werd geschakeld. (CAMP-40365)
* Probleem verholpen waarbij werd voorkomen dat koppelingen werden ingevoegd op een tekstsegment dat is geselecteerd. (CAMP-41406)
* Probleem verholpen waarbij de datum werd gewijzigd wanneer een tijdzone werd geselecteerd in de query-editor. (CAMP-38277)

**Overige wijzigingen**

* De **KPIs-afstemming met de out-of-the-box workflow van Adobe Analytics** loopt nu tot de huidige datum in plaats van één dag.
* De MCPNS steunt niet het toevoegen van APNS en APNS-SANDBOX allebei als platforms in een app. Nadat u het certificaat hebt toegevoegd in Adobe Campaign Standard, kunt u de instellingen nu niet meer wijzigen omdat er slechts één APNS-platform (productie of sandbox) aan de MCPNS-app kan worden toegevoegd.

**Integratie van ervaringsplatforms**

>[!NOTE]
>
>De functies van het Adobe Experience Platform in Campaign Standard worden momenteel in bèta weergegeven, die vaak zonder kennisgeving kan worden bijgewerkt. Raadpleeg de gedetailleerde documentatie: [Ervaring Platform Data Connector](../../administration/using/aep-about-data-connector.md), [Publiek Doelen](../../audiences/using/aep-about-audience-destinations-service.md)

* In workflowlogboeken wordt om de 10 minuten het aantal records weergegeven dat al is verwerkt door de taak die momenteel wordt uitgevoerd.
* Probleem verholpen die kon optreden bij het importeren van een Adobe Experience Platform-profiel dat uit de database was verwijderd.
* Probleem verholpen in workflowlogboeken waarbij een onjuist resultaat kon worden weergegeven voor het totale aantal geïmporteerde records.

**Patches**

* Probleem verholpen met de activiteit van de **verrijkingsworkflow** die kan optreden wanneer spaties worden toegevoegd in het veld **Alias** , dat vervolgens een nieuw rijitem heeft gemaakt. (CAMP-39229)
* Probleem verholpen waarbij elk testprofiel als doel kon worden ingesteld bij het verzenden van een proefdrukbericht.
* Oplossing voor een probleem dat optrad na het verwijderen en verwijderen van een gebeurtenisconfiguratie. [Meer informatie](../../administration/using/configuring-transactional-messaging.md#deleting-an-event)
* Probleem verholpen waarbij de knop **Opslaan** verdwijnt wanneer u wijzigingen aanbrengt in workflows.
* Probleem verholpen bij het handmatig verwijderen van een privacyaanvraag in Campagne nadat deze was verwerkt. Hierdoor konden gegevens die aan de aanvraag waren gekoppeld, niet worden verwijderd, zelfs na opschoning.
* Probleem verholpen dat kon optreden tijdens het voorvertonen of verzenden van berichten met speciale tekens van Adobe Experience Manager.
* Probleem verholpen dat in workflows kon voorkomen wanneer een activiteit met verschillende binnenkomende overgangen werd uitgevoerd.
* Probleem verholpen waarbij standaardgebruikers de &#39;Abonnementen op een toepassing&#39; niet konden gebruiken als de doeldimensie in een workflowquery of een levering. (CAMP-37618)