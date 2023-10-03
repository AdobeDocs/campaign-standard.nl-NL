---
title: Laatste release
description: Op deze pagina vindt u content van de nieuwste release van Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: c1271bc0128c583e9b39ef98a422487e1df20fce
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 59%

---


# Laatste release{#latest-release}

![Configuratiescherm](assets/do-not-localize/cp-icon.png) **Nieuwe release van het configuratiescherm**. [Meer informatie](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=nl){target="_blank"}.



## Release 23.2 - Release 2023 herfst/winter {#fall-23}

>[!AVAILABILITY]
>
>Deze release is alleen beschikbaar voor een aantal organisaties (beperkte beschikbaarheid). Neem voor meer informatie contact op met uw Adobe.

### Verbeteringen {#fall-23-rn-improvements}

* **Integratie met Adobe Experience Manager**. Tijdens het maken van een gepersonaliseerde leveringssjabloon voor transactieberichten in Adobe Experience Manager kunt u nu de in Campaign Standard gedefinieerde verpersoonlijkingsvelden selecteren en gebruiken in een vervolgkeuzelijst. [Meer informatie](../../integrating/using/creating-email-experience-manager.md)

* **Vervaldatum cookie** - De standaardvervaldatum voor cookies is nu ingesteld op 6 maanden, overeenkomstig de aanbevelingen van het Franse Bureau voor gegevensbescherming (CNIL).

* **Verbetering van profielzoekopdracht** - Het zoeken naar profielen is geoptimaliseerd, zodat de time-outscenario&#39;s voor zoekacties kunnen worden verminderd

* **Lokalisatie** - De vertalingen van de term &quot;publiek&quot; voor een groep profielen die bedoeld zijn om een bericht te ontvangen, zijn geharmoniseerd voor alle Digital Experience-producten voor de volgende talen:

   * Duits: Zielgruppe
   * Portugees in Brazilië: público-alvo
   * Spaans: público destinatario

  Deze veranderingen zullen geleidelijk aan met volgende UI en documentatiereleases worden uitgevoerd.


### Andere wijzigingen {#fall-23-rn-other-changes}

* Het Transactionele Overseinen steunt nu het gebruik van veelvoudige komma-gescheiden affiniteiten.

### Oplossingen {#fall-23-rn-fixes}

* Oplossing voor een regressie die prestatieproblemen kan veroorzaken bij het gebruik van grote workflows. (CAMP-53369)
* Probleem verholpen waardoor de e-mailkoppeling in een workflowwaarschuwing of -melding niet werkte. (CAMP-51874)

## Release 23.1 - 2023 lente-/zomerrelease {#apr-23}

### Verbeteringen {#e-rn-improvements}

* De Push-berichtenservice is gemoderniseerd om de ondersteuning te verbeteren. (CAMP-47959)
* De sms-berichtenservice is verbeterd om een verbeterde stabiliteit te bieden. (CAMP-52217)
* Adobe heeft veel toegankelijkheidsoplossingen gemaakt om het algemene gebruiksgemak van de applicatie te verbeteren. Hier zijn enkele voorbeelden van toegankelijkheidsverbeteringen:
   * De toegankelijkheid van het toetsenbord van de interface is in veel schermen geoptimaliseerd.
   * De applicatie is verbeterd voor de gebruikers van touchscreens.
   * De kleur van verschillende items in de interface is gewijzigd om de zichtbaarheid te verbeteren.

### Andere wijzigingen {#e-rn-changes}

* De out-of-the-box **Workflow voor het maken van rapportageverrijking** is toegevoegd. Na het importeren van een targettoewijzing van de ene instantie naar de andere voert u gewoon de workflow uit om de overeenkomstige rapportageverrijkingsitems te importeren. (CAMP-52452)

### Problemen opgelost{#e-rn-patches}

* Er is een probleem opgelost dat kon leiden tot een time-outfout bij het weergeven van het rapport **Hot click**. (CAMP-51582)
* Er is een probleem opgelost waardoor u de integratie met de **Locaties**-service niet kon gebruiken. (CAMP-51923)
* Er is een probleem opgelost waardoor de workflowplanner mogelijk niet correct werkte. (CAMP-52003)
* Er is een probleem opgelost waarbij de uitsplitsingsdetails niet werden weergegeven bij het bekijken van de PDF-versie van een aangepast dynamisch rapport met een grote hoeveelheid gegevens. (CAMP-52178)
* Er is een probleem opgelost waardoor soms een fout werd weergegeven bij het openen van rapporten. (CAMP-52500)
* Er is een probleem opgelost waarbij de parameter **Limit MTA instances for this account** SMS-connector ten onrechte werd toegepast op alle kanalen in plaats van alleen op sms. (CAMP-52640)
