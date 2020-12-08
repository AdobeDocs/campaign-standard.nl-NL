---
solution: Campaign Standard
product: campaign
title: Lijst met rollen
description: Ontdek de lijst met rollen die u aan uw gebruikers kunt toewijzen.
audience: administration
content-type: reference
topic-tags: users-and-security
context-tags: role,overview;role,main
translation-type: tm+mt
source-git-commit: 2c15273c7614204300f615e9060f29c93a4f8481
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 83%

---


# Lijst met rollen{#list-of-roles}

Standaard biedt Adobe Campaign een aantal rollen waarmee u unitaire machtigingen kunt definiëren die zijn toegewezen aan gebruikers en gebruikersgroepen.

In combinatie met bedrijfseenheden geven rollen gebruikers een gefilterde weergave van de interface en bepalen deze de toegang van gebruikers tot de verschillende functies.

Raadpleeg voor meer informatie de tabel [Rollen en machtigingen](/help/administration/using/assets/acs_rights.pdf), waarin de functies worden beschreven die beschikbaar zijn in de interface, afhankelijk van de geselecteerde machtigingen.

[![image](assets/user_management_3.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=en)

Rollen kunnen worden beheerd vanuit het menu **[!UICONTROL Administration > Users & Security > Roles]**.

Standaardrechten zijn:

* **[!UICONTROL Administration]**: Algemene beheerrechten.

   >[!NOTE]
   >
   >Als u Triggers moet maken, hebt u **[!UICONTROL Administration]** nodig om toegang te krijgen tot het menu Triggers. Raadpleeg deze [pagina](../../integrating/using/about-adobe-experience-cloud-triggers.md) voor meer informatie over Triggers.

* **[!UICONTROL Datamodel]**: Recht om publicaties uit te voeren en aangepaste bronnen te maken.
* **[!UICONTROL Generic import]**: Recht om een generieke import op data uit te voeren. Dit werkt alleen als u de rol **[!UICONTROL Generic import]** aan de rol **[!UICONTROL Workflow]** koppelt.
* **[!UICONTROL Prepare deliveries]**: Recht om leveringen te maken, te wijzigen, voor te bereiden en te verwijderen. Gebruikers met deze rol kunnen de levering voorbereiden, maar niet verzenden.
* **[!UICONTROL Start deliveries]**: Recht om leveringen te maken, te wijzigen, voor te bereiden, te verzenden en te verwijderen.
* **[!UICONTROL Workflow]**: Recht om de uitvoering van workflows te beheren (starten, stoppen, pauzeren, enz.). Gebruikers met deze rol kunnen zelfs in een workflow geen levering verzenden.

**Verwante onderwerpen:**

* [Toegangsbeheer](../../administration/using/about-access-management.md)
* [Groepen en gebruikers beheren](../../administration/using/managing-groups-and-users.md)
