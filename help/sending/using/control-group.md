---
title: Een controlegroep toevoegen bij het verzenden van een bericht
description: Leer hoe te om een controlegroep toe te voegen wanneer het bepalen van het doel van een bericht gebruikend Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,segmentation,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cd38d849052e44e5a50c69d7f8184feb2227fdf4
workflow-type: tm+mt
source-wordcount: '1332'
ht-degree: 5%

---


# Een besturingsgroep toevoegen {#adding-control-group}

U kunt controlegroepen gebruiken om het verzenden van berichten naar een gedeelte van uw publiek te vermijden om het effect van uw campagnes te meten.

Om dit in Adobe Campaign te doen, creeer een <b>controlegroep</b> wanneer het bepalen van het doel van uw levering. Profielen worden willekeurig aan de controlegroep toegevoegd, gefilterd of niet, of gebaseerd op criteria.

Vervolgens kunt u het gedrag van de doelgroep die de boodschap heeft ontvangen, vergelijken met het gedrag van contacten die niet als doelgroep werden beschouwd. Gebaseerd op de verzendende logboeken, kunt u een controlegroep in toekomstige campagnes ook richten.

<!--The control group is built when the delivery is prepared.-->

## Overzicht {#overview}

De controlegroep kan willekeurig uit het hoofddoel worden gehaald en/of uit een specifieke populatie worden geselecteerd. Dit betekent dat er twee manieren zijn waarop u een controlegroep kunt definiëren:
* **Extraheer** een aantal profielen uit het hoofddoel.
* **Hiermee sluit** u bepaalde profielen uit op basis van criteria die in een query zijn gedefinieerd.

U kunt beide methoden gebruiken bij het definiëren van een besturingsgroep.

Alle profielen die deel uitmaken van de controlegroep bij de voorbereidingsstap voor levering worden uit het hoofddoel verwijderd. Ze zullen het bericht niet meer ontvangen nadat het is verzonden.

## Uithalen uit de doelpopulatie {#extraction-target-population}

Als u een controlegroep wilt definiëren, kunt u kiezen of u willekeurig of op basis van een sortering, een percentage of een vast aantal profielen wilt extraheren uit de doelpopulatie.

### Doelextractie {#target-extraction}

Bepaal eerst hoe de profielen uit het doel worden gehaald: **willekeurig** of op basis van een **sortering**.

Selecteer onder de **[!UICONTROL Target extraction]** sectie een van de volgende opties:

* **[!UICONTROL Random sampling]**: bij het voorbereiden van de levering haalt Adobe Campaign willekeurig een aantal profielen op dat overeenkomt met het percentage of het maximumaantal dat u als [groottebeperking](#size-limit)instelt.

   Als u de drempelwaarde bijvoorbeeld instelt op 10 in de **[!UICONTROL Limits]** sectie, bestaat de controlegroep uit 10% die willekeurig wordt geselecteerd uit de doelpopulatie.<!--Change screenshot to match example)-->

   ![](assets/control-group-random-sampling.png)

* **[!UICONTROL Keep only the first records after sorting]**: met deze optie kunt u een beperking definiëren op basis van een of meer sorteervolgorden.

   Bijvoorbeeld:

   * Selecteer het **[!UICONTROL Age]** veld als sorteercriterium.
   * Definieer 100 als de drempel in de **[!UICONTROL Limits]** sectie (zie [Groottebeperking](#size-limit)).
   * Laat de **[!UICONTROL Descending sort]** optie ingeschakeld.

   Als gevolg hiervan zal de controlegroep bestaan uit de 100 oudste ontvangers.<!--Change screenshot to match example)-->

   ![](assets/control-group-keep-first-records.png)

   Het kan interessant zijn om een controlegroep te bepalen die profielen omvat die weinig of frequente aankopen doen, en hun gedrag met dat van de gecontacteerde ontvangers te vergelijken.

>[!NOTE]
>
>Selecteer **[!UICONTROL No extraction]** als u de **[!UICONTROL Target extraction]** optie niet wilt gebruiken.

<!--![](assets/control-group-no-extraction.png)-->

### Groottebeperking {#size-limit}

Of u nu selecteert **[!UICONTROL Random sampling]** of **[!UICONTROL Keep only the first records after sorting]**, u moet instellen hoe u het aantal profielen dat u uit het hoofddoel extraheert, gaat beperken. Voer een van de volgende handelingen uit:

* Selecteer **[!UICONTROL Size (as a % of the initial population)]** en vul het bijbehorende frame in.

   Als u bijvoorbeeld 10 instelt, afhankelijk van de hierboven geselecteerde optie, zal Adobe Campaign:
   * Extraheer willekeurig 10% van de doelpopulatie.
   * Als u het **[!UICONTROL Age]** veld als sorteercriterium hebt geselecteerd, haalt u de 10% oudste profielen uit de doelpopulatie.

   >[!NOTE]
   >
   >Als u de **[!UICONTROL Descending sort]** optie uitschakelt, worden de 10% jongste profielen geëxtraheerd.

* Selecteer **[!UICONTROL Maximum size]** en vul het bijbehorende frame in.

   Als u bijvoorbeeld 100 instelt, zal Adobe Campaign:
   * Extraheer willekeurig 100 profielen uit de doelpopulatie.
   * Als u het **[!UICONTROL Age]** veld als sorteercriterium hebt geselecteerd, extraheert u de 100 oudste profielen uit de doelpopulatie.

   >[!NOTE]
   >
   >Als u de **[!UICONTROL Descending sort]** optie uitschakelt, worden de 100 jongste profielen geëxtraheerd.

## Exclusief een specifieke populatie {#excluding-specific-population}

Een andere manier om een controlegroep te bepalen is een specifieke bevolking van het doel uit te sluiten gebruikend een vraag.

Dit doet u als volgt:

1. From the **[!UICONTROL Target exclusion]** section, click **[!UICONTROL Define target exclusion]**.

   ![](assets/control-group-define-target-exclusion.png)

1. Bepaal de uitsluitingscriteria gebruikend de [vraagredacteur](../../automating/using/editing-queries.md). U kunt ook een eerder [gemaakt publiek](../../audiences/using/about-audiences.md) selecteren.

   ![](assets/control-group-target-exclusion.png)

1. Klik op **[!UICONTROL Confirm]**.

De profielen die overeenkomen met het resultaat van de query worden van het doel uitgesloten.

<!--For more on using the query editor, see the [Editing queries](../../automating/using/editing-queries.md) section.-->

## Hoofdlettergebruik: een controlegroep instellen {#control-group-example}

Hieronder ziet u een voorbeeld van hoe u een besturingsgroep definieert met beide methoden: het halen van profielen van het belangrijkste doel en het gebruiken van een vraag om een specifieke bevolking uit te sluiten.

1. Een workflow maken. De gedetailleerde stappen voor het maken van een workflow worden uitgelegd in de sectie [Een workflow maken](../../automating/using/building-a-workflow.md).
1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, sleep en laat vallen een activiteit van de [Vraag](../../automating/using/query.md) . Dubbelklik op de activiteit en definieer het doel. <!--For example, in **[!UICONTROL Shortcuts]**, drag and drop **[!UICONTROL Profile]**, select **[!UICONTROL Age]** with the operator **[!UICONTROL Greater than]** and type 25 in the **[!UICONTROL Value]** field.-->

1. Sleep in **[!UICONTROL Activities]** > **[!UICONTROL Channels]** een [e-mailbezorgingsactiviteit](../../automating/using/email-delivery.md) na het hoofddoelsegment en bewerk deze.
1. Klik op het **[!UICONTROL Audience]** blok van het bezorgdashboard.

1. Selecteer het tabblad **[!UICONTROL Control group]**. 

   ![](assets/control-group-tab.png)

1. Selecteer in de **[!UICONTROL Target extraction]** sectie **[!UICONTROL Keep only the first records after sorting]**.
1. Sorteer op de leeftijd en laat de **[!UICONTROL Descending]** sorteeroptie ingeschakeld.

   ![](assets/control-group-sorting-column.png)

1. Stel 100 in als de maximale grootte. De 100 oudste profielen van het doel worden geëxtraheerd.

1. Definieer in de **[!UICONTROL Target exclusion]** sectie de profielen die van het doel worden uitgesloten op basis van de criteria van uw keuze met de [query-editor](../../automating/using/editing-queries.md). Bijvoorbeeld: &quot;Leeftijd is minder dan 20&quot;.

   ![](assets/control-group-target-exclusion-example.png)

   Profielen die jonger zijn dan 20 jaar worden uitgesloten.

1. Start de [voorbereiding](../../sending/using/preparing-the-send.md) van de levering en [bevestig de verzending](../../sending/using/confirming-the-send.md).

De profielen die zijn geëxtraheerd (de 100 oudste profielen) en de profielen die zijn gedefinieerd op basis van de query (profielen onder 20), worden uit het hoofddoel verwijderd. Ze zullen het bericht niet ontvangen.

## De resultaten vergelijken {#delivery-logs}

Nu u uw levering verzond, wat kunt u met de controlegroep doen?

U kunt de **verzendende logboeken** halen om te vergelijken hoe de controlegroep die de mededeling niet ontving in vergelijking met het efficiënte doel handelde. U kunt de leveringslogboeken ook gebruiken om een andere het richten **te** bouwen.

>[!IMPORTANT]
>
>U moet een [beheerdersrol](../../administration/using/users-management.md#functional-administrators) hebben en deel uitmaken van de **[!UICONTROL All]** organisatie-eenheid [](../../administration/using/organizational-units.md) om verbinding te kunnen maken met Adobe Campaign. Als u toegang voor een bepaalde gebruiker of een groep gebruikers wilt beperken, koppel het niet aan **[!UICONTROL All]** eenheden om tot leveringslogboeken toegang te hebben.

### De leveringslogs controleren {#checking-logs}

Als u wilt zien welke profielen uit het doel zijn verwijderd nadat het bericht is verzonden, selecteert u de optie **[!UICONTROL Delivery logs]**. Voor meer op de leveringslogboeken en hoe te om tot hen toegang te hebben, zie [deze sectie](../../sending/using/monitoring-a-delivery.md#delivery-logs).

* Op het **[!UICONTROL Sending logs]** tabblad ziet u de geëxtraheerde en uitgesloten profielen. Ze hebben de **[!UICONTROL Ignored]** status en **[!UICONTROL Control group]** de oorzaak van een mislukking.

   ![](assets/control-group-sending-logs.png)

* U kunt ook het **[!UICONTROL Exclusion causes]** tabblad controleren om te zien hoeveel profielen niet zijn opgenomen in de levering.

   ![](assets/control-group-exclusion-causes.png)

### De logboeken van de controlegroep gebruiken {#using-logs}

Nadat de levering is verzonden, kunt u de leveringslogboeken gebruiken om te filteren op de profielen die het bericht niet hebben ontvangen. Voer de onderstaande stappen uit:

1. Een workflow maken. De gedetailleerde stappen voor het maken van een workflow worden uitgelegd in de sectie [Een workflow maken](../../automating/using/building-a-workflow.md).
1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, sleep en laat vallen een activiteit van de [Vraag](../../automating/using/query.md) .
1. In het **[!UICONTROL Properties]** lusje, plaats **[!UICONTROL Delivery logs]** als **[!UICONTROL Resource]** en **[!UICONTROL Profile]** als **[!UICONTROL Targeting dimension]**.

   ![](assets/control-group-delivery-properties.png)

1. Klik op het tabblad **[!UICONTROL Target]** op **[!UICONTROL Delivery logs]**.
1. Sleep en zet **[!UICONTROL Status]** de aanwijzer neer en selecteer deze **[!UICONTROL Ignored]** als filtervoorwaarde.

   ![](assets/control-group-status-ignored.png)

1. Klik op **[!UICONTROL Confirm]**.

1. Blijf op het **[!UICONTROL Target]** tabblad, sleep en zet het neer **[!UICONTROL Nature of failure]** en selecteer **[!UICONTROL Control group]** als filtervoorwaarde.

   ![](assets/control-group-nature-of-failure.png)

1. Klik op **[!UICONTROL Confirm]**.

   ![](assets/control-group-delivery-target.png)

U kunt de logboekgegevens dan uitvoeren gebruikend een **Extraheren dossieractiviteit** die door een activiteit van het **Overdracht van dossierdossier** wordt gevolgd. Hierdoor kunt u in uw eigen rapportagehulpprogramma de resultaten van uw campagne analyseren op het effectieve doel in vergelijking met de controlegroep. For more on exporting logs, see [this section](../../automating/using/exporting-logs.md).

### Het richten van de controlegroep {#targeting-control-group}

Als u zich wilt richten op basis van de profielen die het bericht niet hebben ontvangen, kunt u ook de leveringslogboeken gebruiken. Voer de onderstaande stappen uit:

1. Een workflow maken. De gedetailleerde stappen voor het maken van een workflow worden uitgelegd in de sectie [Een workflow maken](../../automating/using/building-a-workflow.md).
1. Sleep in **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** een eerste [zoekactie](../../automating/using/query.md) .
1. Controleer in het **[!UICONTROL Properties]** tabblad of de **[!UICONTROL Profile]** bron is geselecteerd als de bron **[!UICONTROL Resource]** en **[!UICONTROL Targeting dimension]**.

   ![](assets/control-group-delivery-properties-profile.png)

1. Vouw het **[!UICONTROL Target]** tabblad uit **[!UICONTROL Delivery]** en sleep en zet het neer **[!UICONTROL Delivery logs]**.

   ![](assets/control-group-query-delivery-logs.png)

1. Sleep in het **[!UICONTROL Add a rule]** venster en zet de aanwijzer neer **[!UICONTROL Delivery]**.

   ![](assets/control-group-rule-delivery.png)

1. Selecteer de e-mail die u als filtervoorwaarde hebt verzonden. Klik op **[!UICONTROL Confirm]**.

   ![](assets/control-group-email-sent.png)

1. Sleep terug in het **[!UICONTROL Add a rule]** venster en zet het neer **[!UICONTROL Status]** en selecteer **[!UICONTROL Ignored]** als filtervoorwaarde. Klik op **[!UICONTROL Confirm]**.

   ![](assets/control-group-status-ignored.png)

1. Sleep en zet **[!UICONTROL Nature of failure]** de aanwijzer neer en selecteer deze **[!UICONTROL Control group]** als filtervoorwaarde. Klik op **[!UICONTROL Confirm]**.

   ![](assets/control-group-nature-of-failure.png)

1. Zorg ervoor dat alle voorwaarden zijn uitgelijnd met de operator **AND** boolean.

   ![](assets/control-group-delivery-logs-conditions.png)

1. Klik op **[!UICONTROL Confirm]**.

U kunt nu de profielen activeren waarvoor uw eerste bericht niet is ontvangen omdat deze deel uitmaakten van de controlegroep en hun een e-mail sturen.

In dezelfde workflow kunt u ook een andere query maken voor de profielen die de e-mail wel hebben ontvangen en deze een ander bericht sturen.

![](assets/control-group-targeted-by-delivery.png)