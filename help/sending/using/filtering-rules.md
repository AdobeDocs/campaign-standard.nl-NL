---
title: Filterregels
description: Gebruik filterregels om het publiek van uw berichten te verfijnen.
page-status-flag: never-activated
uuid: ed3eea62-3a47-4318-ae22-d82aa857448f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 7ddaf36c-74e6-4501-b3eb-3d03f005aaa6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1f15e28bed22e3defb29f16875fcf4c07f4af5a3
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 3%

---


# Regels filteren {#filtering-rules}

Met filterregels kunt u een deel van het berichtdoel uitsluiten volgens criteria die in een query zijn gedefinieerd, zoals quarantineprofielen of profielen die al een bepaald aantal e-mailberichten hebben ontvangen.

## Standaardfiltertypologieregels {#default-filtering-typology-rules}

De lijst hieronder verstrekt informatie over uit-van-de-doos het filtreren regels, evenals hun verwante kanalen.

| Label | Kanaal | Beschrijving |
---------|----------|---------
| **[!UICONTROL Address not specified]** | Alles | Hiermee sluit u de doelpopulatie zonder opgegeven adres (e-mail, postadres, enz.) uit. volgens het geselecteerde kanaal). |
| **[!UICONTROL Denylisted address]** | Alles | Sluit adressen uit die op de lijst van afgewezen personen zijn. |
| **[!UICONTROL Duplicate]** | Alles | Hiermee worden duplicaten op basis van het **[!UICONTROL Address]** doelpopulatieveld uitgesloten. |
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

Dit is om te voorkomen dat het toegevoegd op lijst van gewenste personen wordt als gevolg van kwaadwillige activiteit, met name het gebruik van een Spamtrap. Als bijvoorbeeld een spamtrap wordt gebruikt om zich te abonneren via een van uw webformulieren, wordt automatisch een bevestigingsbericht verzonden naar die spamtrap. Hierdoor wordt uw adres automatisch toegevoegd aan de lijst van afgewezen personen.

>[!NOTE]
>
>De adressen en domeinnamen in de globale suppressielijst worden verborgen. Alleen het aantal uitgesloten ontvangers wordt vermeld in de logboeken van de leveringsanalyse.

## Creating a filtering rule {#creating-a-filtering-rule}

U kunt uw eigen het filtreren regels op uw behoeften tot stand brengen. U kunt bijvoorbeeld de doelpopulatie van nieuwsbrieven filteren, zodat abonnees die jonger zijn dan 18 jaar nooit communicatie ontvangen.

Voer de volgende stappen uit om een filtreertypologieregel te maken:

1. Maak een nieuwe typologieregel. De belangrijkste stappen voor het opstellen van typologische regels worden in [deze sectie](../../sending/using/managing-typology-rules.md)beschreven.

1. Selecteer het **[!UICONTROL Filtering]** regeltype en geef vervolgens het gewenste kanaal op.

1. Selecteer op het **[!UICONTROL Filtering criteria]** tabblad de abonnementen in de **[!UICONTROL Subscription]** categorie.

   ![](assets/typology_create-rule-subscription.png)

1. In het **[!UICONTROL Explorer]** lusje van de vraagredacteur, sleep en laat vallen de **[!UICONTROL Subscriber]** knoop in het belangrijkste deel van het scherm.

   ![](assets/typology_create-rule-subscriber.png)

1. Selecteer het **[!UICONTROL Age]** gebied en bepaal de het filtreren voorwaarden zodat de leeftijd van de abonnees 18 of hoger is.

   ![](assets/typology_create-rule-age.png)

1. Koppel deze regel in het **[!UICONTROL Typologies]** tabblad aan een typologie.

   ![](assets/typology_create-rule-typology.png)

1. Zorg ervoor dat de typologie is geselecteerd in de leveringssjabloon die u wilt gebruiken. Raadpleeg [deze sectie](../../sending/using/managing-typologies.md#applying-typologies-to-messages) voor meer informatie.

   ![](assets/typology_template.png)

Wanneer deze regel in een bericht wordt gebruikt, worden abonnees die als minderjarigen worden beschouwd, automatisch uitgesloten.

## Het vormen van het filtreren regels richten context {#configuring-filtering-rules-targeting-context}

Campaign Standard staat u toe om de het **richten** en het **Filtreren** dimensies te vormen om afhankelijk van de gegevens te gebruiken die u wilt richten.

Om dit te doen, open de eigenschappen van de typologieregel, dan heb toegang tot de **[!UICONTROL Advanced information]** sectie.

By default, filtering is carried out on the **[!UICONTROL Profiles]**. Als de regel bijvoorbeeld op een mobiele toepassing is gericht, **[!UICONTROL Filtering dimension]** kan deze worden gewijzigd in **[!UICONTROL Subscriptions to an application]**.

![](assets/typology_rule-order_2.png)

## Restricting the applicability of a filtering rule {#restricting-the-applicability-of-a-filtering-rule}

U kunt de toepasbaarheid van een het filtreren regel volgens het te verzenden bericht beperken.

1. Schakel op het **[!UICONTROL Application criteria]** **[!UICONTROL Apply the rule on all deliveries]** tabblad van de typologieregel de optie uit, die standaard is ingeschakeld.

   ![](assets/typology_limit.png)

1. Gebruik de vraagredacteur om een filter te bepalen. U kunt de regel bijvoorbeeld alleen toepassen op berichten waarvan het label met een bepaald woord begint of waarvan de id bepaalde letters bevat.

   ![](assets/typology_limit-rule.png)

In dit geval wordt de regel alleen toegepast op de berichten die aan de gedefinieerde criteria voldoen.
