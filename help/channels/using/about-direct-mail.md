---
solution: Campaign Standard
product: campaign
title: Informatie over direct mail
description: Ontdek de belangrijkste specifieke kenmerken van het direct-mailkanaal in Adobe Campaign.
audience: channels
content-type: reference
topic-tags: direct-mail
context-tags: delivery,directMailContent,back;deliveryCreation,wizard
feature: Direct mail
role: Zakelijke praktiserer
level: Intermediair
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 97%

---


# Informatie over direct mail{#about-direct-mail}

Direct mail is een offline kanaal waarmee u het bestand dat wordt vereist door direct-mailproviders kunt personaliseren en genereren. Het biedt u de mogelijkheid om online en offline kanalen in uw klanttrajecten te combineren.

>[!NOTE]
>
>Deze functie is optioneel. Controleer hiervoor uw licentieovereenkomst. De rol **[!UICONTROL Export]** is vereist om direct mail te gebruiken. Neem contact op met uw beheerder.

Met online kanalen kunt u uw berichten (e-mail, sms, levering van mobiele apps, enzovoort) maken en ze vanuit Adobe Campaign direct naar uw doelgroep verzenden. Bij offline kanalen is dit anders. Wanneer u een direct-maillevering voorbereidt, genereert Adobe Campaign een bestand met alle doelprofielen en de gekozen contactinformatie (bijvoorbeeld postadres). U kunt dit bestand dan naar uw direct-mailprovider sturen, die voor de werkelijke verzending zorgt.

In de volgende sectie wordt uitgelegd hoe u een eenmalige direct-maillevering maakt en genereert. U kunt ook direct-mailactiviteiten opnemen in een workflow om campagnes te organiseren waarin online en offline kanalen worden gecombineerd. Raadpleeg de handleiding [Workflows](../../automating/using/get-started-workflows.md) voor meer informatie.

Het gebruikersproces in Adobe Campaign is als volgt:

1. De levering maken
1. De doelgroep kiezen
1. De content definiëren
1. De contactdatum instellen
1. Het bestand genereren

**Verwante onderwerpen:**

* [Hoofdlettergebruik: Koppeling van e-mail- en direct-mailleveringen](../../automating/using/coupling-email-direct-mail.md)

## Aanbevelingen {#recommendations}

### Direct-mailproviders {#direct-mail-providers}

Ten eerste moet u contact opnemen met uw direct-mailprovider en de aanbevelingen van deze provider verzamelen. Identificeer welke profielinformatie in het extractiebestand moet worden opgenomen zodat de provider de communicatie kan personaliseren en naar de doelgroep verzenden. Bijvoorbeeld de voornaam en achternaam, het postadres, een promotiecode, enzovoort. Dit zijn de velden die u toevoegt op het tabblad [Defining the extraction](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) van de content voor direct mail.

Controleer of u het selectievakje **[!UICONTROL Address specified]** in de profieldata hebt ingeschakeld. Als deze optie is geactiveerd, wordt het profiel toegevoegd aan het doel. Als dit niet het geval is, wordt het door een typologieregel tijdens de voorbereidingsfase uitgesloten (zie [Direct mail maken](../../channels/using/creating-the-direct-mail.md)). Vergeet niet dit veld bij te werken tijdens het importeren van profielen.

![](assets/direct_mail_22.png)

### Postadressen {#postal-addresses}

Wanneer u de velden toevoegt die u in het extractiebestand wilt opnemen, zijn de velden voor postadressen beschikbaar in het knooppunt **[!UICONTROL Location]**.

Adobe Campaign biedt u een reeks vooraf gedefinieerde, berekende velden die de meest gebruikelijke standaarden voor postadressen volgen. De velden zijn beschikbaar in het knooppunt **[!UICONTROL Postal address]**.

Een adres kan standaard maximaal zes regels bevatten: het eerste berekende veld (**[!UICONTROL Line 1]**) bevat de voornaam en achternaam, de volgende regels bevatten het postadres (de weg, enzovoort) en de laatste regel bevat de postcode en de plaats of stad.

![](assets/direct_mail_23.png)
