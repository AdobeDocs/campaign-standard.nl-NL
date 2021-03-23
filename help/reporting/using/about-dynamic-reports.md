---
solution: Campaign Standard
product: campaign
title: Aan de slag met dynamische rapporten
description: Met dynamische rapporten, sleep en laat vallen variabelen en dimensies in uw vrije vormmilieu en analyseer het succes van uw campagnes.
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Rapporten
role: Leader
level: Beginner
translation-type: tm+mt
source-git-commit: fb9a6218bb754f803affde1fdf6c6fc01570126f
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 5%

---


# Aan de slag met dynamische rapporten {#about-dynamic-reports}

De dynamische Rapportering verstrekt volledig klantgerichte en real-time rapporten. Het voegt toegang tot profielgegevens toe, toelatend demografische analyse door profieldimensies zoals geslacht, stad en leeftijd naast functionele e-mailcampagnegegevens zoals opent en klikt. Met de interface voor slepen en neerzetten kunt u data onderzoeken, bepalen hoe de e-mailcampagnes voor uw belangrijkste klantensegmenten hebben gepresteerd en hun invloed op de ontvangers meten.

>[!NOTE]
>
>Alleen gebruikers met beheerrechten of met organisatorische eenheden ingesteld op **All** kunnen een nieuw rapport maken of opslaan. Raadpleeg deze [sectie](../../administration/using/users-management.md) voor meer informatie.

## Toegang tot dynamische rapporten {#accessing-dynamic-reports}

Rapporten zijn toegankelijk:

* Van de homepage door **[!UICONTROL Reports]** lusje in de hoogste bar te selecteren of **[!UICONTROL Reports]** kaart om tot rapporten voor alle leveringen toegang te hebben.

   ![](assets/campaign_reports_access.png)

* In elk programma, campagne, en bericht, van **Rapporten** knoop door **Dynamische Rapporten** te klikken om de rapporten slechts te bekijken specifiek voor de levering.

   ![](assets/campaign_reports_description.png)

Bepaalde rapporten kunnen niet direct na een levering beschikbaar zijn, afhankelijk van de tijd die het kost om informatie te verzamelen en te verwerken.

Dynamische rapporten worden in twee categorieën onderverdeeld:

* **Sjablonen**, die kunnen worden gewijzigd door ze te kopiëren met de optie  **Opslaan** (**Project > Opslaan als..**) in de sjabloon.
* **Aangepaste rapporten**  (weergegeven in blauw) die u rechtstreeks kunt maken door op de knop  **Nieuw** project maken op de pagina  **** Rapporten te klikken.

>[!NOTE]
>
>De gegevens worden gefilterd afhankelijk van uw organisatorische eenheden.

![](assets/dynamic_report_overview.png)

## Dynamische gebruiksovereenkomst voor rapportage {#dynamic-reporting-usage-agreement}

Het doel van de dynamische rapportgebruiksovereenkomst is als pop-uptoestemming voor gegevensverwerking te werken. Standaard is de overeenkomst alleen zichtbaar en kan deze alleen worden geaccepteerd of geweigerd door gebruikers met beheerrechten.

Er zijn drie opties beschikbaar:

* **[!UICONTROL Ask me later]**: Als u later **op** Vragen klikt, wordt het venster 24 uur niet meer weergegeven. Totdat u de overeenkomst accepteert of afwijst, worden de profielafmetingen niet weergegeven in uw rapporten en worden de persoonlijke identificatiegegevens van uw klanten niet verzameld of verzonden.
* **[!UICONTROL Accept]**: Door deze overeenkomst te accepteren, machtigt u Adobe Campaign om de persoonlijke identiteitsgegevens van uw klanten te verzamelen en deze over te dragen aan het rapportage- of datacenter.
* **[!UICONTROL Decline]**: Als u de overeenkomst afwijst, worden de profielafmetingen niet weergegeven in uw rapporten en worden de persoonlijke identificatiegegevens van uw klanten niet verzameld of verzonden. Let erop dat in dit geval externalID nog steeds wordt verzameld en gebruikt om eindgebruikers te identificeren.

In de onderstaande tabel ziet u wat er gebeurt als u deze overeenkomst accepteert, afhankelijk van uw regio.

|  | Dynamische rapportage | Microsoft Dynamics 365-connector |
|---|---|---|
| Amerika en APAC (Azië-Stille Oceaan) | **Functie beschikbaar**. <br>Alle informatie over alle out-of-the-box (d.w.z. stad, land/regio, staat, geslacht en segmenten op basis van leeftijd) en aangepaste profielen die naar het Amerikaanse rapportagecentrum wordt doorgestuurd. Raadpleeg voor meer informatie over profielafmetingen deze [pagina](../../reporting/using/list-of-components-.md) | **Functie beschikbaar**. <br>Alle velden voor out-of-the-box en aangepaste profielen en Adobe Campaign Standard-gebeurtenisvelden worden verwerkt in het Amerikaanse datacenter. |
| EMEA (Europa, Midden-Oosten en Afrika) | **Functie beschikbaar**. <br>Alle informatie over alle out-of-the-box (d.w.z. stad, land/regio, staat, geslacht en segmenten op basis van leeftijd) en aangepaste profielen die naar het EMEA-rapportagecentrum wordt doorgestuurd. Raadpleeg voor meer informatie over profielafmetingen deze [pagina](../../reporting/using/list-of-components-.md) | **Functie beschikbaar.** <br>Alle velden voor out-of-the-box en aangepaste profielen en Adobe Campaign Standard-gebeurtenisvelden die in het EMEA-datacenter worden verwerkt. <br>**[!UICONTROL Control data]**die Adobe I/O registratiegegevens en id&#39;s van gebruikersgebeurtenissen voor eindgebruikers bevat die in het Amerikaanse datacenter worden verzonden en opgeslagen. |

In de onderstaande tabel ziet u wat er gebeurt als deze overeenkomst wordt geweigerd, afhankelijk van uw regio. Merk op dat zelfs als u deze overeenkomst afwijst, het melden van leveringen en de integratie van de Dynamica 365 van Microsoft nog beschikbaar zal zijn.

| Regio | Dynamische rapportage | Microsoft Dynamics 365-connector |
|---|---|---|
| Amerika en APAC (Azië-Stille Oceaan) | **Functie beschikbaar**. <br> Geen informatie over out-of-the-box &amp; aangepaste profielen die naar het rapportcentrum van de V.S. met uitzondering van ExternalID wordt geduwd. | **Functie beschikbaar**. <br>Er worden geen buiten-de-box of aangepaste profielvelden verzonden naar het Amerikaanse datacenter, met uitzondering van de externe id en de ontvanger-id. <br>Alle Adobe Campaign Standard-gebeurtenisvelden die worden verwerkt in het Amerikaanse datacenter, met uitzondering van de ID van de spiegel. <br>Voor meer informatie over de integratie van de Dynamiek 365 van Microsoft, verwijs naar deze  [pagina](../../integrating/using/d365-acs-get-started.md). |
| EMEA (Europa, Midden-Oosten en Afrika) | **Functie beschikbaar**. <br>Geen informatie over out-of-the-box en aangepaste profielen doorgegeven aan het EMEA-rapportagecentrum, met uitzondering van ExternalID. | **Functie beschikbaar.** <br>Geen velden met een out-of-the-box- of aangepast profiel die naar het EMEA-datacenter worden verzonden, met uitzondering van de externe id en de ontvanger-id. <br>Alle Adobe Campaign Standard-gebeurtenissenvelden die in het EMEA-datacenter worden verwerkt, met uitzondering van de mirror page ID.  <br>**[!UICONTROL Control data]**die Adobe I/O registratiegegevens en id&#39;s van gebruikersgebeurtenissen voor eindgebruikers bevat die in het Amerikaanse datacenter worden verzonden en opgeslagen.<br>Voor meer informatie over de integratie van de Dynamiek 365 van Microsoft, verwijs naar deze  [pagina](../../integrating/using/d365-acs-get-started.md). |

Deze keuze is niet definitief, u kunt deze altijd wijzigen door **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** te selecteren in **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**.

De waarde kan op elk gewenst moment worden gewijzigd. De waarde 1 komt overeen met **[!UICONTROL Ask me later]**, 2 **[!UICONTROL Decline]** en 3 **[!UICONTROL Accept]**.

![](assets/pii_window_2.png)
