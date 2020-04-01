---
title: Het gebruiken van de Dynamica 365 van Microsoft met de Standaardintegratie van de Campagne
description: Leer hoe te om de Dynamica 365 van Microsoft met de integratie van de Standaard van de Campagne te gebruiken
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bff3b8f8f58c491e4010d24132b0fa3e93c3a7ab

---


# Het gebruiken van de Dynamica 365 van Microsoft met de Standaardintegratie van de Campagne

Deze integratie biedt verschillende functies:

* **Contactsynchronisatie**: De contacten worden verzonden van Dynamiek 365 naar Campagne (nota: eenzijdige synchronisatie).
* **Aangepaste entiteitssynchronisatie**: De entiteitverslagen van de douaneentiteit worden verzonden van Dynamiek 365 naar Campagne (nota unidirectionele synchronisatie).  Zie de pagina over aangepaste entiteiten voor meer informatie.
* **Weergave** gebeurtenis: Bepaalde e-mailmarketinggebeurtenissen worden vanuit Campagne verzonden naar Dynamics 365. Zie onderstaande opmerking.
* **Contactverwijdering**: Campagneprofiel wordt toegevoegd aan de verwijderingswachtrij met betrekking tot privacy wanneer de bijbehorende contactpersoon wordt verwijderd in Dynamics 365.
* **Synchronisatie** uitschakelen: Opt-outs worden gesynchroniseerd tussen Dynamiek 365 en Campagne afhankelijk van de configuratie die de klant tijdens onboarding selecteert (d.w.z., Dynamiek 365 aan de synchronisatie van de Campagne, Campagne aan Dynamiek 365 synchronisatie, of bidirectionele synchronisatie).
* **Single Sign On (SSO)**: Uw integratiedetails in Unifi kunnen direct van Campagne worden betreden, gebruikend uw authentificatie van Adobe IMS.

>[!NOTE]
>
>Voor de weergave **van** gebeurtenissen worden maximaal 10 k gebeurtenissen opgehaald wanneer de egress-taak in Unifi wordt uitgevoerd.

## Adobe Campagne Standard - Gebruikerservaring

Wanneer een contact nieuw of gewijzigd in Dynamiek 365 wordt gecreeerd, zal het over aan Campagne worden gesynchroniseerd nadat de synchronisatie van Contacten in werking is gesteld.  Deze contacten zullen in het scherm van Profielen in Campagne zichtbaar zijn en kunnen in marketing campagnes worden gericht.  Zie het scherm Profielen hieronder.

![](assets/MSdynamicsACS-usage1.png)

Wanneer een contact in Dynamiek 365 wordt geschrapt, wordt het overeenkomstige profiel in Campagne toegevoegd aan de rij van de privacydienst schrapt in het scherm van het Verzoek van de Privacy in Campagne.  Voor meer informatie over het uitvoeren van gegevenssubject kunt u verzoeken verwijderen die vereist zijn om te voldoen aan de toepasselijke privacywetten voor gegevens in Campagne. Raadpleeg &#39;Hoe kan ik aanvragen voor verwijderen met een wettelijke machtiging uitvoeren&#39; in Adobe Campagnestandaard.

![](assets/MSdynamicsACS-usage2.png)

Het is belangrijk om op te merken dat als u het proces in twee stappen hebt geactiveerd in het eigenschappenscherm, u de verwijdering van elke record in het privacyscherm handmatig moet bevestigen voordat deze definitief worden verwijderd.  Zie het processcherm in twee stappen hieronder:

![](assets/MSdynamicsACS-usage3.png)

Wanneer een opt-out/blacklist-kenmerk wordt gewijzigd in Campagne, wordt dit weergegeven in Dynamics 365 als u de Camera-to-Dynamics 365 of de bidirectionele opt-out-configuratie hebt geselecteerd en als dat specifieke kenmerk correct is toegewezen.

Om tot uw integratiedetails via enig teken toegang te hebben, ga naar het menu van de Navigatie van de Campagne en klik Beleid > de Integratie van de Dynamica 365 van Microsoft.

![](assets/sso_d365_admin_panel.png)

Deze pagina bevat koppelingen naar documentatie over de integratie en richtlijnen voor het gebruik van de functies in overeenstemming met uw potentiële wettelijke verplichtingen. Klik op het pictogram van de bol, dat automatisch zal leiden en u in uw instantie van Unifi registreren waar u uw integratiedetails kunt beheren.

In de onderstaande video ziet u een video van deze functionaliteit.

>[!VIDEO](https://video.tv.adobe.com/v/29254)

>[!NOTE]
>
>U moet een ticket naar de klantenservice van Adobe verzenden (rechtstreeks of via uw Adobe-contactpersoon) om de markering voor eenmalige aanmelding in uw Campagne te kunnen gebruiken.

![](assets/sso_screen.png)

>[!NOTE]
>
>U zult niet het pictogram van de Integratie van de Dynamica 365 van Microsoft in uw admin paneel uit-van-de-doos zien.  U (of uw Adobe-contactpersoon) moet een ticket verzenden om deze functiemarkering voor uw Campagne-instantie te laten inschakelen.
>
>Ook, zal Unifi gebruikers voor SSO toegang moeten toelaten alvorens zij met succes via SSO van Campaign kunnen aanmelden.

## Gebruikerservaring voor Microsoft Dynamics 365

Voor gebeurtenisweergave worden de volgende e-mailmarketinggebeurtenissen verzonden van Campagne naar Dynamics 365 en weergegeven in de tijdlijnweergave van Dynamics 365 als aangepaste activiteiten:

* E-mailbericht voor Adobe-campagne verzenden

* Adobe Campagne-e-mail openen

* URL voor campagne van Adobe via e-mail klikken

* Bounce voor e-mailcampagne van Adobe

Om de Chronologie van een contact te bekijken, navigeer aan uw contactenlijst door op de Hub van de Verkoop van de Dynamiek 365 drop-down menu te klikken.  Klik vervolgens op Contactpersonen op de linkermenubalk en selecteer een contactpersoon.

>[!NOTE]
>
>De Adobe-campagne voor dynamiek 365-app in AppSource moet zijn geïnstalleerd in uw instantie Dynamics 365 om deze gebeurtenissen te kunnen weergeven.

Hieronder ziet u een momentopname van het scherm van het Contact voor &quot;Gebruiker van de Dynamiek&quot;.  In de mening van de Chronologie, zult u merken dat de Gebruiker van de Dynamiek een e-mail werd verzonden verbonden aan de Naam van de Campagne &quot;2019LoyaltyCamp&quot;en de Naam van de Levering &quot;DM190&quot;.  Dynamics User opende het e-mailbericht en klikte ook een URL in e-mail; beide acties hebben gebeurtenissen gemaakt die ook hieronder worden weergegeven .  Als u naar de rechterhoek kijkt, ziet u de RA-kaart (Relationship Assistant). bevat momenteel een taak die moet worden opgevolgd op de aangeklikte URL.

![](assets/MSdynamicsACS-usage4.png)

Zie hieronder voor een close-up van de mening van de Chronologie voor de Gebruiker van de Dynamiek.

![](assets/MSdynamicsACS-usage5.png)

Hieronder volgt een close-up van de Relationship Assistant-kaart (RA).  De app AppSource bevat een workflow die zoekt naar een Adobe-gebeurtenis Click URL.  Wanneer deze gebeurtenis zich voordoet, wordt een taak gemaakt en wordt een vervaldatum ingesteld.  Hierdoor kan de taak worden weergegeven in de RA-kaart, waardoor deze meer zichtbaar wordt.  Er is een vergelijkbare workflow voor Adobe e-mailstuitgebeurtenissen, waarbij u een taak toevoegt om het ongeldige e-mailadres te combineren.  Deze workflows kunnen in de oplossing worden uitgeschakeld.

![](assets/MSdynamicsACS-usage6.png)

Als u klikt op het onderwerp van de verzendgebeurtenis, ziet u een formulier dat lijkt op het hieronder weergegeven formulier.  De formulieren voor open en bounce-gebeurtenissen zijn vergelijkbaar.

![](assets/mirror_page_url_send.png)

Het formulier voor URL-klikgebeurtenissen voor e-mail voegt een extra kenmerk toe voor de URL waarop is geklikt:

![](assets/mirror_page_url_click.png)

Hieronder volgt een lijst met kenmerken en een beschrijving:

* Betreft: onderwerp van het evenement; die bestaat uit de campagne-id en de bezorgings-id van de e-maillevering

* Eigenaar: De gebruiker van de toepassing die in de post-levering stappen wordt gecreeerd

* Betreffende: De naam van de contactpersoon

* Naam campagne: Campagne-id in Campagnestandaard

* Naam van levering: De leverings-id in de standaard

* Datum van verzending/openen/klikken/teruglopen: Datum/tijd waarop de gebeurtenis is gemaakt

* URL bijhouden: URL waarop is geklikt

* URL spiegel: De URL naar de spiegelpagina van het e-mailbericht dat is verzonden/geopend/geklikt/teruggestuurd

In de onderstaande video ziet u een video van de URL van de spiegelpagina die wordt gebruikt.

>[!VIDEO](https://video.tv.adobe.com/v/29253)

>[!NOTE]
>
>Voor opt-out, wanneer een opt-out attribuut in Dynamiek 365 wordt gewijzigd, zal het in Campagne worden weerspiegeld als u de Dynamiek 365-aan-Campagne of bidirectionele opt-out configuratie hebt geselecteerd, en als u die bepaalde eigenschap correct in kaart gebracht hebt.

**Verwante onderwerpen**

* Campagne voor de integratie van Campaign/Dynamics 365 configureren
* Dynamiek configureren voor integratie van Campagne/Dynamics 365
* Unifi configureren voor integratie van Campagne/Dynamics 365
* Leer hoe u aangepaste bronnen en aangepaste entiteiten kunt toewijzen