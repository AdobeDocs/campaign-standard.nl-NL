---
solution: Campaign Standard
product: campaign
title: De juiste doelgroep definiëren
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: '"Wanneer u uw inhoud klaar hebt, leer hoe u zorgvuldig bepaalt wie uw bericht zal ontvangen."'
feature: Deliverability
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 11%

---


# De juiste doelgroep definiëren {#define-the-right-audience}

Gerichte populatie is van essentieel belang: uw lijsten zorgvuldig samen te stellen, uw e-mailberichten te testen op populaire e-mailclients en mobiele apparaten en ervoor te zorgen dat uw e-maillijsten up-to-date zijn (zonder onbekende of verouderde adressen). U kunt ook proefdrukken verzenden waarmee u een volledige validatiecyclus kunt instellen.

Meer informatie over doelpopulaties [in deze sectie](../../audiences/using/selecting-an-audience-in-a-message.md)

## Doelgroep {#target-the-right-audience}

Wanneer u uw inhoud klaar hebt, moet u zorgvuldig bepalen wie uw bericht zal ontvangen.

Om uw levering succesvol te maken, wilt u de meest relevante gepersonaliseerde inhoud naar de juiste ontvangers verzenden. Met Adobe Campaign kunt u het meest nauwkeurige doel maken: u kunt ontvangers selecteren op basis van hun leeftijd, lokalisatie, wat ze hebben gekocht, als ze op een koppeling hebben geklikt in een vorige levering, enzovoort. Met Adobe Campaign kunt u ook testprofielen, controlegroepen en zaadadressen definiëren om te controleren of het doel correct is.

## Doeltoewijzingen {#target-mappings}

Standaard richten leveringssjablonen **Profielen**. Adobe Campaign biedt andere doeltoewijzingen voor uw leveringen die u op basis van uw behoeften kunt wijzigen.

Deze toewijzingen worden [in deze sectie](../../automating/using/query.md#targeting-dimensions-and-resources) voorgesteld.

U kunt ook een aangepaste doeltoewijzing maken en gebruiken. Raadpleeg [deze sectie](../../administration/using/target-mappings-in-campaign.md) voor meer informatie.

## Externe gegevens {#external-data}

U kunt leveren aan ontvangers die in een extern dossier eerder dan opgeslagen in het gegevensbestand worden opgeslagen. Hiertoe ontwerpt u een workflow om gegevens uit een bestand in uw database te laden en een bijbehorend publiek te maken.  Lees meer [in dit gebruiksgeval](../../automating/using/use-case-calling-workflow.md). Zie ook [Een workflow aanroepen met parameters](../../automating/using/calling-a-workflow-with-external-parameters.md).

## Verzend naar uw abonnees {#send-to-subscribers}

Om berichten naar de abonnees van een nieuwsbrief te verzenden, kunt u de abonnees aan de overeenkomstige informatiedienst direct richten. Meer informatie [in deze sectie](../../audiences/using/about-subscriptions.md).

**Tip**  - U kunt een publiek van de Lijst tot stand brengen dat de abonnees aan uw nieuwsbrief richt gebruikend een werkschema. U kunt dit publiek vervolgens in een levering selecteren. Voor meer op dit, zie [Creërend lijstpubliek](../../audiences/using/creating-audiences.md#creating-list-audiences).

## Proefdrukken, testprofielen en controlegroepen {#proofs-test-control-groups}

Om uw levering te testen, gebruik proef alvorens naar het belangrijkste doel te verzenden.
Zorg ervoor dat u de juiste ontvangers voor het bewijs selecteert, omdat deze het formulier en de inhoud van het bericht valideren. De stappen voor het verzenden van proefdrukken worden [in deze sectie](../../sending/using/sending-proofs.md) voorgesteld.

Meer informatie over testprofielen [in deze sectie](../../audiences/using/managing-test-profiles.md).

U kunt [Controlegroepen](../../sending/using/control-group.md) gebruiken om het effect van uw campagnes te meten door een deel van hun publiek uit te sluiten. Vervolgens kunt u de gedragingen van de doelgroep die het bericht heeft ontvangen, vergelijken met de gedragingen van contactpersonen die niet zijn getarget. Op basis van de verzendlogboeken kunt u in toekomstige campagnes ook een controlegroep targeten.

## Gedupliceerde adressen {#deduplicate-addresses}

Het is belangrijk om dubbele e-mailadressen te vermijden, omdat dit van invloed kan zijn op uw doel:

* Hetzelfde bericht kan meerdere keren worden verzonden wanneer een doel wordt gesplitst.

* Als een ontvanger zich afmeldt na het ontvangen van een bericht, zal hun dubbele profiel nog toekomstige berichten ontvangen.

Deduplicating adressen beschermt uw verzendende reputatie en verzekert goed quarantainebeheer.

Lees meer [in dit gebruiksgeval](../../automating/using/deduplicating-data-imported-file.md).
