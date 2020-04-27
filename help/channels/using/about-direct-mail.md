---
title: Over direct mail
description: Ontdek de belangrijkste specifieke kenmerken van het directe-mailkanaal in de Campagne van Adobe.
page-status-flag: never-activated
uuid: 24add992-2efe-4b73-81c9-cda3e921ab16
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: e1fbf39c-9c30-493c-8322-9c71e18ce98c
context-tags: delivery,directMailContent,back;deliveryCreation,wizard
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2

---


# Over direct mail{#about-direct-mail}

Directe post is een off-line kanaal dat u toestaat om het dossier te personaliseren en te produceren dat door directe postleveranciers wordt vereist. Het biedt u de mogelijkheid om online en off-line kanalen in uw klantenreizen te mengen.

>[!NOTE]
>
>Deze functie is optioneel. Controleer uw licentieovereenkomst. De **[!UICONTROL Export]** rol is vereist om direct mail te gebruiken. Neem contact op met uw beheerder.

Met onlinekanalen kunt u uw berichten maken (e-mail, sms, levering van mobiele apps, enz.) en stuur ze rechtstreeks vanuit Adobe Campaign naar uw doelgroep. Bij offlinekanalen is dit anders. Wanneer u een directe postbestelling voorbereidt, genereert Adobe Campagne een dossier met alle gerichte profielen en de gekozen contactinformatie (postadres bijvoorbeeld). U kunt dit bestand dan naar uw directe-mailprovider sturen, die voor de verzending zal zorgen.

In de volgende sectie wordt uitgelegd hoe u een enkelvoudige directe maillevering maakt en genereert. U kunt ook direct-mailactiviteiten opnemen in een workflow om campagnes te organiseren waarin online en offline kanalen worden gecombineerd. Raadpleeg de handleiding [Workflows](../../automating/using/workflow-data-and-processes.md) voor meer informatie.

Het gebruikersproces in Adobe Campaign is als volgt:

1. De levering maken
1. Het publiek kiezen
1. De inhoud definiëren
1. De contactdatum instellen
1. Het bestand genereren

## Aanbevelingen {#recommendations}

### Direct-mailproviders {#direct-mail-providers}

Ten eerste moet u contact opnemen met uw directe-mailprovider en de aanbevelingen van deze provider verzamelen. Identificeer welke profielinformatie in het extractiedossier moet worden omvat zodat zij de mededeling kunnen personaliseren en het naar het publiek verzenden. Bijvoorbeeld de voornaam en achternaam, het postadres, een promotiecode, enz. Dit zijn de velden die u toevoegt op het tabblad [Definiining the extraction](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) of the direct mail&#39;s content.

Controleer of u het **[!UICONTROL Address specified]** selectievakje in de profielgegevens hebt ingeschakeld. Als deze optie is geactiveerd, wordt het profiel toegevoegd aan het doel. Dit is niet het geval, het zal door een typologieregel tijdens de voorbereidingsfase worden uitgesloten (zie [Het direct mail](../../channels/using/creating-the-direct-mail.md)creëren). Vergeet niet dit veld bij te werken tijdens het importeren van profielen.

![](assets/direct_mail_22.png)

### Postadressen {#postal-addresses}

Wanneer u de velden toevoegt die u in het extractiebestand wilt opnemen, zijn de velden voor postadressen beschikbaar in het **[!UICONTROL Location]** knooppunt.

Adobe Campagne biedt u een reeks vooraf gedefinieerde, berekende velden die de meest gebruikelijke normalisatie van het postadres volgen. De velden zijn beschikbaar in het **[!UICONTROL Postal address]** knooppunt.

Een adres kan maximaal zes lijnen door gebrek bevatten: het eerste berekende veld (**[!UICONTROL Line 1]** bevat de voornaam en achternaam, de volgende regels bevatten het postadres (weg enz.) en de laatste regel bevat de postcode en de plaats of stad.

![](assets/direct_mail_23.png)

