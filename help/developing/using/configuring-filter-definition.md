---
title: Filterdefinitie configureren
description: Ontdek de filterfunctie voor het beheer van grote gegevenssets.
page-status-flag: never-activated
uuid: c9db95fe-e9aa-40f8-9c0a-e74bb21ac14b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 993ab2bd-e05f-468e-9ef8-a603761247f8
context-tags: cusResource,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Filterdefinitie configureren{#configuring-filter-definition}

Op het **[!UICONTROL Filter definition]** tabblad kunt u geavanceerde filters maken waartoe gebruikers rechtstreeks toegang hebben wanneer ze complexe query&#39;s maken, zoals wanneer ze een publiek definiëren.

Deze stap is niet verplicht omdat u uw bron nog steeds kunt vullen en toegang hebt tot de gegevens via workflows, publiek en REST API.

![](assets/custom_resource_filter-definition.png)

Deze filters worden gebruikt in de vraagredacteur in de vorm van pre-gevormde regels. Met deze instructies kunt u het aantal stappen beperken dat nodig is om de gewenste configuratie op te halen. Dit kan bijzonder gunstig zijn voor herhaalde segmentaties.

U kunt bijvoorbeeld een filter maken waarmee u alle transacties kunt selecteren die groter zijn dan een bepaalde hoeveelheid in de laatste drie maanden.

Om dit te doen, moet u het **[!UICONTROL Profiles]** middel uitbreiden en een filter bepalen die aan een transactietabel (die u eerder hebt gecreeerd) met een regel verbinden erop wijst die dat de transactieprijs groter dan of gelijk aan een bepaalde parameter moet zijn en dat de transactiedatum binnen een waaier moet vallen die aan de laatste drie maanden beantwoordt.

1. Zorg ervoor dat u een transactietabel maakt en publiceert. Zie [De bron](../../developing/using/creating-or-extending-the-resource.md)maken of uitbreiden.

   >[!NOTE]
   >
   >Deze procedure gebruikt het voorbeeld van een lijst van de douanetransactie. Pas de kwestie aan uw bedrijfsbehoeften aan.

1. Alvorens een filter met betrekking tot de transactietabel in het **[!UICONTROL Profiles]** middel te bepalen, zorg ervoor u de verbinding aan deze lijst bepaalt en uw veranderingen publiceert. Zie Koppelingen [definiëren met andere bronnen](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources) en de databasestructuur [](../../developing/using/updating-the-database-structure.md)bijwerken.
1. Selecteer de transactietabel op het **[!UICONTROL Definition]** tabblad van het definitiescherm van het nieuwe filter.

   ![](assets/custom_resource_filter-definition_example-empty.png)

1. Sleep de transactietabel in het **[!UICONTROL Add a rule - Profiles/Transactions]** venster naar de werkruimte. Selecteer in het volgende venster dat wordt weergegeven het veld dat u wilt gebruiken.

   ![](assets/custom_resource_filter-definition_example-field.png)

1. Schakel het **[!UICONTROL Optional parameter settings]** selectievakje in in **[!UICONTROL Add a rule - Transactions]** het **[!UICONTROL Switch to parameters]** venster.

   Selecteer in het **[!UICONTROL Filter conditions]** dialoogvenster de **[!UICONTROL Greater than or equal to]** operator. Voer in het **[!UICONTROL Parameters]** veld een naam in en klik op het plusteken om de nieuwe parameter te maken.

   ![](assets/custom_resource_filter-definition_example-parameter.png)

1. Bevestig uw wijzigingen. Deze definitie komt overeen met een configureerbaar veld dat de gebruiker later moet invullen om de query uit te voeren.

   ![](assets/custom_resource_filter-definition_ex_edit-rule.png)

1. Combineer deze regel met een andere regel die specificeert dat de transactiedatum binnen een waaier moet vallen die aan de laatste drie maanden beantwoordt.

   ![](assets/custom_resource_filter-definition_example.png)

1. Kies de categorie waarin het filter wordt weergegeven.

   ![](assets/custom_resource_filter-definition_category.png)

1. Wijzig op het **[!UICONTROL Parameters]** tabblad van het scherm met filterdefinitie de beschrijving en het label om het onderwerp van het filter duidelijk aan te geven voor de gebruikers. Deze informatie zal in de vraagredacteur verschijnen.

   ![](assets/custom_resource_filter-definition_parameters.png)

   Als u veelvoudige configureerbare gebieden bepaalt, kunt u de orde wijzigen waarin zij in de interface verschijnen.

1. Sla uw wijzigingen op en publiceer de bronnen. Raadpleeg voor meer informatie de sectie [De databasestructuur](../../developing/using/updating-the-database-structure.md) bijwerken.

Zodra de **[!UICONTROL Profiles]** middeluitbreiding wordt gepubliceerd, zullen de gebruikers dit filter onder het kortere weglusje in de interface van de [vraagredacteur](../../automating/using/editing-queries.md) zien.

Hierdoor kan de gebruiker zijn publiek gemakkelijk definiëren wanneer hij of zij een e-mail maakt om te verzenden naar alle clients die de afgelopen drie maanden meer dan een bepaald bedrag hebben uitgegeven.

![](assets/custom_resource_filter-definition_email-audience.png)

In plaats van het zelf te configureren, moeten ze gewoon de gewenste hoeveelheid invoeren in het dialoogvenster dat wordt weergegeven.

![](assets/custom_resource_filter-definition_email-audience_filter.png)

