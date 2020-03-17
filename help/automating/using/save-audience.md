---
title: Adviezen opslaan
description: Met de activiteit voor het opslaan van het publiek kunt u een bestaand publiek bijwerken of een nieuw publiek maken op basis van de populatie die stroomopwaarts in een workflow is berekend.
page-status-flag: never-activated
uuid: 8babb173-fa59-44a7-a2a5-49f45ba6bf99
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 1f6bb048-7abd-499b-a4b0-187f9492dc47
context-tags: saveAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Adviezen opslaan{#save-audience}

## Beschrijving {#description}

![](assets/save_audience.png)

Met de **[!UICONTROL Save audience]** activiteit kunt u een bestaand publiek bijwerken of een nieuw publiek maken van de bevolking die stroomopwaarts in een workflow is berekend. Het publiek dat met deze activiteit wordt gemaakt of bijgewerkt, is **List** - of **File** -publiek. Ze worden toegevoegd aan de lijst met doelgroepen van toepassingen en worden beschikbaar gesteld via het **[!UICONTROL Audiences]** menu.

>[!NOTE]
>
>Als het publiek dat door de **[!UICONTROL Save audience]** activiteit wordt gecreeerd met extra gegevens is verrijkt, zult u niet deze gegevens kunnen gebruiken om een standalone levering te personaliseren. Ze kunnen alleen worden gebruikt vanuit een levering die wordt uitgevoerd in een workflow.

Met deze activiteit kunt u profielen ook exporteren als Adobe Experience Cloud-publiek/segmenten. Op die manier kunt u deze soorten publiek benutten in andere Adobe Experience Cloud-oplossingen. Voor meer informatie over gedeeld publiek, verwijs naar het [Werken met Campagne en de Dienst](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)van de Kern van Mensen.

## Gebruikscontext {#context-of-use}

De **[!UICONTROL Save audience]** activiteit wordt hoofdzakelijk gebruikt om populatiegroepen in de zelfde werkschema gegevens te bewaren, door hen in herbruikbaar publiek om te zetten.

## Configuratie {#configuration}

1. Zet een **[!UICONTROL Save audience]** activiteit neer in uw werkschema.
1. Verbind het na andere het richten activiteiten zoals een vraag, een doorsnede, een unie, of een uitsluiting.
1. Selecteer de activiteit, dan open het gebruikend de ![](assets/edit_darkgrey-24px.png) knoop van de snelle acties die verschijnen.
1. Selecteer de actie die u wilt uitvoeren:

   * **[!UICONTROL Update an existing audience]**: Selecteer een bestaand publiek en kies het type update:

      * **[!UICONTROL Replace audience content with new data]**: De volledige inhoud van het publiek wordt vervangen. De oude gegevens gaan verloren. Alleen de gegevens van de binnenkomende overgang van de activiteit voor het opslaan van het publiek blijven behouden.
      * **[!UICONTROL Complete audience with new data]**: De oude publieksgegevens worden bewaard en de gegevens van sparen publieksactiviteit&#39;s binnenkomende overgang wordt toegevoegd aan het.
   * **[!UICONTROL Create then update an audience]**: Voer de naam van het publiek in en selecteer het updatetype. Als het publiek nog niet bestaat, wordt het gemaakt. Als deze al bestaat, wordt deze bijgewerkt volgens de geselecteerde modus:

      * **[!UICONTROL Replace audience content with new data]**: De volledige inhoud van het publiek wordt vervangen. De oude gegevens gaan verloren. Alleen de gegevens van de binnenkomende overgang van de activiteit voor het opslaan van het publiek blijven behouden.

         Waarschuwing: met deze optie wist u het publiekstype en de doeldimensie van het bijgewerkte publiek.

      * **[!UICONTROL Complete audience with new data]**: De oude publieksgegevens worden bewaard en de gegevens van sparen publieksactiviteit&#39;s binnenkomende overgang wordt toegevoegd aan het.

         Waarschuwing: deze optie veroorzaakt een fout als het publiekstype of de doeldimensie van het bijgewerkte publiek niet compatibel zijn met de huidige configuratie van de workflow. U kunt een publiek met bestandstypen bijvoorbeeld niet voltooien met profielen die afkomstig zijn van een query.
   * **[!UICONTROL Create a new audience]**: Voer de naam in van het publiek dat u wilt maken. De tijd en datum waarop het publiek wordt gemaakt, worden automatisch toegevoegd aan de naam van het publiek. Dit maakt het publiek uniek telkens als het werkschema wordt uitgevoerd.
   * **[!UICONTROL Share in Adobe Experience Cloud]**: Als u doelprofielen hebt en u uw publiek wilt exporteren naar Adobe Experience Cloud, selecteert u deze optie en selecteert u een bestaand gedeeld publiek of maakt u een nieuw publiek.

      Selecteer ook een bestand **[!UICONTROL Shared Data source]** dat overeenkomt met de bron van de gegevens in het publiek, zodat de gegevens op de juiste wijze worden afgestemd in Adobe Experience Cloud.

      Als u deze optie gebruikt, wordt het gedeelde publiek niet toegevoegd aan de lijst met Adobe-soorten publiek dat beschikbaar is via het **[!UICONTROL Audiences]** menu.

      >[!NOTE]
      >
      >Deze optie is alleen beschikbaar als de functionaliteit voor gedeeld publiek met Adobe Experience Cloud door uw beheerder is geconfigureerd. Voor meer informatie, verwijs naar het [Werken met Campagne en de Dienst](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)van de Kern van Mensen.
   Het type publiek dat tijdens een update wordt opgeslagen of beschikbaar is, is afhankelijk van de activiteiten die stroomopwaarts in de workflow worden geplaatst.

   Als de doeldimensie van het publiek onbekend is wanneer deze wordt opgeslagen (bijvoorbeeld als deze afkomstig is van een geïmporteerd bestand), wordt het publiek gemaakt of bijgewerkt als een **[!UICONTROL File]** soort publiek.

   Als de het richten dimensie van het bewaarde publiek reeds wordt bepaald wanneer het wordt bewaard (bijvoorbeeld, als het uit het richten, na een vraag, enz. komt), dan wordt het publiek bewaard of bijgewerkt als **[!UICONTROL List]** typepubliek.

   De inhoud van het opgeslagen publiek is dan beschikbaar in de gedetailleerde weergave van het publiek, die toegankelijk is via het **[!UICONTROL Audiences]** menu. De kolommen beschikbaar van deze mening beantwoorden aan de kolommen van de binnenkomende overgang van de werkschema sparen publieksactiviteit. Bijvoorbeeld: de kolommen van het ingevoerde dossier, de extra gegevens die van een vraag worden toegevoegd.

1. Bevestig de configuratie van uw activiteit en sla uw werkschema op.

## Voorbeeld {#example}

De workflow die in dit voorbeeld wordt gedefinieerd, toont een regelmatige publieksupdate van het doel:

* Het wordt automatisch één keer per maand uitgevoerd gebruikend een **[!UICONTROL Scheduler]**.
* U kunt een bestand gebruiken **[!UICONTROL Query]** om alle profielen te herstellen die zijn geabonneerd op de verschillende beschikbare toepassingsservices.
* De **[!UICONTROL Save audience]** activiteit werkt het publiek bij door profielen te schrappen die van de dienst sinds de laatste werkschemauitvoering hebben losgemaakt en door de onlangs geabonneerde profielen toe te voegen.

![](assets/save_audience_example_1.png)

De **[!UICONTROL Save audience]** activiteit wordt gevormd als volgt:

![](assets/save_audience_example_2.png)

