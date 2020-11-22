---
solution: Campaign Standard
product: campaign
title: De onderwerpregel en de afzender van een e-mail definiëren
description: Ontdek hoe u de onderwerpregel en de afzender van een e-mailbericht kunt definiëren in de e-mailontwerper.
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 2%

---


# De onderwerpregel en de afzender van een e-mail definiëren{#defining-the-subject-line-of-an-email}

## Defining the subject line of an email {#subject-line}

Het bericht is verplicht om het bericht voor te bereiden en te verzenden.

>[!NOTE]
>
>Als de onderwerpregel leeg is, wordt een waarschuwing weergegeven op het berichtdashboard en in de e-mailontwerper.

1. Een e-mail maken.
1. Ga naar het **[!UICONTROL Properties]** tabblad van de introductiepagina E-mail Designer (toegankelijk via het introductiepictogram).
1. Fill in the **[!UICONTROL Subject]** section.

   ![](assets/email_designer_subject.png)

1. U kunt ook aanpassingsvelden, inhoudsblokken en dynamische inhoud toevoegen aan de onderwerpregel door op de corresponderende pictogrammen te klikken. For more on this, see [Personalization](../../designing/using/personalization.md).
1. U kunt verschillende onderwerpreeksen uitproberen om een schatting te krijgen van uw e-mailopen tarief alvorens u het verzendt. Zie [De onderwerpregel van een e-mail](../../sending/using/testing-subject-line-email.md)testen voor meer informatie.

## De e-mailafzender van een e-mailbericht definiëren {#email-sender}

Als u de naam wilt definiëren van de afzender die wordt weergegeven in de koptekst van de verzonden berichten, gaat u naar het **[!UICONTROL Properties]** tabblad van de introductiepagina E-mail Designer (toegankelijk via het introductiepictogram).

![](assets/delivery_content_edition16.png)

* In het **[!UICONTROL From: name]** veld kunt u de naam van de afzender invoeren. Standaard wordt het standaardnaamblok van de **afzender** automatisch in het veld ingevoerd. Het standaard e-mailadres en de naam van de afzender zijn gedefinieerd in **[!UICONTROL Brands]** toegankelijk via het Adobe Campaign-logo onder het geavanceerde menu **[!UICONTROL Administration > Instance settings > Brand configuration]** .

   U kunt de naam van de afzender wijzigen door op het naamblok van de **afzender** te klikken. Het veld wordt bewerkbaar en u kunt de naam invoeren die u wilt gebruiken.

   U kunt dit veld aanpassen. Hiervoor kunt u aanpassingsvelden, inhoudsblokken en dynamische inhoud toevoegen door op de pictogrammen onder de naam van de afzender te klikken. For more on this, see [Personalization](../../designing/using/personalization.md).

* Het **[!UICONTROL From: email address]** veld kan niet vanuit deze sectie worden bewerkt. U kunt dit wijzigen door de eigenschappen van de e-mail te bewerken vanaf het dashboard. Zie [Lijst met geavanceerde e-mailparameters](../../administration/using/configuring-email-channel.md#advanced-parameters)voor meer informatie.

>[!NOTE]
>
>De headerparameters mogen niet leeg zijn. Het adres van de afzender is verplicht om een e-mailbericht toe te staan (norm RFC). Adobe Campaign controleert de syntaxis van de ingevoerde e-mailadressen.

**Verwante onderwerpen:**

* [Een personalisatieveld invoegen](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Een inhoudsblok toevoegen](../../designing/using/personalization.md#adding-a-content-block)
* [Dynamische inhoud in een e-mail definiëren](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
