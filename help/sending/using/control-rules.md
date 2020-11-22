---
solution: Campaign Standard
product: campaign
title: Controleregels
description: Leer hoe te om de kwaliteitscontrole van uw berichten met controleregels te versterken.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 3%

---


# Controleregels {#control-rules}

Met de besturingsregels kunt u de geldigheid en kwaliteit van de berichten controleren voordat ze worden verzonden, zoals de weergave van tekens, de grootte van SMS-berichten, de adresindeling, enzovoort.

>[!NOTE]
>
>Om veiligheidsredenen, zijn de controleregels read-only en kunnen niet worden gewijzigd.

## Standaardbesturingsregels {#default-control-rules}

Een reeks standaardregels verzekert de standaardcontroles. In de onderstaande tabel vindt u informatie over deze regels en de bijbehorende kanaal- en [uitvoeringsfasen](#control-rules-execution-phases).

| Label | Kanaal | Uitvoeringsfase | Beschrijving |
---------|----------|---------|---------
| **[!UICONTROL A/B Test]** | Email | Aan het begin van personalisatie | Extraheert de testpopulatie voor een levering met een A/B-test. |
| **[!UICONTROL Check delivery size]** | Alles | Na doelframes | Controleert de grootte van de berichten. |
| **[!UICONTROL Check email content is not empty]** | Email | Na doelframes | Genereert een fout als de inhoud van het bericht leeg is. |
| **[!UICONTROL Check In-App content for broadcast template]** | In app | Aan het begin personaliseren | Controleert of inhoud/triggers in de app niet leeg zijn voor de uitgezonden sjabloon. |
| **[!UICONTROL Check In-App content for profile template]** | In app | Aan het begin van personalisatie | Hiermee wordt gecontroleerd of inhoud/triggers in de app niet leeg zijn voor de profielsjabloon. |
| **[!UICONTROL Check In-App content for subscriber template]** | In app | Aan het begin van personalisatie | Controleert of inhoud/triggers in de app niet leeg zijn voor de abonneesjabloon. |
| **[!UICONTROL Check proof size]** | Alles | Na doelframes | Genereert een foutbericht als de proefdoelpopulatie groter is dan 100 ontvangers. |
| **[!UICONTROL Check social network sharing link]** | Email | Aan het begin van personalisatie | Controleert de aanwezigheid van een verbinding aan een spiegelpagina wanneer het omvatten van een sociale netwerk delende verbinding (ViralLinks) in de inhoud. |
| **[!UICONTROL Check subject]** | Email | Aan het begin van personalisatie | Controleert dat het onderwerp en het afzenderadres geen speciale karakters bevatten die problemen op bepaalde agenten van de postoverdracht kunnen veroorzaken, en controleert dat het berichtonderwerp is voltooid. |
| **[!UICONTROL Check unsubscription link]** | Email | Aan het begin van personalisatie | Controleert op de aanwezigheid van minstens één niet-abonnements (opt-out) URL in elke inhoud (HTML en Tekst). |
| **[!UICONTROL Check URL labels]** | Email | Aan het begin van personalisatie | Controleert dat elke volgende URL een etiket heeft. |
| **[!UICONTROL Check URLs]** | Email | Aan het begin van personalisatie | Controleert URLs het volgen (aanwezigheid van &quot;&amp;&quot;karakter). |

## Uitvoeringsfasen van regelregels {#control-rules-execution-phases}

Regels voor controle kunnen worden toegepast in verschillende fasen van de levenscyclus van de levering:

* **Bij het begin van de doelgerichte** actie: De controleregel kan in deze fase worden toegepast zodat de verpersoonlijkingsstap niet in het geval van een fout wordt uitgevoerd.

* **Na aanwijzen**: Het uitvoeren na het richten staat u toe om het volume van het doel te kennen om de controleregel toe te passen.

   De regel voor het controleren van de grootte **van de** proefdruk is bijvoorbeeld van toepassing na het doelstadium: deze regel verhindert de voorbereiding van berichtverpersoonlijking als er teveel bewijsontvangers zijn.

* **Aan het begin van de personalisatie**: Is van toepassing wanneer de controle op de goedkeuring van de berichtverpersoonlijking betrekking heeft. De personalisatie van berichten wordt uitgevoerd tijdens de analysefase.

* **Aan het einde van de analyse**: Wanneer een controle berichtverpersoonlijking vereist om volledig te zijn.
