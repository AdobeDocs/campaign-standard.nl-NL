---
solution: Campaign Standard
product: campaign
title: Filterregels
description: Gebruik filterregels om het publiek van uw berichten te verfijnen.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
feature: Typologieregels
role: User
level: Intermediate
exl-id: 43e97f3c-ed82-4fcc-ac0d-fcee6a22da35
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 3%

---

# Filterregels {#filtering-rules}

Met filterregels kunt u een deel van het berichtdoel uitsluiten volgens criteria die in een query zijn gedefinieerd, zoals quarantineprofielen of profielen die al een bepaald aantal e-mailberichten hebben ontvangen.

## Standaardfiltertypologieregels {#default-filtering-typology-rules}

De lijst hieronder verstrekt informatie over uit-van-de-doos het filtreren regels, evenals hun verwante kanalen.

| Label | Kanaal | Beschrijving |
| ---------|----------|---------|
| **[!UICONTROL Address not specified]** | Alles | Hiermee sluit u de doelpopulatie zonder opgegeven adres (e-mail, postadres, enz.) uit. volgens het geselecteerde kanaal). |
| **[!UICONTROL Address on denylist]** | Alles | Sluit adressen uit die op de lijst van gewezen personen zijn. |
| **[!UICONTROL Duplicate]** | Alles | Hiermee sluit u duplicaten op basis van het veld **[!UICONTROL Address]** van de doelpopulatie uit. |
| **[!UICONTROL Exclude mobile applications]** | Mobiele toepassing | Hiermee sluit u app-abonnementen uit die niet overeenkomen met de mobiele toepassing die in het bericht is gedefinieerd. |
| **[!UICONTROL Exclude mobile applications for In-App]** | In app | Hiermee sluit u toepassingsabonnementen uit die niet overeenkomen met de mobiele toepassing die in het bericht is gedefinieerd (In-App-sjabloon). |
| **[!UICONTROL Exclude mobile applications for In-App broadcast]** | In app | Hiermee sluit u toepassingsabonnementen uit die niet overeenkomen met de mobiele toepassing die in het bericht is gedefinieerd (In-App-uitzendsjabloon) |
| **[!UICONTROL Exclude mobile applications for Push]** | Mobiele toepassing | Hiermee sluit u app-abonnementen uit die niet overeenkomen met de mobiele toepassing die in het bericht is gedefinieerd (voor Push) |
| **[!UICONTROL Quarantined address]** | Alles | Sluit quarantined adressen uit. |
| **[!UICONTROL Target limited in size]** | Alles | Controleert of de maximale leveringsgrootte voor het doel is bereikt. Is van toepassing op direct-mailleveringen waarbij de optie &quot;leveringslimiet&quot; is geactiveerd. |

Naast deze standaard het filtreren regels, zijn twee uitsluitingsregels beschikbaar:

* **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** )
* **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** ).

Tijdens de e-mailanalyse, vergelijken deze regels de ontvankelijke e-mailadressen met de verboden adressen of domeinnamen in een gecodeerde globale suppressielijst die in de leveringsinstantie wordt beheerd. Als er een gelijke is, wordt het bericht niet verzonden naar die ontvanger.

Hiermee voorkomt u dat de lijst van gewezen personen wordt toegevoegd vanwege kwaadwillige activiteiten, met name het gebruik van een Spamtrap. Als bijvoorbeeld een spamtrap wordt gebruikt om zich te abonneren via een van uw webformulieren, wordt automatisch een bevestigingsbericht verzonden naar die spamtrap. Hierdoor wordt uw adres automatisch toegevoegd aan de lijst van gewezen personen.

>[!NOTE]
>
>De adressen en domeinnamen in de globale suppressielijst worden verborgen. Alleen het aantal uitgesloten ontvangers wordt vermeld in de logboeken van de leveringsanalyse.

## Filterregels maken {#creating-a-filtering-rule}

U kunt uw eigen het filtreren regels op uw behoeften tot stand brengen. U kunt bijvoorbeeld de doelpopulatie van nieuwsbrieven filteren, zodat abonnees die jonger zijn dan 18 jaar nooit communicatie ontvangen.

Voer de volgende stappen uit om een filtreertypologieregel te maken:

1. Maak een nieuwe typologieregel. De belangrijkste stappen om typologische regels tot stand te brengen zijn gedetailleerd in [deze sectie](../../sending/using/managing-typology-rules.md).

1. Selecteer het regeltype **[!UICONTROL Filtering]** en geef vervolgens het gewenste kanaal op.

1. Selecteer op het tabblad **[!UICONTROL Filtering criteria]** de abonnementen in de categorie **[!UICONTROL Subscription]**.

   ![](assets/typology_create-rule-subscription.png)

1. Op **[!UICONTROL Explorer]** lusje van de vraagredacteur, sleep en laat vallen **[!UICONTROL Subscriber]** knoop in het belangrijkste deel van het scherm.

   ![](assets/typology_create-rule-subscriber.png)

1. Selecteer het **[!UICONTROL Age]** gebied en bepaal de het filtreren voorwaarden zodat de leeftijd van de abonnees 18 of hoger is.

   ![](assets/typology_create-rule-age.png)

1. Koppel deze regel aan een typologie op het tabblad **[!UICONTROL Typologies]**.

   ![](assets/typology_create-rule-typology.png)

1. Zorg ervoor dat de typologie is geselecteerd in de leveringssjabloon die u wilt gebruiken. Raadpleeg [deze sectie](../../sending/using/managing-typologies.md#applying-typologies-to-messages) voor meer informatie.

   ![](assets/typology_template.png)

Wanneer deze regel in een bericht wordt gebruikt, worden abonnees die als minderjarigen worden beschouwd, automatisch uitgesloten.

## Het vormen van het filtreren regels richten context {#configuring-filtering-rules-targeting-context}

Met Campaign Standard kunt u de **Targeting** en **Filtering**-afmetingen configureren voor gebruik, afhankelijk van de gegevens die u als doel wilt gebruiken.

Om dit te doen, open de eigenschappen van de typologieregel, dan toegang tot **[!UICONTROL Advanced information]** sectie.

Door gebrek, wordt het filtreren uitgevoerd op **[!UICONTROL Profiles]**. Als de regel bijvoorbeeld is gericht op een mobiele toepassing, kan **[!UICONTROL Filtering dimension]** worden gewijzigd in **[!UICONTROL Subscriptions to an application]**.

![](assets/typology_rule-order_2.png)

## De toepasbaarheid van een filterregel beperken {#restricting-the-applicability-of-a-filtering-rule}

U kunt de toepasbaarheid van een het filtreren regel volgens het te verzenden bericht beperken.

1. Schakel op het tabblad **[!UICONTROL Application criteria]** van de typologieregel de optie **[!UICONTROL Apply the rule on all deliveries]** uit, die standaard is ingeschakeld.

   ![](assets/typology_limit.png)

1. Gebruik de vraagredacteur om een filter te bepalen. U kunt de regel bijvoorbeeld alleen toepassen op berichten waarvan het label met een bepaald woord begint of waarvan de id bepaalde letters bevat.

   ![](assets/typology_limit-rule.png)

In dit geval wordt de regel alleen toegepast op de berichten die aan de gedefinieerde criteria voldoen.
