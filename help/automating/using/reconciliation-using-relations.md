---
title: Afstemming van gegevens met behulp van relaties
description: In het volgende voorbeeld ziet u een workflow die de database bijwerkt met de aankoopgegevens in een bestand.
page-status-flag: never-activated
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: reconciliation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---


# Afstemming van gegevens met behulp van relaties {#reconciliation-relations}

In het volgende voorbeeld ziet u een workflow die de database bijwerkt met de aankoopgegevens in een bestand. De aankoopgegevens bevatten gegevens die verwijzen naar elementen van andere dimensies, zoals de e-mails van de klant en productcodes.

>[!NOTE]
>
>De **Transacties** en de middelen van **Producten** die in dit voorbeeld worden gebruikt bestaan niet door gebrek in het gegevensbestand van Adobe Campaign. Ze zijn daarom vooraf gemaakt met behulp van de functie [Aangepaste bronnen](../../developing/using/data-model-concepts.md) . De profielen die overeenkomen met de e-mailadressen in het geïmporteerde bestand en de producten zijn vooraf in de database geladen.

De workflow bestaat uit de volgende activiteiten:

![](assets/reconciliation_example1.png)

* Een [activiteit van het Dossier](../../automating/using/load-file.md) van de Lading, die de gegevens van het in te voeren dossier laadt en ontdekt. Het geïmporteerde bestand bevat de volgende gegevens:

   * Transactiedatum
   * E-mailadres client
   * Code van het aangekochte product

   ```
   date;client;product
   2015-05-19 09:00:00;mail1@email.com;ZZ1
   2015-05-19 09:01:00;mail2@email.com;ZZ2
   2015-05-19 09:01:01;mail3@email.com;ZZ2
   2015-05-19 09:01:02;mail4@email.com;ZZ2
   2015-05-19 09:02:00;mail5@email.com;ZZ3
   2015-05-19 09:03:00;mail6@email.com;ZZ4
   2015-05-19 09:04:00;mail7@email.com;ZZ5
   2015-05-19 09:05:00;mail8@email.com;ZZ7
   2015-05-19 09:06:00;mail9@email.com;ZZ6
   ```

* Een [afstemmingsactiviteit](../../automating/using/reconciliation.md) om het kopen van gegevens aan gegevensbestandprofielen evenals producten te binden. Daarom moet een verband worden gedefinieerd tussen de bestandsgegevens en de profielentabel en de producttabel. Deze configuratie wordt uitgevoerd op het **[!UICONTROL Relations]** tabblad van de activiteit:

   * Relatie met de **profielen**: De **clientkolom** van het bestand is gekoppeld aan het **e-mailveld** van de **profieldimensie** .
   * Verhouding tot de **producten**: De **productkolom** van het bestand is gekoppeld aan het veld **productCode** van de **profieldimensie** .
   Kolommen worden toegevoegd aan de binnenkomende gegevens om te verwijzen naar de externe sleutels van de gekoppelde afmetingen.

   ![](assets/reconciliation_example3.png)

* Met een [updategegevensactiviteit](../../automating/using/update-data.md) kunt u de databasevelden definiëren die u wilt bijwerken met behulp van de geïmporteerde gegevens. Aangezien de gegevens reeds als deel van de dimensie van **Transacties** in de vorige activiteit werden geïdentificeerd, kunt u de **[!UICONTROL Directly using the targeting dimension]** identificatieoptie gebruiken.

   Als u de optie gebruikt waarmee automatisch velden worden gedetecteerd die moeten worden bijgewerkt, worden de koppelingen die in de vorige activiteit zijn geconfigureerd (naar profielen en producten) toegevoegd aan de lijst met **[!UICONTROL Fields to update]**. U moet er ook voor zorgen dat het veld dat overeenkomt met de transactiedatum correct wordt toegevoegd aan deze lijst.

   ![](assets/reconciliation_example5.png)

   ![](assets/reconciliation_example4.png)
