---
title: Sjablonen voor meertalige berichten
description: Leer hoe u meertalige e-mail- en sms-leveringen definieert en uitvoert via één levering op basis van de voorkeurstaal van uw automatisch gesegmenteerde klanten. Rapporteer de prestaties van elke levering tot aan de taal en het individuele niveau.
page-status-flag: never-activated
uuid: 7a2cd5f7-c0fc-4825-a770-a62816c66b3f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: managing-templates
discoiquuid: 064c5c4a-f579-4bab-adf3-51c92eb4518f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2

---


# Sjablonen voor meertalige berichten {#multilingual-messages-template}

Een meertalige sjabloon is een specifieke sjabloon voor het beheren van meertalige berichten. Dit soort sjabloon is beschikbaar voor **e-mail** - en **sms-berichten** en kan worden gebruikt in de zelfstandige modus, in een workflow of in een terugkerende levering.

In de meertalige eigenschapmalplaatjes, is het taalbeheer gebaseerd op varianten. **Elke variant vertegenwoordigt één taal**. Adobe Campaign Standard kan maximaal 40 varianten instellen.

Adobe Campaign wordt geleverd met een standaardtaal die is ingesteld op **EN**. De standaardtaal kan worden gewijzigd in een andere variant, maar mag nooit worden verwijderd.

Tijdens het creëren van het malplaatje, kunt u het aantal varianten toevoegen die aan het aantal nodig talen in het bericht beantwoorden.

Voer de volgende stappen uit om een SMS- of e-mailsjabloon te maken:

1. Dupliceer een bestaande meertalige sjabloon (SMS of e-mail).

   ![](assets/multi_template_duplicate.png)

   >[!NOTE]
   >
   >U kunt ook een bestaande standaardsjabloon in een meertalige sjabloon wijzigen door op de **[!UICONTROL Initialize content variant]** knop in de sjablooneigenschappen te klikken.

1. Wijzig de eigenschappen om label, tekstspatiëring enzovoort aan te passen.
1. Wijzig het aantal gewenste varianten door op de tegel Varianten te klikken. Het venster Varianten wordt weergegeven

   ![](assets/multi_template_variants.png)

   U kunt varianten toevoegen of verwijderen. Als u een variant wilt toevoegen, voert u het **[!UICONTROL New content variant]** venster in.

   ![](assets/multi_template_newvariant.png)

   >[!NOTE]
   >
   >Verwijder niet de &quot;standaard&quot;variant aangezien het de variant is die naar profielen zonder voltooide aangewezen taalparameter wordt verzonden.

1. Pas indien nodig de labelvariant aan en klik op **[!UICONTROL Confirm]**.
1. U kunt de inhoud voor elke variant ook rechtstreeks toevoegen.

U kunt nu een e-mail of een SMS-bericht maken op basis van deze meertalige sjabloon.

**Verwante onderwerpen:**

* [Een meertalige e-mail maken](../../channels/using/creating-a-multilingual-email.md)
* [Profielen maken](../../audiences/using/creating-profiles.md)
