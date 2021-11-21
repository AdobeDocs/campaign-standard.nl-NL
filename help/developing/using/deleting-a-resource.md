---
title: Een bron verwijderen
description: 'Leer hoe u een bron verwijdert '
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
feature: Data Model
role: Developer
level: Experienced
exl-id: 4ddfdbcc-a154-4c10-a97e-73ad888d1f1f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 14%

---

# Een bron verwijderen{#deleting-a-resource}

Als u een bron wilt verwijderen, moet de bron in kwestie een **[!UICONTROL Draft]**. De bron bevindt zich in **[!UICONTROL Draft]** status indien:

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
   >Als u een extensie van de box-out opnieuw ontwerpt **Profielen (profiel)** bron, moet u ook elk **Testprofiel (seedMember)** extensie die u hebt gedefinieerd. Zie voor meer informatie over het uitbreiden van de profielbron [deze sectie](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. Publiceer de bron. Voor meer gedetailleerde stappen raadpleegt u [Een aangepaste bron publiceren](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   De bron gaat vervolgens in **Concept** modus en de activeringsstatus is **[!UICONTROL Inactive]**.

1. In **[!UICONTROL List]** modus, controleer de te verwijderen bron en klik op de knop ![](assets/delete_darkgrey-24px.png) **[!UICONTROL Delete element]** pictogram.

   ![](assets/schema_extension_uc28.png)

Uw bron wordt verwijderd uit het gegevensmodel.

>[!NOTE]
>
>Als een veld van een aangepaste bron die wordt gebruikt voor een gebeurtenis, wordt aangepast of verwijderd, wordt de publicatie van de overeenkomstige gebeurtenis automatisch ongedaan gemaakt. Zie [Publicatie van een transactiegebeurtenis opheffen](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).
