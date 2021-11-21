---
title: Controleregels
description: Leer hoe te om de kwaliteitscontrole van uw berichten met controleregels te versterken.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
feature: Typology Rules
role: User
level: Intermediate
exl-id: 6461c128-1e42-4685-88f8-507244147e6f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
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

Een reeks standaardregels verzekert de standaardcontroles. De onderstaande tabel bevat informatie over deze regels en het bijbehorende kanaal en [uitvoeringsfasen](#control-rules-execution-phases).

| Label | Kanaal | Uitvoeringsfase | Beschrijving |
|---------|----------|---------|---------|
| **[!UICONTROL A/B Test]** | Email | Aan het begin van personalisatie | Extraheert de testpopulatie voor een levering met een A/B-test. |
| **[!UICONTROL Check delivery size]** | Alles | Na doelframes | Controleert de grootte van de berichten. |
| **[!UICONTROL Check email content is not empty]** | E-mail | Na doelframes | Genereert een fout als de inhoud van het bericht leeg is. |
| **[!UICONTROL Check In-App content for broadcast template]** | In app | Aan het begin personaliseren | Controleert of inhoud/triggers in de app niet leeg zijn voor de uitgezonden sjabloon. |
| **[!UICONTROL Check In-App content for profile template]** | In app | Aan het begin van personalisatie | Hiermee wordt gecontroleerd of inhoud/triggers in de app niet leeg zijn voor de profielsjabloon. |
| **[!UICONTROL Check In-App content for subscriber template]** | In app | Aan het begin van personalisatie | Controleert of inhoud/triggers in de app niet leeg zijn voor de abonneesjabloon. |
| **[!UICONTROL Check proof size]** | Alles | Na doelframes | Genereert een foutbericht als de proefdoelpopulatie groter is dan 100 ontvangers. |
| **[!UICONTROL Check social network sharing link]** | E-mail | Aan het begin van personalisatie | Controleert de aanwezigheid van een verbinding aan een spiegelpagina wanneer het omvatten van een sociale netwerk delende verbinding (ViralLinks) in de inhoud. |
| **[!UICONTROL Check subject]** | E-mail | Aan het begin van personalisatie | Controleert dat het onderwerp en het afzenderadres geen speciale karakters bevatten die problemen op bepaalde agenten van de postoverdracht kunnen veroorzaken, en controleert dat het berichtonderwerp is voltooid. |
| **[!UICONTROL Check unsubscription link]** | E-mail | Aan het begin van personalisatie | Controleert op de aanwezigheid van minstens één niet-abonnements (opt-out) URL in elke inhoud (HTML en Tekst). |
| **[!UICONTROL Check URL labels]** | E-mail | Aan het begin van personalisatie | Controleert dat elke volgende URL een etiket heeft. |
| **[!UICONTROL Check URLs]** | E-mail | Aan het begin van personalisatie | Controleert URLs het volgen (aanwezigheid van &quot;&amp;&quot;karakter). |

## Uitvoeringsfasen van regelregels {#control-rules-execution-phases}

Regels voor controle kunnen worden toegepast in verschillende fasen van de levenscyclus van de levering:

* **Aan het begin van de doelgerichte**: De controleregel kan in deze fase worden toegepast zodat de verpersoonlijkingsstap niet in het geval van een fout wordt uitgevoerd.

* **Na doelframes**: Het uitvoeren na het richten staat u toe om het volume van het doel te kennen om de controleregel toe te passen.

   De **Proefdrukgrootte controleren** de controleregel is van toepassing na de doelfase: deze regel verhindert de voorbereiding van berichtverpersoonlijking als er teveel bewijsontvangers zijn.

* **Aan het begin van personalisatie**: Is van toepassing wanneer de controle op de goedkeuring van de berichtverpersoonlijking betrekking heeft. De personalisatie van berichten wordt uitgevoerd tijdens de analysefase.

* **Aan het einde van de analyse**: Wanneer een controle berichtverpersoonlijking vereist om volledig te zijn.
