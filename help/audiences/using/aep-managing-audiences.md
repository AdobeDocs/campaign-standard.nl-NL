---
title: Adobe Experience Platform-publiek beheren
description: Leer hoe u Adobe Experience Platform beheert binnen de Campagnestandaard.
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
source-git-commit: 2ef524d1d276abb1ff0a7149462452cafe8e5cd3

---


# Adobe Experience Platform-publiek beheren {#about-audiences}

>[!IMPORTANT]
>
>De Dienst van de Doelen van het publiek is momenteel in bèta, die aan regelmatige updates zonder bericht kan worden onderworpen. Klanten moeten op Azure (momenteel alleen in bèta voor Noord-Amerika) worden gehost om toegang te krijgen tot deze mogelijkheden. Neem contact op met de klantenservice van Adobe als u toegang wilt.

## Toegang tot publiek van Adobe Experience Platform

Als u toegang wilt krijgen tot de segmentbuilder van het Adobe Experience Platform, navigeert u naar de **[!UICONTROL Audiences]** kaart op de startpagina van Campagne Standard (of de **[!UICONTROL Audiences]** koppeling in de koptekst) en selecteert u de **[!UICONTROL Adobe Experience Platform]** omgeving.

![](assets/aep_audiences_access.png)

U wordt eerst verwezen naar de pagina met segmentlijsten voor het Adobe Experience Platform, waar u toegang hebt tot bestaande Adobe Experience Platform-segmenten voor verdere bewerking.

Er zijn een zoekbalk en filter beschikbaar waarmee u het gewenste Adobe Experience Platform-segment kunt vinden.

![](assets/aep_audiences_list.png)

## Adobe Experience Platform-publiek maken

Voer de volgende stappen uit om een publiek van het Adobe Experience Platform rechtstreeks in de Campagnestandaard te maken:

1. Klik op de pagina met segmentlijsten voor Adobe Experience Platform op de **[!UICONTROL New audience]** knop in de rechterhoek.

   ![](assets/aep_audiences_creation_create.png)

1. De Unified Segment Builder moet nu in uw werkruimte worden weergegeven. Hiermee kunt u een segment maken met behulp van gegevens van het Adobe Experience Platform die uiteindelijk worden gebruikt om uw publiek te maken.

1. Geef het segment een naam in het rechterdeelvenster en voer een beschrijving in (optioneel).

   ![](assets/aep_audiences_creation_edit_name.png)

1. Als u een segment wilt maken, moet u een **samenvoegbeleid** selecteren dat overeenkomt met uw marketingdoel voor dit segment.

   In de instellingenruit, wordt een Platform standaardsamenvoegbeleid geselecteerd. Voor meer informatie over fusiebeleid, verwijs naar de specifieke sectie van de de gebruikersgids [van de Bouwer van het](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)Segment.

   ![](assets/aep_audiences_mergepolicy.png)

1. Bepaal de regels die de profielen zullen identificeren die in uw publiek moeten worden teruggewonnen.

   Om dit te doen, sleep de gewenste attributen en/of de gebeurtenissen van de linkerruit in de werkruimte, bepaal de overeenkomstige regels dan klik de **[!UICONTROL Create segment]** knoop om het segment (zie [Gebruikend de Verenigde Bouwer](../../audiences/using/aep-using-segment-builder.md)van het Segment) te bewaren.

   ![](assets/aep_audiences_creation_query.png)

Het publiek is nu klaar om te worden geactiveerd en u kunt het gebruiken als doel voor uw campagnes (zie [Doelgroepen van het Adobe Experience Platform](../../automating/using/aep-targeting-audiences.md)).

## Soorten publiek bewerken

Om een publiek uit te geven, open het en wijzig de regels zoals nodig binnen de Verenigde interface van de Bouwer van het Segment (zie het [Gebruiken van de Verenigde Bouwer](../../audiences/using/aep-using-segment-builder.md)van het Segment).

Nadat de wijzigingen zijn voltooid, klikt u op de **[!UICONTROL Save segment]** knop om het publiek bij te werken.

![](assets/aep_audiences_editing.png)
