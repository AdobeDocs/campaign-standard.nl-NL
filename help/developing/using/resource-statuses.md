---
title: Bronstatussen
description: Ontdek de verschillende bronstatussen volgens hun publicatiestatus.
page-status-flag: never-activated
uuid: 215c0a2e-27ec-43f3-baac-1eaac7640784
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 85516477-1b95-4273-a0a7-d2cbb9950afd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Bronstatussen{#resource-statuses}

Bronnen kunnen verschillende statussen hebben afhankelijk van hun publicatie- of activeringsstatus.

Er zijn twee kolommen gewijd aan het tonen van deze statussen in het **[!UICONTROL Custom resources]** scherm.

![](assets/schema_colonne_1.png)

**Publicatiestatus**

* **Concept**: de bron is zojuist gecreëerd of opnieuw opgesteld. Om de gegevensbestandlijsten evenals overeenkomstige APIs tot stand te brengen moet het middel opnieuw worden gepubliceerd. Als een bron opnieuw wordt geschreven, wordt deze na de publicatiestap automatisch inactief gemaakt.
* **Opnieuw samenstellen** in behandeling: de bron is opnieuw opgesteld. Het proces voor het opnieuw ontwerpen vindt plaats tijdens de volgende publicatie. Herformulering is onomkeerbaar. In verschillende waarschuwingsberichten wordt de gebruiker gewaarschuwd voor dit feit, zowel bij het opnieuw opstellen als bij het voorbereiden van publicatie.

   Zie [Een bron](../../developing/using/deleting-a-resource.md)verwijderen voor meer informatie over het opnieuw opmaken.

   >[!NOTE]
   >
   >De **[!UICONTROL Cancel re-draft]** optie is beschikbaar wanneer de bron die u opnieuw wilt ontwerpen nog steeds koppelingen bevat via andere bronnen met de status &quot;Gepubliceerd&quot;. Met deze optie kunt u het proces voor het opnieuw samenstellen van concepten herstellen. De aangepaste bronnen gaan dan terug naar hun oorspronkelijke status.

* **Gepubliceerd**: de bron is gepubliceerd. Als de bron na de laatste gewijzigde datum wordt gewijzigd, verschijnt er een bericht waarin de gebruiker wordt gevraagd deze opnieuw te publiceren om rekening te houden met de laatste wijzigingen.

Met dit **[!UICONTROL Do not publish latest modifications]** veld wordt voorkomen dat wijzigingen in toekomstige publicaties in aanmerking worden genomen.

Dit gebied kan in de definitie van het douanemiddel worden gevormd.
