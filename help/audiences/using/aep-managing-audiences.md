---
solution: Campaign Standard
product: campaign
title: Adobe Experience Platform-doelgroepen beheren
description: Leer hoe u Adobe Experience Platform beheert binnen Campaign Standard.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 3%

---


# Adobe Experience Platform-doelgroepen beheren {#about-audiences}

>[!IMPORTANT]
>
>De Dienst van de Doelen van het publiek is momenteel in bèta, die aan regelmatige updates zonder bericht kan worden onderworpen. Klanten moeten op Azure (momenteel alleen in bèta voor Noord-Amerika) worden gehost om toegang te krijgen tot deze mogelijkheden. Neem contact op met de klantenservice van Adobe als u toegang wilt.

## Toegang tot Adobe Experience Platform-publiek

Als u toegang wilt krijgen tot de Adobe Experience Platform-segmentbuilder, navigeert u naar de **[!UICONTROL Audiences]** kaart op de homepage van de Campaign Standard (of de **[!UICONTROL Audiences]** koppeling in de koptekst) en selecteert u de **[!UICONTROL Adobe Experience Platform]** omgeving.

![](assets/aep_audiences_access.png)

U wordt eerst omgeleid naar de pagina met Adobe Experience Platform-segmentlijsten, waar u reeds bestaande Adobe Experience Platform-segmenten kunt openen voor verdere bewerking.

Er zijn een zoekbalk en filter beschikbaar waarmee u het gewenste Adobe Experience Platform-segment kunt vinden.

![](assets/aep_audiences_list.png)

## Adobe Experience Platform-publiek maken

Voer de volgende stappen uit om een Adobe Experience Platform-publiek rechtstreeks in Campaign Standard te maken:

1. Klik op de pagina met segmentlijsten in Adobe Experience Platform op de **[!UICONTROL New audience]** knop in de rechterhoek.

   ![](assets/aep_audiences_creation_create.png)

1. De Segment Builder moet nu in uw werkruimte worden weergegeven. Hiermee kunt u een segment maken met gegevens uit Adobe Experience Platform die uiteindelijk worden gebruikt om uw publiek te maken.

1. Geef het segment een naam in het rechterdeelvenster en voer een beschrijving in (optioneel).

   ![](assets/aep_audiences_creation_edit_name.png)

1. Als u een segment wilt maken, moet u een **samenvoegbeleid** selecteren dat overeenkomt met uw marketingdoel voor dit segment.

   In de instellingenruit, wordt een Platform standaardsamenvoegbeleid geselecteerd. Voor meer informatie over fusiebeleid, verwijs naar de specifieke sectie van de de gebruikersgids [van de Bouwer van het](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html)Segment.

   ![](assets/aep_audiences_mergepolicy.png)

1. Bepaal de regels die de profielen zullen identificeren die in uw publiek moeten worden teruggewonnen.

   Om dit te doen, sleep de gewenste attributen en/of de gebeurtenissen van de linkerruit in de werkruimte, bepaal de overeenkomstige regels dan klik de **[!UICONTROL Create segment]** knoop om het segment (zie het [Gebruiken van de Bouwer](../../audiences/using/aep-using-segment-builder.md)van het Segment) te bewaren.

   ![](assets/aep_audiences_creation_query.png)

Het publiek is nu klaar om te worden geactiveerd en u kunt het gebruiken als doel voor uw campagnes (zie [gericht op het publiek](../../automating/using/aep-targeting-audiences.md)van Adobe Experience Platform).

## Doelgroepen bewerken

Om een publiek uit te geven, open het en wijzig de regels zoals nodig binnen de interface van de Bouwer van het Segment (zie het [Gebruiken van de Bouwer](../../audiences/using/aep-using-segment-builder.md)van het Segment).

Nadat de wijzigingen zijn voltooid, klikt u op de **[!UICONTROL Save segment]** knop om het publiek bij te werken.

![](assets/aep_audiences_editing.png)
