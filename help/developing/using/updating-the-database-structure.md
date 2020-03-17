---
title: De databasestructuur bijwerken
description: Ontdek hoe u de Adobe Campagne-database kunt bijwerken.
page-status-flag: never-activated
uuid: 6c802f4f-d298-4ca4-acdb-09f2ad3865b9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 2448b126-66b8-4608-aa6c-8028fb1902a4
context-tags: deploy,main;eventCusResource,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# De databasestructuur bijwerken{#updating-the-database-structure}

Om uw wijzigingen in het gegevensmodel effectief te maken en hen te kunnen gebruiken, moet de gegevensbestandstructuur worden bijgewerkt.

>[!NOTE]
>
>Aangepaste bronnen worden automatisch vernieuwd tijdens automatische updates die door Adobe worden uitgevoerd.

## Een aangepaste bron publiceren {#publishing-a-custom-resource}

Om de veranderingen toe te passen die op de middelen worden uitgevoerd, moet u een gegevensbestandupdate uitvoeren.

>[!NOTE]
>
>Als een gebied van een douanemiddel dat op een gebeurtenis wordt gebruikt wordt gewijzigd of geschrapt, zal de overeenkomstige gebeurtenis automatisch unpublished. Zie Transactioneel overseinen [Vormen](../../administration/using/configuring-transactional-messaging.md).

1. Selecteer in het geavanceerde menu via het Adobe Campagne-logo **[!UICONTROL Administration]** > **[!UICONTROL Development]** en **[!UICONTROL Publishing]**.
1. De optie **[!UICONTROL Determine modifications since the last publication]** is standaard ingeschakeld, wat betekent dat alleen de wijzigingen worden toegepast die zijn uitgevoerd sinds de laatste update.

   >[!NOTE]
   >
   >De **[!UICONTROL Repair database structure]** herstelt een correcte configuratie als de publicatie alvorens te voltooien ontbrak. Alle wijzigingen die rechtstreeks in de database zijn uitgevoerd en geen aangepaste bronnen gebruiken, worden verwijderd.

   ![](assets/schema_extension_12.png)

1. Klik op de **[!UICONTROL Prepare publication]** knop om de analyse te starten. Houd er rekening mee dat grote tabelupdates moeten worden uitgevoerd wanneer het exemplaar niet intensief wordt gebruikt door workflows.

   Raadpleeg Een bron met API-extensie [](#publishing-a-resource-with-api-extension)publiceren voor meer informatie over de actie die moet worden uitgevoerd op de API voor profielen en services.

   ![](assets/schema_extension_13.png)

1. Nadat de publicatie is uitgevoerd, klikt u op de **[!UICONTROL Publish]** knop om de nieuwe configuraties toe te passen.
1. Na publicatie geeft het **[!UICONTROL Summary]** deelvenster van elke bron aan dat de status nu is **[!UICONTROL Published]** en geeft het de datum van de laatste publicatie op.

   >[!NOTE]
   >
   >Als u nieuwe wijzigingen aanbrengt in een bron, moet u deze bewerking herhalen om de wijzigingen toe te passen.

   Als bronnen de **[!UICONTROL Pending re-draft]** status hebben voordat ze worden gepubliceerd, verschijnt er een extra bericht waarin u wordt gevraagd uw acties te controleren, omdat het publiceren resulteert in definitieve wijzigingen (het verwijderen van kolommen, tabellen...). Om u te helpen deze laatste verandering uitvoeren, is een **[!UICONTROL SQL Script]** lusje beschikbaar. Het verstrekt het SQL bevel dat tijdens de publicatie zal worden uitgevoerd.

   ![](assets/schema_extension_scriptsql.png)

   >[!NOTE]
   >
   >U kunt het proces van het nieuwe ontwerp tegenhouden door de **[!UICONTROL Cancel re-draft]** knoop te klikken. Met deze handeling wordt de oorspronkelijke status van de bron hersteld.

1. Als uw publicatie is mislukt, kunt u altijd teruggaan naar de vorige publicatie door op **[!UICONTROL Back to latest successful publication]** te klikken.

   Als u de publicatie in de status Niet geslaagd verlaat, wordt een pop-upvenster geopend zodra u zich aanmeldt bij uw exemplaar om u eraan te herinneren deze publicatie te herstellen. Uw exemplaar zal niet met nieuwe productversies tot uw publicatie wordt bevestigd.

   ![](assets/schema_extension_31.png)

## Een bron met API-extensie publiceren {#publishing-a-resource-with-api-extension}

U kunt de profiel- en services-API in de volgende gevallen maken:

* Wanneer u de aangepaste bronnen uitbreidt **[!UICONTROL Profiles]** of **[!UICONTROL Services]** de API voor profielen en services bijwerkt, zodat de velden die zijn gedeclareerd in de extensie voor aangepaste bronnen, worden geïntegreerd.
* Wanneer u een douanemiddel bepaalt en u een verbinding tussen de middelen **[!UICONTROL Profiles]** of **[!UICONTROL Services]** en het douanemiddel creeert, kunt u een update uitvoeren om de nieuwe middel in API te omvatten.

U kunt deze optie selecteren in het publicatiescherm.

* Als de API nog niet is gepubliceerd (wat betekent dat u de bron nog nooit hebt uitgebreid of als u deze optie nog niet hebt ingeschakeld voor deze bron of een andere bron), hebt u de keuze om deze wel of niet te maken.

   ![](assets/create-profile-and-services-api.png)

* Als de API al is gepubliceerd (wat betekent dat u de bron al hebt uitgebreid en deze optie eenmaal hebt ingeschakeld), wordt de API-update geforceerd.

   Als de API eenmaal is gemaakt, wordt deze automatisch bijgewerkt wanneer u deze opnieuw publiceert. Zo voorkomt u dat het profiel of de servicemobron van deze API wordt verbroken en schade aan uw instantie wordt toegebracht.

Merk op dat door gebrek, het douanemiddel wordt geïntegreerd, maar, voor een specifiek gedrag, als u deze middel niet wilt publiceren, kunt u de optie selecteren **[!UICONTROL Hide this resource from APIs]** beschikbaar in **[!UICONTROL Resource Properties]**.

![](assets/removefromextoption.png)

Na de **[!UICONTROL Prepare Publication]** stap geeft Adobe Campaign de delta weer tussen de huidige versie van de API en de toekomstige versie na de publicatie op het tabblad **[!UICONTROL Profiles & Services API Preview]**. Als u de API voor het eerst uitbreidt, vergelijkt de delta de out-of-the-box definitie van het douanemiddel met uw uitbreiding.

De informatie die op het tabblad wordt weergegeven, bestaat uit drie gedeelten: toegevoegde, verwijderde en gewijzigde elementen.

![](assets/extendpandsapi_diff.png)

De analyse van de delta is een verplichte stap, aangezien de publicatiestap het API-gedrag zal wijzigen en hoogstwaarschijnlijk de omringende ontwikkeling in een domino-effect zal beïnvloeden.

>[!NOTE]
>
>Deze publicatie werkt de **[!UICONTROL profilesAndServicesExt]** API bij. De **[!UICONTROL profilesAndServices]** API is niet bijgewerkt.

Meer informatie over de Adobe Campagne-API vindt u in de speciale documentatie van Adobe Campagne over [Adobe IO](https://docs.campaign.adobe.com/doc/standard/en/adobeio.html).
