---
title: Adobe Experience Platforms publiek beheren
description: Leer hoe u Adobe Experience Platform beheert in Campaign Standard.
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d487600fc4f3004804e93347b83edfe4e01cceeb
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---


# Adobe Experience Platforms publiek beheren {#about-audiences}

>[!IMPORTANT]
>
>De Dienst van de Doelen van het publiek is momenteel in bèta, die aan regelmatige updates zonder bericht kan worden onderworpen. Klanten moeten op Azure (momenteel alleen in bèta voor Noord-Amerika) worden gehost om toegang te krijgen tot deze mogelijkheden. Neem contact op met de klantenservice van Adobe als u toegang wilt.

## Toegang tot publiek Adobe Experience Platform

Als u toegang wilt krijgen tot de builder van het Adobe Experience Platform, navigeert u naar de **[!UICONTROL Audiences]** kaart op de startpagina van Campaign Standard (of de **[!UICONTROL Audiences]** koppeling in de koptekst) en selecteert u de **[!UICONTROL Adobe Experience Platform]** omgeving.

![](assets/aep_audiences_access.png)

U zult eerst aan de pagina van de de segmentlijst van het Adobe Experience Platform worden geleid, waar reeds bestaande segmenten van het Adobe Experience Platform voor verdere het uitgeven kunnen worden betreden.

Er zijn een zoekbalk en filter beschikbaar waarmee u het gewenste Adobe Experience Platform kunt vinden.

![](assets/aep_audiences_list.png)

## Adobe Experience Platforms publiek maken

Ga als volgt te werk om een publiek van een Adobe Experience Platform rechtstreeks in Campaign Standard te maken:

1. Van de pagina van de de segmentlijst van het Adobe Experience Platform, klik de **[!UICONTROL New audience]** knoop die in de juiste hoek wordt gevestigd.

   ![](assets/aep_audiences_creation_create.png)

1. De Segment Builder moet nu in uw werkruimte worden weergegeven. Het staat u toe om een segment te bouwen gebruikend gegevens van Adobe Experience Platform die uiteindelijk zullen worden gebruikt om uw publiek tot stand te brengen.

1. Geef het segment een naam in het rechterdeelvenster en voer een beschrijving in (optioneel).

   ![](assets/aep_audiences_creation_edit_name.png)

1. Als u een segment wilt maken, moet u een **samenvoegbeleid** selecteren dat overeenkomt met uw marketingdoel voor dit segment.

   In de instellingenruit, wordt een Platform standaardsamenvoegbeleid geselecteerd. Voor meer informatie over fusiebeleid, verwijs naar de specifieke sectie van de de gebruikersgids [van de Bouwer van het](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html)Segment.

   ![](assets/aep_audiences_mergepolicy.png)

1. Bepaal de regels die de profielen zullen identificeren die in uw publiek moeten worden teruggewonnen.

   Om dit te doen, sleep de gewenste attributen en/of de gebeurtenissen van de linkerruit in de werkruimte, bepaal de overeenkomstige regels dan klik de **[!UICONTROL Create segment]** knoop om het segment (zie het [Gebruiken van de Bouwer](../../audiences/using/aep-using-segment-builder.md)van het Segment) te bewaren.

   ![](assets/aep_audiences_creation_query.png)

Het publiek is nu klaar om te worden geactiveerd, kunt u het gebruiken als doel voor uw campagnes (zie [Doelgroepen van Adobe Experience Platforms](../../automating/using/aep-targeting-audiences.md)).

## Soorten publiek bewerken

Om een publiek uit te geven, open het en wijzig de regels zoals nodig binnen de interface van de Bouwer van het Segment (zie het [Gebruiken van de Bouwer](../../audiences/using/aep-using-segment-builder.md)van het Segment).

Nadat de wijzigingen zijn voltooid, klikt u op de **[!UICONTROL Save segment]** knop om het publiek bij te werken.

![](assets/aep_audiences_editing.png)
