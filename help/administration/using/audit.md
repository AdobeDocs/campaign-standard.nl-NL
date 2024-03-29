---
title: Audit trail
description: Handelingen en gebeurtenissen bewaken met het audittrail voor campagne
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: bda6f8d5-3bcf-498c-a7c4-d3c2c79b9510
source-git-commit: 64da7ac09e1b0fbf13ba1e563b6dc7be995b1640
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 3%

---

# Audit trail {#audit}

De **[!UICONTROL Audit trail]** geeft u toegang tot de volledige geschiedenis van veranderingen die binnen uw instantie worden aangebracht.

**[!UICONTROL Audit trail]** legt in real-time een uitgebreide lijst vast met acties en gebeurtenissen die plaatsvinden in uw Adobe Campaign Standard-instantie. Het omvat een zelf-servermanier om tot een geschiedenis van gegevens toegang te hebben helpen vragen zoals beantwoorden: wat met uw werkschema&#39;s, douanemiddelen en opties gebeurde, die hen het laatst bijgewerkt of wat uw gebruikers in de instantie deden.

![](assets/audit-trail.png)

**[!UICONTROL Audit trail]** bestaat uit drie onderdelen:

* **Actief bronnenaudittrail**: controleer de activiteit en laatste wijziging die aan douanemiddelen wordt gedaan.

  Voor meer informatie over **[!UICONTROL Custom resources]**, verwijzen naar [page](../../developing/using/key-steps-to-add-a-resource.md).

* **Workflowaudittrail**: controleer de activiteit en de laatste wijziging die aan werkschema&#39;s wordt uitgevoerd, en daarnaast, de staat van uw werkschema&#39;s zoals:

   * Gemaakt
   * gewijzigd
   * Verwijderd
   * Start van workflow
   * Werkstroom pauzeren
   * Werkstroomstop
   * Workflow opnieuw starten
   * Workflowopschoning
   * Workflow simuleren
   * Workflowwakeup
   * Werkstroom direct stoppen
   * Workflow opnieuw starten met dezelfde gebruiker
   * Opnieuw starten van werkstroom Onbekend, opdracht

  Voor meer informatie over **[!UICONTROL Workflows]**, verwijzen naar [page](../../automating/using/get-started-workflows.md).

* **Optie-audittrail**: controleer de activiteit en laatste wijziging aan opties.

  Voor meer informatie over **[!UICONTROL Options]**, verwijzen naar [page](../../administration/using/about-campaign-standard-settings.md).

De retentieperiode bedraagt standaard 30 dagen.

## Audittrail openen {#audit-access}

Ga als volgt te werk om het audittrail van uw instantie te openen:

1. Selecteer in Adobe Campaign Standard in het menu Geavanceerd de optie **[!UICONTROL Administration]** > **[!UICONTROL Audit trail]**.

   ![](assets/audit-trail.png)

1. De **[!UICONTROL Audit trail]** wordt geopend met de lijst van uw entiteiten. Adobe Campaign Standard controleert het maken, bewerken en verwijderen van acties voor workflows, opties en aangepaste bronnen.

   Van de **[!UICONTROL Search]** kunt u uw entiteit filteren op:

   * **[!UICONTROL Start date]**
   * **[!UICONTROL End date]**
   * **[!UICONTROL Type]**: Type van entiteit tussen allen, Werkschema, het Middel van de Douane en Optie.
   * **[!UICONTROL Entity name]**: ID van uw workflow, optie of aangepaste bron

   ![](assets/audit-trail_2.png)

1. Selecteer een van de entiteiten voor meer informatie over de laatste wijzigingen.

1. Het venster van de Controleorganisatie geeft u meer gedetailleerde informatie over de gekozen entiteit zoals:

   * **[!UICONTROL Entity]**: ID van uw workflow, optie of aangepaste bron.
   * **[!UICONTROL Action]**: Laatste actie uitgevoerd op deze entiteit.
   * **[!UICONTROL Changed by]**: Gebruikersnaam van de laatste persoon die deze entiteit als laatste heeft gewijzigd.
   * **[!UICONTROL Changed date]**: Datum van de laatste actie die op deze entiteit is uitgevoerd.
   * **[!UICONTROL Content]**: Codeblok dat u meer informatie geeft over wat precies in uw entiteit is gewijzigd.

   In dit voorbeeld, kunnen wij zien dat het werkschema WKF110 op 26 augustus door de Bedrijfs beheerder van deze instantie is begonnen.

   ![](assets/audit-trail_3.png)

## Audittrail in-/uitschakelen {#enable-disable-audit}

>[!NOTE]
>
> Alleen functionele beheerders kunnen het audittrail in- of uitschakelen. Raadpleeg [deze pagina](../../administration/using/users-management.md#functional-administrators) voor meer informatie.

Audittrail kan gemakkelijk worden geactiveerd of gedeactiveerd voor een specifieke activiteit.

Dit doet u als volgt:

1. Selecteer in Adobe Campaign Standard in het menu Geavanceerd de optie **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.

   ![](assets/audit-trail_4.png)

1. Selecteer een van de volgende opties, afhankelijk van de entiteit die u wilt uitschakelen:

   * **[!UICONTROL XtkAudit_Workflows]** optie voor het beheren van het audittrail voor Workflows.
   * **[!UICONTROL XtkAudit_Option]** optie om het spoor van de Controle voor Opties te beheren.
   * **[!UICONTROL XtkAudit_CusResource]** optie voor het beheren van het audittrail voor de middelen van de Douane.
   * **[!UICONTROL XtkAudit_Enable_All]** optie om het audittrail voor elke entiteit te beheren.

     >[!NOTE]
     >
     >Als de **[!UICONTROL XtkAudit_Enable_All]** optie is ingesteld op 0, de **[!UICONTROL Audit trail]** Deze functie wordt volledig uitgeschakeld, ongeacht andere individuele optiewaarden.

   ![](assets/audit-trail_5.png)

1. Van uw **[!UICONTROL Options]** pagina instellen **[!UICONTROL Value (integer)]** tot 0 als u het **[!UICONTROL Audit trail]** of 1 om deze in te schakelen.

   ![](assets/audit-trail_6.png)

1. Klik op **[!UICONTROL Save]**.
