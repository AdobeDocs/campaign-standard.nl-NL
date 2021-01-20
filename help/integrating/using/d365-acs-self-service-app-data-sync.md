---
title: Gegevens synchroniseren tussen Campagne en de Dynamica van Microsoft
description: Gegevens synchroniseren tussen Campagne en Dynamica
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: 6be7a20cde8fcaee73972b8919765ea631f2f1ee
workflow-type: tm+mt
source-wordcount: '1795'
ht-degree: 0%

---


# Gegevens synchroniseren

U kunt lijsten van de Dynamica 365 van Microsoft aan de marketing van de Campagne en van de Campagne metriek synchroniseren aan de Dynamica 365 van Microsoft. De synchronisatie wordt uitgevoerd door drie specifieke technische werkschema&#39;s: **[!UICONTROL Microsoft Dynamics 365 to Campaign]**, **[!UICONTROL Campaign to Microsoft Dynamics 365]**, **[!UICONTROL Opt-In/Out]**. Zie deze sectie voor [meer informatie](../../integrating/using/d365-acs-self-service-app-workflows.md).

>[!IMPORTANT]
>U moet de **[!UICONTROL Microsoft Dynamics 365 to Campaign]** workflow stoppen/starten om rekening te houden met uw wijzigingen. [Meer informatie](../../integrating/using/d365-acs-self-service-app-workflows.md)


## Tabellen van Microsoft Dynamics 365 toewijzen aan Campagne

De **[!UICONTROL Microsoft Dynamics 365 to Campaign]** pagina toont een lijst van entiteiten in de Dynamica 365 van Microsoft en de douanemiddelen in Adobe Campaign zij zullen worden gesynchroniseerd met. U kunt nieuwe toewijzingen toevoegen, bestaande toewijzingen bewerken of verwijderen.

![](assets/d365-to-acs-ui-page-ingress-top.png)

Hier volgt een beschrijving van elk van de kolommen in deze tabel:

* **[!UICONTROL MICROSOFT DYNAMICS 365 TABLE]**: Deze kolom identificeert welke entiteit in de Dynamica 365 van Microsoft de bron van gegevens voor de afbeelding zal zijn.

* **[!UICONTROL CAMPAIGN TABLE]**: Deze kolom identificeert welke bron in Adobe Campaign de bestemming van gegevens voor de afbeelding zal zijn.

* **[!UICONTROL ACTIONS]**: hieronder worden mogelijke acties vermeld :

   * Klik op het pictogram **[!UICONTROL Edit]** om deze toewijzing te bewerken.

   * Gebruik het pictogram **[!UICONTROL Delete]** om een lijstafbeelding te schrappen.

   * Klik op het pictogram **[!UICONTROL Replay Data]** om alle gegevens in de tabel Microsoft Dynamics 365 opnieuw te synchroniseren. Normaal gesproken zal de integratietoepassing slechts de gegevens in de Dynamica 365 synchroniseren van Microsoft die onlangs is veranderd.  Nochtans, in sommige gevallen (bijvoorbeeld, hebt u een verandering aangebracht of een fout gemaakt) zou u alle gegevens kunnen willen opnieuw worden gesynchroniseerd.  In deze gevallen zou u op deze knop klikken en de volgende keer dat u de **[!UICONTROL Microsoft Dynamics 365 to Campaign]**-workflow onderbreekt/start, zouden uw gegevens beginnen te synchroniseren.

      Als u op de **[!UICONTROL Replay Data]** knoop klikt en de controles succesvol zijn, zal het pictogram onbruikbaar worden gemaakt: geeft aan dat de gegevens voor dit tabeltoewijzingsbestand opnieuw worden gesynchroniseerd met de volgende uitvoering van de **[!UICONTROL Microsoft Dynamics 365 to Campaign]**-workflow.

      U kunt niet selecteren om de gegevens opnieuw af te spelen wanneer het volgende waar is:

      * Als er 2.000.000 (of meer) punten in Backlog metrisch verbonden aan **[!UICONTROL Microsoft Dynamics 365 to Campaign]** werkschema (getoond in **[!UICONTROL Workflows]** pagina) zijn
      * Als er 2.000.000 of meer verslagen in de Dynamica 365 van Microsoft Lijst zijn

      Het aantal records dat opnieuw moet worden gesynchroniseerd, varieert. Als u een groot aantal records hebt, kan het enige tijd duren om het synchronisatieproces te voltooien. Raadpleeg de **[!UICONTROL Backlog]**-metrische informatie op de pagina **[!UICONTROL Workflows]** als de integratietoepassing werkt om het synchronisatieproces te voltooien.

      >[!IMPORTANT]
      >
      > U wordt ten zeerste aangeraden de integratieworkflow te stoppen wanneer u wijzigingen in Adobe Campaign Standard of Microsoft Dynamics 365 publiceert. Toepasselijke wijzigingen zijn onder meer: updates van bronnen/entiteiten (en de bijbehorende velden), koppelingen, kolommen met id, enz. die momenteel door de integratie worden gebruikt.




## Nieuwe toewijzing maken {#add-a-new-mapping}

Voer de volgende stappen uit om een nieuwe toewijzing te maken:

1. op de pagina **[!UICONTROL Microsoft Dynamics 365 to Campaign]** klikt u op de knop **[!UICONTROL Add New Mapping]**.

1. Gebruik de drop-down lijsten om de Dynamica 365 van Microsoft en de lijsten van de Campagne te selecteren om in kaart te brengen.
De meeste andere invoer op de pagina is afhankelijk van de tabellen die u kiest.

   ![](assets/d365-to-acs-ui-page-ingress-choose-tables.png)

   >[!NOTE]
   >U kunt niet elke tabel meerdere keren toewijzen. Daarom zult u opmerken dat de dropdown selecties geen lijsten zullen omvatten die reeds in kaart zijn gebracht.

1. Klik **[!UICONTROL OK]** om te bevestigen: de toepassing zal een korte tijd nodig hebben om in gebiedsinformatie te lezen verbonden aan de geselecteerde lijsten.

U kunt dan met de toewijzingsconfiguratie te werk gaan. [Meer informatie](#new-mapping-settings)

>[!IMPORTANT]
>
>U kunt de tabellen op deze pagina alleen kiezen wanneer u de toewijzing voor het eerst toevoegt. Controleer of u de juiste tabellen hebt geselecteerd voordat u op de knop **[!UICONTROL Save]** klikt: als de tabel eenmaal is opgeslagen, zijn de tabelselectievelden **alleen-lezen**.

### Een bestaande toewijzing bewerken

Als u een bestaande afbeelding bewerkt, ziet u dat de tabelselecties niet bewerkbaar zijn.

![](assets/d365-to-acs-ui-page-ingress-table-read-only.png)

Dit gebeurt door ontwerp, omdat de invoer verderop op op de pagina is gebaseerd op de velden die aan deze tabellen zijn gekoppeld. Als u de tabellen wijzigt, worden alle velden die aan deze tabellen zijn gekoppeld, ongeldig.  Als u de tabel waarnaar u wilt toewijzen wilt wijzigen, gaat u terug naar de vorige pagina, verwijdert u de toewijzing die u wilt wijzigen en voegt u een nieuwe toewijzing toe.

### Een afzonderlijke tabeltoewijzing {#new-mapping-settings} configureren

In deze sectie zult u leren hoe te om een **single** afbeelding van één lijst van de Dynamiek 365 van Microsoft aan één lijst van Adobe Campaign te vormen.

U kunt de volgende instellingen definiëren:

* **[!UICONTROL Tables]**: Deze sectie maakt een lijst van de naam van de Dynamica 365 van Microsoft lijst en de lijst van de Campagne waaraan het zal worden in kaart gebracht.
* **[!UICONTROL Field Mappings]**: Meer informatie in  [deze sectie](#field-mappings)
* **[!UICONTROL Field Replacements]**: Meer informatie in  [deze sectie](#field-replacements)
* **[!UICONTROL Filters]**: Meer informatie in  [deze sectie](#filters)
* **[!UICONTROL Advanced Settings]**: Meer informatie in  [deze sectie](#advanced-settings)

### Veldtoewijzingen {#field-mappings}

#### Primaire toetsen

Wanneer het toevoegen van nieuwe Dynamica 365 van Microsoft aan de lijstafbeelding van de Campagne, moet u het gebied van identiteitskaart identificeren.

![](assets/d365-to-acs-ui-page-ingress-mappings-first-key.png)

De primaire sleutel van de Dynamica 365 van Microsoft is read-only omdat de toepassing het zal ontdekken.

Voor Campagne, moet u selecteren welk gebied de unieke sleutel zal zijn. Het moet als [CRM ID douanemiddel](../../developing/using/uc-calling-resource-id-key.md) worden gevormd en moet geen duplicaten hebben.

>[!NOTE]
>
>U kunt alleen het veld Id in de tabel kiezen wanneer u **[!UICONTROL Add New Mapping]** hebt geselecteerd. Als u op de knop Bewerken klikt om een bestaande tabeltoewijzing te bewerken, is het veld Id alleen-lezen.

De primaire sleutels zullen altijd de eerste gebiedsnamen zijn die in **[!UICONTROL Field Mappings]** sectie worden vermeld. Ter herinnering wordt het volgende pictogram rechts weergegeven om u eraan te herinneren dat dit de primaire toetsen zijn.

![](assets/d365-to-acs-icon-primary-key.png)

#### Andere veldtoewijzingen toevoegen

Met de sectie **[!UICONTROL Field Mappings]** kunt u andere veldtoewijzingen toevoegen dan de primaire toetsen. Om een nieuwe afbeelding van een gebied van de Dynamica 365 van Microsoft aan Adobe Campaign toe te voegen, klik **[!UICONTROL Add new field mapping]** knoop.

Selecteer de gebieden van de Dynamiek 365 van Microsoft en van de Campagne in de lijsten:

![](assets/d365-to-acs-ui-page-ingress-new-field-mapping.png)

Deze lijsten bevatten de gebiedsnamen die met de Dynamica 365 van Microsoft en de lijsten van de Campagne worden geassocieerd u bij de bovenkant van de pagina hebt geselecteerd.

Met de schakeloptie **[!UICONTROL Apply updates]** kunt u bepalen of updates voor dit veld worden doorgegeven van Microsoft Dynamics 365 naar Campagne:
* Als ![](assets/d365-to-acs-icon-switch-on.png) wordt ingeschakeld, worden updates van de waarde(n) in Microsoft Dynamics 365 doorgegeven aan Adobe Campaign wanneer de updates plaatsvinden.

* Als u ![](assets/d365-to-acs-icon-switch-off.png) uitschakelt, wordt de waarde doorgegeven wanneer gegevens voor het eerst worden geladen (of opnieuw worden afgespeeld), maar worden incrementele updates van het veld in Microsoft Dynamics 365 niet doorgegeven.

>[!NOTE]
>
>Klik op de kolomkop **[!UICONTROL Apply updates]** om **all** van de schakelaars aan of weg bij te werken.


Als u veldwaarden selecteert, wordt het gegevenstype weergegeven onder de vervolgkeuzemenu&#39;s.   Dit is iets waarmee u rekening moet houden wanneer u waarden van het ene veld naar het andere toewijst.

![](assets/d365-to-acs-ui-page-ingress-mappings-fields-selected.png)

>[!NOTE]
>
> U kunt geen veelvoudige Dynamica 365 van Microsoft gebieden aan één enkel gebied van de Campagne in kaart brengen.

### Veldvervangingen {#field-replacements}

Gebruik de knop **[!UICONTROL Add New Field Replacement]** om een nieuwe veldvervanging te definiëren.

Met veldvervangingen kunt u het volgende identificeren:

* een Microsoft Dynamics 365-veldnaam (die hierboven is toegevoegd in de sectie veldtoewijzingen),
* een bestaande waarde (die in de Dynamica 365 van Microsoft bestaat), en
* een nieuwe waarde om naar Adobe Campaign te schrijven

Er wordt een vervolgkeuzelijst weergegeven voor picklist, opsomming en Booleaanse waarden. Een tekstvak wordt gebruikt voor andere tekenreeks- en numerieke typen.

### Filters {#filters}

Gebruik de **[!UICONTROL Add New Filter]** knoop om te selecteren welke Dynamica 365 van Microsoft verslagen aan Campagne zullen worden verspreid. U kunt elk veld kiezen dat is gekoppeld aan een record om aan filters toe te voegen (de veldnaam hoeft niet aan de veldtoewijzingen te worden toegevoegd).

U geeft een filter op door de volgende informatie in te vullen:

* Microsoft Dynamics 365, veldnaam
* een vergelijkingswaarde, en
* a value (from Microsoft Dynamics 365)
Als de veldnaam, vergelijking en waarde voor een bepaalde record de waarde true oplevert, wordt de record doorgegeven aan Adobe Campaign.

U kunt kiezen hoe deze filters worden geëvalueerd door het invoerlabel **[!UICONTROL Choose the filter comparison operator]** in te stellen.  Als u **And** kiest, moeten alle filters waar voor een verslag zijn om aan Campagne worden verspreid. Als u **Of** kiest, zal het verslag worden verspreid als om het even welk van hen aan waar evalueert.

Met de optie **[!UICONTROL Do you want to delete records in Adobe Campaign Standard that will be filtered out from Microsoft Dynamics 365?]** bepaalt u of records die zijn uitgefilterd, uit Campagne moeten worden verwijderd. Als u **No** selecteert, blijven de records in Adobe Campaign. Selecteer **Ja** om deze door de integratielogica te verwijderen.

>[!NOTE]
>
> Als er geen filters worden toegevoegd, worden alle gewijzigde records doorgegeven aan Adobe Campaign.


### Geavanceerde instellingen {#advanced-settings}

U kunt de volgende aanvullende opties instellen wanneer u een toewijzing configureert:

* Stel de optie **[!UICONTROL Apply deletes in Microsoft Dynamics 365 to Campaign?]** in op **Yes** als u verwijderingen die voorkomen in Microsoft Dynamics 365 wilt doorgeven aan het corresponderende veld in Adobe Campaign (op basis van de veldnaamtoewijzing). Selecteer **Nee** om verwijderingen in Microsoft Dynamics 365 te negeren.

* Stel de optie **[!UICONTROL Use technical values in Microsoft Dynamics 365 picklists?]** in op **Nee** als u wilt propageren voor Campagne over de weergavewaarde die aan een keuzelijst voor Microsoft Dynamics 365 is gekoppeld. Selecteer **Ja** om de technische waarde door te geven.

## Campagne marketing gebeurtenissen aan de Dynamica 365 van Microsoft synchroniseren

Op de pagina **[!UICONTROL Campaign to Microsoft Dynamics 365]** kunt u zien welke e-mailmarketinggebeurtenissen van Adobe Campaign aan Microsoft Dynamics 365 worden toegewezen.

De vier metriek die u kunt controleren zijn: **Verzendt**, **Klik**, **Opens**, en **Bounces**.

![](assets/d365-to-acs-ui-page-workflows-egress.png)

Selecteer **Yes** om te bevestigen dat u gebeurtenissen van dat type aan de Dynamica 365 van Microsoft wilt stromen.

Klik [hier](../../integrating/using/d365-acs-self-service-app-workflows.md) voor meer informatie over deze e-mailgebeurtenisstromen.

## Workflow {#opt-in-out-wf} in- en uitschakelen

Met de **Opt-In/Out**-workflow kunt u de stroom van de gegevens voor in- en uitschakelen tussen Microsoft Dynamics 365 en Adobe Campaign identificeren. Hierbij wordt ervan uitgegaan dat de gegevens zijn gekoppeld aan de Microsoft Dynamics 365-entiteit &quot;contact&quot; en het Adobe Campaign-bronprofiel.

Meer informatie over Opt-out beheer in [deze sectie](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out).

Houd er rekening mee dat u op &quot;Opslaan&quot; moet klikken om uw selecties op te slaan. Herinner ook dat u **Campagne aan de Dynamica 365** van Microsoft moet ophouden werkschema en dan spel voor de integratie klikken om uw veranderingen op te nemen.

![](assets/d365-to-acs-ui-page-workflows-optinout-disabled.png)

### Richting voor in- en uitsynchroniseren

Hieronder vindt u een lijst met beschikbare opties voor het synchroniseren van gegevens:

* **[!UICONTROL Disabled]**: Als deze optie is geselecteerd, wordt er geen informatie over in- en uitschakelen verplaatst tussen Adobe Campaign en Microsoft Dynamics 365.

* **[!UICONTROL Unidirectional (Microsoft Dynamics 365 to Campaign)]**: Deze optie wordt gebruikt om opt-in/uit van de Dynamiek 365 van Microsoft aan Adobe Campaign slechts te stromen. De integratietoepassing zal u niet de stroom in dit scherm laten vormen; Klik in plaats daarvan op **[!UICONTROL Save button]** en navigeer naar de **[!UICONTROL Microsoft Dynamics 365 to Campaign]**-workflow. In deze workflow kunt u de toewijzing van contactpersonen/profieltabellen bewerken om te bepalen hoe u wilt dat uw velden voor in- en uitschakelen worden toegewezen.

* **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**: Met deze optie wordt de sectie  **** Toewijzingen weergegeven. Met deze invoer kunt u bepalen welke Adobe Campaign-velden gegevens toewijzen aan welke velden in Microsoft Dynamics 365. Dit betekent dat als u toevallig een waarde in de Dynamica 365 van Microsoft manueel bijwerkt dan zijn waarde door de waarde van Adobe Campaign zou worden beschreven als het gebeurt om te veranderen.

* **[!UICONTROL Bidirectional]**: Met deze optie wordt de sectie  **** Toewijzingen weergegeven. Deze paren zullen identificeren welke gebieden in de Dynamica 365 van Microsoft en Adobe Campaign aan elkaar in kaart zullen brengen. [Meer informatie](../../integrating/using/d365-acs-notices-and-recommendations.md).

### Toewijzingen

Deze sectie is slechts van toepassing wanneer het van de Opt-in/uit synchrone richtingsgebied aan **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** of **[!UICONTROL Bidirectional]** wordt geplaatst. U kunt bepalen welke gebieden in de Dynamica 365 van Microsoft aan welke input in Adobe Campaign in kaart brengen.

De de gebiedsnamen van de Dynamiek 365 van Microsoft omvatten alle die van type **boolean** zijn.

De Adobe Campaign-veldnamen zijn een vaste set waarden die specifiek zijn voor opt-in/out. De Adobe Campaign-veldnamen zijn een vaste set waarden die specifiek zijn voor opt-in/out. **De reeks waarden in deze lijst kan niet worden gewijzigd**.
