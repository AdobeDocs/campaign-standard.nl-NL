---
title: Informatie over de integratie van Campaign-Experience Manager
description: Met de Adobe Experience Manager-integratie kunt u inhoud rechtstreeks in AEM maken en later in Adobe Campaign gebruiken.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: ff94f69b-3036-4103-a841-6b85feb0eb7e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 1%

---

# Informatie over de integratie van Campaign-Experience Manager{#integrating-with-experience-manager}

Dankzij deze integratie tussen Adobe Campaign Standard en Adobe Experience Manager kunt u inhoud die in Adobe Experience Manager is gemaakt, gebruiken in uw Adobe Campaign-e-mails.

U kunt dus optimaal gebruikmaken van de Adobe Experience Manager-functies voor het bewerken van inhoud en van Adobe Campaign-functionaliteit voor levering en gegevensbeheer. U kunt geen A/B-tests uitvoeren voor inhoud die is geïmporteerd uit Adobe Experience Manager.

Adobe Campaign Standard is compatibel met Adobe Experience Manager 6.1, 6.2, 6.3, 6.4 en 6.5. In de volgende secties wordt een overzicht gegeven van de handelingen die u kunt uitvoeren. Raadpleeg de secties die gewijd zijn aan [configuratie](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html) en de [gebruiken](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html) van de integratie.

>[!NOTE]
>
> Adobe Campaign Standard-sjablonen zijn niet meer beschikbaar met Adobe Experience Manager 6.5.

## Tips voor het gebruik van de integratie tussen Campagne en Experience Manager {#tips-aem}

* **Weet welke sjabloon moet worden gebruikt voor de integratie**

  Aangezien e-mailsjablonen bewerkbaar zijn in Adobe Experience Manager, is het misschien gemakkelijker om een sjabloon te bewerken in Adobe Experience Manager. Bepaalde sjablonen zijn echter niet gemakkelijk te verwerken. Afzonderlijke sjablonen die specifiek zijn voor één klant worden niet aanbevolen voor deze integratie en moeten rechtstreeks in Adobe Campaign Standard worden bewerkt.

  Raadpleeg deze voor meer informatie over sjablonen [page](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html).

* **Zorg ervoor dat Externalzer tijdens de implementatie is geconfigureerd**

  Wanneer u de Externalzer configureert terwijl u Experience Manager voor Adobe Campaign Standard implementeert, kunt u een bronnenpad transformeren in een URL. Hierdoor kunt u uw afbeeldingen zichtbaar maken op de pagina. Als de ExternalAlizer niet correct is geconfigureerd, bevatten uw e-mails beschadigde afbeeldingen.

  Om te leren hoe te om Externalzer te vormen, verwijs naar dit [page](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/externalizer.html).

* **Organiseer uw e-mailsjablonen om misbruik te voorkomen.**

  Door sjablonen te organiseren zorgt u ervoor dat de juiste sjablonen zich in de juiste mappen bevinden en dat de verkeerde sjablonen niet per ongeluk worden gekozen. Tijdens implementatie, zouden de wegen moeten worden gecreeerd om malplaatjes in de juiste plaatsen op te slaan.

  Raadpleeg deze voor meer informatie over sjablonen [page](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html#template-availability).

* **Ga snel aan de slag met onderdelen die niet meer in de verpakking staan.**

  Componenten die buiten de box vallen in Adobe Experience Manager for Adobe Campaign Standard kunnen u helpen snel aan de slag te gaan als uw sjablonen niet complex zijn.
Er zijn zeven out-of-the-box componenten in Experience Manager die u kunt beginnen te gebruiken:

   * Kop
   * Afbeelding
   * Koppeling
   * Scene7-afbeeldingssjabloon
   * Gerichte referentie
   * Tekst en afbeelding
   * Tekst en personalisatie

* **HTML voor e-mails is anders dan HTML voor het web**

  Het is belangrijk om te begrijpen dat u niet dezelfde componenten kunt gebruiken als in uw webinhoud voor e-mailsjablonen. Het gebruiken van uit-van-de-doos componenten zorgt ervoor dat uw componenten e-mail-compatibel zullen zijn.

* **Inhoud loskoppelen van sjablonen en deze telkens opnieuw gebruiken.**

  Wanneer u e-mailberichten instelt in Campaign Standard en een sjabloon voor Experience Managers selecteert, kunt u alleen een sjabloon kiezen die nog niet aan een andere campagne is gekoppeld. Als u de inhoud van de ene campagne wijzigt in Adobe Experience Manager en deze vernieuwt, kunt u de inhoud van de andere campagne onbedoeld beïnvloeden.
Als u dit wilt voorkomen, kunt u de sjabloon ontkoppelen en opnieuw gebruiken nadat u de sjabloon hebt gebruikt. U hoeft alleen de sjabloon te selecteren en op **[!UICONTROL Delete the link with Adobe Experience Manager content]**.

* **Met Adobe Experience Manager kunt u verschillende e-mails voor Adobe Campaign Standard maken.**

  Dankzij deze integratie kunt u eenvoudig één e-mail omzetten in verschillende versies met de segmentatie.
Raadpleeg deze voor meer informatie over het instellen van segmentatie in Adobe Experience Manager en het maken van e-mail met gerichte inhoud [page](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem).

* **Voor een succesvolle synchronisatie, moet de segmentnaam in Experience Manager de segmentnaam in nauwkeurig Campagne aanpassen.**
