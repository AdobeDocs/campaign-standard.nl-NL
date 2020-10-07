---
title: Onbewerkte tekst, HTML- en mobiele e-mailindelingen bewerken
description: De modi Onbewerkte tekst en HTML detecteren
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 0%

---


# Onbewerkte tekst, HTML- en mobiele e-mailindelingen bewerken {#plain-text-and-html-modes}

Met de e-mailontwerper kunt u verschillende rendering van uw e-mails bewerken. U kunt een tekstversie van uw e-mail genereren, de HTML-bron van een e-mail bewerken en e-mails ontwerpen voor de mobiele weergave.

## Een tekstversie van de e-mail genereren {#generating-a-text-version-of-the-email}

Standaard wordt de **[!UICONTROL Plain text]** versie van uw e-mailbericht automatisch gegenereerd en gesynchroniseerd met de **[!UICONTROL Edit]** versie.

De gebieden van de aanpassing en inhoudsblokken die aan de versie van HTML worden toegevoegd worden ook gesynchroniseerd met de gewone tekstversie.

>[!NOTE]
>
>Als u inhoudsblokken in de versie zonder opmaak wilt gebruiken, moet u ervoor zorgen dat ze geen HTML-code bevatten.

Als u een andere versie voor normale tekst wilt gebruiken dan de HTML-versie, kunt u deze synchronisatie uitschakelen door op de **[!UICONTROL Sync with HTML]** switch in de **[!UICONTROL Plain text]** weergave van de e-mail te klikken.

![](assets/email_designer_textversion.png)

Vervolgens kunt u de versie zonder tekst naar wens bewerken.

>[!NOTE]
>
>Als u de **[!UICONTROL Plain text]** versie bewerkt terwijl synchronisatie is uitgeschakeld, worden de wijzigingen die u in de versie zonder opmaak hebt aangebracht, vervangen door de HTML-versie wanneer u de **[!UICONTROL Sync with HTML]** optie weer inschakelt. De in **[!UICONTROL Plain text]** weergave aangebrachte wijzigingen kunnen niet in de **[!UICONTROL HTML]** weergave worden weergegeven.

## Een e-mailinhoudsbron bewerken in HTML {#editing-an-email-content-source-in-html}

Voor de meest geavanceerde gebruikers en foutopsporing kunt u de e-mailinhoud rechtstreeks in HTML weergeven en bewerken.

U kunt de HTML-versie van de e-mail op twee manieren bewerken:

* Selecteer **[!UICONTROL Edit]** > **[!UICONTROL HTML]** om de HTML-versie van het volledige e-mailbericht te openen.

   ![](assets/email_designer_html1.png)

* Selecteer een element in de WYSIWYG-interface en klik op het **[!UICONTROL Source code]** pictogram.

   Alleen de bron van het geselecteerde element wordt weergegeven. U kunt de broncode bewerken als het geselecteerde element een **[!UICONTROL HTML]** inhoudscomponent is. Andere componenten bevinden zich in de modus Alleen-lezen, maar kunnen nog steeds worden bewerkt in de volledige HTML-versie van de e-mail.

   ![](assets/email_designer_html2.png)

Als u de HTML-code wijzigt, kan de reactiesnelheid van de e-mail worden verbroken. Controleer dit met de **[!UICONTROL Preview]** knop. Zie [Berichten voorvertonen](../../sending/using/previewing-messages.md).

## E-mails ontwerpen voor mobiele rendering {#switching-to-mobile-view}

U kunt het responsieve ontwerp van een e-mail perfectioneren door alle stijlopties voor mobiele weergave afzonderlijk te bewerken. U kunt bijvoorbeeld marges en opvulling aanpassen, kleinere of grotere lettergrootten gebruiken, knoppen wijzigen of andere achtergrondkleuren toepassen die specifiek zijn voor de mobiele versie van uw e-mail.

Alle stijlopties zijn beschikbaar in de mobiele weergave. De e-mailDesigner-stijlinstellingen worden eerder op deze pagina weergegeven.

1. Maak een e-mail en begin met het bewerken van de inhoud. Zie Een geheel nieuwe e-mailinhoud [ontwerpen voor meer informatie](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Selecteer de **[!UICONTROL Switch to mobile view]** knop voor toegang tot de toegewezen mobiele weergave.

   ![](assets/email_designer_mobile_view_switch.png)

   De mobiele versie van het e-mailbericht wordt weergegeven. Het bevat alle componenten en stijlen die in Desktopmening werden bepaald.

1. Alle stijlinstellingen zoals achtergrondkleur, uitlijning, opvulling, marge, lettertypefamilie, tekstkleur enzovoort onafhankelijk bewerken.

   ![](assets/email_designer_mobile_view.png)

1. Wanneer u een stijlinstelling bewerkt in de mobiele weergave, worden de wijzigingen alleen toegepast op de mobiele weergave.

   Verklein bijvoorbeeld de grootte van een afbeelding, voeg een groene achtergrond toe en wijzig de opvulling in de mobiele weergave.

   ![](assets/email_designer_mobile_view_change.png)

1. U kunt een component verbergen wanneer deze op een mobiel apparaat wordt weergegeven. U doet dit door een keuze te maken **[!UICONTROL Show only on desktop devices]** in het **[!UICONTROL Display options]** menu.

   U kunt deze component ook verbergen op bureaubladapparaten, wat betekent dat deze alleen op mobiele apparaten wordt weergegeven. Selecteer **[!UICONTROL Show only on mobile devices]** deze optie.

   Met deze optie kunt u bijvoorbeeld een specifieke afbeelding op mobiele apparaten en een andere afbeelding op desktopapparaten weergeven.

   U kunt deze optie instellen in de weergave Mobiel of Desktop.

   ![](assets/email_designer_mobile_hide.png)

1. Klik nogmaals op de **[!UICONTROL Switch to mobile view]** knop om terug te gaan naar de standaardweergave op het bureaublad. De wijzigingen die u zojuist hebt aangebracht in de stijl worden niet doorgevoerd.

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >De enige uitzondering zijn de **[!UICONTROL Style inline]** instellingen. Elke wijziging in de inline-instelling van de stijl wordt ook toegepast op de standaardweergave op het bureaublad.

1. Eventuele andere wijzigingen in de structuur of de inhoud van de e-mail, zoals tekstbewerkingen, het uploaden van een nieuwe afbeelding, het toevoegen van een nieuwe component, enz. wordt ook toegepast op de standaardweergave.

   Ga bijvoorbeeld terug naar de mobiele weergave, bewerk wat tekst en vervang een afbeelding.

   ![](assets/email_designer_mobile_view_change_content.png)

1. Klik nogmaals op de **[!UICONTROL Switch to mobile view]** knop om terug te gaan naar de standaardweergave op het bureaublad. De wijzigingen worden weerspiegeld.

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. Als u een stijl verwijdert in de mobiele weergave, keert u terug naar de stijl die is toegepast in de bureaubladmodus.

   Pas in de mobiele weergave bijvoorbeeld een groene achtergrondkleur toe op een knop.

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. Schakel over naar de bureaubladweergave en pas een grijze achtergrond toe op dezelfde knop.

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. Schakel opnieuw over naar de mobiele weergave en schakel de **[!UICONTROL Background color]** instelling uit.

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   De achtergrondkleur die is gedefinieerd in de bureaubladweergave wordt nu toegepast: wordt grijs (niet leeg).

   De enige uitzondering is de **[!UICONTROL Border color]** instelling. Wanneer deze optie is uitgeschakeld in de mobiele weergave, wordt er geen rand meer toegepast, zelfs niet wanneer een randkleur is gedefinieerd in de desktopweergave.

>[!NOTE]
>
>De mobiele weergave is niet beschikbaar in [fragmenten](../../designing/using/using-reusable-content.md#about-fragments).
