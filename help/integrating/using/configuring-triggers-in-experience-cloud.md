---
title: Triggers configureren in Experience Cloud
description: Leer hoe u de integratie van Adobe Experience Cloud Triggers configureert om op basis van hun eerdere gedrag persoonlijke leveringen naar uw klanten te sturen.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 50e9fb7a-b28a-40b0-9f2c-3673c792529a
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 6%

---

# Triggers configureren in Experience Cloud{#configuring-triggers-in-experience-cloud}

## De functionaliteit activeren {#activating-the-functionality}

De functionaliteit moet in Adobe Campaign door Adobe worden geactiveerd. Neem contact op met uw Adobe-accountmanager of professionele servicepartner.

Het Adobe-team heeft de volgende informatie nodig om triggers te activeren:

* Marketing Cloud Company Name
* Organisatie-ID
* Analytics Login Company (kan het zelfde zijn als de Naam van het Bedrijf van Marketing Cloud)

## Oplossingen en services configureren {#configuring-solutions-and-services}

Als u deze functie wilt gebruiken, hebt u toegang nodig tot de volgende oplossingen/kernservices:

* Adobe Campaign
* Adobe Analytics Ultimate, Premium, Foundation, OD, Select, Prime, Mobile Apps, Select of Standard.
* Experience Cloud Triggers-kernservice

  ![](assets/trigger_uc_prereq_1.png)

* Experience Cloud DTM-kernservice

  ![](assets/trigger_uc_prereq_2.png)

* Experience Cloud Visitor ID- en Experience Cloud People-kernservice

  ![](assets/trigger_uc_prereq_3.png)

U hebt ook een werkende website nodig.

![](assets/trigger_uc_prereq_4.png)

>[!CAUTION]
>
>Subdomeinconfiguratie is een sleutelelement voor de beschikbaarheid. Zorg ervoor dat de e-mails van Adobe Campaign worden verzonden vanuit hetzelfde domein als dat van de website.

U moet [ de Dienst van de Kern van Experience Cloud vormen DTM ](#configuring-experience-cloud-dtm-core-service), [ Dienst van de Kern van de Mensen van Experience Cloud ](#configuring-experience-cloud-people-core-service) en [ Campagne ](#configuring-triggers-and-aliases-in-campaign) om deze gebruiksgevallen in werking te stellen.

### Experience Cloud DTM Core-service configureren {#configuring-experience-cloud-dtm-core-service}

1. Activeer in Experience Cloud DTM Core Service (Dynamic Tag Management) de Experience Cloud ID en Adobe Analytics voor uw websitepagina&#39;s.

   ![](assets/trigger_uc_conf_1.png)

1. Voor het koppelen van id&#39;s tussen de website, Adobe Analytics en Adobe Campaign moet aliasing worden gebruikt. Maak bijvoorbeeld een alias met de naam &quot;bezoeker&quot;.

   ![](assets/trigger_uc_conf_2.png)

### Experience Cloud People Core Service configureren {#configuring-experience-cloud-people-core-service}

De alias waarnaar eerder in DTM wordt verwezen, moet in de Experience Cloud People Core Service worden gemaakt via een kenmerk van de Klant. Zorg ervoor dat u een nieuwe maakt en dat u in de integratiecode naar dezelfde DTM-alias verwijst (bijvoorbeeld &quot;bezoeker&quot;).

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>We gaan dit kenmerk van klant gebruiken in de gegevensbron in Adobe Campaign (volgende stap).

### Triggers en aliassen configureren in campagne {#configuring-triggers-and-aliases-in-campaign}

1. Zorg ervoor dat **[!UICONTROL Experience Cloud triggers]** zichtbaar is op uw Adobe Campaign Standard-instantie. Als u dat niet doet, neemt u contact op met de Adobe Campaign-beheerders.

   ![](assets/remarketing_1.png)

1. Met aliassen kan een contactpersoon in Analytics worden afgestemd op een profiel in Campagne. U moet de aliassen die in de dienst van Experience Cloud ID met Gedeelde Gegevens Source in Campagne worden bepaald aanpassen. U moet de aliasresolutie in Adobe Campaign configureren via een gegevensbron ( **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Shared Data Sources]** ). Zorg ervoor dat u de juiste gegevensbron kiest in het vervolgkeuzemenu **[!UICONTROL Data Source/Alias]** , dat wordt toegewezen aan dezelfde gegevensbron voor kenmerk van klant die in de vorige stap is gemaakt.

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >U kunt uw triggers afstemmen voor zowel anonieme als aangemelde gebruikers. Voor anonieme gebruikers moet het profiel bestaan in Adobe Campaign en is een e-mail verzonden naar de gebruiker eerder. Hiervoor is de configuratie van bezoekersidentiteitskaart voldoende. Nochtans, als u trekkers voor het programma geopende gebruikers wilt in overeenstemming brengen, moet u de Verklaarde Gegevens van identiteitskaart Source plaatsen. Voor meer op dit, verwijs naar [ configuratie van Source van Gegevens ](../../integrating/using/integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources).

## Een trigger maken in de Experience Cloud-interface {#creating-a-trigger-in-the-experience-cloud-interface}

Er moet een Adobe Experience Cloud-trigger worden gemaakt, zodat u deze kunt gebruiken in Campagne.

Maak een nieuwe trigger in Experience Cloud en selecteer de rapportsuite die op uw website wordt gebruikt. Zorg ervoor dat u de juiste afmeting kiest, zodat de trigger wordt geactiveerd.

Verwijs naar de [ documentatie van Adobe Experience Cloud ](https://experienceleague.adobe.com/docs/experience-cloud/triggers/create.html).

## Triggert beste praktijken en beperkingen {#triggers-best-practices-and-limitations}

Hier volgt een lijst met beste praktijken en beperkingen voor het gebruik van de campagne - Triggers-integratie:

* Als u meerdere instanties van Campaign Standard hebt, kunnen triggers door alle instanties worden ontvangen zolang ze zich binnen dezelfde organisatie bevinden. Analyses moeten ook binnen dezelfde organisatie plaatsvinden.
* U kunt geen trekker in de Dienst van de Kern van de Trigger tot stand brengen gebruikend gebeurtenissen van twee verschillende rapportreeksen.
* Triggers zijn gebaseerd op transactieberichten. Transactieberichten worden gebruikt wanneer u een bericht zeer snel moet verzenden. U kunt geen transactiemeldingen in de wachtrij plaatsen en deze vervolgens in batch herhalen.
* Triggers zijn niet deterministisch van aard. Wanneer een trigger wordt gegenereerd, verstuurt deze alle aliassen die aan het cookie zijn gekoppeld. In het geval van gedeelde browsers, zoals in winkelkiosken, bibliotheken, cybercafes of gedeelde apparaten thuis (echtgenoot en echtgenote die zich aanmelden vanaf hetzelfde apparaat), is het dus niet mogelijk om de juiste id toe te wijzen. Alle id&#39;s die worden gebruikt om u aan te melden bij de browser, worden verzonden naar Campagne die een bericht verzendt op basis van de eerste afstemming. Als er meerdere &#39;e-mail-id&#39;s&#39; zijn die in aanmerking komen voor afstemming, verzendt Campagne geen e-mail. Campagne kan niet weten wat de juiste e-mailadres is, tenzij deze wordt vastgelegd en verzonden door Analytics.
* U kunt geen inhoud van lading in Campagne opslaan. Triggers kunnen niet worden gebruikt om de gegevens van een profiel bij te werken.
* Kenmerken van klanten worden niet ondersteund in Triggers (er kunnen alleen gegevens uit de rapportsuite worden gebruikt om de regels voor het starten van Triggers te definiëren).
* Verzameling van verzamelingen wordt niet ondersteund in campagne.

>[!CAUTION]
>
>Uw website moet in hetzelfde domein worden uitgevoerd als de Adobe Campaign-server. Als dat niet het geval is, kunt u de bezoeker-id niet gebruiken om gebruikers die anoniem de website bezoeken, te verzoenen en te bereiken.
