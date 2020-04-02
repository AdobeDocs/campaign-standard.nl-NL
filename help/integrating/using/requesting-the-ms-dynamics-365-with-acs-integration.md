---
title: Het vragen van en het vormen van de Dynamica 365 van Microsoft met de Standaardintegratie van de Campagne
description: Leer hoe te om de Dynamica 365 van Microsoft met de integratie van de Standaard van de Campagne te vragen en te vormen
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
source-git-commit: 4dd1ada05b6681a4e2f7676b177747bdfb0e9bff

---


# Het vragen van de Dynamica 365 van Microsoft met de integratie van de Standaard van de Campagne

Om deze integratie mogelijk te maken, moet u de onderstaande stappen volgen.

Houd er rekening mee dat deze integratie gebruikmaakt van een externe provider, Unifi.  In verband met uw verzoeken om ondersteuning is Adobe mogelijk vereist om uw Adobe Campagne-instantie-informatie te delen met Unifi.

Volg hieronder het stroomschema en de stroomdiagramdetails om de integratie aan te vragen en te vormen.

![](assets/provisioning-wf.png)

Stroomdiagramdetails (afbeeldingen tot bovenstaande stappen):

1. U moet reeds de Norm van de Campagne en Dynamica 365 van Microsoft provisioned, met admin toegang hebben om deze integratie te beginnen uitvoeren.

1. Lees dit artikel, controleer berichten en configuratiestappen.

1. Stuur een accountverzoek naar adobe-support@unifisoftware.com; Unifi vereist de volgende informatie wanneer u een account aanvraagt:
   * Voornaam gebruiker
   * Achternaam gebruiker
   * E-mail gebruiker
   * Bedrijfsnaam
   * Regio (Noord-Amerika, EMEA of APAC)
   * Gebruikstype:  Het Type van klant (klantengebruikers die hun productiegegevens in deze integratie zullen gebruiken), of het Type van Partner (partneradviseurs die uit de integratie testen om een beter inzicht te krijgen zodat zij hun klanten van de Campagne kunnen helpen) of Intern Type (de interne gebruikers van Adobe die de integratie uittesten om een beter inzicht in de oplossing te krijgen)
   * De standaardgegevensstatus van de campagne (die met schone gegevensbestand beginnen of bestaande gegevens aan integratie brengen)
   * Identiteitskaart van de Aannemer van de campagne (zie Vorm de sectie van de integratie van de Campagne 3 om uw identiteitskaart van de Aannemer te krijgen)
   * URL van campagneexemplaar
   Unifi-verwachte responstijd: 1 uur tijdens normale kantooruren in de VS (9.00 tot 17.00 uur Pacific Time, ma - vrijdag, met uitzondering van feestdagen).

1. Voltooi de stappen na levering voor de Dynamica 365 van Microsoft en voor de Norm van de Campagne.
Stuur bovendien een ticket naar de klantenservice van Adobe (rechtstreeks of via uw Adobe-contactpersoon) om de markering voor eenmalige aanmelding in uw Campagne in te schakelen. Partners moeten hun Adobe-partner sandbox-vertegenwoordiger bereiken en in plaats daarvan contact opnemen met de klantenservice van Adobe om de functiemarkering in te schakelen.
Als u bestaande gegevens in Campagne hebt die u van plan bent om in de integratie op te nemen, dan volg de richtlijnen in &quot;Bestaande Gegevens van de Campagne&quot;en raadpleeg nauw met uw technische contact van Adobe alvorens te werk te gaan.

1. Voltooi de eerste instapstappen in Unifi door naar Unifi te navigeren, door onboarding screens te klikken, Dynamics 365 en Campaign Standard account credentials in te vullen en Unifi op de hoogte te brengen wanneer deze zijn voltooid.

1. Unifi zal de klant om hun gewenste opt-out configuratie en opt-out kenmerkafbeelding vragen.

1. De klant zal op de geselecteerde opt-out configuratie en opt-out kenmerkafbeelding wijzen.
Unifi-verwachte responstijd: 1 werkdag (maandag t/m vrijdag, met uitzondering van feestdagen)

1. Als u Unifi configureert, moet u OOTB-toewijzingen, filters, taken, enzovoort controleren. en indien nodig wijzigingen aan te brengen.  Zie de Unifi-gebruikershandleiding voor meer informatie.
Bij deze stap wordt de uitvoeringsfrequentie van de Unifi-schema&#39;s ingesteld
* Stel de uitvoeringsfrequentie van de schema&#39;s in het planningsscherm in Unifi in; voor ingress- en egress-planningen voert u deze echter één keer handmatig uit voordat u de planningsfrequentie instelt
* De volgende doseringsfrequenties worden aanbevolen: Ingress (15 minuten), Egress (15 minuten), Deletes (eenmaal per dag), Opt-Outs (eenmaal per dag)

**Het wordt aanbevolen om met Unifi en/of Adobe Consulting (neem contact op met uw Adobe-accountteam) te werken bij het configureren van Unifi.**

Om de integratie tussen de Norm van de Campagne van Adobe en de Dynamica 365 van Microsoft toe te laten, moeten de klanten een gebruikersrekening met Unifi, een derdeleverancier tot stand brengen, zoals die in dit document wordt beschreven.   Als eindgebruiker van het Unifi-systeem moet de klant voor alle vragen met betrekking tot gegevensverzoeken die door de klant binnen het Unifi-systeem worden geïnitieerd, contact opnemen met Unifi.

## Deze integratie configureren

Voor deze integratie moeten drie systemen worden ingericht en geconfigureerd: Adobe Campaign Standard, Microsoft Dynamics 365 for Sales en Unifi. De artikelen van de configuratie zijn hieronder verbonden.

>[!CAUTION]
>
>Voor elk systeem, moeten deze stappen door een beheerder worden uitgevoerd.
>
>De stappen in de onderstaande artikelen begeleiden u bij het maken van integraties/registraties die het toewijzen van machtigingen en/of beheerderstoegang inhouden.  Het is uw verantwoordelijkheid om ervoor te zorgen dat deze stappen voldoen aan uw bedrijfsbeleid alvorens uit te voeren, en hen zorgvuldig uit te voeren.

In ADOBE CAMPAIGN moet u API-toegang instellen en een nieuwe integratie voor Unifi configureren. Raadpleeg [dit artikel](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)om dit te bereiken.

In MICROSOFT DYNAMICS 365, moet u een nieuwe toepassingsregistratie tot stand brengen en een toepassingsgebruiker toelaten om de integratie te gebruiken.  Om de Dynamiek 365 van Microsoft voor deze integratie te vormen, verwijs naar [dit artikel](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

In UNIFI, moet u integratie opzetten en afbeelding vormen of douanekenmerken toevoegen. Raadpleeg [dit artikel](../../integrating/using/configure-unifi-for-microsoft-dynamics-365-integration.md)om Unifi voor deze integratie te configureren.

## Ondersteuning aanvragen

Neem contact op met de UNIFI-klantenondersteuning als u problemen ondervindt: [support@unifisoftware.atlassian.net](mailto:support@unifisoftware.atlassian.net).

Unifi-verwachte responstijd: 4 uur tijdens normale kantooruren in de VS (9.00 tot 17.00 uur Pacific Time, ma - vrijdag, met uitzondering van feestdagen).

>[!CAUTION]
>
>In verband met uw verzoek om ondersteuning kan het zijn dat Adobe vereist is om uw Adobe Campagne-instantie-informatie te delen met Unifi.