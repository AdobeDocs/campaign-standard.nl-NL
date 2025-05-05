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
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 2%

---

# Dynamische content Target toevoegen{#adding-target-dynamic-content}

Dankzij de Adobe Target-integratie kunnen dynamische afbeeldingen aan een levering worden toegevoegd om uw inhoud aan uw wensen aan te passen.

Tijdens het bewerken van een e-mailbericht kunt u een dynamische afbeelding uit Adobe Target invoegen die afhankelijk is van de ontvanger.

Voordat u de afbeelding opent in Adobe Campaign, moet u eerst de volgende taken uitvoeren in Adobe Target:

* Een of meerdere maken [omleiding van aanbiedingen](https://experienceleague.adobe.com/docs/target/using/experiences/offers/offer-redirect.html?lang=nl-NL), waarin u de URL moet opgeven van de afbeelding die u wilt gebruiken.
* Een of meerdere maken [publiek](https://experienceleague.adobe.com/docs/target/using/audiences/create-audiences/audiences.html?lang=nl-NL), om het doel van uw activiteit te definiëren.
* Een [Formuliergebaseerde ervaringscomposer](https://experienceleague.adobe.com/docs/target/using/experiences/form-experience-composer.html?lang=nl-NL) activiteit, waarin u een radibox moet selecteren en verscheidene ervaringen, afhankelijk van het aantal nieuwe aanbiedingen specificeren. Voor elke ervaring moet je een van de nieuwe aanbiedingen selecteren.
* Maak segmenten met behulp van informatie uit Adobe Campaign om ervaringen op te geven. Als u gegevens van Adobe Campaign wilt gebruiken in de selectieregels van de aanbieding, moet u de gegevens opgeven in het tekstvak in Adobe Target.

1. Maak een e-maillevering.
1. Ga bij het bewerken van de inhoud van een e-mail- of landingspagina naar een afbeeldingsblok en selecteer **[!UICONTROL Dynamic image from Adobe Target]** via het contextmenu.

   ![](assets/tar_insert_dynamic_image.png)

1. Selecteer de afbeelding die standaard in de e-mail wordt weergegeven. U kunt de afbeeldings-URL rechtstreeks opgeven of een afbeelding selecteren die via [Activa](../../integrating/using/working-with-campaign-and-assets-core-service.md).

   De integratie ondersteunt alleen statische afbeeldingen. De rest van de inhoud kan niet worden aangepast.

1. Voer de naam in van het tekstvak dat in Adobe Target is opgegeven.
1. Als u Enterprise-machtigingen gebruikt in uw instellingen in Adobe Target, voegt u de bijbehorende eigenschap toe in dit veld. Meer informatie over Target Enterprise-machtigingen vindt u in [deze pagina](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html?lang=nl-NL). Dit veld is optioneel en niet vereist als u de Enterprise-machtigingen in Target niet gebruikt.
1. In **[!UICONTROL Additional decision parameters]** geeft u de toewijzing op tussen de velden die zijn gedefinieerd in de Adobe Target-segmenten en de Adobe Campaign-velden.

   De Adobe Campaign-velden die worden gebruikt, moeten zijn opgegeven in de keuzelijst. In dit voorbeeld definieert u verschillende ervaringen afhankelijk van het geslacht van de ontvanger.

   ![](assets/tar_additional_decisionning_parameters.png)

1. Bekijk een voorbeeld van uw e-mail om te zien of de ingevoegde afbeelding bij het selecteren van verschillende profielen verandert afhankelijk van de parameters die zijn opgegeven in de Adobe Target-activiteit en in Adobe Campaign.

De levering met de dynamische afbeelding kan nu worden verzonden. De resultaten zijn te vinden in Adobe Target.

**Verwante onderwerpen:**

* [Adobe Target Portal](https://experienceleague.adobe.com/docs/target/using/integrate/campaign-and-target.html?lang=nl-NL)
* [Over het ontwerpen van e-mailinhoud](../../designing/using/designing-content-in-adobe-campaign.md)
* [E-mailafbeeldingen in realtime aanpassen](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) video
