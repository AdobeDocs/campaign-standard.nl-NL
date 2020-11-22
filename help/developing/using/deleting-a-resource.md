---
solution: Campaign Standard
product: campaign
title: Een resource verwijderen
description: 'Leer hoe u een bron verwijdert '
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 14%

---


# Een resource verwijderen{#deleting-a-resource}

Als u een bron wilt verwijderen, moet de bron in kwestie een **[!UICONTROL Draft]**. De resource is in **[!UICONTROL Draft]** status als:

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
   >Als u een uitbreiding van de uit-van-de-doos bron van **Profielen (profiel)** opnieuw ontwerpt, moet u om het even welke uitbreiding van het **Testprofiel (zaadLid)** ook opnieuw ontwerpen u kunt bepaald hebben. Zie [deze sectie](../../developing/using/extending-the-profile-resource-with-a-new-field.md)voor meer informatie over het uitbreiden van de profielbron.

1. Publiceer de bron. Voor meer gedetailleerde stappen, verwijs naar het [Publiceren van een douanemiddel](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   De bron gaat vervolgens naar de **conceptmodus** en de activeringsstatus is **[!UICONTROL Inactive]**.

1. Controleer in de **[!UICONTROL List]** modus de te verwijderen bron en klik op het ![](assets/delete_darkgrey-24px.png)**[!UICONTROL Delete element]** pictogram.

   ![](assets/schema_extension_uc28.png)

Uw bron wordt verwijderd uit het gegevensmodel.

>[!NOTE]
>
>Als een veld van een aangepaste bron die wordt gebruikt voor een gebeurtenis, wordt aangepast of verwijderd, wordt de publicatie van de overeenkomstige gebeurtenis automatisch ongedaan gemaakt. See [Configuring transactional messaging](../../administration/using/configuring-transactional-messaging.md).

