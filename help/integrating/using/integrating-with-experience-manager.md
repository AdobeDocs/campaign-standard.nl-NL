---
title: De integratie van Campagne-Experience Manager
description: Met de integratie met Adobe Experience Manager kunt u inhoud rechtstreeks in AEM maken en deze later gebruiken in Adobe Campaign.
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 37e86c6143c52841e69d610fa9db35dff70a3587

---


# De integratie van Campagne-Experience Manager{#integrating-with-experience-manager}

Dankzij deze integratie tussen Adobe Campaign Standard en Adobe Experience Manager kunt u inhoud die in Adobe Experience Manager is gemaakt, gebruiken in uw e-mails over Adobe Campagne.

U kunt daarom optimaal gebruikmaken van de functies voor het bewerken van inhoud in Adobe Experience Manager en van de functies voor levering en gegevensbeheer van Adobe Campaign. U kunt geen A/B-tests uitvoeren voor inhoud die is geïmporteerd uit Adobe Experience Manager.

Adobe Campaign Standard is compatibel met Adobe Experience Manager 6.1, 6.2, 6.3, 6.4 en 6.5. In de volgende secties wordt een overzicht gegeven van de handelingen die u kunt uitvoeren. Voor meer informatie, verwijs naar de secties gewijd aan [configuratie](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html) en het [gebruik](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/campaign.html) van de integratie.

>[!NOTE]
>
> Adobe Campagne Standard-sjablonen zijn niet meer beschikbaar in Adobe Experience Manager 6.5.

## Tips voor het gebruik van de integratie van Campagne-Experience Manager {#tips-aem}

* **Weet welke sjabloon moet worden gebruikt voor de integratie**

   Aangezien e-mailsjablonen kunnen worden bewerkt in Adobe Experience Manager, is het misschien gemakkelijker om een sjabloon te bewerken in Adobe Experience Manager. Bepaalde sjablonen zijn echter niet gemakkelijk te verwerken. Afzonderlijke sjablonen die specifiek zijn voor één klant worden niet aanbevolen voor deze integratie en moeten rechtstreeks worden bewerkt in Adobe Campagnestandaard.

   Raadpleeg deze [pagina](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html)voor meer informatie over sjablonen.

* **Zorg ervoor dat Externalzer tijdens de implementatie is geconfigureerd**

   Wanneer u de ExternalAlizer configureert terwijl u Experience Manager implementeert voor Adobe Campaign Standard, kunt u een bronnenpad omzetten in een URL. Hierdoor kunt u uw afbeeldingen zichtbaar maken op de pagina. Als de ExternalAlizer niet correct is geconfigureerd, bevatten uw e-mails beschadigde afbeeldingen.

   Leren hoe te om Externalzer te vormen, verwijs naar deze [pagina](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/externalizer.html).

* **Organiseer uw e-mailsjablonen om misbruik te voorkomen.**

   Door sjablonen te organiseren zorgt u ervoor dat de juiste sjablonen zich in de juiste mappen bevinden en dat de verkeerde sjablonen niet per ongeluk worden gekozen. Tijdens implementatie, zouden de wegen moeten worden gecreeerd om malplaatjes in de juiste plaatsen op te slaan.

   Raadpleeg deze [pagina](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html#template-availability)voor meer informatie over sjablonen.

* **Ga snel aan de slag met onderdelen die niet meer in de verpakking staan.**

   Componenten die niet in de handel zijn in Adobe Experience Manager voor Adobe Campaign Standard kunnen u helpen snel aan de slag te gaan als uw sjablonen niet complex zijn.
Er zijn zeven out-of-the-box componenten in de Manager van de Ervaring die u kunt beginnen te gebruiken:

   * Kop
   * Afbeelding
   * Koppeling
   * Scene7-afbeeldingssjabloon
   * Gerichte referentie
   * Tekst en afbeelding
   * Tekst en personalisatie

* **HTML voor e-mails is anders dan HTML voor het web**

   Het is belangrijk om te begrijpen dat u niet dezelfde componenten kunt gebruiken die in uw webinhoud worden gebruikt voor e-mailsjablonen. Het gebruiken van uit-van-de-doos componenten zorgt ervoor dat uw componenten e-mail-compatibel zullen zijn.

* **Inhoud loskoppelen van sjablonen en deze telkens opnieuw gebruiken.**

   Als u uw e-mails instelt in Campagnestandaard en een sjabloon voor Experience Manager selecteert, kunt u alleen een sjabloon kiezen die nog niet aan een andere campagne is gekoppeld. Als u de inhoud van de ene campagne wijzigt in Adobe Experience Manager en de inhoud vernieuwt, kunt u de inhoud van de andere campagne onbedoeld beïnvloeden.
Als u dit wilt voorkomen, kunt u de sjabloon ontkoppelen en opnieuw gebruiken nadat u de sjabloon hebt gebruikt. U hoeft alleen de sjabloon te selecteren en te klikken **[!UICONTROL Delete the link with Adobe Experience Manager content]**.

* **Met Adobe Experience Manager kunt u variaties van e-mails maken voor Adobe Campagne Standard.**

   Dankzij deze integratie kunt u eenvoudig één e-mail omzetten in verschillende versies met de segmentatie.
Raadpleeg deze [pagina](https://docs.adobe.com/help/en/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem)voor informatie over het instellen van segmentatie in Adobe Experience Manager en over het maken van e-mail met gerichte inhoud.

* **Voor een succesvolle synchronisatie, moet de segmentnaam in de Manager van de Ervaring de segmentnaam in nauwkeurig Campagne aanpassen.**