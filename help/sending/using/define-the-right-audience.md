---
title: Het juiste publiek definiëren
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: true
description: Wanneer u uw inhoud klaar hebt, leer hoe u zorgvuldig bepaalt wie uw bericht zal ontvangen.
feature: Deliverability
role: User
level: Intermediate
exl-id: 1e06fd9d-e850-4856-8f7b-b581dbe157df
source-git-commit: ac925ec5f59f1bb57b56b430fd175a27b08c3bfe
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 0%

---

# Het juiste publiek definiëren {#define-the-right-audience}

De doelgroep is belangrijk: maak uw lijsten zorgvuldig, test uw e-mails op populaire e-mailclients en mobiele apparaten en controleer of uw e-maillijsten up-to-date zijn (zonder onbekende of verouderde adressen). U kunt ook proefdrukken verzenden waarmee u een volledige validatiecyclus kunt instellen.

Leer meer over doelpopulaties [ in deze sectie ](../../audiences/using/selecting-an-audience-in-a-message.md)

## Doelgroep {#target-the-right-audience}

Wanneer u uw inhoud klaar hebt, moet u zorgvuldig bepalen wie uw bericht zal ontvangen.

Om uw levering succesvol te maken, wilt u de meest relevante gepersonaliseerde inhoud naar de juiste ontvangers verzenden. Met Adobe Campaign kunt u het meest nauwkeurige doel maken: u kunt ontvangers selecteren op basis van hun leeftijd, lokalisatie, wat ze hebben gekocht, als ze op een koppeling in een vorige levering klikken, enzovoort. Met Adobe Campaign kunt u ook testprofielen, controlegroepen en zaadadressen definiëren om te controleren of het doel correct is.

## Doeltoewijzingen {#target-mappings}

Door gebrek, richten de leveringsmalplaatjes **Profielen**. Adobe Campaign biedt andere doeltoewijzingen voor uw leveringen die u op basis van uw behoeften kunt wijzigen.

Deze afbeeldingen worden voorgesteld [ in deze sectie ](../../automating/using/query.md#targeting-dimensions-and-resources).

U kunt ook een aangepaste doeltoewijzing maken en gebruiken. Voor meer op dit, verwijs naar [ deze sectie ](../../administration/using/target-mappings-in-campaign.md).

## Externe gegevens {#external-data}

U kunt leveren aan ontvangers die in een extern dossier eerder dan opgeslagen in het gegevensbestand worden opgeslagen. Hiertoe ontwerpt u een workflow om gegevens uit een bestand in uw database te laden en een bijbehorend publiek te maken.  Leer meer [ in dit gebruiksgeval ](../../automating/using/use-case-calling-workflow.md). Zie ook [ het Roepen van een werkschema met parameters ](../../automating/using/calling-a-workflow-with-external-parameters.md).

## Verzenden naar uw abonnees {#send-to-subscribers}

Om berichten naar de abonnees van een nieuwsbrief te verzenden, kunt u de abonnees aan de overeenkomstige informatiedienst direct richten. Leer meer [ in deze sectie ](../../audiences/using/about-subscriptions.md).

**Uiteinde** - u kunt een publiek van de Lijst tot stand brengen dat de abonnees aan uw bulletin richt gebruikend een werkschema. U kunt dit publiek vervolgens in een levering selecteren. Voor meer op dit, zie [ Creërend lijstpubliek ](../../audiences/using/creating-audiences.md#creating-list-audiences).

## Proefdrukken, testprofielen en controlegroepen {#proofs-test-control-groups}

Om uw levering te testen, gebruik proef alvorens naar het belangrijkste doel te verzenden.
Zorg ervoor dat u de juiste ontvangers voor het bewijs selecteert, omdat deze het formulier en de inhoud van het bericht valideren. De stappen voor het verzenden van proeven worden voorgesteld [ in deze sectie ](../../sending/using/sending-proofs.md).

Leer meer over testprofielen [ in deze sectie ](../../audiences/using/managing-test-profiles.md).

U kunt [ groepen van de Controle ](../../sending/using/control-group.md) gebruiken om het effect van uw campagnes te meten door een gedeelte van hun publiek uit te sluiten. Vervolgens kunt u het gedrag van de doelgroep die de boodschap heeft ontvangen, vergelijken met het gedrag van contacten die niet als doelgroep werden beschouwd. Gebaseerd op de verzendende logboeken, kunt u een controlegroep in toekomstige campagnes ook richten.

## Gedupliceerde adressen {#deduplicate-addresses}

Het is belangrijk om dubbele e-mailadressen te vermijden, omdat dit van invloed kan zijn op uw doel:

* Hetzelfde bericht kan meerdere keren worden verzonden wanneer een doel wordt gesplitst.

* Als een ontvanger zich afmeldt na het ontvangen van een bericht, zal hun dubbele profiel nog toekomstige berichten ontvangen.

Deduplicating adressen beschermt uw verzendende reputatie en verzekert goed quarantainebeheer.

Leer meer [ in dit gebruiksgeval ](../../automating/using/deduplicating-data-imported-file.md).
