---
title: Een bron oproepen met een samengestelde identificatiesleutel
description: Leer hoe u een bron aanroept met een samengestelde id-toets
feature: Data Model
role: Developer
level: Experienced
exl-id: c7aca0c3-525d-4195-8c04-2fad32ca43b7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 7%

---

# Een bron oproepen met een samengestelde identificatiesleutel{#calling-a-resource-using-a-composite-identification-key}

In sommige gevallen moet u voor een resource mogelijk een identificatiesleutel definiëren die uit twee velden bestaat. Zodra de identificatiesleutel wordt gevormd, moet u een filterdefinitie vormen om het middel met deze identificatiesleutel, of van de interface van het Campaign Standard of APIs te kunnen roepen.

In dit geval wordt de **Profiel** resource is uitgebreid met aangepaste **&quot;CRM-ID&quot;** en **&quot;categorie&quot;** velden. We maken een identificatiesleutel voor de profielbron, die uit deze twee velden zal bestaan. Vervolgens configureren we een filterdefinitie, zodat we toegang hebben tot de profielbron met behulp van de identificatietoets.

De belangrijkste stappen voor dit gebruiksgeval zijn:

1. Vorm de identificatiesleutel voor het middel van het Profiel, dat op de twee gebieden wordt gebaseerd.
1. Vorm de filterdefinitie, om het middel van het Profiel te kunnen roepen gebruikend zijn identificatiecode.
1. Roep het middel van het Profiel van de interface of van APis aan.

Verwante onderwerpen:

* [De bron maken of uitbreiden](../../developing/using/creating-or-extending-the-resource.md)
* [Identificatiesleutels definiëren](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [Campaign Standard REST API&#39;s](../../api/using/get-started-apis.md)

## Stap 1: De identificatietoets configureren{#step-1-configure-the-identification-key}

>[!NOTE]
> Algemene concepten bij het configureren van identificatietoetsen worden gedetailleerd in [deze sectie](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

1. Voordat u de identificatiesleutel configureert, moet u controleren of de bron is uitgebreid met de gewenste velden en of deze is gepubliceerd. Raadpleeg [deze sectie](../../developing/using/creating-or-extending-the-resource.md) voor meer informatie.

1. Ga naar de **[!UICONTROL Administration]** / **[!UICONTROL Development]** / **[!UICONTROL Custom resources]** en open vervolgens het menu **[!UICONTROL Profile]** resource.

   ![](assets/uc_idkey1.png)

1. In de **[!UICONTROL Identification keys]** klikt u op de **[!UICONTROL Create element]** knop.

   ![](assets/uc_idkey2.png)

1. Voeg de twee aangepaste velden CRM-id en Categorie toe en klik vervolgens op **[!UICONTROL Confirm]**.

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > Als u de twee aangepaste velden in de interface van het profiel wilt weergeven, configureert u de **[!UICONTROL Screen definition]** tab. Raadpleeg [deze sectie](../../developing/using/configuring-the-screen-definition.md) voor meer informatie.

1. U kunt de filterdefinitie nu configureren om de bron aan te roepen met behulp van de id-sleutel.

## Stap 2: Vorm de filterdefinitie{#step-2-configure-the-filter-definition}

>[!NOTE]
> Algemene concepten bij het configureren van filterdefinities worden beschreven in [deze sectie](../../developing/using/configuring-filter-definition.md).

1. In de **[!UICONTROL Filter definition]** tabblad, klikt u op **[!UICONTROL Add an element]** Voer vervolgens het label en de id van de filterdefinitie in.

1. Bewerk de eigenschappen van de filterdefinitie om de regels ervan te configureren.

   ![](assets/uc_idkey4.png)

1. Sleep de tabel met de velden in de identificatietoets naar de werkruimte.

   ![](assets/uc_idkey5.png)

1. Selecteer het eerste veld dat wordt gebruikt in de identificatiecode (&quot;CRM-id&quot;) en activeer vervolgens het veld **[!UICONTROL Switch to parameters]** -optie.

   ![](assets/uc_idkey6.png)

1. In de **[!UICONTROL Filter conditions]** de **[!UICONTROL Equal]** , definieert u vervolgens de naam van de parameter en klikt u op het plusteken om deze te maken.

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > Nadat u op de knop **+** wordt de naam van de parameter automatisch gegenereerd. Let op deze informatie omdat u deze nodig hebt om het filter van de API&#39;s te gebruiken.

1. Herhaal bovenstaande stappen met alle velden waaruit de identificatiesleutel bestaat (&quot;categorie&quot;) en sla uw wijzigingen op.

   ![](assets/uc_idkey8.png)

1. De filterdefinitie is nu geconfigureerd. U kunt de bron publiceren zodat het filter beschikbaar is.

## Stap 3: Roep de bron op basis van de identificatiesleutel{#step-3-call-the-resource-based-on-its-identification-key}

Zodra de identificatiesleutel en zijn filterdefinitie worden gevormd, kunt u hen gebruiken om het middel, of van de standaardinterface van de Campagne of REST APIs te roepen.

Als u de filterdefinitie van de interface wilt gebruiken, gebruikt u een **[!UICONTROL Query]** activiteit in een werkstroom (zie [deze sectie](../../automating/using/query.md)). Het filter is vervolgens beschikbaar in het linkerdeelvenster.

![](assets/uc_idkey9.png)

Gebruik de onderstaande syntaxis om de filterdefinitie van Campaign Standard REST API&#39;s te gebruiken:

```
GET /profileAndServicesExt/<resourceName>/by<filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

>[!NOTE]
>Als u een aangepast filter wilt aanroepen, gebruikt u het voorvoegsel &quot;by&quot; gevolgd door de filternaam die is gedefinieerd tijdens het configureren van de filterdefinitie in [stap 2](../../developing/using/uc-calling-resource-id-key.md#step-2-configure-the-filter-definition).

In ons geval zou de syntaxis om een profiel op te halen uit de categorie &quot;spring&quot; met de CRM-id &quot;123456&quot; als volgt zijn:

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byidentification_key?category_parameter=spring&crm_id_parameter=123456
```

Raadpleeg voor meer informatie [Documentatie voor REST API&#39;s van Campaign Standard](../../api/using/filtering.md).
