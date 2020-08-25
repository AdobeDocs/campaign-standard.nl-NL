---
title: Merkpositionering
description: Ontdek alle tools die beschikbaar zijn om uw merkidentiteit te beheren.
page-status-flag: never-activated
uuid: d66ac5a2-2ae1-4870-b48e-7f276744ffdd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: cbb1dcec-3bc6-4013-87fa-27d0e5d32bf8
context-tags: branding,overview;branding,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1efcd646f4af86175b3b09b53185c792cb4cf7dd
workflow-type: tm+mt
source-wordcount: '983'
ht-degree: 100%

---


# Merkpositionering{#branding}

## Merkidentiteit {#about-brand-identity}

Elk bedrijf heeft visuele en technische richtlijnen voor de merkidentiteit. Met Adobe Campaign kunt u een reeks specificaties instellen om een consistente merkidentiteit en -beleving aan uw klanten te bieden, van logo&#39;s tot technische aspecten, zoals een e-mailafzender, URL of domeinen.

Technische beheerders kunnen een of meer merken definiëren om de parameters voor de identiteit van een merk centraal in te voeren. Dit zijn onder andere het merklogo, het domein van de toegangs-URL voor de landingspagina&#39;s of de instellingen voor de tracking van berichten. Met Adobe Campaign kunt u deze merken maken en ze koppelen aan berichten of landingspagina&#39;s. Deze configuratie wordt beheerd in sjablonen.

## Merken configureren en gebruiken {#configuring-and-using-brands}

Het belangrijkste principe voor het configureren en gebruiken van merken is het volgende:

1. Maak en configureer het merk. Deze bewerking vereist specifieke machtigingen en wordt uitgevoerd door de technische beheerder van Adobe Campaign.
1. Maak een of meer sjablonen voor leveringen en landingspagina&#39;s voor dit merk. Raadpleeg de sectie [Een sjabloon maken](../../start/using/marketing-activity-templates.md).
1. Maak berichten en landingspagina&#39;s op basis van deze sjabloon. Raadpleeg de secties [Een e-mail maken](../../channels/using/creating-an-email.md) en [Een landingspagina maken](../../channels/using/designing-a-landing-page.md).

>[!IMPORTANT]
>
>Merken kunnen niet door eindgebruikers worden gemaakt of gewijzigd. Deze bewerkingen moeten worden uitgevoerd door de technische beheerder van Adobe Campaign. Neem voor elk verzoek contact op met de klantenservice van Adobe.
>
>Positionering van meerdere merken kan niet worden gebruikt in de context van transactionele berichten. Raadpleeg [Transactionele berichten en merkpositionering](../../channels/using/transactional-messaging-limitations.md#permissions-and-branding) voor meer informatie.

U vindt merken in het menu **[!UICONTROL Administration > Instance settings > Brand configuration]**.

Een nieuw gemaakt merk is standaard alleen zichtbaar voor gebruikers aan wie de beheerder de bijbehorende rechten heeft toegekend.

Een **merk** wordt gedefinieerd door de volgende kenmerken:

* Een **identiteit** die uw merk definieert en personaliseert. Deze sectie bevat de volgende velden:

   ![](assets/branding_01.png)

   * **Label** zichtbaar in de interface
   * **Brand name**
   * **Website URL** en **Website label** van het merk
   * **Brand logo**

* **[!UICONTROL Header parameters of sent emails]** personaliseert wat de ontvangers van uw campagnes te zien krijgen. Deze sectie bevat de volgende velden:

   ![](assets/branding_04_header.png)

   * **Sender (email address)** met het e-mailadres van het merk.
   * **Sender (name)** met de naam van het merk.
   * **Reply to (email address)** met het e-mailadres waarop de klant kan antwoorden.
   * **Reply to (name)** met de naam van het merk.
   * **Error (email address)** met het e-mailadres dat moet worden gebruikt in geval van een fout.

   >[!IMPORTANT]
   >
   >Nadat u de koptekstparameters van de e-mails hebt bijgewerkt, controleert u de geavanceerde instellingen van de sjabloon als de naam en het e-mailadres van de afzender niet zijn gewijzigd in de e-mail die met de sjabloon is gemaakt.

* **Server(s) exposed on the Internet** definieert de servers die worden gebruikt voor tracking, maar ook voor toegang tot landingspagina&#39;s. Deze sectie bevat de volgende velden:

   ![](assets/configure_branding_04.png)

   * **External URL of the application server** wordt gebruikt voor het hosten en openen van de verschillende landingspagina&#39;s die u maakt.
   * **External URL of the tracking server** wordt gebruikt als de URL die wordt getraceerd tijdens de leveringen.
   * **External URL of the mirror page server** wordt gebruikt als standaard spiegelpagina in uw leveringen.

   >[!NOTE]
   >
   >Als u het voorbeeld van de landingspagina en de weergave van de spiegelpagina wilt weergeven in de gebruikersinterface van Campaign, moeten de URL&#39;s van de applicatieserver en de spiegelpaginaserver veilig zijn. Gebruik in dat geval https:// in plaats van http:// wanneer u deze URL&#39;s instelt.

* **[!UICONTROL Tracking URL configuration (Web Analytics)]** definieert de configuratie van URL-tracking voor uw merk.

   Hier worden de aanvullende parameters gedefinieerd waarmee de koppelingen kunnen worden bijgehouden op externe systemen, zoals Web Analytics-tools zoals Adobe Analytics of Google Analytics.

   ![](assets/branding_05.png)

## Een merk toewijzen aan een e-mail {#assigning-a-brand-to-an-email}

### Een merk koppelen aan een sjabloon {#linking-a-brand-to-a-template}

Om de parameters te gebruiken die voor een merk worden bepaald, moet het merk aan een leveringssjabloon of een landingspaginasjabloon worden gekoppeld. Hiervoor moet u een sjabloon maken of bewerken.

>[!NOTE]
>
>Raadpleeg de sectie [Een sjabloon maken](../../start/using/marketing-activity-templates.md) voor meer informatie over het maken van een sjabloon.

Nadat u de sjabloon hebt gemaakt, kunt u deze koppelen aan een merk. Dit doet u als volgt:

1. Klik op de knop **[!UICONTROL Edit properties]** voor toegang tot de sjablooneigenschappen.

   ![](assets/branding_04.png)

1. Gebruik de vervolgkeuzelijst om het merk te selecteren dat u aan de sjabloon wilt koppelen.

   >[!NOTE]
   >
   >Standaard is **[!UICONTROL Default brand (branding)]** geselecteerd.

   ![](assets/branding_05.png)

   Klik op het pictogram **[!UICONTROL Navigate to the detail of the element selected]** om te zien hoe het geselecteerde merk is geconfigureerd.

   ![](assets/branding_06.png)

1. Bevestig uw selectie en sla uw sjabloon op.

Uw sjabloon wordt gekoppeld aan het merk. In de e-maileditor maken de elementen zoals **Email address of default sender**, **Default sender name** of **Logo** gebruik van de geconfigureerde merkdata.

### Gebruiksscenario voor merkpositionering {#branding-use-case}

In dit voorbeeld gaan we een nieuw aan reizen gerelateerd merk maken en dit in een e-mail gebruiken.

#### Een nieuw merk configureren {#configure-a-new-brand}

>[!IMPORTANT]
>
>Merkconfiguratie wordt alleen door Adobe beheerd omdat hiervoor specifieke machtigingen en technische instellingen vereist zijn.

1. De Adobe Campaign-beheerder maakt het merk in **[!UICONTROL Administration > Instance settings > Brand configuration]**. Hij voegt het element **Vacations in the Tropics** toe vanaf het geavanceerde menu en configureert de **[!UICONTROL ID]** en de **[!UICONTROL Header parameters of sent emails]** van het merk.

   ![](assets/branding_07.png)

1. De beheerder configureert vervolgens de URL van de **Server(s) exposed on the Internet**, zodat landingspagina&#39;s kunnen worden gebruikt en daarna de tracking-URL&#39;s.

   In dit voorbeeld is de **Web Analytics**-tool die wordt gebruikt **Google Analytics**. De beheerder configureert de tracking-URL als volgt:

   ![](assets/branding_12.png)

Het merk wordt correct gemaakt en geconfigureerd. Het kan nu door de marketingteams worden gebruikt.

#### Een nieuw merk implementeren {#implement-a-new-brand}

Als leveringsbeheerder bent u verantwoordelijk voor het maken van de leveringssjablonen die het nieuwe merk gebruiken. Volg onderstaande stappen om dit te bereiken:

1. Dupliceer in het geavanceerde menu **[!UICONTROL Resources > Templates > Delivery templates]** een ingebouwde sjabloon om een nieuwe leveringssjabloon te configureren.

   ![](assets/branding_08.png)

1. Als u deze sjabloon wilt koppelen aan het merk **Vacations in the Tropics**, bewerkt u de sjablooneigenschappen en selecteert u het merk in de vervolgkeuzelijst.

   ![](assets/branding_09.png)

1. Configureer deze e-mailsjabloon om de merkidentiteit weer te geven.
1. Nadat de sjabloon is voltooid, kunt u deze opslaan.

   ![](assets/branding_10.png)

   De leveringssjabloon kan nu worden gebruikt om e-mails te maken die naar een doelgroep worden verzonden.

#### Het nieuwe merk in een levering gebruiken {#use-the-new-brand-in-a-delivery}

Voer de onderstaande stappen uit om een e-mail te maken die aan een merk is gekoppeld:

1. Klik op de knop **[!UICONTROL Create]** in het menu **[!UICONTROL Marketing activities]**.

   ![](assets/branding_14.png)

1. Selecteer de activiteit **[!UICONTROL Email]** en kies vervolgens de sjabloon die aan het nieuwe merk is gekoppeld.

   ![](assets/branding_15.png)

1. Uw e-mail is al geconfigureerd. U kunt de informatie controleren voordat u deze test met behulp van de testprofielen en de e-mail vervolgens naar de doelgroep verzenden.

   ![](assets/branding_16.png)

