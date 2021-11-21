---
title: Krijg Toegang tot de Integratie van Adobe Campaign Standard met Dynamics 365 Self-Service App
description: Adobe Campaign Standard-integratie met Dynamics 365 Self-Service App
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 44b59f56-99be-41ae-af8d-76272bb94d18
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 0%

---

# Toegang tot de Adobe Campaign Standard-integratie met Microsoft Dynamics 365 Self-Service App

Voor deze configuratie moet u met een Experience Cloud (EC)-beheerder voor uw organisatie werken. Dit zijn de aanvankelijke stappen die worden vereist om u toegang tot de interface van de zelfbedieningstoepassing te geven. Zodra u toegang tot het hulpmiddel hebt, zult u opstellingsverbindingen aan uw gegevens en de stroom van gegevens tussen Adobe Campaign en de Dynamica 365 van Microsoft vormen.

>[!NOTE]
>
>U moet contact opnemen met uw Adobe-vertegenwoordiger en de Adobe Campaign Standard org- en instantienamen opgeven. Er wordt een ticket geregistreerd om aan te vragen dat de integratie-app voor uw organisatie is ingeschakeld.

## Een productprofiel toevoegen

In deze sectie leert u hoe u toegang kunt verlenen tot de Adobe Campaign Standard-integratie met de zelfbedieningsapp Microsoft Dynamics 365. Gebruikers die toegang hebben tot uw organisatie in Adobe Experience Cloud, hebben geen toegang tot de zelfbedieningsapp voor integratie, tenzij u de onderstaande stappen uitvoert om hun toegang te verlenen.

>[!IMPORTANT]
>
> Deze stappen vereisen **Beheerder** rol in de Experience Cloud voor uw organisatie.

1. Blader naar https://experience.adobe.com/ en meld u aan bij de Adobe Experience Cloud.
1. Toegang krijgen tot **Admin Console**.

   ![](assets/do-not-localize/d365-to-acs-access-3.png)

1. Klikken op **[!UICONTROL Products]** voor toegang tot uw Experience Cloud-oplossingen.

   ![](assets/do-not-localize/d365-to-acs-access-6.png)


   >[!IMPORTANT]
   >
   >De resterende stappen in deze sectie worden uitgevoerd voor elk van uw campagneinstanties (ontwikkelen, tekst, productie).

1. Klik op de eerste instantie die u wilt configureren.

   ![](assets/do-not-localize/d365-to-acs-access-6.png)

   De instantiepagina moet er ongeveer als volgt uitzien:

   ![](assets/do-not-localize/d365-to-acs-access-8.png)

1. Klik op de knop **[!UICONTROL New Profile]** en voeg een nieuwe ingang toe genoemd: **Campaign Standard - uw-prod-instantie-naam - D365/ACS-integratie**

   * Als dit item in de lijst wordt weergegeven, hoeft u niet verder te gaan. Klikken op **Adobe Campaign Standard** in het linkermenu en controleer de andere instanties van de Campagne.

   * Vervang &quot;uw-prod-instantie-naam&quot; door de werkelijke naam voor de instantie.

1. U kunt de **[!UICONTROL Permission Group]** vervolgkeuzelijst met de standaardwaarde.

1. Als de items er als volgt uitzien, klikt u op de knop **[!UICONTROL Done]** knop.

   ![](assets/do-not-localize/d365-to-acs-access-14.png)

   Het nieuwe productprofiel is toegevoegd.

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

## Toegang verlenen aan gebruikers {#add-users-to-profile}

Van de **[!UICONTROL Products]**  pagina, selecteert u uw Campagne-instantie en volgt u de onderstaande stappen:

1. Klik op het nieuwe profiel dat u eerder hebt gemaakt:  **Campaign Standard - uw-prod-instantie-naam - D365/ACS-integratie**

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

1. Klik op de knop **[!UICONTROL Developers]** tab.

   ![](assets/do-not-localize/d365-to-acs-access-18.png)

1. Klik op de knop **[!UICONTROL Add Developer]** knop

1. Voer de naam of het e-mailadres in van de gebruiker die u wilt toevoegen.  Selecteer het resultaat dat overeenkomt met de gebruiker.

   Als dit de eerste keer is dat de gebruiker aan de organisatie wordt toegevoegd, voert u details in.

1. Klikken **[!UICONTROL Save]** ter bevestiging.
