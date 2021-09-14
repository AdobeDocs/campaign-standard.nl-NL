---
title: Dynamische content Target toevoegen
description: Leer hoe u dynamische Adobe Target-inhoud toevoegt aan een van uw Adobe Campaign-leveringen.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 7dfbd89f-877e-4598-bfe3-d743bb31ae9e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 4%

---

# Dynamische content Target toevoegen{#adding-target-dynamic-content}

Dankzij de Adobe Target-integratie kunnen dynamische afbeeldingen aan een levering worden toegevoegd om uw inhoud aan uw wensen aan te passen.

Tijdens het bewerken van een e-mailbericht kunt u een dynamische afbeelding uit Adobe Target invoegen die afhankelijk is van de ontvanger.

Voordat u de afbeelding opent in Adobe Campaign, moet u eerst de volgende taken uitvoeren in Adobe Target:

* Maak een of meer [redirect aanbiedingen](https://experienceleague.adobe.com/docs/target/using/experiences/offers/offer-redirect.html), waarin u de URL van de afbeelding moet opgeven die u wilt gebruiken.
* Maak een of meer [soorten publiek](https://experienceleague.adobe.com/docs/target/using/audiences/create-audiences/audiences.html) om het doel van uw activiteit te definiëren.
* Maak een [Form-based ervaringscomposer](https://experienceleague.adobe.com/docs/target/using/experiences/form-experience-composer.html) activiteit, waarin u een box moet selecteren en verschillende ervaringen moet opgeven, afhankelijk van het aantal nieuwe aanbiedingen. Voor elke ervaring moet je een van de nieuwe aanbiedingen selecteren.
* Maak segmenten met behulp van informatie uit Adobe Campaign om ervaringen op te geven. Als u gegevens van Adobe Campaign wilt gebruiken in de selectieregels van de aanbieding, moet u de gegevens opgeven in het tekstvak in Adobe Target.

1. Een e-maillevering maken.
1. Wanneer u de inhoud van een e-mail- of landingspagina bewerkt, gaat u naar een afbeeldingsblok en selecteert u **[!UICONTROL Dynamic image from Adobe Target]** via het contextmenu.

   ![](assets/tar_insert_dynamic_image.png)

1. Selecteer de afbeelding die standaard in de e-mail wordt weergegeven. U kunt de afbeeldings-URL rechtstreeks opgeven of een afbeelding selecteren die wordt gedeeld via [Middelen](../../integrating/using/working-with-campaign-and-assets-core-service.md).

   De integratie ondersteunt alleen statische afbeeldingen. De rest van de inhoud kan niet worden aangepast.

1. Voer de naam in van het tekstvak dat in Adobe Target is opgegeven.
1. Als u Enterprise-machtigingen gebruikt in uw instellingen in Adobe Target, voegt u de bijbehorende eigenschap toe in dit veld. Meer informatie over de rechten van Target Enterprise vindt u op [deze pagina](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html). Dit veld is optioneel en niet vereist als u de Enterprise-machtigingen in Target niet gebruikt.
1. Geef in **[!UICONTROL Additional decision parameters]** de toewijzing op tussen de velden die zijn gedefinieerd in de Adobe Target-segmenten en de Adobe Campaign-velden.

   De Adobe Campaign-velden die worden gebruikt, moeten zijn opgegeven in de keuzelijst. Hier zullen we verschillende ervaringen definiëren afhankelijk van het geslacht van de ontvanger.

   ![](assets/tar_additional_decisionning_parameters.png)

1. Bekijk een voorbeeld van uw e-mail om te zien of de ingevoegde afbeelding bij het selecteren van verschillende profielen verandert afhankelijk van de parameters die zijn opgegeven in de Adobe Target-activiteit en in Adobe Campaign.

De levering met de dynamische afbeelding kan nu worden verzonden. De resultaten zijn te vinden in Adobe Target.

**Verwante onderwerpen:**

* [Adobe Target Portal](https://experienceleague.adobe.com/docs/target/using/integrate/campaign-and-target.html)
* [Over het ontwerpen van e-mailinhoud](../../designing/using/designing-content-in-adobe-campaign.md)
* [E-mailafbeeldingen aanpassen in Real-](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) Time video
