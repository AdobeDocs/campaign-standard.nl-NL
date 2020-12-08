---
solution: Campaign Standard
product: campaign
title: Een resource verwijderen
description: 'Leer hoe u een bron verwijdert '
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
translation-type: tm+mt
source-git-commit: a51943e4da04f5d19aaecdfcf956f5c4f3d804c8
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 14%

---


# Een resource verwijderen{#deleting-a-resource}

Als u een bron wilt verwijderen, moet de bron in kwestie een **[!UICONTROL Draft]** zijn. De resource heeft de status **[!UICONTROL Draft]** als:

* Het is zojuist opgericht en is nog niet gepubliceerd.
* Als het al is gepubliceerd, moet de bron opnieuw worden opgesteld.

>[!IMPORTANT]
>
>Het herschrijven en schrappen van een douanemiddel zijn gevoelige verrichtingen die andere middelen kunnen beïnvloeden. Deze handelingen mogen alleen door een deskundige gebruiker worden uitgevoerd.

Een gepubliceerde bron opnieuw samenstellen en verwijderen:

1. Selecteer de bron die u opnieuw wilt samenstellen.
1. Klik op de knop **[!UICONTROL Re-draft]** op de actiebalk.

   ![](assets/schema_extension_uc26.png)

1. Klik op **[!UICONTROL Ok]**.

   >[!IMPORTANT]
   >
   >Deze actie is definitief: de de gegevensbestandlijst of kolommen van het middel en hun gegevens zullen permanent worden geschrapt wanneer de wijziging wordt gepubliceerd, die in gebroken verbindingen van andere douanemiddelen kan resulteren. Alleen de brondefinitie blijft beschikbaar.

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >Als u een uitbreiding van de uit-van-de-doos **Profielen (profiel)** middelen opnieuw ontwerpt, moet u om het even welke **uitbreiding van de Test (seedMember)** ook opnieuw ontwerpen u zou kunnen bepaald hebben. Zie [deze sectie](../../developing/using/extending-the-profile-resource-with-a-new-field.md) voor meer informatie over het uitbreiden van de profielbron.

1. Publiceer de bron. Voor meer gedetailleerde stappen, verwijs naar [het Publiceren van een douanemiddel](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   De bron gaat dan naar de modus **Concept** en de activeringsstatus is **[!UICONTROL Inactive]**.

1. Controleer in de modus **[!UICONTROL List]** de te verwijderen bron en klik op het pictogram ![](assets/delete_darkgrey-24px.png) **[!UICONTROL Delete element]**.

   ![](assets/schema_extension_uc28.png)

Uw bron wordt verwijderd uit het gegevensmodel.

>[!NOTE]
>
>Als een veld van een aangepaste bron die wordt gebruikt voor een gebeurtenis, wordt aangepast of verwijderd, wordt de publicatie van de overeenkomstige gebeurtenis automatisch ongedaan gemaakt. Zie [Publicatie van een transactiegebeurtenis opheffen](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).
