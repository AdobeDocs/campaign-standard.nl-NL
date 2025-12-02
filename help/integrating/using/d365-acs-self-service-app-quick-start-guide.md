---
title: Aan de slag met het integratieprogramma
description: Aan de slag met het integratieprogramma
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: e73e2069-e86d-4be2-bf73-22e6dc164340
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '1079'
ht-degree: 1%

---

# Aan de slag met de zelfbedieningsintegratie-app {#gs-self-service-app}

De integratie van Adobe Campaign Standard met Microsoft Dynamics 365 zelfbedieningstoepassing geeft u de capaciteit om gegevensstromen te vormen, te controleren of zij lopen, en waarin milieu. U moet echter een aantal voorwaarden voltooien voordat u de toepassing voor zelfintegratie gaat gebruiken.

## Concepten en beperkingen {#concepts-and-restrictions}

Voordat u begint met het integratieprogramma, moet u de concepten en instructies begrijpen die aan de integratie zijn gekoppeld en een aantal eerste stappen ondernemen om toegang te krijgen.

Meer informatie vindt u in de volgende secties:

* [Aan de slag met de Microsoft Dynamics 365-integratie](../../integrating/using/d365-acs-get-started.md)
* [Aanbevolen werkwijzen en beperkingen voor integratie](../../integrating/using/d365-acs-notices-and-recommendations.md)
* [Ontdek de belangrijkste stappen om deze integratie te implementeren](../../integrating/using/d365-acs-get-started.md#request-and-implement-this-integration)
* [De integratie van Microsoft Dynamics 365 gebruiken](../../integrating/using/d365-acs-using-the-integration.md)

## Vereisten {#self-service-app-prerequisites}

U moet Microsoft Dynamics 365 en Adobe Campaign Standard zodanig configureren dat de integratie-app toegang heeft tot uw gegevens. Dit zal wat tijd vergen om in Dynamica 365, Adobe Campaign Standard, en Adobe I/O te vormen; nochtans, zodra zij worden gevormd, zult u de integratie door het gebruikersinterface van de zelfbedieningsintegratietoepassing kunnen controleren.

Meer informatie vindt u in de volgende secties:

* [Microsoft Dynamics 365 configureren voor integratie van campagnes](../../integrating/using/d365-acs-configure-d365.md)
* [Adobe I/O configureren](../../integrating/using/d365-acs-configure-adobe-io.md)
* [Aangepaste bronnen voor campagne toewijzen en aangepaste entiteiten voor Microsoft Dynamics 365](../../integrating/using/d365-acs-notices-and-recommendations.md)

## Belangrijke stappen voor het configureren van de zelfbedieningsintegratie-app {#self-service-app-configuration-steps}

U kunt dan met het integratiehulpmiddel beginnen. Voer de volgende stappen uit:

1. [Toegang tot de integratie-app krijgen](../../integrating/using/d365-acs-self-service-app-control-access.md)
1. [De integratie-app voor uw gebruik configureren](../../integrating/using/d365-acs-self-service-app-settings.md)
1. [Gegevenssynchronisatie implementeren](../../integrating/using/d365-acs-self-service-app-data-sync.md)
1. [Synchronisatieworkflows configureren](../../integrating/using/d365-acs-self-service-app-workflows.md)

## Koppeling naar de integratie-app {#self-service-app-link}

Open een browser en blader aan de schakelaar verbonden aan uw gebied:

* [&#x200B; Azië Pacific &#x200B;](https://d365-acs-ap.ea.adobe.com/)
* [&#x200B; Europa, Midden-Oosten, of Afrika (EMEA) &#x200B;](https://d365-acs-em.ea.adobe.com/)
* [&#x200B; Amerika &#x200B;](https://d365-acs-am.ea.adobe.com/)

## Bevestiging van privacyverzoek {#self-service-app-acknowledgement}

Wanneer het doorbladeren aan zelfbediening UI voor het eerst, zult u met de privacyerkenning worden voorgesteld. U moet erkennen dat u uw rol in het afzonderlijk uitvoeren van privacyverzoeken in Campagne en Microsoft Dynamics 365 begrijpt voordat u kunt doorgaan.
Leer meer over uw privacyverantwoordelijkheden en over hoe te om privacyverzoeken in [&#x200B; te beheren deze sectie &#x200B;](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).

## Uw referenties instellen {#self-service-app-credentials}

Wanneer u voor het eerst naar de gebruikersinterface bladert, wordt een pagina met een koptekst weergegeven die er als volgt uitziet:

![](assets/do-not-localize/d365-to-acs-ui-header.png)

>[!NOTE]
>
> Het is normaal om waarschuwingen op te halen die aangeven dat het &quot;niet in staat is om verbinding te maken&quot; met Adobe Campaign Standard of Microsoft Dynamics 365 als de app-instellingen nog niet zijn geconfigureerd.

Controleer of de selecties &quot;ORG&quot; en &quot;INSTANTIE&quot; de selecties zijn die u wilt configureren.  Als dat niet het geval is, klikt u op de vervolgkeuzelijst en selecteert u de juiste org en variant.

>[!IMPORTANT]
>
> Als u de schakelaar voor het eerst vormt en/of u nieuw aan dit proces bent, dan roepen wij **sterk** u aan om de &quot;stadium&quot;of &quot;dev&quot;instantie te selecteren. U zult ervoor willen zorgen om te verifiëren dat uw configuratie goed alvorens de opstelling in productie te proberen werkt.

Als u over de juiste org en instantie beschikt, klikt u op het menu &quot;hamburger&quot; om een vervolgkeuzemenu weer te geven. Klik vervolgens op **[!UICONTROL Settings...]** in de vervolgkeuzelijst om de pagina te bezoeken waarop u uw gegevens voor Microsoft Dynamics 365 en Campagne hebt ingevoerd (zie hieronder).

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-menu-pointers.png)

Vul de volgende secties in op de pagina **[!UICONTROL Settings]** :

* Microsoft Dynamics 365 Credentials
* Adobe Credentials

Ga [&#x200B; hier &#x200B;](../../integrating/using/d365-acs-self-service-app-settings.md) om gedetailleerdere informatie over te vinden waar te om de informatie voor elke input te vinden. Wanneer u klaar bent, klikt u op de knop **[!UICONTROL Save]** onderaan.

## De eerste configuratie controleren {#self-service-app-initial-config}

Ervan uitgaande dat u de bovenstaande voorwaarden hebt vervuld en dat u al uw referenties correct hebt toegevoegd, gaan we nu naar de pagina **[!UICONTROL Workflows]** . Leer meer over de integratie app werkschema&#39;s in [&#x200B; deze pagina &#x200B;](../../integrating/using/d365-acs-self-service-app-workflows.md).

Klik in de pagina **[!UICONTROL Workflows]** op het potloodpictogram dat is gekoppeld aan de **[!UICONTROL Microsoft Dynamics 365 to Campaign]** -workflow om de configuratie ervan te bewerken.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-edit-pointer.png)

Op de pagina **[!UICONTROL Microsoft Dynamics 365 to Campaign]** hebt u toegang tot de lijst met tabeltoewijzingen die u hebt geconfigureerd.  U wordt standaard toegewezen aan een contact-/profieltoewijzing buiten het vak. Alle andere aangepaste entiteiten moeten afzonderlijk worden geconfigureerd.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top-pointers.png)

Controleer op de pagina **[!UICONTROL Edit Table Mapping]** de sectie **[!UICONTROL Mappings]** om ervoor te zorgen dat velden uit Microsoft Dynamics 365 worden toegewezen aan het juiste veld in Campagne. Als u andere toewijzingen moet toevoegen, doet u dit nu, evenals om het even welke vervangingen of filters. [Meer informatie](../../integrating/using/d365-acs-self-service-app-data-sync.md).

Als u nieuwe afbeeldingen wilt toevoegen, verwijs naar [&#x200B; deze sectie &#x200B;](../../integrating/using/d365-acs-self-service-app-data-sync.md#add-a-new-mapping) voor meer informatie.

Wanneer de configuratie juist is, klikt u op de knop **[!UICONTROL Play]** naast de **[!UICONTROL Microsoft Dynamics 365 to Campaign]** -workflow om de integratie en de gegevensstroom te starten.

>[!IMPORTANT]
>
>Wij **adviseren sterk** dat u eerst dit in uw milieu&#39;s van het Stadium of van het Dev alvorens in Productie in werking stelt. Controleer of het werkgebied/de instantie dev is geselecteerd in de koptekst.
>

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-play-pointer.png)

Als de bewerking eenmaal is gestart, kunt u testen door items toe te voegen of te wijzigen in Microsoft Dynamics 365 en deze wijzigingen binnen een paar minuten te observeren in Adobe Campaign. Als u dit proces op elk gewenst moment moet stoppen, drukt u gewoon op dezelfde knop om het te stoppen. [Meer informatie](../../integrating/using/d365-acs-self-service-app-workflows.md#workflow-status)


## De werkruimte van de integratie-app {#self-service-app-workspace}

### App-header {#app-header}

Met de header in de zelfbedieningsapp kunt u definiëren welke org en instantie u momenteel bekijkt en/of configureert.

Selecteer **ORG** en **INSTANTIE** u wilt bekijken/uitgeven. Deze velden worden alleen-lezen weergegeven, maar kunnen worden bewerkt wanneer u de muiscursor erop plaatst.

Er wordt een vervolgkeuzemenu weergegeven wanneer u op de knop klikt met de drie horizontale lijnen ![](assets//do-not-localize/d365-to-acs-icon-hamburger.png) rechts van de koptekst.

De items in het keuzemenu zijn:

* **Montages**: Het selecteren van deze optie zal u naar een scherm verzenden dat u toestaat om API geloofsbrieven voor Microsoft Dynamics 365 en Adobe Campaign, evenals andere algemene montages voor de toepassing te specificeren.

* **Documentatie**: Deze optie is een verbinding met de Documentatie van Adobe Campaign specifiek voor deze integratie

* **de Zorg van 0&rbrace; Klant**: Dit is een verbinding aan de documentatie van Experience Cloud met betrekking tot het openen van een Klantenticket van de Zorg van de Klant

* **Teken uit**: Dit zal u uit de toepassing ondertekenen en u toestaan terug binnen als een andere gebruiker te ondertekenen.

* **Ongeveer**: Dit toont een dialoog die informatie over de toepassing, met inbegrip van auteursrechtinformatie bevat.

### Broodkruimels {#app-breadcrumbs}

Terwijl u door de app navigeert, worden er onder aan bepaalde schermen balken weergegeven.

**Voorbeeld:**

Hieronder ziet u een voorbeeld van het scherm **[!UICONTROL Edit Table Mapping]** waarin de broodkruimels en de paginatitel worden weergegeven. In dit geval kunt u op de **[!UICONTROL Workflows]** - of **[!UICONTROL Microsoft Dynamics 365 to Campaign]** -tekst klikken om naar een van de vorige schermen te gaan. **[!UICONTROL Edit Table Mapping]** in de broodkruimels is in dit geval niet klikbaar omdat het het huidige scherm is.

![](assets/do-not-localize/d365-to-acs-breadcrumbs-ingress.png)

### Algemene knoppen {#app-buttons}

De volgende pictogrammen worden gebruikt op meerdere pagina&#39;s in de zelfbedieningsapp.

![](assets/do-not-localize/d365-to-acs-icon-add.png) - Voeg een nieuw punt aan een lijst toe.

![](assets/do-not-localize/d365-to-acs-icon-edit.png) - Een bestaande bewerking bewerken

![](assets/do-not-localize/d365-to-acs-icon-delete.png) - Een item verwijderen uit een lijst met items
