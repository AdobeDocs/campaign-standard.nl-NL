---
title: De onderwerpregel en de afzender van een e-mail definiëren
description: Ontdek hoe u de onderwerpregel en de afzender van een e-mailbericht kunt definiëren in de e-mailontwerper.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 259f7033310982298024462c0134989404c096f4

---


# De onderwerpregel en de afzender van een e-mail definiëren{#defining-the-subject-line-of-an-email}

Het bericht is verplicht om het bericht voor te bereiden en te verzenden.

>[!NOTE]
>
>Als de onderwerpregel leeg is, wordt een waarschuwing weergegeven op het berichtdashboard en in de e-mailontwerper.

Als u het onderwerp van de e-mail wilt configureren, gaat u naar het **[!UICONTROL Properties]** tabblad van de introductiepagina E-mail Designer (toegankelijk via het introductiepictogram) en vult u de **[!UICONTROL Subject]** sectie in.

**De onderwerpregel van een e-mail** definiëren:

1. Maak een e-mail.
1. Sluit homepage.
1. Ga naar het **[!UICONTROL Properties]** tabblad van de introductiepagina E-mail Designer (toegankelijk via het introductiepictogram) en vul de **[!UICONTROL Subject]** sectie in.

![](assets/email_designer_subject.png)

U kunt ook aanpassingsvelden, inhoudsblokken en dynamische inhoud toevoegen aan de onderwerpregel door op de corresponderende pictogrammen te klikken.

## Predictieve onderwerpregel {#predictive-subject-line}

Wanneer u een e-mailbericht bewerkt, kunt u verschillende onderwerpregel uitproberen en een schatting krijgen van de openstaande frequentie voordat u het bericht verzendt.

Deze functie is standaard uitgeschakeld. Deze optie wordt ingeschakeld wanneer het eerste model wordt geïmporteerd. Een model is het resultaat van reeksen van opleidingsgegevens die specifiek zijn voor een bepaalde bedrijfstak. Met modellen kan het systeem voorspellen wat de open snelheid van de e-mail is wanneer een nieuwe onderwerpregel wordt verzonden.

>[!NOTE]
>
>Deze functie is beschikbaar voor e-mailberichten en voor databases die alleen Engelse inhoud bevatten. Het getrainde model is inconsistent en leidt tot onjuiste resultaten als uw exemplaar e-mails in andere talen bevat. De optie waarmee u een onderwerp kunt testen, is alleen zichtbaar als er al een model beschikbaar is in uw exemplaar.

**Verwante onderwerpen**

* [De onderwerpregel van een e-mail testen](../../sending/using/testing-subject-line-email.md)

## De e-mailafzender van een e-mailbericht definiëren {#email-sender}

Als u de naam wilt definiëren van de afzender die wordt weergegeven in de koptekst van de verzonden berichten, gaat u naar het **[!UICONTROL Properties]** tabblad van de introductiepagina E-mail Designer (toegankelijk via het introductiepictogram).

![](assets/delivery_content_edition16.png)

* In het **[!UICONTROL From: name]** veld kunt u de naam van de afzender invoeren. Standaard wordt het standaardnaamblok van de **afzender** automatisch in het veld ingevoerd. Het standaard e-mailadres en de naam van de afzender zijn gedefinieerd in **[!UICONTROL Brands]** toegankelijk via het logo van de Campagne van Adobe onder het geavanceerde menu **[!UICONTROL Administration > Instance settings > Brand configuration]** .

   U kunt de naam van de afzender wijzigen door op het naamblok van de **afzender** te klikken. Het veld wordt bewerkbaar en u kunt de naam invoeren die u wilt gebruiken.

   U kunt dit veld aanpassen. Hiervoor kunt u aanpassingsvelden, inhoudsblokken en dynamische inhoud toevoegen door op de pictogrammen onder de naam van de afzender te klikken.

* Het **[!UICONTROL From: email address]** veld kan niet vanuit deze sectie worden bewerkt. U kunt dit wijzigen door de eigenschappen van de e-mail te bewerken vanaf het dashboard. Zie [Lijst met geavanceerde e-mailparameters](../../administration/using/configuring-email-channel.md#advanced-parameters)voor meer informatie.

>[!NOTE]
>
>De headerparameters mogen niet leeg zijn. Het adres van de afzender is verplicht om een e-mailbericht toe te staan (norm RFC). Adobe Campagne controleert de syntaxis van e-mailadressen ingegaan.

**Verwante onderwerpen:**

* [Een aanpassingsveld invoegen](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Een inhoudsblok toevoegen](../../designing/using/personalization.md#adding-a-content-block)
* [Dynamische inhoud in een e-mail definiëren](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
