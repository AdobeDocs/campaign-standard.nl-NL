---
title: Gegevens importeren met importsjablonen
description: Leer hoe u gegevens kunt verzamelen om uw Campagne-database te voeden.
page-status-flag: never-activated
uuid: bfc03235-2032-448a-a9ed-21ff2a83fa09
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: fb511bb8-6be7-43f6-86ab-94d5cfa3efc9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Gegevens importeren met importsjablonen{#importing-data-with-import-templates}

Door gegevens te importeren, kunt u gegevens verzamelen om de database van uw campagne te voeden.

Als alternatief voor [Workflows](../../automating/using/get-started-workflows.md)biedt Adobe Campaign een vereenvoudigde importfunctie waarmee de gebruiker bepaalde typen importbewerkingen kan beheren die door een beheerder zijn gedefinieerd.

Het operationele beginsel is als volgt: een **beheerder** definieert en beheert importsjablonen (zie [Importsjablonen](../../automating/using/defining-import-templates.md)definiëren). Deze importsjablonen worden vervolgens beschikbaar gesteld aan gebruikers met vereenvoudigde weergaven onder het menu **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Imports]** .

Deze gebruikers moeten daarom alleen het type import selecteren dat ze willen uitvoeren en het bestand met de te importeren gegevens uploaden. De workflow die door de beheerder is gedefinieerd, wordt transparant uitgevoerd voor de gebruiker, die toegang heeft tot de details van het resultaat van de import nadat deze is voltooid.

>[!NOTE]
>
>De functie voor data-import kan worden beheerd door gebruikers met de rollen **[!UICONTROL GENERIC IMPORT (import)]** en **[!UICONTROL WORKFLOW (workflow)]**. Raadpleeg [deze sectie](../../administration/using/list-of-roles.md) voor meer informatie over rollen.

Invoer kan worden gefilterd op basis van de sjabloon vanwaar deze werd uitgevoerd, de uitvoeringsdatum en de uitvoeringsstatus.

1. Klik in het overzicht van de importbewerking op de **[!UICONTROL Create]** knop. De wizard wordt geopend.
1. Selecteer het type import dat u wilt uitvoeren. De importtypen komen overeen met de beschikbare importsjablonen.
1. Download indien nodig het voorbeeldbestand dat aan de sjabloon is gekoppeld naar de computer om de gegevenstypen weer te geven die in het te importeren bestand worden verwacht.
1. Download het bestand met de gegevens die u wilt importeren in de wizard.
1. Start het importeren. De tovenaar sluit en neemt u terug naar de lijst van de invoer die met het gebruikte malplaatje wordt uitgevoerd.
1. Vernieuw de pagina en selecteer de importbewerking die u zojuist hebt uitgevoerd om de details van de uitvoering weer te geven.

   ![](assets/simplified_import1.png)

De details van het uitvoeren van de import zijn nu beschikbaar. Zowel het bestand dat is geïmporteerd als het bestand met de geweigerde gegevens (gegevens die niet zijn geïmporteerd) kunnen naar de computer worden gedownload.
