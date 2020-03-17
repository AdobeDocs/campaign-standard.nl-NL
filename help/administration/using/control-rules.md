---
title: Controlevoorschriften
description: Leer hoe te om de kwaliteitscontrole van uw berichten met controleregels te versterken.
page-status-flag: never-activated
uuid: 33a1c90c-534e-4fe1-982c-f4e1858d4d2d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 305cadde-6424-4c6f-b11b-1e8bdbad6ef1
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Controlevoorschriften{#control-rules}

De controleregels staan de gebruiker toe om de geldigheid en de kwaliteit van de berichten te controleren alvorens zij worden verzonden, zoals karaktervertoning, de grootte van het SMS- bericht, adresformaat, enz.

Een reeks standaardregels beschikbaar in de Campagne van Adobe verzekert de standaardcontroles:

* **[!UICONTROL Check subject]** (e-mail): controleert of het onderwerp en het afzenderadres geen speciale karakters bevatten die problemen op bepaalde agenten van de postoverdracht kunnen veroorzaken, en controleert dat het berichtonderwerp is voltooid.
* **[!UICONTROL Check URL labels]** (e-mail): controleert of elke URL die het bijhouden van een URL uitvoert, een label heeft.
* **[!UICONTROL Check URLs]** (e-mail): Hiermee controleert u de URL&#39;s die worden gevolgd (aanwezigheid van het teken &quot;&amp;&quot;).
* **[!UICONTROL Check proof size]** (alle kanalen): genereert een foutbericht als de proefdoelpopulatie groter is dan 100 ontvangers.
* **Koppeling** voor uitschrijven van abonnement controleren (e-mail): controleert op de aanwezigheid van ten minste één niet-abonnements-URL (opt-out) in elke inhoud (HTML en Tekst).
* **[!UICONTROL Check delivery size]** (alle kanalen): controleert de grootte van de berichten.
* **[!UICONTROL Check social network sharing link]** (e-mail): controleert de aanwezigheid van een verbinding aan een spiegelpagina wanneer het omvatten van een sociale netwerk delende verbinding (ViralLinks) in de inhoud.
* **[!UICONTROL A/B Test]**: extraheert de testpopulatie voor een levering met een A/B-test.

U kunt het tijdstip kiezen waarop de regel wordt toegepast vanuit een van de fasen van de levenscyclus van de levering. Selecteer in het **[!UICONTROL Phase]** veld van de typologieregel de waarde die u wilt toepassen in de vervolgkeuzelijst.

![](assets/typology_phase.png)

Mogelijke waarden zijn:

* **Aan het begin van de doelgerichte**

   De controleregel kan in deze fase worden toegepast zodat de verpersoonlijkingsstap niet in het geval van een fout wordt uitgevoerd.

* **Na doelframes**

   Als u het volume van het doel moet kennen om de controleregel toe te passen, selecteer deze fase.

   De regel voor het controleren van de grootte **van de** proefdruk is bijvoorbeeld van toepassing na het doelstadium: deze regel verhindert de voorbereiding van berichtverpersoonlijking als er teveel bewijsontvangers zijn.

* **Aan het begin van personalisatie**

   Deze fase moet worden geselecteerd als de controle berichtverpersoonlijking goedkeurt. De personalisatie van berichten wordt uitgevoerd tijdens de analysefase.

* **Aan het einde van de analyse**

   Wanneer een controle berichtverpersoonlijking om vereist te zijn volledig, selecteer deze fase.

>[!NOTE]
>
>Om veiligheidsredenen kan de inhoud van de controleregels niet worden gewijzigd. Het **[!UICONTROL Code]** veld is alleen-lezen.
