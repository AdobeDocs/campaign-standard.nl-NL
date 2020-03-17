---
title: Belangrijkste stappen voor het instellen van een bestemmingspagina
description: Leer de belangrijkste stappen voor het instellen van een bestemmingspagina
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c71c207d724dac914935b3667527a3ce4403dd63

---


# Aan de slag met bestemmingspagina&#39;s {#getting-started-with-landing-pages}

## Informatie over openingspagina&#39;s {#about-landing-pages}

De campagne komt met het landen pagina&#39;s die Webvormen zijn die kunnen worden gebruikt om informatie over uw publiek te vangen, abonnementen aan de dienst aan te bieden, gegevens te tonen en uw gegevensbestand te kweken. Openingspagina&#39;s kunnen ook worden gebruikt voor het aanschaffen of bijwerken van bestaande profielen.

Aanvoerpagina&#39;s kunnen ook worden gebruikt om een dubbele aanmeldingsprocedure in te stellen, zodat u het platform kunt beschermen tegen onjuiste of ongeldige e-mailadressen of spambots. Raadpleeg voor meer informatie de [speciale](../../channels/using/setting-up-a-double-opt-in-process.md)gebruikscase.

De belangrijkste stappen bij het instellen van bestemmingspagina&#39;s zijn als volgt:

![](assets/lp_steps.png)

Op deze pagina vindt u informatie over elk van deze stappen en verwijzingen naar de specifieke documentatie voor meer informatie.

**Verwante onderwerpen:**

* [Video](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/communication-channels/landing-pages/landing-page-create-and-edit.html) over het maken van zelfstudies voor landingspagina&#39;s
* [Een service maken](../../audiences/using/creating-a-service.md)
* [Een dubbele opt-in-procedure instellen](setting-up-a-double-opt-in-process.md)

## Beperkingen op landingspagina{#landing-page-limitations}

In de onderstaande sectie worden de beperkingen weergegeven die u moet kennen voordat u start met het instellen van bestemmingspagina&#39;s.

**Gegevens schrijven en bijwerken**

* Openingspagina&#39;s zijn beperkt tot **[!UICONTROL Profile]** en alleen **[!UICONTROL Subscription]** bronnen. Een record kan worden opgeslagen en bijgewerkt vanuit **[!UICONTROL Profile]** en via een abonnement of abonnement op een **[!UICONTROL Service]**.
Meer over middelenconfiguratie leren, zie het [Vormen van de de gegevensstructuur](../../developing/using/configuring-the-resource-s-data-structure.md)van het middel.

>[!CAUTION]
>
>Een landingspagina kan geen gegevens van een andere bron tonen of bijwerken dan **[!UICONTROL Profile]** en **[!UICONTROL Subscription]**.

**Vooraf laden**

* Op de bestemmingspagina kan niet automatisch een lijst met records worden weergegeven. Er kunnen geen services worden vermeld waarop profielen al zijn geabonneerd. Raadpleeg deze [pagina](../../audiences/using/creating-a-service.md)voor meer informatie over services.

* Openingspagina met een vooraf ingevuld formulier (gegevens worden vooraf met de pagina geladen) is alleen toegankelijk via een e-mailbericht voor Adobe Campagne. Een dergelijk formulier kan niet worden geopend vanaf een websitepagina.

**Verzoening**

* Het afstemmingsgedrag is als volgt: zodra een overeenkomst wordt gevonden, stopt het afstemmingsproces. Dit betekent dat de afstemming alleen kan worden uitgevoerd op één profielrecord en niet op meerdere records wanneer er duplicaten zijn.

U wilt bijvoorbeeld de volgende aanschafpagina naar uw profielen verzenden om uw Campagne-database bij te werken met de mobiele nummers van uw profielen.

![](assets/landing_page_limitation_1.png)

Als een van uw profiel uw landingspagina vult met nieuwe informatie maar al een gedupliceerd profiel heeft, wordt het overeenkomende profiel met de vroegste aanmaakdatum bijgewerkt omdat profielen alleen prioriteit krijgen op basis van de aanmaakdatum.

Hier is alleen het eerste profiel bijgewerkt sinds het de oudste vermelding was.

![](assets/landing_page_limitation_2.png)

**Testlandingspagina&#39;s**

* Het landen van pagina&#39;s werkt alleen aan profielen en niet testprofielen, wat betekent dat bestemmingspagina&#39;s niet kunnen worden getest als onderdeel van een e-mailproefdruk.

## Stap 1 - vorm het het landen paginasjabloon {#configure-the-landing-page-template}

Voordat u een bestemmingspagina instelt, moet u eerst een sjabloon voor een bestemmingspagina configureren die aan uw behoeften voldoet. Zodra het malplaatje klaar is, zullen alle het landen pagina&#39;s die op het worden gebaseerd vooraf gevormd met de gewenste parameters.

1. Selecteer / **[!UICONTROL Resources]** / **[!UICONTROL Templates]** **[!UICONTROL Landing page templates]**/ in het menu Geavanceerd via het Adobe Campagne-logo en dupliceer vervolgens de sjabloon die u wilt gebruiken.
1. Geef in de sjablooneigenschappen alle parameters op die de bestemmingspagina&#39;s gemeenschappelijk moeten hebben. Bijvoorbeeld: de doeldimensie, de toegangsparameters voor bepaalde of niet-geïdentificeerde bezoekers, acties die specifiek zijn voor formuliervalidatie door een bezoeker, het merk/logo dat/dat in de inhoud moet worden gebruikt, enz. Raadpleeg [deze sectie voor meer informatie over eigenschappen van bestemmingspagina&#39;s](../../channels/using/configuring-landing-page.md)
1. Sla uw wijzigingen op.

Raadpleeg [deze sectie](../../channels/using/getting-started-with-landing-pages.md)voor meer informatie over sjablonen voor landingspagina&#39;s.

![](assets/lp-steps1.png)

## Stap 2 - creeer en vorm de het landen pagina {#create-and-configure-the-landing-page}

Maak een nieuwe bestemmingspagina in een programma of campagne op basis van de sjabloon die in de vorige stap is gedefinieerd.

1. Maak de landingspagina op basis van de gewenste sjabloon.
1. Voer de algemene parameters van de landingspagina in (label, beschrijving, enz.).
1. Vervolgens hebt u toegang tot het dashboard voor de bestemmingspagina. Bewerk indien nodig de eigenschappen van de bestemmingspagina (zie Een openingspagina [](../../channels/using/configuring-landing-page.md)configureren). Door gebrek, zijn de eigenschappen die in het het landen paginasjabloon worden gevormd.
Om veiligheidsredenen en platformprestaties raden we u ten zeerste aan een vervaldatum in te stellen in de eigenschappen van de bestemmingspagina. Als u klaar bent, wordt de bestemmingspagina automatisch op de geselecteerde datum gepubliceerd. For more on validity parameters, refer to [this section](../../channels/using/testing-publishing-landing-page.md#setting-up-validity-parameters).

   ![](assets/lp-steps3.png)

   >[!NOTE]
   >
   >Uw wijzigingen zijn alleen effectief voor de bestemmingspagina die wordt bewerkt. Als u deze wijzigingen wilt toepassen op andere bestemmingspagina&#39;s, kunt u hen uitvoeren in een specifiek malplaatje en dan andere landende pagina&#39;s van dat malplaatje creëren.

## Stap 3 - Ontwerp de landingspagina {#design-the-landing-page}

U kunt nu de inhoud van de openingspagina definiëren. De openingspagina bevat standaard drie pagina&#39;s die via schuivende pijlen kunnen worden geopend: de hoofdpagina met inhoud, een bevestigingspagina en een foutpagina.

![](assets/lp-steps4.png)

Verscheidene gebieden worden gevormd door gebrek op elke pagina. Indien nodig, kunt u hun eigenschappen en afbeelding bewerken.

U kunt ook configureren hoe de bevestigingsknop zich gedraagt wanneer een profiel erop klikt en de inhoud aanpassen aan uw wensen (afbeelding, aanpassingsvelden, enz.). U kunt bijvoorbeeld de voornaam van een profiel invoegen op de bevestigingspagina van de bestemmingspagina om u te bedanken voor de registratie.

Raadpleeg [deze sectie](../../channels/using/designing-a-landing-page.md)voor meer informatie over het ontwerpen van bestemmingspagina&#39;s.

## Stap 4 - Test de landingspagina {#test-the-landing-page}

Als de bestemmingspagina eenmaal is gedefinieerd, kunt u simuleren hoe deze wordt uitgevoerd en zich gedraagt wanneer deze online beschikbaar is.

![](assets/lp-steps5.png)

>[!CAUTION]
>
>De landingspagina-tests kunnen alleen worden uitgevoerd met profielen en niet met testprofielen. Wanneer het formulier wordt verzonden, worden de gegevens van het geselecteerde profiel bijgewerkt voor real-time. Als u wilt voorkomen dat echte profielen worden gewijzigd, gebruikt u een onecht klantprofiel.

Als u tevreden bent met de manier waarop de bestemmingspagina zich gedraagt, kunt u het publiceren om het online ter beschikking te stellen.

Raadpleeg [deze sectie](../../channels/using/testing-publishing-landing-page.md#testing-the-landing-page-)voor meer informatie over het testen van een bestemmingspagina.

## Stap 5 - Publiceer de landingspagina {#publish-the-landing-page}

Als de tests zijn voltooid, kunt u de bestemmingspagina publiceren met de **[!UICONTROL Publish]** knop op de actiebalk in het dashboard. Een controleblok geeft de voortgang en status van de publicatie aan.

Door de bestemmingspagina te publiceren, kunt u deze online openen. Na publicatie kunt u deze altijd bijwerken: om dit te doen, moet u het na elke wijziging opnieuw publiceren. U kunt de publicatie van een bestemmingspagina ook op elk gewenst moment ongedaan maken, zodat deze niet meer beschikbaar is.

![](assets/lp-steps6.png)

Na publicatie is de bestemmingspagina klaar om te worden gebruikt. Vervolgens kunt u verschillende mechanismen instellen waarmee u toegang hebt tot het programma voor het aanschaffen van nieuwe profielen in uw database of voor het verkrijgen van aanvullende informatie over bestaande profielen.

Raadpleeg [deze sectie](../../channels/using/testing-publishing-landing-page.md#publishing-a-landing-page)voor meer informatie over het publiceren van bestemmingspagina&#39;s.
