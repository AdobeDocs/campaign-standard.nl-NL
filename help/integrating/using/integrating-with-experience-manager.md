---
title: Informatie over de integratie van Campaign-Experience Manager
description: Met de Adobe Experience Manager-integratie kunt u inhoud rechtstreeks in AEM maken en later in Adobe Campaign gebruiken.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ff94f69b-3036-4103-a841-6b85feb0eb7e
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 1%

---

# Informatie over de integratie van Campaign-Experience Manager{#integrating-with-experience-manager}

Dankzij deze integratie tussen Adobe Campaign Standard en Adobe Experience Manager kunt u inhoud die in Adobe Experience Manager is gemaakt, gebruiken in uw Adobe Campaign-e-mails.

U kunt dus optimaal gebruikmaken van de Adobe Experience Manager-functies voor het bewerken van inhoud en van Adobe Campaign-functionaliteit voor levering en gegevensbeheer. U kunt geen A/B-tests uitvoeren voor inhoud die is geïmporteerd uit Adobe Experience Manager.

Adobe Campaign Standard is compatibel met Adobe Experience Manager 6.1, 6.2, 6.3, 6.4 en 6.5. In de volgende secties wordt een overzicht gegeven van de handelingen die u kunt uitvoeren. Voor meer informatie, verwijs naar de secties gewijd aan [ configuratie ](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html) en het [ gebruik ](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html) van de integratie.

>[!NOTE]
>
> Adobe Campaign Standard-sjablonen zijn niet meer beschikbaar met Adobe Experience Manager 6.5.

## Tips voor het gebruik van de integratie tussen Campagne en Experience Manager {#tips-aem}

* **weet welk malplaatje met de integratie te gebruiken**

  Aangezien e-mailsjablonen bewerkbaar zijn in Adobe Experience Manager, is het misschien gemakkelijker om een sjabloon te bewerken in Adobe Experience Manager. Bepaalde sjablonen zijn echter niet gemakkelijk te verwerken. Afzonderlijke sjablonen die specifiek zijn voor één klant worden niet aanbevolen voor deze integratie en moeten rechtstreeks in Adobe Campaign Standard worden bewerkt.

  Voor meer informatie over malplaatjes, verwijs naar deze [ pagina ](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html).

* **zorg ervoor Externalzer tijdens implementatie** werd gevormd

  Wanneer u de Externalzer configureert terwijl u Experience Manager for Adobe Campaign Standard implementeert, kunt u een bronnenpad transformeren in een URL. Hierdoor kunt u uw afbeeldingen zichtbaar maken op de pagina. Als de ExternalAlizer niet correct is geconfigureerd, bevatten uw e-mails beschadigde afbeeldingen.

  Leren hoe te om Externalzer te vormen, verwijs naar deze [ pagina ](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/externalizer.html).

* **organiseer uw e-mailmalplaatjes om misbruik te vermijden.**

  Door sjablonen te organiseren zorgt u ervoor dat de juiste sjablonen zich in de juiste mappen bevinden en dat de verkeerde sjablonen niet per ongeluk worden gekozen. Tijdens implementatie, zouden de wegen moeten worden gecreeerd om malplaatjes in de juiste plaatsen op te slaan.

  Voor meer informatie over malplaatjes, verwijs naar deze [ pagina ](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html#template-availability).

* **krijgt snel begonnen met uit-van-de-dooscomponenten.**

  Componenten die buiten de box vallen in Adobe Experience Manager for Adobe Campaign Standard kunnen u helpen snel aan de slag te gaan als uw sjablonen niet complex zijn.
Er zijn zeven kant-en-klare componenten in Experience Manager die u kunt gebruiken:

   * Kop
   * Afbeelding
   * Koppeling
   * Scene7-afbeeldingssjabloon
   * Gerichte referentie
   * Tekst en afbeelding
   * Tekst en Personalization

* **HTML voor e-mails is verschillend van HTML voor Web**

  Het is belangrijk om te begrijpen dat u niet dezelfde componenten kunt gebruiken als in uw webinhoud voor e-mailsjablonen. Het gebruiken van uit-van-de-doos componenten zorgt ervoor dat uw componenten e-mail-compatibel zullen zijn.

* **ontkoppel inhoud van malplaatjes en hergebruik hen opnieuw en opnieuw.**

  Als u e-mails instelt in Campaign Standard en een Experience Manager-sjabloon selecteert, kunt u alleen een sjabloon kiezen die nog niet is gekoppeld aan een andere campagne. Als u de inhoud van de ene campagne wijzigt in Adobe Experience Manager en deze vernieuwt, kunt u de inhoud van de andere campagne onbedoeld beïnvloeden.
Als u dit wilt voorkomen, kunt u de sjabloon ontkoppelen en opnieuw gebruiken nadat u de sjabloon hebt gebruikt. U hoeft alleen de sjabloon te selecteren en op **[!UICONTROL Delete the link with Adobe Experience Manager content]** te klikken.

* **Gebruik Adobe Experience Manager om variaties van e-mails voor Adobe Campaign Standard tot stand te brengen.**

  Dankzij deze integratie kunt u eenvoudig één e-mail omzetten in verschillende versies met de segmentatie.
Leren hoe te opstellings segmentatie in Adobe Experience Manager en hoe te om e-mail met gerichte inhoud tot stand te brengen, verwijs naar deze [ pagina ](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem).

* **voor een succesvolle synchronisatie, moet de segmentnaam in Experience Manager de segmentnaam in nauwkeurig Campagne aanpassen.**
