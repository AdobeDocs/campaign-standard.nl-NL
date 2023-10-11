---
title: Informatie over de Adobe Experience Platform-gegevensconnector
description: Beheer XDM-schema's om uw Campaign Standard gegevens beschikbaar te maken op Adobe Experience Platform.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: f4fcf256-e030-4d7b-b4b7-2448acc2ae1c
hide: true
hidefromtoc: true
source-git-commit: 376f00576ca1d0dfb536b29dbf25d88f7c93b9a8
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 4%

---

# Informatie over de Adobe Experience Platform-gegevensconnector {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector is nu afgekeurd. Verouderde mogelijkheden zijn nog beschikbaar, maar worden niet verder verbeterd en worden niet ondersteund. Meer informatie vindt u [op deze pagina](../../rn/using/deprecated-features.md)

Adobe Experience Platform Data Connector helpt bestaande klanten hun gegevens op Adobe Experience Platform beschikbaar te maken door XTK-gegevens (gegevens die in Campaign worden opgenomen) toe te wijzen aan XDM-gegevens (Experience Data Model) op Adobe Experience Platform.

De connector is **in één richting** en verzendt de gegevens van Adobe Campaign Standard naar Adobe Experience Platform. De gegevens worden nooit van de Adobe Experience Platform naar Adobe Campaign Standard verzonden.

Adobe Experience Platform Data Connector is bedoeld voor **gegevensengineers** die de aangepaste bronnen van Adobe Campaign Standard begrijpen en begrijpen hoe het algemene gegevensschema van de klant zich in Adobe Experience Platform moet bevinden.

In de volgende secties worden de belangrijkste stappen beschreven voor het uitvoeren van een gegevenstoewijzing tussen Campaign Standard en Adobe Experience Platform. Dit begint met de verwezenlijking van een schema XDM en een dataset.

![](assets/do-not-localize/how-to-video.png) [Ontdek deze functie in video](#video)

>[!NOTE]
>Zodra de Verbinding van Gegevens van Adobe Experience Platform wordt gevormd en de gegevens met succes in Adobe Experience Platform worden opgenomen, moet u de dataset toelaten zodat de gegevens in het Profiel van de Klant in real time worden omvat.
>
>Dit kan worden uitgevoerd via de API&#39;s of de Adobe Experience Platform-interface. Raadpleeg de desbetreffende documentatie voor meer informatie:
>
>* [Een gegevensset inschakelen voor realtime klantprofiel](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/datasets/dataset.html)
>* [Een gegevensset configureren voor realtime profiel en identiteitsservice van klanten met behulp van API&#39;s](https://experienceleague.adobe.com/docs/experience-platform/catalog/api/getting-started.html)

## Belangrijkste concepten {#key-concepts}

* Uit de functie voor het toewijzen van vakken is alleen beschikbaar voor velden die standaard in het Campaign Standard worden opgegeven. Voor het opnemen van alle douanegebieden en middelen, moet elke klant hun eigen afbeelding bepalen.

* Adobe Experience Platform Data Connector zorgt ervoor dat profielgegevens regelmatig via het platform worden doorgegeven. &#x200B; De intervalduur is 15 minuten. Deze waarde kan met [Adobe Experience Platform API&#39;s](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html).

* Gegevenstechnicus kan de toewijzing publiceren, wijzigen en pauzeren van Campagne naar Adobe Experience Platform.

* Elke doeldimensie kan worden toegewezen. De aanbeveling is één enkele afbeelding te maken voor alle gebieden in één enkele doeldimensie.

* Alle profielupdates, inclusief kanaalopt-ins/opt-outs, maken deel uit van de batchupdate.

* Wijzigingen in Adobe Campaign Standard- of XDM-schema moeten handmatig opnieuw worden toegewezen. &#x200B;

* Gegevens voor bijhouden van logbestanden en uitzending worden automatisch als Experience Events aan Adobe Experience Platform doorgegeven. Deze inname wordt in real-time gestreamd naar Adobe Experience Platform.

* De Dienst van identiteitskaart van het Experience Cloud (ECID) is een apparatenherkenningsteken dat door gebrek met de Gebeurtenissen van de Ervaring wordt verzonden.

  Het is een unieke en permanente id die aan een bezoeker is toegewezen en die door de Platform Identity Service kan worden gebruikt om dezelfde bezoeker en zijn gegevens in verschillende oplossingen voor Experiencen Cloud te identificeren. Raadpleeg voor meer informatie de [Help bij Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html).

  >[!NOTE]
  >
  >Houd er rekening mee dat als twee of meer profielen hetzelfde apparaat delen, de ECID hetzelfde is voor deze twee profielen in de Unified Identity-service.

## Beperkingen {#limitations}

* De out-of-box overdracht van abonnementsgebeurtenissen wordt niet ondersteund. Om abonnementsgebeurtenissen over te brengen, kunt u overeenkomstige XDM en dataset op Adobe Experience Platform tot stand brengen, dan een afbeelding van douanegegevens voor deze gegevens vormen.

* Met betrekking tot privacyverzoeken (zowel Access- als Delete-handelingen) moeten klanten afzonderlijke verzoeken indienen via de [Privacy Core-service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests): een voor Campagne en een voor Adobe Experience Platform. Zie voor meer informatie [Over privacyverzoeken](https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=nl#getting-started) en [Privacyverzoeken beheren](https://helpx.adobe.com/nl/campaign/kb/acs-privacy.html#ManagingPrivacyRequests) in Campaign.

* Voor elk XDM gebied, moet het DULE etiketteren in Adobe Experience Platform worden gedaan. Dit is de verantwoordelijkheid van de klant om DULE-labels toe te passen.

* Beperkingen op marketingacties worden pas van toepassing nadat DULE-labels zijn toegepast in Adobe Experience Platform. Vóór dat, zijn alle gegevens beschikbaar voor alle soorten marketing acties.

* Om de 15 minuten wordt de batchtaak uitgevoerd en worden de records geïdentificeerd die zijn gewijzigd sinds de laatste batch. Als alle records tegelijk veranderen, kan een knelpunt in de prestaties de opname van alle profielen beheren

## Video over zelfstudie {#video}

Deze video biedt een overzicht over de Adobe Experience Platform Data Connector.

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12&captions=eng)

Er zijn aanvullende video&#39;s beschikbaar over de Adobe Experience Platform Data Connector [hier](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html).
