---
title: Dynamische doelinhoud toevoegen
description: Leer hoe u dynamische inhoud van Adobe Target toevoegt aan een van uw Adobe-campagneleveringen.
page-status-flag: never-activated
uuid: b3cc045f-7924-480e-8c61-8246510f3adb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
discoiquuid: 45ddf7b7-98f7-4fdd-bb4a-49ec8490e877
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 594b2d3c3dcc1ec13ab06ca6219ad59fe1a267d8

---


# Dynamische doelinhoud toevoegen{#adding-target-dynamic-content}

Dankzij de integratie met Adobe Target kunnen dynamische afbeeldingen aan een levering worden toegevoegd om uw inhoud aan uw wensen aan te passen.

Tijdens het bewerken van een e-mailbericht kunt u een dynamische afbeelding invoegen vanuit Adobe Target. Deze wordt aangepast aan de ontvangers.

Voordat u de afbeelding kunt openen in Adobe Campaign, moet u de volgende taken uitvoeren in Adobe Target:

* Maak een of meer [omleidingsaanbiedingen](https://docs.adobe.com/content/help/en/target/using/experiences/offers/offer-redirect.html), waarin u de URL moet opgeven van de afbeelding die u wilt gebruiken.
* Maak een of meer [soorten publiek](https://docs.adobe.com/content/help/en/target/using/audiences/create-audiences/audiences.html)om het doel van uw activiteit te definiëren.
* Maak een [op formulieren gebaseerde ervaringscomposer](https://docs.adobe.com/content/help/en/target/using/experiences/form-experience-composer.html) -activiteit, waarin u een keuzelijst moet selecteren en verschillende ervaringen moet opgeven, afhankelijk van het aantal nieuwe aanbiedingen. Voor elke ervaring moet je een van de nieuwe aanbiedingen selecteren.
* Maak segmenten met behulp van informatie uit Adobe Campaign om ervaringen op te geven. Als u gegevens uit Adobe Campaign wilt gebruiken in de selectieregels van de aanbieding, moet u de gegevens opgeven in het keuzemenu van Adobe Target.

1. Maak een e-maillevering.
1. Wanneer u de inhoud van een e-mail- of landingspagina bewerkt, gaat u naar een afbeeldingsblok en selecteert u deze vervolgens **[!UICONTROL Dynamic image from Adobe Target]** via het contextmenu.

   ![](assets/tar_insert_dynamic_image.png)

1. Selecteer de afbeelding die standaard in de e-mail wordt weergegeven. U kunt de afbeeldings-URL rechtstreeks opgeven of een afbeelding selecteren die via [Middelen](../../integrating/using/working-with-campaign-and-assets-core-service.md)wordt gedeeld.

   De integratie ondersteunt alleen statische afbeeldingen. De rest van de inhoud kan niet worden aangepast.

1. Voer de naam in van het tekstvak dat is opgegeven in Adobe Target.
1. Als u Enterprise-machtigingen gebruikt in uw instellingen in Adobe Target, voegt u de bijbehorende eigenschap in dit veld toe. Meer informatie over de rechten van Target Enterprise vindt u op [deze pagina](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html). Dit veld is optioneel en niet vereist als u de Enterprise-machtigingen in Target niet gebruikt.
1. Geef in **[!UICONTROL Additional decision parameters]** dit deelvenster de toewijzing op tussen de velden die zijn gedefinieerd in de Adobe Target-segmenten en de Adobe Campagne-velden.

   De Adobe-campagnevelden moeten zijn opgegeven in de keuzelijst. Hier zullen we verschillende ervaringen definiëren afhankelijk van het geslacht van de ontvanger.

   ![](assets/tar_additional_decisionning_parameters.png)

1. Geef een voorbeeld van uw e-mail weer om te zien of de ingevoegde afbeelding bij het selecteren van verschillende profielen verandert, afhankelijk van de parameters die zijn opgegeven in de activiteit Adobe Target en in de Adobe-campagne.

De levering met de dynamische afbeelding kan nu worden verzonden. De resultaten van dit programma vindt u in Adobe Target.

**Verwante onderwerpen:**

* [Adobe Target Portal](https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html)
* [Over het ontwerpen van e-mailinhoud](../../designing/using/designing-content-in-adobe-campaign.md)
* [E-mailafbeeldingen aanpassen in realtime](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) video

