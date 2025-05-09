---
title: Problemen met de leverbaarheid van Adobe Campaign Standard oplossen
description: Leer wat je moet doen als je problemen hebt met de levering van Adobe Campaign Standard.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 0470b986-c00a-4441-8621-82c7112a9953
source-git-commit: 449187bba167f9ce00e644d44a124b36030ba001
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 1%

---

# Problemen oplossen{#troubleshooting}

Ondervindt u een probleem met de leesbaarheid? U kunt hier de oplossing vinden.

## Hetzelfde foutbericht voor een ISP {#same-error-for-an-isp}

**waarom ik altijd het zelfde foutenbericht voor bepaalde ISP krijg?**

Als u altijd het zelfde foutenbericht voor ISP krijgt, kan uw e-mail of IP als gebrek door ISP worden ontdekt. Voer de volgende aanbevelingen uit:

* Controle of u een groot percentage mislukkingen met onbestaande e-mailadressen verbonden ontvangt (**Gebruiker onbekend** mislukkingen).
* Werk uw abonnementsformulieren bij om fouten in de ingevoerde domeinnamen te detecteren (bijvoorbeeld: gmaul.com of yaho.com).
* Als u fouten opmerkt die verklaren dat uw berichten als spam worden verklaard, of dat uw berichten constant worden geblokkeerd, probeer exclusief de ontvangers die niet in één van uw berichten in de laatste 12 maanden van het doel hebben geopend of geklikt.

Als het probleem zich blijft voordoen, neemt u contact op met de services voor commercieel gebruik of voor levering, of met de Adobe Campaign-ondersteuning.

## Lijst van gewezen personen versus quarantaine {#denylist-versus-quarantine}

* **wat is het verschil tussen een e-mailadres op lijst van gewezen personen en een quarantined e-mailadres?**

   * De status **[!UICONTROL On denylist]** is een resultaat van a [ terugkoppelt lijn ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=nl-NL#feedback-loops) (wanneer een persoon een bericht als spam meldt).

   * De status **[!UICONTROL Quarantined]** is het resultaat van een zachte of harde stuit.

  Zie [deze sectie](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist) voor meer informatie.

* **wat de verschillende redenen van de quarantainefout betekenen?**

  Hier zijn 10 mogelijke redenen: niet bepaald, gebruiker onbekend, ongeldig domein, adres op lijst van gewezen personen, geweigerd, fout genegeerd, onbereikbaar, rekening gehandicapt, brievenbus volledig, niet verbonden.

  Voor meer op dit, zie [ Begrijpend quarantainebeheer ](../../sending/using/understanding-quarantine-management.md).

## Verwijderen uit lijst van gewezen personen {#removing-from-denylist}

* **Één van mijn ontvangers werd per ongeluk toegevoegd aan de lijst van gewezen personen. Hoe verwijder ik hen uit de lijst van gewezen personen zodat ik kan beginnen hen berichten opnieuw te verzenden?**

   * Ga naar **[!UICONTROL Administration > Channels > Quarantines > Addresses]** .
   * Stel in de details van de corresponderende record de waarde van het veld **[!UICONTROL Status]** in op **[!UICONTROL Valid]** .
   * Sla de record op.

* **Hoe kan ik weten of één van mijn IPs op lijst van gewezen personen is? Hoe verwijder ik mijn IP(s) uit een lijst van gewezen personen?**

  Om te controleren of uw IP adres op lijst van gewezen personen is, kunt u diverse websites gebruiken om het te verifiëren, zoals:
   * [ MX Toolbox ](https://mxtoolbox.com/)
   * [ wat mijn IP adres ](https://whatismyipaddress.com) is

  Over het algemeen, zal het resultaat van de IP adrescontrole een lijst terugkeren die details van de lijst van gewezen personen en ook de naam van de website bevat die het IP adres blokkeerde.

  Als u op de desbetreffende koppeling klikt, hebt u toegang tot de gegevens van de website.

  Vervolgens kunt u vragen dat uw website wordt verwijderd van de website die het IP-adres aan de lijst van gewezen personen heeft toegevoegd.

  >[!NOTE]
  >
  >Het verwijderingsproces kan afhankelijk van de website variëren. Sommige plaatsen vereisen u om een rekening tot stand te brengen, terwijl anderen enkel u nodig hebben om het IP adres te verstrekken.
