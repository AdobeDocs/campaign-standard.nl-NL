---
solution: Campaign Standard
product: campaign
title: Problemen met de leverbaarheid van Adobe Campaign Standard oplossen
description: Leer wat je moet doen als je problemen hebt met de levering van Adobe Campaign Standard.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 1%

---


# Problemen oplossen{#troubleshooting}

Ondervindt u een probleem met de leesbaarheid? U kunt hier de oplossing vinden.

## Hetzelfde foutbericht voor een ISP {#same-error-for-an-isp}

**Waarom krijg ik altijd het zelfde foutenbericht voor bepaalde ISP?**

Als u altijd het zelfde foutenbericht voor ISP krijgt, kan uw e-mail of IP als gebrek door ISP worden ontdekt. Voer de volgende aanbevelingen uit:
* Controleer of u een groot percentage mislukkingen ontvangt die zijn gekoppeld aan onbestaande e-mailadressen (**Onbekende** fouten van gebruiker).
* Werk uw abonnementsformulieren bij om fouten in de ingevoerde domeinnamen op te sporen (bijvoorbeeld: gmaul.com of yaho.com).
* Als u fouten opmerkt die verklaren dat uw berichten als spam worden verklaard, of dat uw berichten constant worden geblokkeerd, probeer exclusief de ontvangers die niet in één van uw berichten in de laatste 12 maanden van het doel hebben geopend of geklikt.

Als het probleem zich blijft voordoen, neemt u contact op met de services voor commercieel gebruik of voor levering, of met de Adobe Campaign-ondersteuning.

## Lijst van afgewezen personen versus quarantaine {#denylist-versus-quarantine}

* **Wat is het verschil tussen een e-mailadres op lijst van afgewezen personen en een quarantined e-mailadres?**

   * De status **[!UICONTROL On denylist]** is een resultaat van een feedbacklus (wanneer een persoon een bericht rapporteert als spam).

   * De status **[!UICONTROL Quarantined]** is het resultaat van een zachte of harde stuit.
   Zie [deze sectie](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist) voor meer informatie.

* **Wat betekenen de verschillende redenen voor quarantainefouten?**

   Hier volgen tien mogelijke redenen: niet bepaald, gebruiker onbekend, ongeldig domein, adres op lijst van afgewezen personen, geweigerd, fout genegeerd, onbereikbaar, rekening gehandicapt, brievenbus volledig, niet verbonden.

   For more on this, see [Understanding quarantine management](../../sending/using/understanding-quarantine-management.md).

## Verwijderen uit lijst van afgewezen personen {#removing-from-denylist}

* **Een van mijn ontvangers is per ongeluk aan de lijst van afgewezen personen toegevoegd. Hoe verwijder ik hen uit de lijst van afgewezen personen zodat ik kan beginnen hen berichten opnieuw te verzenden?**

   * Ga naar **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * Stel in de details van de corresponderende record de waarde van het **[!UICONTROL Status]** veld in op **[!UICONTROL Valid]**.
   * Sla de record op.

* **Hoe kan ik te weten komen of één van mijn IPs op lijst van afgewezen personen is? Hoe verwijder ik mijn IP(s) uit een lijst van afgewezen personen?**

   Om te controleren of uw IP adres op lijst van afgewezen personen is, kunt u diverse websites gebruiken om het te verifiëren, zoals:
   * [MX-gereedschapset](https://mxtoolbox.com/)
   * [Wat is mijn IP adres](https://whatismyipaddress.com)

   Over het algemeen, zal het resultaat van de IP adrescontrole een lijst terugkeren die details van de lijst van afgewezen personen en ook de naam van de website bevat die het IP adres blokkeerde.

   Als u op de desbetreffende koppeling klikt, hebt u toegang tot de gegevens van de website.

   Vervolgens kunt u vragen dat uw website wordt verwijderd van de website die het IP-adres aan de lijst van afgewezen personen heeft toegevoegd.

   >[!NOTE]
   >
   >Het verwijderingsproces kan afhankelijk van de website variëren. Sommige plaatsen vereisen u om een rekening tot stand te brengen, terwijl anderen enkel u nodig hebben om het IP adres te verstrekken.
