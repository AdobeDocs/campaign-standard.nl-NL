---
title: Aan de slag met dynamische rapporten
description: Met dynamische rapporten, sleep en laat vallen variabelen en dimensies in uw vrije vormmilieu en analyseer het succes van uw campagnes.
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Beginner
exl-id: fc3b28f3-63f6-4edc-923d-c7eb7925d1b7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 2%

---

# Aan de slag met dynamische rapporten {#about-dynamic-reports}

De dynamische Rapportering verstrekt volledig klantgerichte en real-time rapporten. Het voegt toegang tot profielgegevens toe, toelatend demografische analyse door profieldimensies zoals geslacht, stad en leeftijd naast functionele e-mailcampagnegegevens zoals opent en klikt. Met de belemmering-en-dalingsinterface, kunt u gegevens onderzoeken, bepalen hoe uw e-mailcampagnes tegen uw belangrijkste klantensegmenten werden uitgevoerd en hun effect op ontvangers meten.

>[!NOTE]
>
>Alleen gebruikers met beheerrechten of met organisatorische eenheden ingesteld op **Alles** kan een nieuw rapport maken of opslaan. Raadpleeg deze [sectie](../../administration/using/users-management.md) voor meer informatie.

## Dynamische rapporten openen {#accessing-dynamic-reports}

Rapporten zijn toegankelijk:

* Van de homepage door te selecteren **[!UICONTROL Reports]** in de bovenste balk of op de **[!UICONTROL Reports]** kaart voor toegang tot rapporten voor alle leveringen.

  ![](assets/campaign_reports_access.png)

* In elk programma, campagne, en bericht, van **Rapporten** knop door te klikken **Dynamische rapporten** alleen de rapporten weergeven die specifiek zijn voor de levering.

  ![](assets/campaign_reports_description.png)

Bepaalde rapporten kunnen niet direct na een levering beschikbaar zijn, afhankelijk van de tijd die het kost om informatie te verzamelen en te verwerken.

Dynamische rapporten worden in twee categorieën onderverdeeld:

* **Sjablonen**, die kunnen worden gewijzigd door ze te kopiëren met behulp van de **Opslaan als** option (**Project > Opslaan als.**) in de sjabloon.
* **Aangepaste rapporten** (geïdentificeerd in blauw), die direct kan worden tot stand gebracht door te klikken op **Nieuw project maken** op de knop **Rapporten** homepage.

>[!NOTE]
>
>De gegevens worden gefilterd afhankelijk van uw organisatorische eenheden.

![](assets/dynamic_report_overview.png)

## Dynamische gebruiksovereenkomst voor rapportage {#dynamic-reporting-usage-agreement}

Het doel van de dynamische rapportgebruiksovereenkomst is als pop-uptoestemming voor gegevensverwerking te werken. Standaard is de overeenkomst alleen zichtbaar en kan deze alleen worden geaccepteerd of geweigerd door gebruikers met beheerrechten.

Er zijn drie opties beschikbaar:

* **[!UICONTROL Ask me later]**: Klik op **Later vragen**, wordt het venster 24 uur niet meer weergegeven. Totdat u de overeenkomst accepteert of afwijst, worden de profielafmetingen niet weergegeven in uw rapporten en worden de persoonlijke identificatiegegevens van uw klanten niet verzameld of verzonden.
* **[!UICONTROL Accept]**: Door deze overeenkomst te accepteren, machtigt u Adobe Campaign om de persoonlijke identiteitsgegevens van uw klanten te verzamelen en deze over te dragen aan het rapportage- of datacenter.
* **[!UICONTROL Decline]**: Als u de overeenkomst afwijst, worden de profielafmetingen niet in uw rapporten weergegeven en worden de persoonlijke identificatiegegevens van uw klanten niet verzameld of verzonden. Let erop dat in dit geval externalID nog steeds wordt verzameld en gebruikt om eindgebruikers te identificeren.

In de onderstaande tabel ziet u wat er gebeurt als u deze overeenkomst accepteert, afhankelijk van uw regio.

|  | Dynamische rapportage | Microsoft Dynamics 365-connector |
|---|---|---|
| Amerika en APAC (Azië-Stille Oceaan) | **Functie beschikbaar**. <br>Alle informatie over alle out-of-the-box (d.w.z. stad, land/regio, staat, geslacht en segmenten op basis van leeftijd) en aangepaste profielen die naar het Amerikaanse rapportagecentrum wordt doorgestuurd. Raadpleeg voor meer informatie over profielafmetingen [page](../../reporting/using/list-of-components-.md) | **Functie beschikbaar**. <br>Alle velden voor out-of-the-box en aangepaste profielen en Adobe Campaign Standard-gebeurtenisvelden worden verwerkt in het Amerikaanse datacenter. |
| EMEA (Europa, Midden-Oosten en Afrika) | **Functie beschikbaar**. <br>Alle informatie over alle out-of-the-box (d.w.z. stad, land/regio, staat, geslacht en segmenten op basis van leeftijd) en aangepaste profielen die naar het EMEA-rapportagecentrum wordt doorgestuurd. Raadpleeg voor meer informatie over profielafmetingen [page](../../reporting/using/list-of-components-.md) | **Functie beschikbaar.** <br>Alle velden voor out-of-the-box en aangepaste profielen en Adobe Campaign Standard-gebeurtenisvelden die in het EMEA-datacenter worden verwerkt. <br>**[!UICONTROL Control data]**die Adobe I/O registratiegegevens en id&#39;s van gebruikersgebeurtenissen voor eindgebruikers bevat die in het Amerikaanse datacenter worden verzonden en opgeslagen. |

In de onderstaande tabel ziet u wat er gebeurt als deze overeenkomst wordt geweigerd, afhankelijk van uw regio. Zelfs als u deze overeenkomst afwijst, zijn rapportage over leveringen en integratie met Microsoft Dynamics 365 nog steeds beschikbaar.

| Regio | Dynamische rapportage | Microsoft Dynamics 365-connector |
|---|---|---|
| Amerika en APAC (Azië-Stille Oceaan) | **Functie beschikbaar**. <br> Geen informatie over out-of-the-box &amp; aangepaste profielen die naar het rapportcentrum van de V.S. wordt geduwd met uitzondering van ExternalID. | **Functie beschikbaar**. <br>Er worden geen buiten-de-box of aangepaste profielvelden verzonden naar het Amerikaanse datacenter, met uitzondering van de externe id en de ontvanger-id. <br>Alle Adobe Campaign Standard-gebeurtenisvelden die worden verwerkt in het Amerikaanse datacenter, met uitzondering van de ID van de spiegel. <br>Raadpleeg voor meer informatie over de integratie met Microsoft Dynamics 365 deze [page](../../integrating/using/d365-acs-get-started.md). |
| EMEA (Europa, Midden-Oosten en Afrika) | **Functie beschikbaar**. <br>Geen informatie over out-of-the-box en aangepaste profielen doorgegeven aan het EMEA-rapportagecentrum, met uitzondering van ExternalID. | **Functie beschikbaar.** <br>Geen velden met een out-of-the-box- of aangepast profiel die naar het EMEA-datacenter worden verzonden, met uitzondering van de externe id en de ontvanger-id. <br>Alle Adobe Campaign Standard-gebeurtenissenvelden die in het EMEA-datacenter worden verwerkt, met uitzondering van de mirror page ID.  <br>**[!UICONTROL Control data]**die Adobe I/O registratiegegevens en id&#39;s van gebruikersgebeurtenissen voor eindgebruikers bevat die in het Amerikaanse datacenter worden verzonden en opgeslagen.<br>Raadpleeg voor meer informatie over de integratie met Microsoft Dynamics 365 deze [page](../../integrating/using/d365-acs-get-started.md). |

Deze keuze is niet definitief. U kunt deze altijd wijzigen door **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** in **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**.

De waarde kan op elk gewenst moment worden gewijzigd. De waarde 1 komt overeen met **[!UICONTROL Ask me later]**, 2 **[!UICONTROL Decline]** en 3 **[!UICONTROL Accept]**.

![](assets/pii_window_2.png)
