---
title: Toewijzingsdefinitie
description: Leer hoe u een veld Campagnestandaard toewijst aan een veld Experience Data Model (XDM).
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c2ed4b3c85ceef3b604a8f68d924c7e5d9fad900

---


# Toewijzingsdefinitie {#mapping-definition}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector is momenteel in bèta, die vaak zonder kennisgeving kan worden bijgewerkt. Klanten moeten op Azure (momenteel alleen in bèta voor Noord-Amerika) worden gehost om toegang te krijgen tot deze mogelijkheden. Neem contact op met de klantenservice van Adobe als u toegang wilt.

In deze sectie, zult u ontdekken hoe te om een Standaardgebied van de Campagne met een gebied van de Gegevens van de Ervaring in kaart te brengen XDM (XDM).

Om deze taak uit te voeren, zijn de eerste vereisten:

* een XDM-schemadefinitie via de interface of met behulp van de REST API die aan XDM is gekoppeld
* een verwezenlijking Dataset die op de XDM schemadefinitie wordt gebaseerd

1. Ga naar **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** en kies de **[!UICONTROL Data mappings]** vermelding.

1. Klik op **[!UICONTROL Create]** om een nieuwe XDM-toewijzing te starten.

   ![](assets/aep_createmapping.png)

1. Vul de verplichte velden in en selecteer:

   * een **gerichte dimensie**: dit is het standaardschema van de Campagne om in kaart te brengen
   * een **gegevensset**: Dit is het gegevenspakket dat is gekoppeld aan een XDM-schema in het Adobe Experience Platform.

>[!NOTE]
>
>Als een partij in het Profiel van de Klant in real time of de Dienst van de Identiteit moet worden opgenomen, moet de dataset voor het Profiel [van de Klant in real time worden](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/intro/get-started.html)toegelaten.
>
>Als de gegevensset die u selecteert al wordt gebruikt in een bestaande gegevenstoewijzing, wordt een waarschuwing weergegeven dat uw gegevens mogelijk worden overschreven op het Adobe Experience Platform. Dit kan gebeuren wanneer er sommige gemeenschappelijke ontvangers in datamappings gebruikend een zelfde dataset zijn.

In het volgende scherm wordt de **[!UICONTROL Field mappings]** sectie weergegeven waarin u een nieuwe toewijzing kunt maken voor elk veld in het schema Standaard campagne.

![](assets/aep_fieldmappings.png)

Met de **[!UICONTROL Create new field mapping]** knop kunt u het veld Campagnestandaard en de bijbehorende padexpressie voor velden selecteren in het XDM-schema.

Als u geen veld Campagnestandaard kunt vinden, kunt u het zoekveld gebruiken om naar het veld te zoeken. Op dit moment werkt alleen zoeken naar velden die zijn geopend in de hiërarchie.

![](assets/aep_mapfield.png)

De uitgebreide bronnen die zijn gedefinieerd in de Campagnestandaard worden toegewezen aan alle native velden. Ze worden gedefinieerd in de extensie _customer/default in XDM.

![](assets/aep_fieldscusmapping.png)

U kunt de XDM-extensie aanpassen via de API en uw eigen extensie definiëren, zodat u een betere controle hebt over de toewijzing.

Zie [Schema Registry API zelfstudie](https://docs.adobe.com/content/help/en/experience-platform/xdm/api/getting-started.html) voor meer informatie over XDM API.

Als u een opsommingsveld wilt toewijzen, moet u de expressie-editor gebruiken om elke opsommingswaarde te definiëren die overeenkomt met de XDM-waarde. Het postadressfield moet bijvoorbeeld als volgt worden gedefinieerd:

![](assets/aep_enummapping.png)

Als de waarde XDM als opsomming in het Schema XDM wordt bepaald, kunt u de inheemse functie gebruiken EXDM die automatisch de **lif** syntaxis zal vervangen.

![](assets/aep_enummappingexdm.png)

Als u een XDM-toewijzing wilt bewerken, opent u deze, wijzigt u de gewenste informatie en slaat u deze op.

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>Als u momenteel een waarde in de **[!UICONTROL Field mappings]** sectie bewerkt en vervolgens buiten het veld klikt, wordt de wijziging pas in de interface weergegeven wanneer u op de **[!UICONTROL Save]** knop klikt. Dit gedrag treedt slechts eenmaal op, wanneer de bewerking op de eerste bewerking op de pagina **[!UICONTROL Field Mappings]** is.
