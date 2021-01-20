---
title: 'Aan de slag met het integratieprogramma '
description: Aan de slag met het integratieprogramma
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: 1e05db3fecc87a026750f40acb0ff063706e3f38
workflow-type: tm+mt
source-wordcount: '1071'
ht-degree: 2%

---


# Aan de slag met de integratie-app {#gs-self-service-app} voor zelfbediening

De integratie van Adobe Campaign Standard met de zelfbedieningstoepassing van de Integratie van de Dynamica 365 van Microsoft geeft u de capaciteit om gegevensstromen te vormen, te controleren of zij lopen, en waarin milieu. U moet echter een aantal voorwaarden voltooien voordat u de toepassing voor zelfintegratie gaat gebruiken.

## Concepten en beperkingen {#concepts-and-restrictions}

Voordat u begint met het integratieprogramma, moet u de concepten en instructies begrijpen die aan de integratie zijn gekoppeld en een aantal eerste stappen ondernemen om toegang te krijgen.

Meer informatie vindt u in deze secties:

* [Aan de slag met de integratie van Microsoft Dynamics 365](../../integrating/using/d365-acs-get-started.md)
* [Aanbevolen werkwijzen en beperkingen voor integratie](../../integrating/using/d365-acs-notices-and-recommendations.md)
* [Belangrijke stappen leren om deze integratie te implementeren](../../integrating/using/d365-acs-get-started.md#request-and-implement-this-integration)
* [De integratie van Microsoft Dynamics 365 gebruiken](../../integrating/using/d365-acs-using-the-integration.md)

## Vereisten {#self-service-app-prerequisites}

U moet Microsoft Dynamics 365 en Adobe Campaign Standard zodanig configureren dat de integratie-app toegang heeft tot uw gegevens. Dit zal wat tijd vergen om in Dynamica 365, Adobe Campaign Standard, en Adobe I/O te vormen; nochtans, zodra zij worden gevormd, zult u de integratie door het gebruikersinterface van de zelfbedieningstoepassing kunnen controleren.

Meer informatie vindt u in deze secties:

* [De integratie van Microsoft Dynamics 365 voor Campaign configureren](../../integrating/using/d365-acs-configure-d365.md)
* [Adobe I/O configureren](../../integrating/using/d365-acs-configure-adobe-io.md)
* [Aangepaste bronnen voor campagne toewijzen en aangepaste entiteiten voor Microsoft Dynamics 365](../../integrating/using/d365-acs-notices-and-recommendations.md)

## Belangrijke stappen voor het configureren van de integratie-app {#self-service-app-configuration-steps} voor zelfbediening

U kunt dan met het integratiehulpmiddel beginnen. Voer de volgende stappen uit:

1. [Toegang tot de integratie-app krijgen](../../integrating/using/d365-acs-self-service-app-control-access.md)
1. [De integratie-app voor uw gebruik configureren](../../integrating/using/d365-acs-self-service-app-settings.md)
1. [Gegevenssynchronisatie implementeren](../../integrating/using/d365-acs-self-service-app-data-sync.md)
1. [Synchronisatieworkflows configureren](../../integrating/using/d365-acs-self-service-app-workflows.md)

## Koppeling naar de integratie-app {#self-service-app-link}

Open een browser en blader aan de schakelaar verbonden aan uw gebied:

* [Azië, Stille Oceaan](http://d365-acs-ap.ea.adobe.com/)
* [Europa, Midden-Oosten of Afrika (EMEA)](http://d365-acs-em.ea.adobe.com/)
* [Amerika](http://d365-acs-na.ea.adobe.com/)

## Bevestiging van privacyverzoek {#self-service-app-acknowledgement}

Wanneer het doorbladeren aan zelfbediening UI voor het eerst, zult u met de privacyerkenning worden voorgesteld. U moet erkennen dat u uw rol in het uitvoeren van privacyverzoeken in Campagne en de Dynamica 365 van Microsoft afzonderlijk begrijpt alvorens u kunt verdergaan.
Meer informatie over uw privacyverantwoordelijkheden en over het beheren van privacyverzoeken vindt u in [deze sectie](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).

## Uw referenties instellen {#self-service-app-credentials}

Wanneer u voor het eerst naar de gebruikersinterface bladert, wordt een pagina met een koptekst weergegeven die er als volgt uitziet:

![](assets/d365-to-acs-ui-header.png)

>[!NOTE]
>
> Het is normaal om alarm te krijgen die erop wijzen dat het &quot;niet&quot;met Adobe Campaign Standard of de Dynamica 365 van Microsoft kan verbinden als de toepassingsmontages nog niet zijn gevormd.

Controleer of de selecties &quot;ORG&quot; en &quot;INSTANTIE&quot; de selecties zijn die u wilt configureren.  Als dat niet het geval is, klikt u op de vervolgkeuzelijst en selecteert u de juiste org en variant.

>[!IMPORTANT]
>
> Als u de connector voor het eerst configureert en/of als u nog niet vertrouwd bent met dit proces, wordt u aangeraden **strongly** te selecteren om de instantie &quot;stage&quot; of &quot;dev&quot; te selecteren. U zult ervoor willen zorgen om te verifiëren dat uw configuratie goed alvorens de opstelling in productie te proberen werkt.

Als u over de juiste org en instantie beschikt, klikt u op het menu &quot;hamburger&quot; om een vervolgkeuzemenu weer te geven. Klik vervolgens op **[!UICONTROL Settings...]** in de keuzelijst om de pagina te bezoeken waarop u uw referenties voor Microsoft Dynamics 365 en Campagne (zie hieronder) invoert.

![](assets/d365-to-acs-ui-page-workflows-menu-pointers.png)

Vul de volgende secties in op de pagina **[!UICONTROL Settings]**:

* Microsoft Dynamics 365 Credentials
* Adobe Credentials

Ga [hier](../../integrating/using/d365-acs-self-service-app-settings.md) om gedetailleerdere informatie over te vinden waar te om de informatie voor elke input te vinden. Wanneer u wordt gedaan, klik **[!UICONTROL Save]** knoop bij de bodem.

## Controleer de eerste configuratie {#self-service-app-initial-config}

Ervan uitgaande dat u de bovenstaande voorwaarden hebt voltooid en dat u al uw referenties correct hebt toegevoegd, gaan we nu naar de pagina **[!UICONTROL Workflows]**. Meer informatie over de workflows van de integratie-app vindt u op [deze pagina](../../integrating/using/d365-acs-self-service-app-workflows.md).

Klik op de pagina **[!UICONTROL Workflows]** op het potloodpictogram dat is gekoppeld aan de **[!UICONTROL Microsoft Dynamics 365 to Campaign]**-workflow om de configuratie ervan te bewerken.

![](assets/d365-to-acs-ui-page-workflows-ingress-edit-pointer.png)

Op de **[!UICONTROL Microsoft Dynamics 365 to Campaign]** pagina, kunt u tot de lijst van de lijstafbeeldingen toegang hebben die u hebt gevormd.  U wordt standaard toegewezen aan een contact-/profieltoewijzing buiten het vak. Alle andere aangepaste entiteiten moeten afzonderlijk worden geconfigureerd.

![](assets/d365-to-acs-ui-page-ingress-top-pointers.png)

Controleer op de pagina **[!UICONTROL Edit Table Mapping]** de sectie **[!UICONTROL Mappings]** om ervoor te zorgen dat de gebieden van de Dynamica 365 van Microsoft aan het correcte gebied in Campagne in kaart worden gebracht. Als u andere toewijzingen moet toevoegen, doet u dit nu, evenals om het even welke vervangingen of filters. [Meer informatie](../../integrating/using/d365-acs-self-service-app-data-sync.md).

Als u nieuwe afbeeldingen wilt toevoegen, raadpleegt u [deze sectie](../../integrating/using/d365-acs-self-service-app-data-sync.md#add-a-new-mapping) voor meer informatie.

Wanneer de configuratie juist is, klikt u op de **[!UICONTROL Play]** knop naast de **[!UICONTROL Microsoft Dynamics 365 to Campaign]** workflow om de integratie en de gegevensstroom te starten.

>[!IMPORTANT]
>
>Wij **sterk** adviseren dat u dit eerst in uw milieu&#39;s van het Stadium of van het Dev in werking stelt alvorens in Productie in werking te stellen. Controleer of de instantie stage/dev is geselecteerd in de koptekst.


![](assets/d365-to-acs-ui-page-workflows-ingress-play-pointer.png)

Als deze eenmaal is gestart, kunt u testen door items toe te voegen of te wijzigen in Microsoft Dynamics 365 en deze wijzigingen binnen een paar minuten te observeren in Adobe Campaign. Als u dit proces op elk gewenst moment moet stoppen, drukt u gewoon op dezelfde knop om het te stoppen. [Meer informatie](../../integrating/using/d365-acs-self-service-app-workflows.md#workflow-status)


## De werkruimte van de integratie-app {#self-service-app-workspace}

### App-koptekst {#app-header}

Met de header in de zelfbedieningsapp kunt u definiëren welke org en instantie u momenteel bekijkt en/of configureert.

Selecteer **ORG** en **INSTANTIE** u wilt bekijken/uitgeven. Deze velden worden alleen-lezen weergegeven, maar kunnen worden bewerkt wanneer u de muiscursor erop plaatst.

Er wordt een vervolgkeuzemenu weergegeven wanneer u op de knop klikt met de drie horizontale lijnen ![](assets/d365-to-acs-icon-hamburger.png) rechts van de koptekst.

De items in het vervolgkeuzemenu zijn

* **Instellingen**: Als u deze optie selecteert, wordt u naar een scherm gestuurd waarin u API-referenties kunt opgeven voor Microsoft Dynamics 365 en Adobe Campaign en andere algemene instellingen voor de toepassing.

* **Documentatie**: Deze optie is een koppeling naar de Adobe Campaign-documentatie die specifiek is voor deze integratie

* **Klantenservice**: Dit is een koppeling naar de documentatie van Experience Cloud met betrekking tot het openen van een ticket voor de klantenservice

* **Afmelden**: Hiermee meldt u zich af van de toepassing en kunt u zich weer aanmelden als een andere gebruiker.

* **Informatie over**: Dit toont een dialoog die informatie over de toepassing, met inbegrip van auteursrechtinformatie bevat.

### Broodkruimels {#app-breadcrumbs}

Terwijl u door de app navigeert, worden er onder aan bepaalde schermen balken weergegeven.

**Voorbeeld:**

Hieronder ziet u een voorbeeld van het scherm **[!UICONTROL Edit Table Mapping]** dat de broodkruimels en de paginatitel toont. In dit geval kunt u op **[!UICONTROL Workflows]** of **[!UICONTROL Microsoft Dynamics 365 to Campaign]** tekst klikken om naar één van de vorige schermen te gaan. **[!UICONTROL Edit Table Mapping]** in de breadcrumbs kan in dit geval niet worden geklikt omdat het het huidige scherm is.

![](assets/d365-to-acs-breadcrumbs-ingress.png)

### Algemene knoppen {#app-buttons}

De volgende pictogrammen worden gebruikt op meerdere pagina&#39;s in de zelfbedieningsapp.

![](assets/d365-to-acs-icon-add.png) - Voeg een nieuw item toe aan een lijst.

![](assets/d365-to-acs-icon-edit.png) - Een bestaande bewerking bewerken

![](assets/d365-to-acs-icon-delete.png) - Een item uit een lijst met items verwijderen
