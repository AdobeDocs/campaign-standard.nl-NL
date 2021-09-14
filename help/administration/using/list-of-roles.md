---
title: Lijst met rollen
description: Ontdek de lijst met rollen die u aan uw gebruikers kunt toewijzen.
audience: administration
content-type: reference
topic-tags: users-and-security
context-tags: role,overview;role,main
feature: Access Management
role: Admin
level: Experienced
exl-id: 00714c80-bdaf-4241-bf2f-51498ca1dbef
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 84%

---

# Lijst met rollen{#list-of-roles}

Standaard biedt Adobe Campaign een aantal rollen waarmee u unitaire machtigingen kunt definiëren die zijn toegewezen aan gebruikers en gebruikersgroepen.

In combinatie met bedrijfseenheden geven rollen gebruikers een gefilterde weergave van de interface en bepalen deze de toegang van gebruikers tot de verschillende functies.

Rollen kunnen worden beheerd vanuit het menu **[!UICONTROL Administration > Users & Security > Roles]**.

Standaardrechten zijn:

* **[!UICONTROL Administration]**: Algemene beheerrechten.

   >[!NOTE]
   >
   >Als u met de Triggers van de Experience Cloud moet werken, zult u **[!UICONTROL Administration]** recht nodig hebben om tot het menu van de Triggers van de Experience Cloud toegang te hebben. Raadpleeg deze [pagina](../../integrating/using/about-adobe-experience-cloud-triggers.md) voor meer informatie over Experience Cloud-triggers.

* **[!UICONTROL Datamodel]**: Recht om publicaties uit te voeren en aangepaste bronnen te maken.
* **[!UICONTROL Generic import]**: Recht om een generieke import op data uit te voeren. Dit werkt alleen als u de rol **[!UICONTROL Generic import]** aan de rol **[!UICONTROL Workflow]** koppelt.
* **[!UICONTROL Prepare deliveries]**: Recht om leveringen te maken, te wijzigen, voor te bereiden en te verwijderen. Gebruikers met deze rol kunnen de levering voorbereiden, maar niet verzenden.
* **[!UICONTROL Start deliveries]**: Recht om leveringen te maken, te wijzigen, voor te bereiden, te verzenden en te verwijderen.
* **[!UICONTROL Workflow]**: Recht om de uitvoering van workflows te beheren (starten, stoppen, pauzeren, enz.). Gebruikers met deze rol kunnen zelfs in een workflow geen levering verzenden.

Raadpleeg voor meer informatie de tabel [Rollen en machtigingen](/help/administration/using/assets/acs_rights.pdf), waarin de functies worden beschreven die beschikbaar zijn in de interface, afhankelijk van de geselecteerde machtigingen.

[![image](assets/user_management_3.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=en)

**Verwante onderwerpen:**

* [Informatie over toegangsbeheer](../../administration/using/about-access-management.md)
* [Groepen en gebruikers beheren](../../administration/using/managing-groups-and-users.md)
