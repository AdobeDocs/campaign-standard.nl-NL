---
title: Lijsten exporteren
description: Met Adobe Campaign kunt u de gegevens die worden weergegeven als lijsten vanuit een overzichtsscherm rechtstreeks in een bestand exporteren voor toekomstig gebruik.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
old-role: Data Architect
role: Developer
level: Experienced
exl-id: b39ce1f6-0c5b-4270-86a1-b79c49cd199c
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 5%

---

# Lijsten exporteren{#exporting-lists}

Met Adobe Campaign kunt u uw lijsten rechtstreeks in een bestand exporteren voor toekomstig gebruik. Wanneer u een lijst in een bestand exporteert, wordt een logbestandvermelding in het menu **[!UICONTROL Export audits]** gegenereerd. Raadpleeg de sectie [Audits uitvoeren op exportlogboeken](../../administration/using/auditing-export-logs.md) voor meer informatie over exportaudits.

![](assets/do-not-localize/how-to-video.png) [&#x200B; ontdekt hoe te om een lijst in video &#x200B;](#video) te vormen

De de lijstoptie van de uitvoer staat u toe om een maximum van 100.000 lijnen door gebrek uit te voeren en door de **Nms_ExportListLimit** optie wordt bepaald. Deze optie kan worden beheerd door de functionele beheerder via het menu **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** .

De lijst van de uitvoer is beschikbaar in alle schermen die de wijzemening van de Lijst **&#x200B;**, voor gebruikers met de **[!UICONTROL EXPORT (export)]** rol hebben.

1. Ga naar uw gekozen **scherm van de Lijst**. Bijvoorbeeld het scherm met het testprofiel ( **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]** ).
1. Controleer dat het scherm op **1&rbrace; wijze van de Lijst &lbrace;is.**

   ![](assets/export_list_mode_switch.png)

1. Organiseer de kolommen in de lijst in de volgorde waarin u ze wilt exporteren met de knop **[!UICONTROL Configure list]** in de rechterbovenhoek. Naast gevormde kolommen, zal de primaire sleutel van het middel ook worden uitgevoerd.
1. U kunt desgewenst een filter toepassen. Klik hiertoe op de knop in de linkerbovenhoek om het zoekvenster weer te geven.

   Als u een export uitvoert vanuit een lijst die verschillende bronnen bevat, moet u uw filters toepassen zodat er slechts één type bron in de lijst wordt weergegeven.

1. U kunt desgewenst de gekozen kolom(men) sorteren.
1. Selecteer de knop Exporteren ![](assets/exportlistbutton.png) .

   Er verschijnt een pop-up ter bevestiging van het exporteren. Nadat u het exporteren hebt bevestigd, wordt het bestand automatisch naar de computer gedownload.

Het bestand wordt gegenereerd in CSV-indeling met de extensie .TXT. Deze naam is afhankelijk van de geëxporteerde bron en de exportdatum. Bijvoorbeeld: de naam profileBase_20150426_120253.txt zou op een profieluitvoer worden toegepast die op 26 april 2015 bij 12 :02: wordt uitgevoerd 53. Het is gecodeerd in UTF-8-indeling.

De numerieke waarden en datums houden rekening met de lokale tijd (landinstelling) van de gebruiker die het exporteren uitvoert. Bijvoorbeeld: DD-MM-YYYY of MM-DD-YYYY.

Als u een exportbewerking wilt uitvoeren die groter is dan deze, moet u een specifieke workflow maken. Verwijs naar de [&#x200B; dossier van de Extraheren &#x200B;](../../automating/using/extract-file.md) sectie.

**Voorbeeld**

In het volgende voorbeeld wordt een export uitgevoerd uit de onderstaande profiellijst:

* Getoonde kolommen (in volgorde): Achternaam, Voornaam, Geboortedatum, E-mailadres.
* Namen worden alfabetisch gesorteerd.

![](assets/export_list_example1.png)

Het gegenereerde bestand wordt als volgt weergegeven (voor de eerste tien records):

```
Last name;First name;Birth date;Email;Zip code
Abalo;Patrick;11/11/1941 02:00:00;patrick.a@testmail.com;29200
Abasq;Joel;21/08/1977 02:00:00;abasq.joel@testmail.com;92160
Abernot;John;12/07/1963 01:00:00;john.abernot@testmail.com;78510
Abiven;Christian;16/03/1975 01:00:00;chris.a@mailtest.com;35000
Abouvier;Peter;02/07/1975 01:00:00;pabouvier@mailtest.com;94560
Accardi;Mike;22/06/1948 01:00:00;mike.accardi@mail.com;76400
Accremont;Frank;27/04/1947 01:00:00;accr.frank@mailtest.com;13500
Adam;Daniel;17/09/1953 01:00:00;danieladam@mail.com;17000
Adama;Pascal;22/01/1990 01:00:00;adapascal@mailtest.com;75012
Adama;Henry;22/09/1992 02:00:00;henry.adama@mail.com;64120
```

**Verwante onderwerpen:**

* [Rollen](../../administration/using/list-of-roles.md)
* [Lijsten aanpassen](../../start/using/customizing-lists.md)

## Video over zelfstudie {#video}

Deze video laat zien hoe u lijsten kunt configureren.

>[!VIDEO](https://video.tv.adobe.com/v/25288/?quality=12)

De extra hoe te video&#39;s van Campaign Standard zijn beschikbaar [&#x200B; hier &#x200B;](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=nl).
