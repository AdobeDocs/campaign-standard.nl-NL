---
title: Informatie over de service Bestemmingen publiek
description: Meer informatie over de service Doelen voor doelgroepen.
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
source-git-commit: 77ceb5e5ca05fc3ee350d8e50fe0c957dec6ea26

---


# Informatie over de service Bestemmingen publiek {#about-audiences}

>[!IMPORTANT]
>
>De dienst van de Doelen van het publiek is momenteel in bèta, die aan regelmatige updates zonder bericht kan worden onderworpen. Klanten moeten op Azure (momenteel alleen in bèta voor Noord-Amerika) worden gehost om toegang te krijgen tot deze mogelijkheden. Neem contact op met de klantenservice van Adobe als u toegang wilt.

Maak uw ervaringen met consumenten kracht door gebruik te maken van het [Adobe Experience Platform](https://www.adobe.io/apis/experienceplatform/home.html) om een doelgericht publiek op te bouwen op basis van grote, complexe datasets. Het Adobe Experience Platform consolideert profielen, gedragingen en gegevens van meerdere entiteiten online en offline bronnen, waaronder Adobe Analytics, om u te helpen een 360-gradenweergave van uw klant te maken, zodat u uw ervaringen met klanten effectief kunt beheren.

Adobe Campaign Standard gebruikt vervolgens de service Doelen **voor** doelgroepen om een verzameling profielen, die bekend staan als **Soorten publiek**, op te halen uit het Adobe Experience Platform voor campagneprogramma&#39;s met meerdere stappen en/of meerdere kanalen.

**Soorten publiek** worden gemaakt door eerst **segmenten** te maken. Dit zijn in wezen een set regels die zijn gebaseerd op vrijwel elke variabele (bijvoorbeeld profiel, gebeurtenis, gegevens van meerdere entiteiten) binnen een klantprofiel van Adobe Experience Platform om een multidimensionaal doel te maken. De globale concepten op Verenigde Profiel &amp; de Diensten van de Segmentatie worden van verwijzingen voorzien in [deze specifieke documenten](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation.html).

Zodra een segment is gecreeerd, kunt u het als publiek voor een levering in de [Standaardwerkschema](../../automating/using/aep-targeting-audiences.md)van de Campagne dan activeren. Daarnaast kunt u contextafhankelijke gegevens van het Adobe Experience Platform gebruiken om dynamische inhoud aan uw campagnes [aan te passen](../../automating/using/aep-personalizing-campaigns.md) en toe te voegen.

Hoe kan ik-video&#39;s zijn ook beschikbaar in [deze sectie](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html).

In deze secties gebruikte termen:

* **Profiel**: Profiel is een standaardgegevensmodel van het ervaringsplatform dat wordt gebruikt om kenmerken van consumenten te definiëren. Een profiel kan ook een aggregaat zijn van gebeurtenisgegevens en -kenmerken die betrekking hebben op een persoon en/of apparaat.

   Voorbeeld: &quot;John Doe is een 55-jarige man.&quot;

* **Segment**: Een set regels die een subset van profielen definieert vanuit uw database, waarbij zowel kenmerken als gebeurtenisgegevens worden gebruikt.

   Voorbeeld: &quot;Menen > 50 jaar oud.&quot;

* **Publiek**: Een verzameling profielen die voldoen aan segmentregels.

   Voorbeeld: Lijst met profielen voor alle mannen > 50 jaar oud in uw database.
