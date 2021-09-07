---
solution: Campaign Standard
product: campaign
title: Audit Trail
description: Handelingen en gebeurtenissen bewaken met het audittrail voor campagne
audience: administration
content-type: reference
topic-tags: users-and-security
feature: Access Management
role: Admin
level: Experienced
exl-id: 4a4c14da-d842-4f65-821a-ca9e73a94adc
source-git-commit: a12b87d93e3badbf31f88c9f0f48b981e206d8b9
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 1%

---

# Audit trail {#audit}

Met **[!UICONTROL Audit trail]** hebt u toegang tot de volledige geschiedenis van wijzigingen die in uw instantie zijn aangebracht.

**[!UICONTROL Audit trail]** legt in real-time een uitgebreide lijst vast met acties en gebeurtenissen die plaatsvinden in uw Adobe Campaign Standard-instantie. Het omvat een zelfbediende manier om tot een geschiedenis van gegevens toegang te hebben helpen vragen zoals beantwoorden: wat er is gebeurd met uw workflows, aangepaste bronnen en opties, die deze voor het laatst hebben bijgewerkt of wat uw gebruikers in het geval hebben gedaan.

![](assets/audit-trail.png)

**[!UICONTROL Audit trail]** bestaat uit drie onderdelen:

* **Actief bronnenaudittrail**: controleer de activiteit en laatste wijziging aan douanemiddelen wordt gedaan die.

   Raadpleeg deze [pagina](../../developing/using/key-steps-to-add-a-resource.md) voor meer informatie over **[!UICONTROL Custom resources]**.

* **Workflowaudittrail**: Controleer de activiteit en laatste wijziging aan werkschema&#39;s, en daarnaast, de staat van uw werkschema&#39;s zoals:

   * Gemaakt
   * Gewijzigd
   * Verwijderd
   * Start van workflow
   * Werkstroom pauzeren
   * Workflow stoppen
   * Workflow opnieuw starten
   * Workflowopschoning
   * Workflow simuleren
   * Workflowwakeup
   * Werkstroom direct stoppen
   * Workflow opnieuw starten met dezelfde gebruiker
   * Opnieuw starten van werkstroom Onbekende opdracht

   Raadpleeg deze [pagina](../../automating/using/get-started-workflows.md) voor meer informatie over **[!UICONTROL Workflows]**.

* **Optie-audittrail**: Controleer de activiteit en laatste wijziging aan opties.

   Raadpleeg deze [pagina](../../administration/using/about-campaign-standard-settings.md) voor meer informatie over **[!UICONTROL Options]**.

De retentieperiode bedraagt standaard 30 dagen.

## Audittrail openen {#audit-access}

Ga als volgt te werk om het audittrail van uw instantie te openen:

1. Selecteer in Adobe Campaign Standard **[!UICONTROL Administration]** > **[!UICONTROL Audit trail]** in het geavanceerde menu.

   ![](assets/audit-trail.png)

1. Het venster **[!UICONTROL Audit trail]** wordt geopend met de lijst van uw entiteiten. Adobe Campaign Standard controleert het maken, bewerken en verwijderen van acties voor workflows, opties en aangepaste bronnen.

   Vanuit het menu **[!UICONTROL Search]** kunt u de entiteit filteren op:

   * **[!UICONTROL Start date]**
   * **[!UICONTROL End date]**
   * **[!UICONTROL Type]**: Het type van de entiteit tussen allen, Werkschema, het Middel van de Douane en Optie.
   * **[!UICONTROL Entity name]**: ID van uw workflow, optie of aangepaste bron

   ![](assets/audit-trail_2.png)

1. Selecteer een van de entiteiten voor meer informatie over de laatste wijzigingen.

1. Het venster van de Controleorganisatie geeft u meer gedetailleerde informatie over de gekozen entiteit zoals:

   * **[!UICONTROL Entity]**: Id van uw workflow, optie of aangepaste bron.
   * **[!UICONTROL Action]**: Laatste actie uitgevoerd op deze entiteit.
   * **[!UICONTROL Changed by]**: Gebruikersnaam van de laatste persoon die deze entiteit als laatste heeft gewijzigd.
   * **[!UICONTROL Changed date]**: Datum van de laatste actie die op deze entiteit is uitgevoerd.
   * **[!UICONTROL Content]**: Codeblok dat u meer informatie geeft over wat precies in uw entiteit is gewijzigd.

   In dit voorbeeld, kunnen wij zien dat het werkschema WKF110 op 26 augustus door de Bedrijfs beheerder van deze instantie is begonnen.

   ![](assets/audit-trail_3.png)

## Audittrail in-/uitschakelen {#enable-disable-audit}

Audittrail kan gemakkelijk worden geactiveerd of gedeactiveerd voor een specifieke activiteit.

Dit doet u als volgt:

1. Selecteer in Adobe Campaign Standard **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** in het geavanceerde menu.

   ![](assets/audit-trail_4.png)

1. Selecteer een van de volgende opties, afhankelijk van de entiteit die u wilt uitschakelen:

   * **[!UICONTROL XtkAudit_Workflows]** optie om het audittrail voor Workflows te beheren.
   * **[!UICONTROL XtkAudit_Option]** optie om het spoor van de Controle voor Opties te beheren.
   * **[!UICONTROL XtkAudit_CusResource]** optie voor het beheren van het audittrail voor de middelen van de Douane.
   * **[!UICONTROL XtkAudit_Enable_All]** optie om het audittrail voor elke entiteit te beheren.

      >[!NOTE]
      >
      >Als de optie **[!UICONTROL XtkAudit_Enable_All]** is ingesteld op 0, wordt de functie **[!UICONTROL Audit trail]** volledig uitgeschakeld, ongeacht andere individuele optiewaarden.
   ![](assets/audit-trail_5.png)

1. Stel **[!UICONTROL Value (integer)]** in op 0 op de pagina **[!UICONTROL Options]** als u **[!UICONTROL Audit trail]** of op 1 wilt uitschakelen om deze in te schakelen.

   ![](assets/audit-trail_6.png)

1. Klik op **[!UICONTROL Save]**.