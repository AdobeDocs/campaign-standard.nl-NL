---
title: Dynamische content Target toevoegen
description: Leer hoe u dynamische Adobe Target-inhoud toevoegt aan een van uw Adobe Campaign-leveringen.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 7dfbd89f-877e-4598-bfe3-d743bb31ae9e
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 2%

---

# Dynamische content Target toevoegen{#adding-target-dynamic-content}

Dankzij de Adobe Target-integratie kunnen dynamische afbeeldingen aan een levering worden toegevoegd om uw inhoud aan uw wensen aan te passen.

Tijdens het bewerken van een e-mailbericht kunt u een dynamische afbeelding uit Adobe Target invoegen die afhankelijk is van de ontvanger.

Voordat u de afbeelding opent in Adobe Campaign, moet u eerst de volgende taken uitvoeren in Adobe Target:

* Creeer één of verscheidene [&#x200B; opnieuw richten aanbiedingen &#x200B;](https://experienceleague.adobe.com/docs/target/using/experiences/offers/offer-redirect.html), waarin u URL van het beeld moet specificeren u zult gebruiken.
* Creeer één of verscheidene [&#x200B; publiek &#x200B;](https://experienceleague.adobe.com/docs/target/using/audiences/create-audiences/audiences.html), om het doel van uw activiteit te bepalen.
* Creeer a [&#x200B; op vorm-gebaseerde ervaring composer &#x200B;](https://experienceleague.adobe.com/docs/target/using/experiences/form-experience-composer.html) activiteit, waarin u een radibox moet selecteren en verscheidene ervaringen, afhankelijk van het aantal gerealiseerde aanbiedingen specificeren. Voor elke ervaring moet je een van de nieuwe aanbiedingen selecteren.
* Maak segmenten met behulp van informatie uit Adobe Campaign om ervaringen op te geven. Als u gegevens van Adobe Campaign wilt gebruiken in de selectieregels van de aanbieding, moet u de gegevens opgeven in het tekstvak in Adobe Target.

1. Maak een e-maillevering.
1. Wanneer u de inhoud van een e-mail- of landingspagina bewerkt, gaat u naar een afbeeldingsblok en selecteert u **[!UICONTROL Dynamic image from Adobe Target]** via het contextmenu.

   ![](assets/tar_insert_dynamic_image.png)

1. Selecteer de afbeelding die standaard in de e-mail wordt weergegeven. U kunt direct het beeld URL specificeren of een beeld selecteren dat via [&#x200B; Assets &#x200B;](../../integrating/using/working-with-campaign-and-assets-core-service.md) wordt gedeeld.

   De integratie ondersteunt alleen statische afbeeldingen. De rest van de inhoud kan niet worden aangepast.

1. Voer de naam in van het tekstvak dat in Adobe Target is opgegeven.
1. Als u Enterprise-machtigingen gebruikt in uw instellingen in Adobe Target, voegt u de bijbehorende eigenschap toe in dit veld. Leer meer over de toestemmingen van de Onderneming van het Doel in [&#x200B; deze pagina &#x200B;](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html). Dit veld is optioneel en niet vereist als u de Enterprise-machtigingen in Target niet gebruikt.
1. Geef in **[!UICONTROL Additional decision parameters]** de toewijzing op tussen de velden die zijn gedefinieerd in de Adobe Target-segmenten en de Adobe Campaign-velden.

   De Adobe Campaign-velden die worden gebruikt, moeten zijn opgegeven in de keuzelijst. In dit voorbeeld definieert u verschillende ervaringen afhankelijk van het geslacht van de ontvanger.

   ![](assets/tar_additional_decisionning_parameters.png)

1. Bekijk een voorbeeld van uw e-mail om te zien of de ingevoegde afbeelding bij het selecteren van verschillende profielen verandert afhankelijk van de parameters die zijn opgegeven in de Adobe Target-activiteit en in Adobe Campaign.

De levering met de dynamische afbeelding kan nu worden verzonden. De resultaten zijn te vinden in Adobe Target.

**Verwante onderwerpen:**

* [&#x200B; Adobe Target Portal &#x200B;](https://experienceleague.adobe.com/docs/target/using/integrate/campaign-and-target.html)
* [Over het ontwerpen van e-mailinhoud](../../designing/using/designing-content-in-adobe-campaign.md)
* [&#x200B; Personaliseer E-mailBeelden in Echt - tijd &#x200B;](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) video
