---
title: 'E-mails ontwerpen via Adobe Campagne-integratie '
description: Ontdek hoe u e-mails kunt ontwerpen via de integratie van Adobe Campagne in de e-mailontwerper.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d8a46a53f2abd453aaf0ff8322b7f9b942ec1c6

---


# E-mailontwerp met meerdere oplossingen {#multi-solution-email-design}

Adobe Campaign biedt verschillende opties voor het schrijven van e-mails. U kunt oplossingen zoals Dreamweaver gebruiken om uw e-mailinhoud te bewerken en responsieve berichten te maken in de e-mailontwerper. U kunt inhoud ook via e-mail verzenden met Adobe Experience Manager en deze gebruiken in uw e-mails in Adobe Campagne Standard.

## Inhoud bewerken in Dreamweaver {#editing-content-in-dreamweaver}

Met de integratie van Adobe Campaign Standard met Dreamweaver kunt u de inhoud van een e-mailbericht bewerken in de Dreamweaver-interface. U hebt toegang tot de krachtige interface van Dreamweaver om responsieve e-mailinhoud te ontwerpen en te ontwikkelen.

* **Bidirectionele synchronisatie**

   Wanneer een bewerking in het ene product wordt uitgevoerd, wordt deze in real-time in het andere product bijgewerkt. Als u de kleur van tekst in Dreamweaver wilt wijzigen, wordt de kleur van de tekst live weergegeven in Campagne zodra u die bewerking uitvoert. Wanneer u bovendien code selecteert in Dreamweaver of Campagne, aangezien de lijnaantallen het zelfde zijn, blijft de selectie tussen de twee producten, wat zeer nuttig is wanneer het zoeken naar iets specifiek in de code.

* **Lokale afbeeldingen uploaden naar Adobe-campagne via Dreamweaver**

   Wanneer u een e-mailbericht maakt of bewerkt in Dreamweaver, kunt u gewoon een afbeelding selecteren op uw bureaublad of op uw lokale computer. Hoewel u dit altijd hebt toegestaan in Dreamweaver, wordt het lokale bestand direct geüpload naar de Adobe Campagneserver wanneer Dreamweaver en Campagne worden verbonden: hoeven afbeeldingen niet handmatig te uploaden wanneer de inhoud verandert. Bovendien zorgt het ervoor dat de recentste beelden altijd in Campagne leven.

* **Aanpassing campagne toevoegen in Dreamweaver**

   Voor de e-mailontwikkelaar is het niet langer nodig om tekst als `[[FIRSTNAME_PLACEHOLDER]]` of de syntaxis van de tabellen van uw gegevensmodel toe te voegen. De werkbalk Campagne in Dreamweaver maakt rechtstreeks verbinding met het gegevensmodel van uw Campagne-instantie. Dat betekent u in om het even welke gegevens kunt trekken u voor verpersoonlijking van iets als Voornaam aan Adres wilt. Als u inhoudsblokken hebt gemaakt in de campagne, kunt u deze ook rechtstreeks naar Dreamweaver trekken.

Deze mogelijkheid wordt beschreven in de Dreamweaver-documentatie die [hier](https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html)kan worden geraadpleegd. Er is ook een [demonstratievideo](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html) beschikbaar.

## Inhoud bewerken in Experience Manager {#editing-content-in-experience-manager}

E-mailinhoud kan worden bewerkt in Experience Manager en vervolgens worden gebruikt voor een of meerdere e-mailberichten in Adobe Campagne Standard. Raadpleeg [dit document](../../integrating/using/integrating-with-experience-manager.md).

## Vergelijking van e-mailontwerpopties {#email-design-options-comparison}

Adobe Campaign biedt verschillende opties voor het schrijven van e-mails. In de onderstaande tabel staan de belangrijkste mogelijkheden, voordelen en beperkingen voor elk van deze twee.

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> E-mailontwerper<br /> </th> 
   <th> Experience Manager<br /> </th> 
   <th> Dreamweaver<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <strong>Lege e e e e-mail starten</strong><br /> </td> 
   <td> Ondersteund<br /> </td> 
   <td> Ondersteund<br /> </td> 
   <td> Ondersteund<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HTML schrijven</strong><br /> </td> 
   <td> Ondersteund<br /> </td> 
   <td> Niet ondersteund<br /> </td> 
   <td> Ondersteund<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HTML bijwerken</strong><br /> </td> 
   <td> Alleen binnen een HTML-component<br /> </td> 
   <td> Niet ondersteund<br /> </td> 
   <td> Ondersteund<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Basisverpersoonlijking</strong><br /> </td> 
   <td> Ondersteund<br /> </td> 
   <td> Ondersteund<br /> </td> 
   <td> Ondersteund<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Geavanceerde personalisatie</strong><br /> </td> 
   <td> Ondersteund<br /> </td> 
   <td> Niet ondersteund<br /> </td> 
   <td> Niet ondersteund<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Proef/voorvertoning</strong><br /> </td> 
   <td> Ondersteund<br /> </td> 
   <td> Voorvertonen in AEM<br /> -proefdruk in campagne<br /> </td> 
   <td> Voorvertonen en proefdrukken in campagne<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Productaanbiedingen</strong><br /> </td> 
   <td> Ondersteund in e-mailtransactieberichten<br /> </td> 
   <td> Niet ondersteund<br /> </td> 
   <td> Niet ondersteund<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Voordelen</strong><br /> </td> 
   <td> 
     <p>- Eenvoudig e-mailen dankzij slepen en neerzetten</p>
     <p>- Functies die vergelijkbaar zijn met de oude inhoudeditor</p>
     <p>- Herbruikbare inhoud met fragmenten</p>
  </td> 
   <td> 
     <p>- Elementen van website opnieuw gebruiken in e-mails</p>
     <p>- De kracht van Experience Manager benutten voor e-mailinhoud</p>
    </td> 
   <td> 
    <p>- Mogelijkheid voor een ontwikkelaar om een e-mail rechtstreeks te coderen</p>
    <p>- Bi-directionele synchronisatie</p>
    <p>- Offline bewerken in Dreamweaver en later synchroniseren</p>
    <p>- Afbeeldingen uploaden naar Adobe Campagne via Dreamweaver</p>
  </td> 
  </tr> 
  <tr> 
   <td> <strong>Beperkingen</strong><br /> </td> 
   <td> 
     <p>- Geen voorwaardelijke inhoud in fragmenten</p>
     <p>- Het gebruik van fragmenten in Experience Manager is niet mogelijk</p>
  </td> 
   <td> 
     <p>- Geavanceerde personalisatie is moeilijk te implementeren</p>
     <p>- Moet tests verzenden in Adobe Campaign</p>
  </td> 
   <td> Dynamische inhoud wordt niet ondersteund<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Publiek</strong><br /> </td> 
   <td> Marketers die de flexibiliteit willen behouden om HTML-componenten te gebruiken in combinatie met functies voor slepen en neerzetten<br /> </td> 
   <td> Marketers die de functie Experience Manager al gebruiken en die standaard e-mailsjablonen willen gebruiken met weinig personalisatie<br /> </td> 
   <td> Ontwikkelaars die e-mailinhoud willen coderen en deze rechtstreeks willen integreren met Adobe Campagne<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Meer informatie</strong><br /> </td> 
   <td> Zie <a href="../../designing/using/designing-content-in-adobe-campaign.md">Informatie over de e-mailontwerper</a>.<br /> </td> 
   <td> Zie <a href="../../integrating/using/integrating-with-experience-manager.md">Integreren met Experience Manager</a>.<br /> </td> 
   <td> Zie <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver en Campagne</a> en bekijk deze <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">video</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>
