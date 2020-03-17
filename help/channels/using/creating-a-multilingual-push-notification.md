---
title: Meertalige pushmeldingen maken
description: Meertalige pushmeldingen maken om gebruikers in hun voorkeurstalen en -regio's te laten kiezen.
page-status-flag: never-activated
uuid: d4aff741-e969-47c6-bae8-787c6c673191
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: f9bb2235-d388-4025-9ace-734beb0c1961
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fc9c6371732aa0eba9e675d2709cd62c25b27b96

---


# Meertalige pushmeldingen maken{#creating-a-multilingual-push-notification}

## Meertalige pushmelding {#about-multilingual-push-notification}

Pas de inhoud van uw pushmelding aan door berichten te verzenden die zijn gebaseerd op de voorkeurstalen en -regio&#39;s van uw gebruikers. U kunt inhoudsvarianten voor meertalige pushmeldingen rechtstreeks importeren in de inhoudeditor en een meertalig pushbericht verzenden in één levering.

Deze functie gebruikt de voorkeurstalen die zijn opgegeven in de profielen van ontvangers of de voorkeur voor de systeemtaal voor Mobile App Subscribers, afhankelijk van de leveringssjabloon die wordt gebruikt voor pushberichten. Als de taalvoorkeur niet voor een bepaalde gebruiker wordt bevolkt, zal het systeem de standaardvariant gebruiken die terwijl het creëren van een meertalige duw- bericht wordt bepaald. Raadpleeg deze [handleiding voor meer informatie over het beheren van uw profielen en abonnees](../../audiences/using/about-profiles-and-audiences.md).

![](assets/multivariant_push_1.png)

Voer de volgende stappen uit als u meertalige inhoudvarianten wilt gebruiken voor het verzenden van pushberichten:

* [Stap 1: Variant voor meertalige inhoud uploaden](#step-1--upload-multilingual-content-variant)
* [Stap 2: Een pushmelding voorvertonen en voltooien met meertalige inhoudsvarianten](#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [Stap 3: Meertalige pushmeldingen verzenden en analyseren](#step-3--send-and-analyze-multilingual-push-notification-delivery)

## Stap 1: Variant voor meertalige inhoud uploaden {#step-1--upload-multilingual-content-variant}

Voordat u uw meertalige pushmelding kunt aanpassen, moeten we eerst de varianten in de inhoud uploaden in een meertalige leveringssjabloon en de levering maken.

>[!NOTE]
>
>U kunt deze stap ook overslaan als u een variant handmatig voor elke taalvariant wilt maken.

1. Klik in het **[!UICONTROL Marketing activities]** dialoogvenster op de **[!UICONTROL Create]** knop en selecteer **[!UICONTROL Push notification]**.
1. Selecteer de sjabloon **[!UICONTROL Send multilingual push to Campaign profiles]** als u de Adobe Campagne-profielen wilt activeren die zijn geabonneerd op uw mobiele toepassing of de sjabloon **[!UICONTROL Send multilingual push to app subscriber]** om een pushmelding te verzenden naar alle gebruikers die zich hebben aangemeld om meldingen van uw mobiele toepassing te ontvangen.

   ![](assets/multivariant_push_2.png)

1. Voer de eigenschappen van uw pushmelding in en selecteer uw mobiele app in het **[!UICONTROL Associate a Mobile App to a delivery]** veld.

   In het vervolgkeuzemenu worden SDK V4- en Adobe Experience Platform SDK&#39;s-toepassingen weergegeven.

1. In de **[!UICONTROL Audiences]** vensters, belemmering en dalingsvragen om uw publiek te verfijnen.

   De toegevoegde vragen hangen van het gekozen malplaatje af: als u de **[!UICONTROL Send multilingual push to Campaign profiles]** sjabloon kiest, kunt u een query uitvoeren op bekende ontvangers van uw mobiele toepassing. Als u de **[!UICONTROL Send multilingual push to app subscriber]** sjabloon kiest, kunt u een query uitvoeren op alle abonnees van een bepaalde app die ervoor hebben gekozen.
   >[!NOTE]
   >
   >Als u doelgroepen richt met specifieke talen, moet u elke beoogde taal in uw CSV-bestand vermelden.

   ![](assets/push_notif_audience.png)

1. Sleep het bestand in het **[!UICONTROL Manage Content Variants]** venster en zet het neer of selecteer een bestand van de computer.

   Het bestand moet UTF8-gecodeerd zijn en moet een specifieke indeling hebben die u kunt vinden door op de **[!UICONTROL Download the sample file]** optie te klikken. U moet ook de juiste syntaxis gebruiken voor waarden van landinstellingen. Raadpleeg dit [technische artikel voor meer informatie over de bestandsindeling en de ondersteunde landinstellingen](https://helpx.adobe.com/campaign/kb/acs-generate-csv-multilingual-push.html).

   ![](assets/multivariant_push_4.png)

1. Nadat u het bestand hebt geüpload, worden de taalvarianten automatisch ingevuld op het **[!UICONTROL Variants]** tabblad. Let op: u kunt een **[!UICONTROL Default variant]** code in het bestand opgeven die uw standaardinhoudsvariant zal zijn als er geen voorkeurstaal is opgegeven voor de doelgebruiker.

   ![](assets/multivariant_push_5.png)

1. Het **[!UICONTROL Variant selection]** lusje zal een manuscript verstrekken om te bepalen welke taalvoorkeur om rekening te houden afhankelijk van het leveringsmalplaatje. Dit is een out-of-the-box manuscript dat u niet vereist om het even welke veranderingen aan te brengen.
1. Als u meer varianten wilt toevoegen die niet aanwezig zijn in het geïmporteerde bestand, kunt u dit doen door op de **[!UICONTROL Add an element]** knop te klikken en zoveel nieuwe taalvarianten toe te voegen als nodig is.

   Door andere varianten toe te voegen dan de varianten die uit het bestand zijn geüpload, wordt er geen inhoud aan deze taal gekoppeld. U moet de inhoud rechtstreeks in het dashboard voor levering bewerken.

   ![](assets/multivariant_push_6.png)

1. Klik **[!UICONTROL Create]** wanneer de configuratie wordt gedaan. U kunt altijd terugkeren naar het **[!UICONTROL Content variant]** venster en wijzigingen aanbrengen vanaf het dashboard voor levering.

   ![](assets/multivariant_push_8.png)

U kunt nu uw meertalige pushmelding aanpassen.

## Stap 2: Een pushmelding voorvertonen en voltooien met meertalige inhoudsvarianten {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

Nadat u het bestand met de inhoudvarianten hebt geüpload, kunt u nu een voorvertoning weergeven van de verschillende varianten vanaf de levering van het pushbericht.

Het is ook mogelijk om meer varianten te maken en te bewerken naast de varianten die uit het bestand zijn geüpload.

1. In het **[!UICONTROL Content]** venster van het leveringsdashboard, staat de drop-down u toe om uw inhoud van het dupbericht afhankelijk van de gekozen taal voor te vertonen.

   ![](assets/multivariant_push_7.png)

1. Als er geen inhoudvariant is opgegeven voor een bepaalde taal, klikt u op het belpictogram onder de voorvertoning om inhoud toe te voegen aan deze taalvariant.

   Door op het **[!UICONTROL Content]** venster te klikken vertegenwoordigt het pushbericht de inhoud van de taal die in de vervolgkeuzelijst is geselecteerd. Wijzigingen die u in dit venster aanbrengt, zijn slechts van invloed op één taal.

1. U kunt ook op een inhoudvariant klikken om deze verder aan te passen, bijvoorbeeld met verpersoonlijkingsvelden.

   Raadpleeg deze [sectie](../../channels/using/customizing-a-push-notification.md)voor meer informatie over het aanpassen van uw pushmelding.

   ![](assets/multivariant_push_9.png)

1. Klik op het **[!UICONTROL Content variant]** venster als u taalvarianten wilt toevoegen of verwijderen.

   Door een nieuwe taal toe te voegen, moet u handmatig inhoud toevoegen aan het pushbericht dat aan de toegevoegde taal is gekoppeld.

   ![](assets/multivariant_push_10.png)

Uw meertalige pushmelding kan nu worden verzonden.

## Stap 3: Meertalige pushmeldingen verzenden en analyseren {#step-3--send-and-analyze-multilingual-push-notification-delivery}

Uw meertalige contentvariantpushberichten kunnen nu naar uw gebruikers worden verzonden.

1. Klik op de **[!UICONTROL Prepare]** knop om het verzenden voor te bereiden.
1. Wanneer de voorbereiding zonder waarschuwingen klaar is, kunt u op de **[!UICONTROL Confirm]** knop klikken om uw meertalige drukknop te verzenden.

   ![](assets/multivariant_push_12.png)

1. Nadat u uw pushmelding hebt verzonden, klikt u op het **[!UICONTROL Reports]** pictogram en analyseert u vervolgens **[!UICONTROL Dynamic reports]** het succes van de levering.

   ![](assets/multivariant_push_13.png)

1. Selecteer **[!UICONTROL Push notification report]**.
1. Sleep de **[!UICONTROL Variant]** dimensie naar het deelvenster om de gegevens te filteren.

   ![](assets/multivariant_push_11.png)

U kunt nu de impact van uw meertalige pushmelding op uw ontvangers meten.

**Verwante onderwerpen:**

* [Pushmeldingsrapport](../../reporting/using/push-notification-report.md)
* [Een pushmelding verzenden binnen een workflow](../../automating/using/push-notification-delivery.md)
* [Meertalig publiek bereiken met één workflow](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
