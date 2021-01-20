---
title: Krijg Toegang tot de Integratie van Adobe Campaign Standard met Dynamics 365 Self-Service App
description: Adobe Campaign Standard-integratie met Dynamics 365 Self-Service App
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: cce30fd5cd3d5d63563d1dab3bb1e7554c26fb3e
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 0%

---


# Heb toegang tot de Integratie van Adobe Campaign Standard met de Dynamica 365 van Microsoft Zelfbediening App

Voor deze configuratie moet u met een Experience Cloud (EC)-beheerder voor uw organisatie werken. Dit zijn de aanvankelijke stappen die worden vereist om u toegang tot de interface van de zelfbedieningstoepassing te geven. Zodra u toegang tot het hulpmiddel hebt, zult u opstellingsverbindingen aan uw gegevens en de stroom van gegevens tussen Adobe Campaign en de Dynamica 365 van Microsoft vormen.

>[!NOTE]
>
>U moet contact opnemen met uw Adobe-vertegenwoordiger en de Adobe Campaign Standard org- en instantienamen opgeven. Er wordt een ticket geregistreerd om aan te vragen dat de integratie-app voor uw organisatie is ingeschakeld.

## Een productprofiel toevoegen

In deze sectie leert u hoe u toegang kunt verlenen tot de Adobe Campaign Standard-integratie met Microsoft Dynamics 365-zelfbedieningstoepassing. Gebruikers die toegang hebben tot uw organisatie in Adobe Experience Cloud, hebben geen toegang tot de zelfbedieningsapp voor integratie, tenzij u de onderstaande stappen uitvoert om hun toegang te verlenen.

>[!IMPORTANT]
>
> Deze stappen vereisen **Beheerder** rol in de Experience Cloud voor uw organisatie.


1. Blader naar https://experience.adobe.com/ en meld u aan bij de Adobe Experience Cloud.
1. Open de **Admin Console**.

   ![](assets/d365-to-acs-access-3.png)

1. Klik op **[!UICONTROL Products]** om toegang te krijgen tot uw Experience Cloud-oplossingen.

   ![](assets/d365-to-acs-access-6.png)


   >[!IMPORTANT]
   >
   >De resterende stappen in deze sectie worden uitgevoerd voor elk van uw campagneinstanties (ontwikkelen, tekst, productie).

1. Klik op de eerste instantie die u wilt configureren.

   ![](assets/d365-to-acs-access-6.png)

   De instantiepagina moet er ongeveer als volgt uitzien:

   ![](assets/d365-to-acs-access-8.png)

1. Klik op de knop **[!UICONTROL New Profile]** en voeg een nieuw item met de naam: **Campaign Standard - your-prod-instance-name - D365/ACS Integration**

   * Als dit item in de lijst wordt weergegeven, hoeft u niet verder te gaan. Klik op **Adobe Campaign Standard** in het linkermenu en controleer de andere instanties van de Campagne.

   * Vervang &quot;uw-prod-instantie-naam&quot; door de werkelijke naam voor de instantie.

1. U kunt het **[!UICONTROL Permission Group]** vervolgkeuzemenu met de standaardwaarde verlaten.

1. Als uw ingangen aan het volgende gelijkaardig kijken, dan klik **[!UICONTROL Done]** knoop.

   ![](assets/d365-to-acs-access-14.png)

   Het nieuwe productprofiel is toegevoegd.

   ![](assets/d365-to-acs-access-15.png)

## Toegang verlenen aan gebruikers {#add-users-to-profile}

Selecteer op de pagina **[!UICONTROL Products]** de instantie Campagne en volg de onderstaande stappen:

1. Klik op het nieuwe profiel dat u eerder hebt gemaakt:  **Campaign Standard - your-prod-instance-name - D365/ACS Integration**

   ![](assets/d365-to-acs-access-15.png)

1. Klik op het tabblad **[!UICONTROL Developers]**.

   ![](assets/d365-to-acs-access-18.png)

1. Klik op de knop **[!UICONTROL Add Developer]**

1. Voer de naam of het e-mailadres in van de gebruiker die u wilt toevoegen.  Selecteer het resultaat dat overeenkomt met de gebruiker.

   Als dit de eerste keer is dat de gebruiker aan de organisatie wordt toegevoegd, voert u details in.

1. Klik **[!UICONTROL Save]** om te bevestigen.
