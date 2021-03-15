---
solution: Campaign Standard
product: campaign
title: Een meertalige pushmelding maken
description: Meertalige pushmeldingen maken om gebruikers in hun voorkeurstalen en -regio's te laten kiezen.
audience: channels
content-type: reference
topic-tags: push-notifications
feature: Push
role: Zakelijke praktiserer
level: Intermediair
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 3%

---


# Een meertalige pushmelding maken{#creating-a-multilingual-push-notification}

## Informatie over meertalige pushmelding {#about-multilingual-push-notification}

Pas de inhoud van uw pushmelding aan door berichten te verzenden die zijn gebaseerd op de voorkeurstalen en -regio&#39;s van uw gebruikers. U kunt inhoudsvarianten voor meertalige pushmeldingen rechtstreeks importeren in de inhoudeditor en een meertalig pushbericht verzenden in één levering.

Deze functie gebruikt de voorkeurstalen die zijn opgegeven in de profielen van ontvangers of de voorkeur voor de systeemtaal voor Mobile App Subscribers, afhankelijk van de leveringssjabloon die wordt gebruikt voor pushberichten. Als de taalvoorkeur niet voor een bepaalde gebruiker wordt bevolkt, zal het systeem de standaardvariant gebruiken die terwijl het creëren van een meertalige duw- bericht wordt bepaald. Voor meer informatie over hoe te om uw profielen en abonnees te beheren, verwijs naar deze [gids](../../audiences/using/get-started-profiles-and-audiences.md).

![](assets/multivariant_push_1.png)

Voer de volgende stappen uit als u meertalige inhoudvarianten wilt gebruiken voor het verzenden van pushberichten:

* [Stap 1: Variant voor meertalige inhoud uploaden](#step-1--upload-multilingual-content-variant)
* [Stap 2: Een pushmelding voorvertonen en voltooien met meertalige inhoudsvarianten](#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [Stap 3: Meertalige pushmeldingen verzenden en analyseren](#step-3--send-and-analyze-multilingual-push-notification-delivery)

## Stap 1: Variant {#step-1--upload-multilingual-content-variant} voor meertalige inhoud uploaden

Voordat u uw meertalige pushmelding kunt aanpassen, moeten we eerst de varianten in de inhoud uploaden in een meertalige leveringssjabloon en de levering maken.

>[!NOTE]
>
>U kunt deze stap ook overslaan als u een variant handmatig voor elke taalvariant wilt maken.

1. Klik in **[!UICONTROL Marketing activities]** op de knop **[!UICONTROL Create]** en selecteer **[!UICONTROL Push notification]**.
1. Selecteer de sjabloon **[!UICONTROL Send multilingual push to Campaign profiles]** als u de Adobe Campaign-profielen wilt activeren die zijn geabonneerd op uw mobiele toepassing of de sjabloon **[!UICONTROL Send multilingual push to app subscriber]** om een pushmelding te verzenden naar alle gebruikers die zich hebben aangemeld voor het ontvangen van berichten van uw mobiele toepassing.

   ![](assets/multivariant_push_2.png)

1. Voer de eigenschappen van uw pushmelding in en selecteer uw mobiele toepassing in het veld **[!UICONTROL Associate a Mobile App to a delivery]**.

   In het vervolgkeuzemenu worden zowel SDK V4- als Adobe Experience Platform SDK-toepassingen weergegeven.

1. In de **[!UICONTROL Audiences]** vensters, belemmering en dalingsvragen om uw publiek te verfijnen.

   De toegevoegde vragen hangen van het gekozen malplaatje af: Als u de sjabloon **[!UICONTROL Send multilingual push to Campaign profiles]** kiest, kunt u een query uitvoeren op bekende ontvangers van uw mobiele toepassing. Als u de sjabloon **[!UICONTROL Send multilingual push to app subscriber]** kiest, kunt u een query uitvoeren op alle abonnees van een bepaalde app die ervoor hebben gekozen.
   >[!NOTE]
   >
   >Als u doelgroepen richt met specifieke talen, moet u elke beoogde taal in uw CSV-bestand vermelden.

   ![](assets/push_notif_audience.png)

1. Sleep in het venster **[!UICONTROL Manage Content Variants]** het bestand en zet het neer of selecteer een bestand van uw computer.

   Het bestand moet UTF8-gecodeerd zijn en moet een specifieke indeling hebben die u kunt vinden door op de optie **[!UICONTROL Download the sample file]** te klikken. U moet ook de juiste syntaxis gebruiken voor waarden van landinstellingen. Raadpleeg [technote](https://docs.adobe.com/content/help/nl-NL/campaign-standard/using/communication-channels/push-notifications/generating-csv-multilingual-push.html) voor meer informatie over de bestandsindeling en de ondersteunde landinstellingen.

   ![](assets/multivariant_push_4.png)

1. Nadat u het bestand hebt geüpload, worden de taalvarianten automatisch ingevuld op het tabblad **[!UICONTROL Variants]**. U kunt een **[!UICONTROL Default variant]** opgeven in het bestand. Dit is de standaard inhoudvariant als er geen voorkeurstaal is opgegeven voor de doelgebruiker.

   ![](assets/multivariant_push_5.png)

1. Het tabblad **[!UICONTROL Variant selection]** bevat een script waarmee wordt bepaald met welke taalvoorkeur rekening moet worden gehouden, afhankelijk van de leveringssjabloon. Dit is een out-of-the-box manuscript dat u niet vereist om het even welke veranderingen aan te brengen.
1. Als u meer varianten wilt toevoegen die niet aanwezig zijn in het geïmporteerde bestand, kunt u dit doen door op de knop **[!UICONTROL Add an element]** te klikken en zoveel nieuwe taalvarianten toe te voegen als nodig is.

   Door andere varianten toe te voegen dan de varianten die uit het bestand zijn geüpload, wordt er geen inhoud aan deze taal gekoppeld. U moet de inhoud rechtstreeks in het dashboard voor levering bewerken.

   ![](assets/multivariant_push_6.png)

1. Klik **[!UICONTROL Create]** wanneer de configuratie wordt gedaan. U kunt altijd terugkeren naar het venster **[!UICONTROL Content variant]** en enkele wijzigingen aanbrengen vanaf het dashboard voor de levering.

   ![](assets/multivariant_push_8.png)

U kunt nu uw meertalige pushmelding aanpassen.

## Stap 2: Een pushmelding voorvertonen en voltooien met meertalige inhoudsvarianten {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

Nadat u het bestand met de inhoudvarianten hebt geüpload, kunt u nu een voorvertoning weergeven van de verschillende varianten vanaf de levering van het pushbericht.

Het is ook mogelijk om meer varianten te maken en te bewerken naast de varianten die uit het bestand zijn geüpload.

1. In het **[!UICONTROL Content]** venster van het leveringsdashboard, staat de drop-down u toe om uw inhoud van het dupbericht afhankelijk van de gekozen taal te voorproef.

   ![](assets/multivariant_push_7.png)

1. Als er geen inhoudvariant is opgegeven voor een bepaalde taal, klikt u op het belpictogram onder de voorvertoning om inhoud toe te voegen aan deze taalvariant.

   Door op het venster **[!UICONTROL Content]** te klikken, vertegenwoordigt het pushbericht de inhoud van de taal die is geselecteerd in de vervolgkeuzelijst. Wijzigingen die u in dit venster aanbrengt, zijn slechts van invloed op één taal.

1. U kunt ook op een inhoudvariant klikken om deze verder aan te passen, bijvoorbeeld met verpersoonlijkingsvelden.

   Raadpleeg deze [sectie](../../channels/using/customizing-a-push-notification.md) voor meer informatie over het aanpassen van uw pushmelding.

   ![](assets/multivariant_push_9.png)

1. Klik op het venster **[!UICONTROL Content variant]** als u taalvarianten wilt toevoegen of verwijderen.

   Door een nieuwe taal toe te voegen, moet u handmatig inhoud toevoegen aan het pushbericht dat aan de toegevoegde taal is gekoppeld.

   ![](assets/multivariant_push_10.png)

Uw meertalige pushmelding kan nu worden verzonden.

## Stap 3: Meertalig pushbericht verzenden en analyseren {#step-3--send-and-analyze-multilingual-push-notification-delivery}

Uw meertalige contentvariantpushberichten kunnen nu naar uw gebruikers worden verzonden.

1. Klik op de knop **[!UICONTROL Prepare]** om het verzenden voor te bereiden.
1. Wanneer de voorbereiding zonder waarschuwingen wordt gebeëindigd, kunt u de **[!UICONTROL Confirm]** knoop klikken beginnen uw meertalige duw te verzenden.

   ![](assets/multivariant_push_12.png)

1. Nadat het verzenden van uw pushmelding is gelukt, klikt u op het pictogram **[!UICONTROL Reports]** en **[!UICONTROL Dynamic reports]** om het succes van de levering te analyseren.

   ![](assets/multivariant_push_13.png)

1. Selecteer **[!UICONTROL Push notification report]**.
1. Sleep de **[!UICONTROL Variant]**-dimensie naar het deelvenster om uw gegevens te filteren.

   ![](assets/multivariant_push_11.png)

U kunt nu de impact van uw meertalige pushmelding op uw ontvangers meten.

**Verwante onderwerpen:**

* [Pushmeldingenrapport](../../reporting/using/push-notification-report.md)
* [Een pushmelding verzenden binnen een workflow](../../automating/using/push-notification-delivery.md)
* [Meertalig publiek bereiken met één workflow](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
