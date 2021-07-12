---
solution: Campaign Standard
product: campaign
title: Problemen met de leverbaarheid van Adobe Campaign Standard oplossen
description: Leer wat je moet doen als je problemen hebt met de levering van Adobe Campaign Standard.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Afleverbaarheid
role: User
level: Intermediate
exl-id: 0470b986-c00a-4441-8621-82c7112a9953
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 2%

---

# Problemen oplossen{#troubleshooting}

Ondervindt u een probleem met de leesbaarheid? U kunt hier de oplossing vinden.

## Hetzelfde foutbericht voor een ISP {#same-error-for-an-isp}

**Waarom krijg ik altijd het zelfde foutenbericht voor bepaalde ISP?**

Als u altijd het zelfde foutenbericht voor ISP krijgt, kan uw e-mail of IP als gebrek door ISP worden ontdekt. Voer de volgende aanbevelingen uit:
* Controleer of u een groot percentage fouten ontvangt die zijn gekoppeld aan onbestaande e-mailadressen (**Onbekende gebruiker** fouten).
* Werk uw abonnementsformulieren bij om fouten in de ingevoerde domeinnamen op te sporen (bijvoorbeeld: gmaul.com of yaho.com).
* Als u fouten opmerkt die verklaren dat uw berichten als spam worden verklaard, of dat uw berichten constant worden geblokkeerd, probeer exclusief de ontvangers die niet in één van uw berichten in de laatste 12 maanden van het doel hebben geopend of geklikt.

Als het probleem zich blijft voordoen, neemt u contact op met de services voor commercieel gebruik of voor levering, of met de Adobe Campaign-ondersteuning.

## Lijst van gewezen personen versus quarantaine {#denylist-versus-quarantine}

* **Wat is het verschil tussen een e-mailadres op lijst van gewezen personen en een quarantined e-mailadres?**

   * De status **[!UICONTROL On denylist]** is een resultaat van een [terugkoppelt lijn](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops) (wanneer een persoon een bericht als spam meldt).

   * De status **[!UICONTROL Quarantined]** is het resultaat van een zachte of harde stuit.
   Zie [deze sectie](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist) voor meer informatie.

* **Wat betekenen de verschillende redenen voor quarantainefouten?**

   Hier volgen tien mogelijke redenen: niet bepaald, gebruiker onbekend, ongeldig domein, adres op lijst van gewezen personen, geweigerd, fout genegeerd, onbereikbaar, rekening gehandicapt, brievenbus volledig, niet verbonden.

   Voor meer op dit, zie [Het begrip quarantainebeheer](../../sending/using/understanding-quarantine-management.md).

## Verwijderen uit lijst van gewezen personen {#removing-from-denylist}

* **Een van mijn ontvangers is per ongeluk aan de lijst van gewezen personen toegevoegd. Hoe verwijder ik hen uit de lijst van gewezen personen zodat ik kan beginnen hen berichten opnieuw te verzenden?**

   * Ga naar **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * Stel in de details van de corresponderende record de waarde van het veld **[!UICONTROL Status]** in op **[!UICONTROL Valid]**.
   * Sla de record op.

* **Hoe kan ik te weten komen of één van mijn IPs op lijst van gewezen personen is? Hoe verwijder ik mijn IP(s) uit een lijst van gewezen personen?**

   Om te controleren of uw IP adres op lijst van gewezen personen is, kunt u diverse websites gebruiken om het te verifiëren, zoals:
   * [MX-gereedschapset](https://mxtoolbox.com/)
   * [Wat is mijn IP adres](https://whatismyipaddress.com)

   Over het algemeen, zal het resultaat van de IP adrescontrole een lijst terugkeren die details van de lijst van gewezen personen en ook de naam van de website bevat die het IP adres blokkeerde.

   Als u op de desbetreffende koppeling klikt, hebt u toegang tot de gegevens van de website.

   Vervolgens kunt u vragen dat uw website wordt verwijderd van de website die het IP-adres aan de lijst van gewezen personen heeft toegevoegd.

   >[!NOTE]
   >
   >Het verwijderingsproces kan afhankelijk van de website variëren. Sommige plaatsen vereisen u om een rekening tot stand te brengen, terwijl anderen enkel u nodig hebben om het IP adres te verstrekken.
