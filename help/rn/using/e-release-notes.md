---
title: Vroege aanvullende informatie
description: Vroege aanvullende informatie
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 46c5454ad712910c88bfda7c067fda0337b043d9
workflow-type: ht
source-wordcount: '235'
ht-degree: 100%

---


# Vroege aanvullende informatie {#e-new-release}

Op deze pagina worden nieuwe verbeteringen en oplossingen beschreven die in de volgende release van Campaign Standard zijn opgenomen.

>[!CAUTION]
>
> Deze content kan zonder voorafgaande kennisgeving worden gewijzigd tot de upgradedatum van de werkgebiedomgevingen. Meer informatie vindt u op de [releaseplanningspagina](../../rn/using/release-planning.md).

## Release 23.2 - Release 2023 herfst/winter {#fall-23}

>[!AVAILABILITY]
>
>Deze release is maar voor een aantal organisaties beschikbaar (beperkte beschikbaarheid). Neem voor meer informatie contact op met uw Adobe-vertegenwoordiger.

### Verbeteringen {#e-rn-improvements}

* **Integratie met Adobe Experience Manager**. Tijdens het maken van een gepersonaliseerde leveringssjabloon voor transactieberichten in Adobe Experience Manager kunt u nu de in Campaign Standard gedefinieerde personalisatievelden selecteren en gebruiken in een vervolgkeuzelijst.

* **Vervaldatum cookies** - De standaard vervaldatum voor cookies is nu ingesteld op 6 maanden, overeenkomstig de aanbevelingen van het Franse Bureau voor gegevensbescherming (CNIL).

* **Verbetering van profielzoekopdracht** - Het zoeken naar profielen is geoptimaliseerd, zodat de time-outscenario&#39;s voor zoekacties kunnen worden verminderd

* **Lokalisatie** - De vertalingen van de term &#39;doelgroep&#39; voor een groep profielen die bedoeld zijn om een bericht te ontvangen, zijn geharmoniseerd voor alle Digital Experience-producten voor de volgende talen:

   * Duits: Zielgruppe
   * Braziliaans Portugees: público-alvo
   * Spaans: público destinatario

  Deze veranderingen zullen geleidelijk met de volgende releases van de gebruikersinterface en documentatie worden uitgevoerd.

### Andere wijzigingen {#e-rn-other-changes}

* Transactional Messaging ondersteunt nu het gebruik van meerdere, door komma&#39;s gescheiden affiniteiten.

### Oplossingen {#e-rn-fixes}

* Er is een regressie verholpen die prestatieproblemen kon veroorzaken bij het gebruik van grote workflows. (CAMP-53369)
* Er is een probleem opgelost waarbij de e-mailkoppeling in een workflowwaarschuwing of -melding van workfing werd verhinderd. (CAMP-51874)
