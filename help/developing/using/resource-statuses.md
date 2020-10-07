---
title: Resourcestatussen
description: Ontdek de verschillende bronstatussen volgens hun publicatiestatus.
page-status-flag: never-activated
uuid: 215c0a2e-27ec-43f3-baac-1eaac7640784
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 85516477-1b95-4273-a0a7-d2cbb9950afd
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 1%

---


# Resourcestatussen{#resource-statuses}

Afhankelijk van hun publicatie- of activeringsstatus kunnen bronnen verschillende statussen hebben.

Er zijn twee kolommen gewijd aan het tonen van deze statussen in het **[!UICONTROL Custom resources]** scherm.

![](assets/schema_colonne_1.png)

**Publicatiestatus**

* **Concept**: de bron is zojuist gecreëerd of opnieuw opgesteld. Om de gegevensbestandlijsten evenals overeenkomstige APIs tot stand te brengen, moet het middel opnieuw worden gepubliceerd. Als een bron opnieuw wordt opgesteld, wordt deze automatisch na de publicatiestap inactief.
* **Opnieuw samenstellen** in behandeling: de bron is opnieuw opgesteld. Het proces voor het opnieuw ontwerpen vindt plaats tijdens de volgende publicatie. Herformulering is onomkeerbaar. Er worden verschillende waarschuwingsberichten weergegeven om de gebruiker op de hoogte te brengen, zowel bij het opnieuw opstellen als bij het voorbereiden van de publicatie.

   Zie [Een bron](../../developing/using/deleting-a-resource.md)verwijderen voor meer informatie over het opnieuw opmaken.

   >[!NOTE]
   >
   >De **[!UICONTROL Cancel re-draft]** optie is beschikbaar wanneer de bron die u opnieuw wilt ontwerpen nog steeds koppelingen bevat via andere bronnen met de status &quot;Gepubliceerd&quot;. Met deze optie kunt u het proces voor het opnieuw samenstellen van concepten herstellen. De aangepaste bronnen gaan dan terug naar hun oorspronkelijke status.

* **Gepubliceerd**: de bron is gepubliceerd. Als de bron na de laatste gewijzigde datum is gewijzigd, wordt een bericht weergegeven waarin u wordt uitgenodigd de bron opnieuw te publiceren om rekening te houden met de laatste wijzigingen.

Met dit **[!UICONTROL Do not publish latest modifications]** veld wordt voorkomen dat wijzigingen in toekomstige publicaties in aanmerking worden genomen.

Dit gebied kan in de definitie van het douanemiddel worden gevormd.
