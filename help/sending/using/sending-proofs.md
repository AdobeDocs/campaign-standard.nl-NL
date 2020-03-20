---
title: Proefdrukken verzenden
description: Leer hoe u proefdrukken verzendt.
page-status-flag: never-activated
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7f90991ed4c7323e3a2f8ac7d38da9ff165ef76

---


# Proefdrukken verzenden {#sending-proofs}

## Proefdrukken {#about-proofs}

Een bewijs is een specifiek bericht dat u toestaat om een bericht te testen alvorens het naar het belangrijkste doel te verzenden. Ontvangers van het bewijs zijn belast met de goedkeuring van het bericht (inhoud en vorm).

Er zijn twee typen ontvangers van bewijzen:

* **Met testprofielen** kunt u zich richten op extra ontvangers die niet voldoen aan de gedefinieerde doelcriteria.

   Ze kunnen worden toegevoegd aan het publiek van een bericht om frauduleus gebruik van de database van de ontvanger op te sporen of om ervoor te zorgen dat de e-mails in de postvakken aankomen. Zie [Testprofielen](../../audiences/using/managing-test-profiles.md)beheren voor meer informatie.

   >[!NOTE]
   >
   >Als u een proefdruk wilt verzenden, moeten de testprofielen worden opgenomen in het publiek van uw bericht.

* **Met vervangingsprofielen** kunt u uzelf in de positie van een van de doelprofielen plaatsen en een exacte weergave krijgen van het bericht dat het profiel ontvangt. Zie E-mailberichten [testen met doelprofielen](../../sending/using/testing-messages-using-target.md)voor meer informatie.

   >[!NOTE]
   >
   >Deze functie is alleen beschikbaar voor het e-mailkanaal.

## Een proefafdruk verzenden {#sending-a-proof}

Voer de volgende stappen uit om proefdrukken te verzenden:

1. Controleer of de ontvangers voor proefdrukken zijn geconfigureerd:
   * **De testprofielen** moeten in het publiek van uw bericht worden omvat.
   * **Vervangende profielen** moeten worden toegevoegd zodra het bericht is voorbereid (zie [deze sectie](../../sending/using/testing-messages-using-target.md)).

1. Klik op de **[!UICONTROL Send a test]** knop.

   ![](assets/bat_select.png)

1. Selecteer het type proefdruk dat u wilt gebruiken:

   * **[!UICONTROL Email rendering]**: Selecteer deze optie om de manier te testen waarop uw bericht wordt ontvangen volgens de beoogde inboxes. Zie [E-mailrendering](../../sending/using/email-rendering.md)voor meer informatie.
   * **[!UICONTROL Proof]**: Selecteer deze optie om het bericht te testen voordat u het naar het hoofddoel verzendt. De ontvangers van de bewijzen zijn verantwoordelijk voor de goedkeuring van de levering, door zowel de inhoud als de vorm ervan te controleren.
   * **[!UICONTROL Proof + Email rendering]**: met deze optie worden de twee vorige opties gecombineerd .
   ![](assets/bat_select1.png)

   >[!NOTE]
   >
   >E-mailrendering is alleen beschikbaar met testprofielen. Als er geen testprofielen aan het bericht zijn toegevoegd, is alleen de **[!UICONTROL Proof]** optie beschikbaar voor selectie.

1. Bevestig uw keuze.

   De proefdrukken worden verzonden naar de ontvangers die zijn gevormd.

   ![](assets/bat_select2.png)

1. U kunt uw proefdrukken bekijken in de **[!UICONTROL Proofs]** vervolgkeuzelijst.

   ![](assets/bat_view.png)

1. Selecteer een proefdruk om het overzicht te openen. Als u voor een e-mail de optie voor het renderen **via** e-mail hebt geselecteerd als proefdruktype, wordt het **[!UICONTROL Access email rendering]** pictogram rechts van het proefdruklabel weergegeven. Zie [E-mailrendering](../../sending/using/email-rendering.md).

   ![](assets/bat_view2.png)

Afhankelijk van de opmerkingen van de personen die de proefafdruk ontvangen, wordt u mogelijk gevraagd de inhoud van de aflevering te wijzigen. Nadat de wijzigingen zijn uitgevoerd, moet u de e-mailvoorbereiding opnieuw starten en vervolgens een proefdruk opnieuw verzenden. Elke nieuwe proefdruk kan met de **[!UICONTROL Show proofs]** knoop worden betreden.

U moet zoveel proefdrukken verzenden als nodig zijn totdat u de inhoud van de levering hebt voltooid. Zodra dit wordt gedaan, kunt u de levering naar het belangrijkste doel verzenden en de goedkeuringscyclus sluiten.

## De onderwerpregel van proefdrukken configureren {#configuring-proofs-subject-line}

Wanneer een proef wordt verzonden, wordt zijn onderwerpregel gevormd door gebrek met het **&quot;Voorvoegsel van het Bewijs&quot;** , evenals een teller die op het aantal van de proef wijst.

![](assets/proof-prefix.png)

Voer de volgende stappen uit om de standaardonderwerpregel te wijzigen die u wilt gebruiken:

1. Klik op de **[!UICONTROL Open properties]** knop in het berichtdashboard.
1. Definieer in de **[!UICONTROL Advanced parameters]** sectie het voorvoegsel dat u standaard wilt gebruiken in de onderwerpregel.

Als u het proefdruknummer wilt verbergen, activeert u de **[!UICONTROL Hide proof prefix counter]** optie.

>[!NOTE]
>
>Laat het veld leeg als u het hele proefdrukvoorvoegsel wilt verbergen. **[!UICONTROL Subject line prefix]**

![](assets/proof-prefix-configuration.png)

1. Klik op **[!UICONTROL Confirm]**. De instellingen worden standaard toegepast op alle proefdrukken die voor het geselecteerde bericht zijn verzonden.

**Verwant onderwerp:**

* [Een test verzenden, een e-mailvideo](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/sending-test-preparing-sending-email.html) voorbereiden en verzenden
* [E-mailberichten testen met behulp van doelprofielen](../../sending/using/testing-messages-using-target.md).
* [Testprofielen](../../audiences/using/managing-test-profiles.md)beheren.
* [Berichten voorvertonen](../../sending/using/previewing-messages.md)
* [E-mailkanaal configureren](../../administration/using/configuring-email-channel.md)
