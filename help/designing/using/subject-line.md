---
title: De onderwerpregel en de afzender van een e-mail definiëren
description: Ontdek hoe u de onderwerpregel en de afzender van een e-mailbericht kunt definiëren in de e-mailontwerper.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Beginner
exl-id: 22112517-40f7-4966-84bf-40794e5d0f79
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 2%

---

# De onderwerpregel en de afzender van een e-mail definiëren{#defining-the-subject-line-of-an-email}

## De onderwerpregel van een e-mailbericht definiëren {#subject-line}

Het bericht is verplicht om het bericht voor te bereiden en te verzenden.

>[!NOTE]
>
>Als de onderwerpregel leeg is, wordt een waarschuwing weergegeven op het berichtdashboard en in de e-mailontwerper.

1. Een e-mail maken.
1. Ga naar de **[!UICONTROL Properties]** tabblad van de introductiepagina E-mail Designer (toegankelijk via het homepictogram).
1. Vul de **[!UICONTROL Subject]** sectie.

   ![](assets/email_designer_subject.png)

1. U kunt ook aanpassingsvelden, inhoudsblokken en dynamische inhoud toevoegen aan de onderwerpregel door op de corresponderende pictogrammen te klikken. Zie voor meer informatie [Personalisatie](../../designing/using/personalization.md).

## De e-mailafzender van een e-mailbericht definiëren {#email-sender}

Als u de naam wilt definiëren van de afzender die wordt weergegeven in de koptekst van de verzonden berichten, gaat u naar **[!UICONTROL Properties]** tabblad van de introductiepagina E-mail Designer (toegankelijk via het homepictogram).

![](assets/delivery_content_edition16.png)

* De **[!UICONTROL From: name]** kunt u de naam van de afzender invoeren. Standaard wordt de standaard **Naam afzender** wordt automatisch in het veld ingevoerd. Het standaard e-mailadres en de naam van de afzender worden gedefinieerd in **[!UICONTROL Brands]** toegankelijk via het Adobe Campaign-logo in het geavanceerde menu **[!UICONTROL Administration > Instance settings > Brand configuration]** .

  U kunt de naam van de afzender wijzigen door op de knop **Naam afzender** blokkeren. Het veld wordt bewerkbaar en u kunt de naam invoeren die u wilt gebruiken.

  U kunt dit veld aanpassen. Hiervoor kunt u aanpassingsvelden, inhoudsblokken en dynamische inhoud toevoegen door op de pictogrammen onder de naam van de afzender te klikken. Zie voor meer informatie [Personalisatie](../../designing/using/personalization.md).

* De **[!UICONTROL From: email address]** kan niet vanuit deze sectie worden bewerkt. U kunt dit wijzigen door de eigenschappen van de e-mail te bewerken vanaf het dashboard. Zie voor meer informatie [Lijst met geavanceerde e-mailparameters](../../administration/using/configuring-email-channel.md#advanced-parameters).

>[!NOTE]
>
>De headerparameters mogen niet leeg zijn. Het adres van de afzender is verplicht om een e-mailbericht toe te staan (norm RFC). Adobe Campaign controleert de syntaxis van de ingevoerde e-mailadressen.

**Verwante onderwerpen:**

* [Een personalisatieveld invoegen](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Een inhoudsblok toevoegen](../../designing/using/personalization.md#adding-a-content-block)
* [Dynamische inhoud in een e-mail definiëren](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
