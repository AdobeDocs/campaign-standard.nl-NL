---
title: Probleemoplossing voor leveringsproblemen in Adobe Campaign Standard
description: Leer wat u moet doen als u problemen ondervindt met de beschikbaarheid van Adobe Campagne Standard.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b4ba56e5cd639c547a7060be9c60985f5564160d

---


# Problemen oplossen{#troubleshooting}

Ondervindt u een probleem met de leesbaarheid? U kunt hier de oplossing vinden.

## Hetzelfde foutbericht voor een ISP {#same-error-for-an-isp}

**Waarom krijg ik altijd het zelfde foutenbericht voor bepaalde ISP?**

Als u altijd het zelfde foutenbericht voor ISP krijgt, kan uw e-mail of IP als gebrek door ISP worden ontdekt. Voer de volgende aanbevelingen uit:
* Controleer of u een groot percentage mislukkingen ontvangt die zijn gekoppeld aan onbestaande e-mailadressen (**Onbekende** fouten van gebruiker).
* Werk uw abonnementsformulieren bij om fouten in de ingevoerde domeinnamen op te sporen (bijvoorbeeld: gmaul.com of yaho.com).
* Als u fouten opmerkt die verklaren dat uw berichten als spam worden verklaard, of dat uw berichten constant worden geblokkeerd, probeer exclusief de ontvangers die niet in één van uw berichten in de laatste 12 maanden van het doel hebben geopend of geklikt.

Neem contact op met de commerciële of leverbare services of met de ondersteuning van Adobe Campagne als het probleem zich blijft voordoen.

## Zwarte lijst versus quarantaine {#blacklisting-versus-quarantine}

* **Wat is het verschil tussen een e-mailadres dat op de zwarte lijst staat en een e-mailadres dat in quarantaine is geplaatst?**

   * De status **[!UICONTROL Blacklisted]** is een resultaat van een feedbacklus (wanneer een persoon een bericht rapporteert als spam).

   * De status **[!UICONTROL Quarantined]** is het resultaat van een zachte of harde stuit. Zie deze [sectie](../../sending/using/understanding-quarantine-management.md)voor meer informatie.

* **Wat betekenen de verschillende redenen voor quarantainefouten?**

   Hier volgen tien mogelijke redenen: niet gedefinieerd, gebruiker onbekend, ongeldig domein, adres op de zwarte lijst, geweigerd, fout genegeerd, onbereikbaar, account uitgeschakeld, postvak vol, niet verbonden.

   Voor meer op dit, zie het [Begrip van quarantainebeheer](../../sending/using/understanding-quarantine-management.md).

## Uitschakelen {#unblacklisting}

* **Een van mijn ontvangers was per ongeluk op de zwarte lijst gezet. Hoe maak ik de zwarte lijst ongedaan zodat ik ze opnieuw kan versturen?**

   * Ga naar **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * Stel in de details van de corresponderende record de waarde van het **[!UICONTROL Status]** veld in op **[!UICONTROL Valid]**.
   * Sla de record op.

* **Hoe kan ik weten of één van mijn IPs zwarte lijst is? Hoe maak ik mijn IP(s) niet op de zwarte lijst?**

   Om te controleren of uw IP adres zwarte lijst is, kunt u diverse websites gebruiken om het te verifiëren:
   * https://mxtoolbox.com/
   * https://whatismyipaddress.com/blacklist-check
   * https://www.blacklistalert.org/
   Over het algemeen, zal het resultaat van de IP adrescontrole een lijst terugkeren die details van de zwarte lijst en ook de naam van de website bevat die het IP adres zwarte lijst maakt.

   Als u op de desbetreffende koppeling klikt, hebt u toegang tot de gegevens van de website.

   Vervolgens kunt u vragen dat uw website wordt verwijderd van de website die het IP-adres op een zwarte lijst zet.

   >[!NOTE]
   >
   >Het verwijderingsproces kan afhankelijk van de website variëren. Sommige plaatsen vereisen u om een rekening tot stand te brengen, terwijl anderen enkel u nodig hebben om het IP adres te verstrekken.
