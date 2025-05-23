---
title: E-mails ontwerpen via Adobe Campaign-integratie
description: Ontdek hoe u e-mails kunt ontwerpen via Adobe Campaign-integratie in de e-mailtoepassing van Designer.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: d5c72f69-68a2-4523-956f-f265ae79b470
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 4%

---

# E-mailontwerp met meerdere oplossingen {#multi-solution-email-design}

Adobe Campaign biedt verschillende opties voor het schrijven van e-mailberichten. U kunt oplossingen zoals Dreamweaver gebruiken om uw e-mailinhoud te bewerken en responsieve berichten te maken in de e-mail-Designer. U kunt ook inhoud via e-mail versturen met Adobe Experience Manager en deze gebruiken in uw e-mails in Adobe Campaign Standard.

## Inhoud bewerken in Dreamweaver {#editing-content-in-dreamweaver}

Dankzij de Adobe Campaign Standard-integratie met Dreamweaver kunt u de inhoud van een e-mail bewerken in de Dreamweaver-interface. U hebt toegang tot de krachtige interface van Dreamweaver om responsieve e-mailinhoud te ontwerpen en te ontwikkelen.

* **bidirectionele die** synchroniseren

  Wanneer een bewerking in het ene product wordt uitgevoerd, wordt deze in real-time in het andere product bijgewerkt. Als u de kleur van tekst in Dreamweaver wilt wijzigen, wordt de kleur van de tekst live weergegeven in Campagne. Wanneer u bovendien code selecteert in Dreamweaver of Campagne, aangezien de lijnaantallen het zelfde zijn, blijft de selectie tussen de twee producten, wat zeer nuttig is wanneer het zoeken naar iets specifiek in de code.

* **upload lokale beelden aan Adobe Campaign door Dreamweaver**

  Wanneer u een e-mailbericht maakt of bewerkt in Dreamweaver, kunt u gewoon een afbeelding op uw bureaublad of op uw lokale computer selecteren. Hoewel Dreamweaver u dit altijd heeft toegestaan, wordt het lokale bestand direct geüpload naar de Adobe Campaign-server wanneer Dreamweaver en Campagne zijn aangesloten. U hoeft de afbeeldingen niet handmatig te uploaden als de inhoud verandert. Bovendien zorgt het ervoor dat de recentste beelden altijd in Campagne leven.

* **voeg de verpersoonlijking van de Campagne in Dreamweaver** toe

  Voor de e-mailontwikkelaar is het niet langer nodig om tekst zoals `[[FIRSTNAME_PLACEHOLDER]]` toe te voegen of de syntaxis van de tabellen in het gegevensmodel op te zoeken. De werkbalk Campagne in Dreamweaver maakt rechtstreeks verbinding met het gegevensmodel van uw Campagne-instantie. Dat betekent u in om het even welke gegevens kunt trekken u voor verpersoonlijking van iets als Voornaam aan Adres wilt. Als u inhoudsblokken hebt gemaakt in de campagne, kunt u deze ook rechtstreeks naar Dreamweaver trekken.

Dit vermogen wordt gedetailleerd in de toegankelijke Documentatie van Dreamweaver [ hier ](https://helpx.adobe.com/nl/dreamweaver/using/working-with-dreamweaver-and-campaign.html).

![](assets/do-not-localize/how-to-video.png) [Ontdek deze functie in video](#video)

## Inhoud bewerken in Experience Manager {#editing-content-in-experience-manager}

E-mailinhoud kan worden bewerkt in Experience Manager en vervolgens worden gebruikt voor een of meerdere e-mailberichten in Adobe Campaign Standard. Verwijs naar [ dit document ](../../integrating/using/integrating-with-experience-manager.md).

## Productaanbiedingen {#product-listing}

>[!CONTEXTUALHELP]
>id="ac_product_listing"
>title="Productlijsten gebruiken"
>abstract="In de productaanbiedingen kunt u verwijzen naar een gegevensverzameling en deze weergeven in de e-mailcontent."

In de productaanbiedingen kunt u verwijzen naar een of meer gegevensverzamelingen in de e-mailinhoud. Deze aanbiedingen zijn beschikbaar voor transactie-e-mails. Een specifieke sectie voor deze eigenschap is beschikbaar [ hier ](../../designing/using/using-product-listings.md).

## Vergelijking van e-mailontwerpopties {#email-design-options-comparison}

Adobe Campaign biedt verschillende opties voor het schrijven van e-mailberichten. In de onderstaande tabel staan de belangrijkste mogelijkheden, voordelen en beperkingen voor elk van deze twee.

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Email Designer<br /> </th> 
   <th> Experience Manager<br /> </th> 
   <th> Dreamweaver<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <strong> Begin blanco e-mail </strong><br /> </td> 
   <td> Ondersteund <br /> </td> 
   <td> Ondersteund <br /> </td> 
   <td> Ondersteund <br /> </td> 
  </tr> 
  <tr> 
   <td> <strong> schrijf HTML </strong><br /> </td> 
   <td> Ondersteund <br /> </td> 
   <td> Niet ondersteund <br /> </td> 
   <td> Ondersteund <br /> </td> 
  </tr> 
  <tr> 
   <td> <strong> Update HTML </strong><br /> </td> 
   <td> Alleen binnen een HTML-component <br /> </td> 
   <td> Niet ondersteund <br /> </td> 
   <td> Ondersteund <br /> </td> 
  </tr> 
  <tr> 
   <td> <strong> Basisverpersoonlijking </strong><br /> </td> 
   <td> Ondersteund <br /> </td> 
   <td> Ondersteund <br /> </td> 
   <td> Ondersteund <br /> </td> 
  </tr> 
  <tr> 
   <td> <strong> Geavanceerde verpersoonlijking </strong><br /> </td> 
   <td> Ondersteund <br /> </td> 
   <td> Niet ondersteund <br /> </td> 
   <td> Niet ondersteund <br /> </td> 
  </tr> 
  <tr> 
   <td> <strong> Bewijs/Voorproef </strong><br /> </td> 
   <td> Ondersteund <br /> </td> 
   <td> Voorvertoning in AEM <br /> Proef in campagne <br /> </td> 
   <td> Voorvertonen en proefdrukken in campagne <br /> </td> 
  </tr> 
  <tr> 
   <td> <strong> de lijsten van het Product </strong><br /> </td> 
   <td> Ondersteund in e-mailtransactieberichten <br /> </td> 
   <td> Niet ondersteund <br /> </td> 
   <td> Niet ondersteund <br /> </td> 
  </tr> 
  <tr> 
   <td> <strong> Voordelen </strong><br /> </td> 
   <td> 
     <p>- Eenvoudig e-mailen dankzij slepen en neerzetten</p>
     <p>- Functies die vergelijkbaar zijn met de oude inhoudeditor</p>
     <p>- Herbruikbare inhoud met fragmenten</p>
  </td> 
   <td> 
     <p>- Elementen van website opnieuw gebruiken in e-mails</p>
     <p>- De kracht van Experience Manager in e-mailinhoud benutten</p>
    </td> 
   <td> 
    <p>- Mogelijkheid voor een ontwikkelaar om een e-mail rechtstreeks te coderen</p>
    <p>- Bi-directionele synchronisatie</p>
    <p>- Offline bewerken in Dreamweaver en later synchroniseren</p>
    <p>- Afbeeldingen uploaden naar Adobe Campaign via Dreamweaver</p>
  </td> 
  </tr> 
  <tr> 
   <td> <strong>Beperkingen</strong><br /> </td> 
   <td> 
     <p>- Geen voorwaardelijke inhoud in fragmenten</p>
     <p>- Het gebruik van Experience Manager-fragmenten is niet mogelijk</p>
  </td> 
   <td> 
     <p>- Geavanceerde personalisatie is moeilijk te implementeren</p>
     <p>- Noodzaak tests te verzenden in Adobe Campaign</p>
  </td> 
   <td> Dynamische inhoud niet ondersteund <br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Doelgroep</strong><br /> </td> 
   <td> Marketers die de flexibiliteit willen behouden om HTML-componenten te gebruiken in combinatie met functies voor slepen en neerzetten <br /> </td> 
   <td> Marketers die Experience Manager al gebruiken en die standaard e-mailsjablonen willen gebruiken met weinig personalisatie <br /> </td> 
   <td> Ontwikkelaars die e-mailinhoud willen coderen en direct met Adobe Campaign willen integreren <br /> </td> 
  </tr> 
  <tr> 
   <td> <strong> om meer te leren </strong><br /> </td> 
   <td> Zie <a href="../../designing/using/designing-content-in-adobe-campaign.md"> Ongeveer e-mail Designer </a>.<br /> </td> 
   <td> Zie <a href="../../integrating/using/integrating-with-experience-manager.md"> Integrerend met Experience Manager </a>.<br /> </td> 
   <td> Zie <a href="https://helpx.adobe.com/nl/dreamweaver/using/working-with-dreamweaver-and-campaign.html"> Dreamweaver en Campagne </a> en bekijk deze <a href="#video"> video </a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Video over zelfstudie {#video}

In deze video ziet u hoe u inhoud voor Adobe Campaign Standard kunt maken en bewerken met Dreamweaver.

>[!VIDEO](https://video.tv.adobe.com/v/23121?quality=12&captions=eng)

De extra hoe te video&#39;s van Campaign Standard zijn beschikbaar [ hier ](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=nl).
