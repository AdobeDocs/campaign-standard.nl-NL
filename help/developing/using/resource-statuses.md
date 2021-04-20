---
solution: Campaign Standard
product: campaign
title: Resourcestatussen
description: Ontdek de verschillende bronstatussen volgens hun publicatiestatus.
audience: developing
content-type: reference
topic-tags: about-custom-resources
feature: Data Model
role: Developer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 1%

---


# Resourcestatussen{#resource-statuses}

Afhankelijk van hun publicatie- of activeringsstatus kunnen bronnen verschillende statussen hebben.

Er zijn twee kolommen gewijd aan het tonen van deze statussen in het **[!UICONTROL Custom resources]** scherm.

![](assets/schema_colonne_1.png)

**Publicatiestatus**

* **Concept**: de bron is zojuist gecreëerd of opnieuw opgesteld. Om de gegevensbestandlijsten evenals overeenkomstige APIs tot stand te brengen, moet het middel opnieuw worden gepubliceerd. Als een bron opnieuw wordt opgesteld, wordt deze automatisch na de publicatiestap inactief.
* **Opnieuw samenstellen** in behandeling: de bron is opnieuw opgesteld. Het proces voor het opnieuw ontwerpen vindt plaats tijdens de volgende publicatie. Herformulering is onomkeerbaar. Er worden verschillende waarschuwingsberichten weergegeven om de gebruiker op de hoogte te brengen, zowel bij het opnieuw opstellen als bij het voorbereiden van de publicatie.

   Zie [Een resource verwijderen](../../developing/using/deleting-a-resource.md) voor meer informatie over het opnieuw opstellen.

   >[!NOTE]
   >
   >De optie **[!UICONTROL Cancel re-draft]** is beschikbaar wanneer de bron die u opnieuw wilt samenstellen nog steeds koppelingen bevat via andere bronnen met de status &quot;Gepubliceerd&quot;. Met deze optie kunt u het proces voor het opnieuw samenstellen van concepten herstellen. De aangepaste bronnen gaan dan terug naar hun oorspronkelijke status.

* **Gepubliceerd**: de bron is gepubliceerd. Als de bron na de laatste gewijzigde datum is gewijzigd, wordt een bericht weergegeven waarin u wordt uitgenodigd de bron opnieuw te publiceren om rekening te houden met de laatste wijzigingen.

Met het veld **[!UICONTROL Do not publish latest modifications]** wordt voorkomen dat wijzigingen in toekomstige publicaties in aanmerking worden genomen.

Dit gebied kan in de definitie van het douanemiddel worden gevormd.
