---
title: Privacyverzoeken
description: Meer informatie over het beheren van privacyverzoeken in Adobe Campaign Standard
page-status-flag: never-activated
uuid: ed9e631c-5ad1-49f1-be1e-b710bc64dc91
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 5227ca05-3856-4e54-aec6-14444d6534e3
translation-type: tm+mt
source-git-commit: 06b886989243405df04b4abef46994afd980f6d8
workflow-type: tm+mt
source-wordcount: '1711'
ht-degree: 0%

---


# Privacyverzoeken beheren {#privacy-requests}

Raadpleeg [deze sectie](../../start/using/privacy-management.md)voor een algemene presentatie over privacybeheer.

Deze informatie is van toepassing op GDPR, CCPA, PDPA en LGPD. For more on these regulations, see [this section](../../start/using/privacy-management.md#privacy-management-regulations).

De opt-out voor de verkoop van persoonsgegevens, die specifiek is voor de CCPA, wordt in [dit deel](#sale-of-personal-information-ccpa)toegelicht.

>[!IMPORTANT]
>
>Vanaf 19.4 is het gebruik van de campagne-API en de interface voor verzoeken om toegang en verwijdering afgekeurd. Voor om het even welke GDPR, CCPA, PDPA, of verzoeken van de Toegang LGPD en van de Schrapping, moet u de de integratiemethode van de Dienst [van de Kern van de](#create-privacy-request) Privacy gebruiken.

## Over privacyverzoeken {#about-privacy-requests}

Om u te helpen uw privacy-gereedheid te vergemakkelijken, kunt u met Adobe Campaign aanvragen voor toegang en verwijdering afhandelen. Het **recht op toegang** en het **recht om te worden vergeten** (schrappingsverzoek) worden beschreven in [deze sectie](../../start/using/privacy-management.md#right-access-forgotten).

Om die verzoeken uit te voeren, moet u de integratie van de Dienst **van de Kern van de** Privacy gebruiken. De verzoeken van de privacy die van de Dienst van de Kern van de Privacy aan alle oplossingen van de Experience Cloud worden geduwd worden automatisch behandeld door Campagne via een specifieke werkschema.

### Vereisten {#prerequesites}

Adobe Campaign beschikt over gegevensbesturingselementen waarmee u privacyverzoeken voor in Adobe Campaign opgeslagen gegevens kunt maken en verwerken. Het is echter de verantwoordelijkheid van de gegevenscontroller om de relatie met het gegevensonderwerp (e-mail, klantenservice of een webportal) af te handelen.

Daarom is het uw verantwoordelijkheid als Data Controller om de identiteit te bevestigen van de betrokkene die het verzoek indient en om te bevestigen dat de gegevens die aan de aanvrager worden teruggegeven over het onderwerp van Gegevens gaan.

>[!NOTE]
>
>Voor meer informatie over persoonsgegevens en over de verschillende entiteiten die gegevens beheren (Data Controller, Data Processor en Data Subject), zie [Persoonsgegevens en Persoonlijke personen](../../start/using/privacy.md#personal-data).

### Naamruimten {#namesspaces}

Voordat u privacyverzoeken maakt, moet u de naamruimte definiëren die u wilt gebruiken. De naamruimte is de sleutel die wordt gebruikt om het gegevensonderwerp in de Adobe Campaign-database te identificeren. Er zijn twee naamruimten beschikbaar die zich buiten het vak bevinden: e-mail en mobiele telefoon. Voer de volgende stappen uit als u een andere naamruimte nodig hebt (bijvoorbeeld een aangepast profielveld).

Raadpleeg ook deze [zelfstudie](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/namespaces-for-privacy-requests.html?lang=en#privacy) over het maken van een naamruimte.

>[!NOTE]
>
>Als u meerdere naamruimten gebruikt, moet u één privacyverzoek per naamruimte maken.

1. Click the Adobe Campaign logo in the top left corner, then select **[!UICONTROL Administration]** > **[!UICONTROL Namespaces]**.

   ![](assets/privacy-namespaces.png)

1. Klik in de lijst met naamruimten op **[!UICONTROL Create]**.

   ![](assets/privacy-namespace-create.png)

1. Voer een **[!UICONTROL Label]** waarde in.

   ![](assets/privacy-namespace-label.png)

1. Als u een bestaande naamruimte voor identiteitsservice wilt gebruiken, kiest **[!UICONTROL Map from Identity Namespace Service]** en selecteert u een naamruimte in de **[!UICONTROL Identity Service Namespaces]** lijst.

   ![](assets/privacy-map-from-namespace.png)

   Als u een nieuwe naamruimte wilt maken in **[!UICONTROL Identity Service]** en deze wilt toewijzen in Campagne, selecteert u **[!UICONTROL Create new]** en voert u een naam in het **[!UICONTROL Identity namespace name]** veld in.

   ![](assets/privacy-create-new-namespace.png)

   Raadpleeg de documentatie bij het [Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=en) voor meer informatie over naamruimten.

1. Één Namespace van de Dienst van de Identiteit wordt in kaart gebracht aan één namespace in Campagne. U moet opgeven hoe de naamruimte in Campagne moet worden afgestemd.

   Selecteer een doeltoewijzing (**[!UICONTROL Recipients]**, **[!UICONTROL Real-time event]** of **[!UICONTROL Subscriptions to an application]**). Als u verschillende doeltoewijzingen wilt gebruiken, moet u één naamruimte per doeltoewijzing maken.

   ![](assets/privacy-namespace-target-mapping.png)

1. Kies de **[!UICONTROL Reconciliation key]**. Dit is het gebied dat zal worden gebruikt om het Onderwerp van Gegevens in het gegevensbestand van Adobe Campaign te identificeren.

   ![](assets/privacy-namespace-reconciliation-key.png)

1. Klik op **[!UICONTROL Create]**. U kunt nu privacyverzoeken maken op basis van uw nieuwe naamruimte. Als u meerdere naamruimten gebruikt, moet u één privacyverzoek per naamruimte maken.

### Creating a Privacy request {#create-privacy-request}

>[!IMPORTANT]
>
>De integratie van de Dienst **van de Kern van de** Privacy is de methode u voor alle verzoeken van de Toegang en van de Schrapping zou moeten gebruiken.
>
>Vanaf 19.4 is het gebruik van de campagne-API en de interface voor verzoeken om toegang en verwijdering afgekeurd. Gebruik de Privacy Service van de Kern voor om het even welke GDPR, CCPA, PDPA, of verzoeken van de Toegang LGPD en van de Schrapping.

De integratie van de Dienst van de Kern van de Privacy staat u toe om uw verzoeken van de Privacy in een multi-oplossingscontext door één enkele vraag van JSON API te automatiseren. De verzoeken van de privacy die van de Dienst van de Kern van de Privacy aan alle oplossingen van de Experience Cloud worden geduwd worden automatisch behandeld door Campagne via een specifieke werkschema.

Raadpleeg de documentatie bij de Privacy Service [van het](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en) Experience Platform voor meer informatie over het maken van privacyverzoeken van de Privacy Core Service.

Elke de kernde dienstbaan van de Privacy wordt verdeeld in veelvoudige verzoeken van de Privacy in Campagne die op hoeveel namespaces wordt gebaseerd, één verzoek beantwoordt aan één namespace. Bovendien kan één taak op meerdere instanties worden uitgevoerd. Daarom worden er meerdere bestanden gemaakt voor één taak. Als een aanvraag bijvoorbeeld twee naamruimten heeft en op drie instanties wordt uitgevoerd, worden in totaal zes bestanden verzonden. Eén bestand per naamruimte en instantie.

Het patroon voor een bestandsnaam is: `<InstanceName>-<NamespaceId>-<ReconciliationKey>.xml`

* **InstanceName**: Instantienaam campagne
* **NamespaceId**: Identiteitsservice-naamruimte-id van de gebruikte naamruimte
* **Afstemmingssleutel**: Gecodeerde afstemmingssleutel

### Lijst met bronnen {#list-of-resources}

Wanneer het uitvoeren van een verzoek van de Privacy van de Schrapping of van de Toegang, zoekt Adobe Campaign alle gegevens van het Onderwerp die op de waarde van de **Verzoening** worden gebaseerd in alle middelen die een verbinding aan het profielmiddel (eigen type) hebben.

Hier is de lijst van uit-van-de-doos middelen die in aanmerking worden genomen wanneer het uitvoeren van de verzoeken van de Privacy:

* Profielen (ontvanger)
* Logbestanden voor profiellevering (wideLogRcp)
* Logbestanden voor het bijhouden van profielen (trackingLogRcp)
* Leveringslogboeken (abonnementen op een toepassing) (wideLogAppSubRcp)
* Logbestanden bijhouden (abonnementen op een toepassing) (trackingLogAppSubRcp)
* Abonnementen op een toepassing (appSubscriptionRcp)
* Abonnementsgeschiedenis van profielen (subHistoRcp)
* Profielabonnementen (subscriptionRcp)
* Bezoekers (bezoeker)

Als u douanemiddelen creeerde die een verbinding aan het profielmiddel (eigen type) hebben, zullen zij ook in aanmerking worden genomen. Bijvoorbeeld, als u een transactiemiddel verbonden aan het profielmiddel en een middel van de transactiedetails verbonden aan het transactiemiddel hebt, zullen zij allebei in aanmerking worden genomen.

Raadpleeg ook [deze zelfstudie](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/custom-resources-for-privacy-requests.html?lang=en#privacy) over het wijzigen van aangepaste bronnen.

Dit werkt alleen als u de **[!UICONTROL Deleting the target record implies deleting records referenced by the link]** optie selecteert in de aangepaste bron:

1. Click the Adobe Campaign logo in the top left corner, then select **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**.

1. Selecteer een douanemiddel dat een verbinding aan het profielmiddel (eigen type) heeft.

1. Klik op de **[!UICONTROL Links]** sectie.

1. Klik voor elke koppeling op het potloodpictogram (**[!UICONTROL Edit properties]**).

1. In the **[!UICONTROL Behavior if deleted/duplicated]** section, select the **[!UICONTROL Deleting the target record implies deleting records referenced by the link]** option.

   ![](assets/privacy-cus-resource-option.png)

### Status van privacyverzoek {#privacy-request-statuses}

Hier volgen de verschillende statussen voor privacyverzoeken:

* **[!UICONTROL New]** / **[!UICONTROL Retry pending]**: de workflow heeft de aanvraag nog niet verwerkt.
* **[!UICONTROL Processing]** / **[!UICONTROL Retry in progress]**: de workflow verwerkt de aanvraag.
* **[!UICONTROL Delete pending]**: in de workflow zijn alle te verwijderen gegevens voor ontvangers geïdentificeerd.
* **[!UICONTROL Delete in progress]**: de workflow verwerkt de verwijdering.
   <!--**[!UICONTROL Delete Confirmation Pending]** (Delete request in 2-steps process mode): the workflow has processed the Access request. Manual confirmation is requested to perform the deletion. The button is available for 15 days.-->
* **[!UICONTROL Complete]**: de verwerking van de aanvraag is zonder fout voltooid.
* **[!UICONTROL Error]**: er is een fout opgetreden in de workflow. De reden wordt getoond in de lijst van de verzoeken van de Privacy in de **[!UICONTROL Request status]** kolom. Bijvoorbeeld, **[!UICONTROL Error data not found]** betekent dat geen ontvankelijke gegevens die de Onderwerp van Gegevens aanpassen in het gegevensbestand **[!UICONTROL Reconciliation value]** zijn gevonden.

### Het proces in twee stappen uitschakelen {#disabling-two-step-process}

De Core-Privacy Service ondersteunt het proces in twee stappen niet.

>[!IMPORTANT]
>
>Alvorens de integratie van de Privacy Service van de Kern te gebruiken om uw verzoeken van de Privacy te beheren, moet u het proces van twee stappen voor verzoeken van de Schrapping van de interface van de Campaign Standard onbruikbaar maken.

Als deze optie niet is uitgeschakeld, blijven alle verwijderverzoeken die met de Privacy Core Service worden beheerd in behandeling en worden deze niet voltooid.

Standaard wordt het proces in twee stappen geactiveerd.

Als u deze modus wilt wijzigen, klikt u **[!UICONTROL Edit properties]** in de rechterbovenhoek van het **[!UICONTROL Privacy Requests]** scherm en schakelt u de **[!UICONTROL Activate the 2-step process]** optie uit.

![](assets/privacy-disable-2-step-process.png)

## Opt-out voor de verkoop van persoonlijke gegevens (CCPA) {#sale-of-personal-information-ccpa}

The **California Consumer Privacy Act** (CCPA) provides California residents new rights in regards to their personal information and imposes data protection responsibilities on certain entities whom conduct business in California.

De configuratie en het gebruik van verzoeken van de Toegang en van de Schrapping zijn gemeenschappelijk voor zowel GDPR als CCPA. In dit deel wordt de opt-out voor de verkoop van persoonsgegevens beschreven, die specifiek is voor de CCPA.

Naast de [instrumenten voor het beheer](../../start/using/privacy-management.md#consent-management) van toestemming die Adobe Campaign biedt, kunt u nagaan of een consument heeft gekozen voor de verkoop van persoonlijke informatie.

Een consument besluit via uw systeem dat hij/zij niet toestaat dat zijn/haar persoonlijke gegevens aan derden worden verkocht. In Adobe Campaign kun je deze gegevens opslaan en volgen.

>[!NOTE]
>
>U kunt de opt-out gebruiken voor de verkoop van persoonlijke gegevens via de Campagne-interface en via de API. U kunt dit niet gebruiken via de Privacy Core Service.

>[!IMPORTANT]
>
>Het is uw verantwoordelijkheid als de verantwoordelijke voor de gegevens om het verzoek van de betrokkene te ontvangen en de aanvraagdata voor de CCPA bij te houden. Als technologieleverancier bieden we alleen een manier om te weigeren. Voor meer op uw rol als Controlemechanisme van Gegevens, zie [Persoonlijke gegevens en Personas](../../start/using/privacy.md#personal-data).

### Vereiste voor aangepaste tabellen {#ccpa-prerequisite}

Vanaf 19.4 wordt het **[!UICONTROL CCPA Opt-Out]** veld in de Campagne-interface en de API buiten de box geplaatst. Het veld is standaard beschikbaar voor de standaardbron. **[!UICONTROL Profile]**

Als u een middel van het douaneprofiel gebruikt, moet u het middel uitbreiden en het gebied toevoegen. Wij adviseren dat u een verschillende naam dan het uit-van-de-doos gebied gebruikt, bijvoorbeeld:  **[!UICONTROL Opt-Out for CCPA]** (optoutcpa). Wanneer een nieuw veld wordt gemaakt, wordt dit automatisch ondersteund door de campagne-API.

Zie [deze sectie](../../developing/using/extending-the-profile-resource-with-a-new-field.md)voor meer informatie over het uitbreiden van de profielbron.

>[!NOTE]
>
>Het wijzigen van middelen is een gevoelige verrichting die door deskundige slechts gebruikers moet worden uitgevoerd.

1. Ga naar **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**. Klik op de aangepaste profielbron. Zie [deze sectie](../../developing/using/creating-or-extending-the-resource.md)voor meer informatie over het uitbreiden van een bron.

   ![](assets/privacy-ccpa-extend-cus.png)

1. Klik **[!UICONTROL Add field]** of **[!UICONTROL Create Element]**, voeg het etiket, identiteitskaart toe en kies het **[!UICONTROL Boolean]** type. Voor de naam, gebruik **Opt-out voor CCPA**. Gebruik voor de id: **optOutCcpa**.

   ![](assets/privacy-ccpa-extend-field.png)

1. Voeg op het **[!UICONTROL Screen definition]** tabblad onder **[!UICONTROL Detail screen configuration]** het veld toe en selecteer **[!UICONTROL Input field]**. Hiermee wordt het veld beschikbaar gesteld in de lijst met profielen en de details.  Zie [deze sectie](../../developing/using/configuring-the-screen-definition.md)voor meer informatie over het configureren van de schermdefinitie.

   ![](assets/privacy-ccpa-extend-screen.png)

1. Ga naar **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**, bereidt de publicatie voor en publiceer de wijzigingen. Zie [deze sectie](../../developing/using/updating-the-database-structure.md)voor meer informatie over het publiceren van een bron.

   ![](assets/privacy-ccpa-extend-pub.png)

1. Controleer of het veld beschikbaar is op de details van een profiel. Zie [deze sectie](#usage)voor meer informatie.

### Gebruik {#usage}

Het is de verantwoordelijkheid van de gegevensverwerker om de waarde van het veld te vullen en de CCPA-richtsnoeren en -regels inzake gegevensverkoop te volgen.

U kunt verschillende methoden gebruiken om de waarden te vullen:

* De interface van de campagne gebruiken door de details van de ontvanger te bewerken (zie hieronder)
* De API voor campagneprivacy gebruiken (zie de [API-documentatie](../../api/using/managing-ccpa-opt-out.md))
* Via een workflow voor het importeren van gegevens

Vervolgens moet u ervoor zorgen dat u nooit de persoonlijke gegevens van profielen die u hebt afgewezen aan derden verkoopt.

1. Bewerk in de interface van de campagne een profiel om de status van de optie Weigeren te wijzigen.

   ![](assets/privacy-ccpa-profile-opt-out.png)

1. Wanneer de waarde van het veld is **[!UICONTROL True]**, wordt de informatie weergegeven in de details van het profiel.

   ![](assets/privacy-ccpa-profile-opt-out-true.png)

1. U kunt de profielenlijst vormen om de op-uit kolom te tonen. Leren hoe te om lijsten te vormen, zie [deze sectie](../../start/using/customizing-lists.md).

   ![](assets/privacy-ccpa-profile-configure-list.png)

1. U kunt op de kolom klikken om ontvangers te sorteren op basis van de gegevens voor niet-deelname.

   ![](assets/privacy-ccpa-profile-sorting.png)
