---
title: Triggers configureren in Experience Cloud
description: 'Leer hoe u de integratie van Adobe Experience Cloud Triggers configureert om op basis van hun eerdere gedrag persoonlijke leveringen naar uw klanten te sturen. '
page-status-flag: never-activated
uuid: 8fd7b804-9528-46a5-a060-bf16b8dc555d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: 4163dc0c-8103-4425-b8bf-7aa45c4d3a06
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Triggers configureren in Experience Cloud{#configuring-triggers-in-experience-cloud}

## De functionaliteit activeren {#activating-the-functionality}

Adobe moet de functionaliteit in Adobe Campaign activeren. Neem contact op met uw Adobe-accountmanager of professionele servicepartner.

Het Adobe-team heeft de volgende informatie nodig om triggers te activeren:

* Bedrijfsnaam van Marketing Cloud
* IMS ORG ID
* Login Company Analytics (kan het zelfde zijn als de Bedrijfsnaam van de Onderneming van de Marketing Cloud)

## Oplossingen en services configureren {#configuring-solutions-and-services}

Als u deze functie wilt gebruiken, hebt u toegang nodig tot de volgende oplossingen/kernservices:

* Adobe-campagne
* Adobe Analytics Ultimate, Premium, Foundation, OD, Select, Prime, Mobile Apps, Select of Standard.
* Experience Cloud Triggers Core Service

   ![](assets/trigger_uc_prereq_1.png)

* Ervaar de Cloud DTM Core-service

   ![](assets/trigger_uc_prereq_2.png)

* Ervaar de Cloud Visitor ID en Ervaar Cloud People Core Service

   ![](assets/trigger_uc_prereq_3.png)

U hebt ook een werkende website nodig.

![](assets/trigger_uc_prereq_4.png)

>[!CAUTION]
>
>Subdomeindelegatie is een essentieel element voor de beschikbaarheid. Zorg ervoor dat de e-mails over Adobe Campagne worden verzonden vanuit hetzelfde domein als dat van de website.

U moet [Experience Cloud DTM Core Service](#configuring-experience-cloud-dtm-core-service), [Experience Cloud People Core Service](#configuring-experience-cloud-people-core-service) en [Campagne](#configuring-triggers-and-aliases-in-campaign) configureren om deze gebruiksgevallen uit te voeren.

### Cloud DTM Core-service configureren {#configuring-experience-cloud-dtm-core-service}

1. Activeer Experience Cloud DTM Core Service (Dynamic Tag Management) en activeer Experience Cloud ID en Adobe Analytics voor uw websitepagina&#39;s.

   ![](assets/trigger_uc_conf_1.png)

1. Voor het afstemmen van id&#39;s tussen de website, Adobe Analytics en Adobe Campaign moet aliasing worden gebruikt. Maak bijvoorbeeld een alias met de naam &quot;bezoeker&quot;.

   ![](assets/trigger_uc_conf_2.png)

### Cloud People Core-service configureren {#configuring-experience-cloud-people-core-service}

De alias waarnaar eerder in DTM wordt verwezen, moet via een kenmerk van de klant worden gemaakt in de Experience Cloud People Core Service. Zorg ervoor dat u een nieuwe maakt en dat u in de integratiecode naar dezelfde DTM-alias verwijst (bijvoorbeeld &quot;bezoeker&quot;).

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>Dit kenmerk van de klant wordt gebruikt in de gegevensbron in Adobe Campagne (volgende stap).

### Triggers en aliassen configureren in campagne {#configuring-triggers-and-aliases-in-campaign}

1. Zorg ervoor dat u de inhoud van de Adobe Campagne Standard ziet. **[!UICONTROL Experience Cloud triggers]** Als u dat niet doet, neemt u contact op met de Adobe Campagnebeheerders.

   ![](assets/remarketing_1.png)

1. Met aliassen kan een contactpersoon in Analytics worden afgestemd op een profiel in Campagne. U moet de aliassen die in de dienst van identiteitskaart van de Wolk van de Ervaring met een Gedeelde Gegevensbron in Campagne worden bepaald aanpassen. U moet de aliasresolutie in Adobe Campaign configureren via een gegevensbron ( **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Shared Data Sources]** ). Zorg ervoor u de correcte gegevensbron in het **[!UICONTROL Data Source/Alias]** drop-down menu kiest, dat met de zelfde die gegevensbron van Attributen van de Klant in vorige stap wordt gecreeerd in kaart wordt gebracht.

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >U kunt uw triggers afstemmen voor zowel anonieme als aangemelde gebruikers. Voor anonieme gebruikers moet het profiel bestaan in Adobe Campaign en is een e-mail verzonden naar de gebruiker eerder. Hiervoor is de configuratie van bezoekersidentiteitskaart voldoende. Nochtans, als u trekkers voor het programma geopende gebruikers wilt in overeenstemming brengen, moet u de Gedeclareerde Gegevensbron van identiteitskaart plaatsen. Voor meer op dit, verwijs naar de configuratie [van de](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources)Gegevensbron.

## Een trigger maken in de interface Experience Cloud {#creating-a-trigger-in-the-experience-cloud-interface}

Er moet een Adobe Experience Cloud-trigger worden gemaakt, zodat u deze kunt gebruiken in Campagne.

Maak een nieuwe trigger in Experience Cloud en selecteer de rapportsuite die op uw website wordt gebruikt. Zorg ervoor dat u de juiste afmeting kiest, zodat de trigger wordt geactiveerd.

Raadpleeg de documentatie [bij](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html) Adobe Experience Cloud en bekijk deze [video](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two).

## Triggert beste praktijken en beperkingen {#triggers-best-practices-and-limitations}

Hier volgt een lijst met beste praktijken en beperkingen voor het gebruik van de campagne - Triggers-integratie:

* Als u veelvoudige instanties van de Norm van de Campagne hebt, dan kunnen de trekkers door alle instanties worden ontvangen zolang zij in zelfde IMS org ID zijn. Analyses moeten ook op dezelfde IMS org-id staan.
* U kunt geen trekker in de Dienst van de Kern van de Trigger tot stand brengen gebruikend gebeurtenissen van twee verschillende rapportreeksen.
* Triggers zijn gebaseerd op transactieberichten. Transactieberichten worden gebruikt wanneer u een bericht zeer snel moet verzenden. U kunt geen transactiemeldingen in de wachtrij plaatsen en deze vervolgens in batch herhalen.
* Triggers zijn niet deterministisch van aard. Wanneer een trigger wordt gegenereerd, verstuurt deze alle aliassen die aan het cookie zijn gekoppeld. In het geval van gedeelde browsers, zoals in winkelkiosken, bibliotheken, cybercafes of gedeelde apparaten thuis (echtgenoot en echtgenote die zich aanmelden vanaf hetzelfde apparaat), is het dus niet mogelijk om de juiste id toe te wijzen. Alle id&#39;s die worden gebruikt om u aan te melden bij de browser, worden verzonden naar Campagne die een bericht verzendt op basis van de eerste afstemming. Als er meerdere &#39;e-mail-id&#39;s&#39; zijn die in aanmerking komen voor afstemming, verzendt Campagne geen e-mail. Campagne kan niet weten wat de juiste e-mailadres is, tenzij deze wordt vastgelegd en verzonden door Analytics.
* U kunt geen inhoud van lading in Campagne opslaan. Triggers kunnen niet worden gebruikt om de gegevens van een profiel bij te werken.
* Kenmerken van klanten worden niet ondersteund in Triggers (er kunnen alleen gegevens uit de rapportsuite worden gebruikt om de regels voor het starten van Triggers te definiëren).
* Verzameling van verzamelingen wordt niet ondersteund in Campagne.

>[!CAUTION]
>
>Uw website moet actief zijn op hetzelfde domein als de Adobe Campagne-server. Als dat niet het geval is, kunt u de bezoeker-id niet gebruiken om gebruikers die anoniem de website bezoeken, te verzoenen en te bereiken.

