---
title: Een meertalige pushmelding maken
description: Meertalige pushmeldingen maken om gebruikers in hun voorkeurstalen en -regio's te laten kiezen.
audience: channels
content-type: reference
topic-tags: push-notifications
feature: Push
role: User
level: Intermediate
exl-id: 1b81f6e9-cb31-4664-af78-22e70043fbc8
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 2%

---

# Een meertalige pushmelding maken{#creating-a-multilingual-push-notification}

## Meertalige pushmelding {#about-multilingual-push-notification}

Pas de inhoud van uw pushmelding aan door berichten te verzenden die zijn gebaseerd op de voorkeurstalen en -regio&#39;s van uw gebruikers. U kunt inhoudsvarianten voor meertalige pushmeldingen rechtstreeks importeren in de inhoudeditor en een meertalig pushbericht verzenden in één levering.

Deze functie gebruikt de voorkeurstalen die zijn opgegeven in de profielen van ontvangers of de voorkeur voor de systeemtaal voor Mobile App Subscribers, afhankelijk van de leveringssjabloon die wordt gebruikt voor pushberichten. Als de taalvoorkeur niet voor een bepaalde gebruiker wordt bevolkt, zal het systeem de standaardvariant gebruiken die terwijl het creëren van een meertalige duw- bericht wordt bepaald. Raadpleeg voor meer informatie over het beheren van uw profielen en abonnees deze [hulplijn](../../audiences/using/get-started-profiles-and-audiences.md).

![](assets/multivariant_push_1.png)

Voer de volgende stappen uit als u meertalige inhoudvarianten wilt gebruiken voor het verzenden van pushberichten:

* [Stap 1: De meertalige inhoudvariant uploaden](#step-1--upload-multilingual-content-variant)
* [Stap 2: Een pushmelding voorvertonen en voltooien met meertalige inhoudvarianten](#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [Stap 3: de levering van meertalige pushmeldingen verzenden en analyseren](#step-3--send-and-analyze-multilingual-push-notification-delivery)

## Stap 1: De meertalige inhoudvariant uploaden {#step-1--upload-multilingual-content-variant}

Voordat u uw meertalige pushmelding kunt aanpassen, moeten we eerst de varianten in de inhoud uploaden in een meertalige leveringssjabloon en de levering maken.

>[!NOTE]
>
>U kunt deze stap ook overslaan als u een variant handmatig voor elke taalvariant wilt maken.

1. In de **[!UICONTROL Marketing activities]** klikt u op de knop **[!UICONTROL Create]** dan selecteert u **[!UICONTROL Push notification]**.
1. Selecteer de sjabloon **[!UICONTROL Send multilingual push to Campaign profiles]** als u de Adobe Campaign-profielen wilt activeren die zijn geabonneerd op uw mobiele toepassing of de sjabloon **[!UICONTROL Send multilingual push to app subscriber]** om een pushmelding te verzenden naar alle gebruikers die zich hebben aangemeld voor het ontvangen van berichten van uw mobiele toepassing.

   ![](assets/multivariant_push_2.png)

1. Voer de eigenschappen van uw pushmelding in en selecteer uw mobiele app in het dialoogvenster **[!UICONTROL Associate a Mobile App to a delivery]** veld.

   In het vervolgkeuzemenu worden zowel SDK V4- als Adobe Experience Platform SDK-toepassingen weergegeven.

1. In de **[!UICONTROL Audiences]** vensters, slepen en neerzetten vragen om uw publiek af te stemmen.

   De toegevoegde vragen hangen van het gekozen malplaatje af: als u verkoos **[!UICONTROL Send multilingual push to Campaign profiles]** sjabloon die u kunt opvragen bij bekende ontvangers van uw mobiele toepassing. Als u de optie **[!UICONTROL Send multilingual push to app subscriber]** in de sjabloon, kunt u een query uitvoeren op alle abonnees van een bepaalde app die zich hebben aangemeld.
   >[!NOTE]
   >
   >Als u doelgroepen richt met specifieke talen, moet u elke beoogde taal in uw CSV-bestand vermelden.

   ![](assets/push_notif_audience.png)

1. In de **[!UICONTROL Manage Content Variants]** , sleep en zet het bestand neer of selecteer een bestand van uw computer.

   Het bestand moet UTF8-gecodeerd zijn en moet een specifieke indeling hebben die u kunt vinden door op het tabblad **[!UICONTROL Download the sample file]** -optie. U moet ook de juiste syntaxis gebruiken voor waarden van landinstellingen. Raadpleeg voor meer informatie over de bestandsindeling en de ondersteunde landinstellingen [page](../../channels/using/generating-csv-multilingual-push.md).

   ![](assets/multivariant_push_4.png)

1. Nadat u het bestand hebt geüpload, worden de taalvarianten automatisch ingevuld in het dialoogvenster **[!UICONTROL Variants]** tab. U kunt een **[!UICONTROL Default variant]** in het bestand dat uw standaardinhoudsvariant zal zijn als er geen voorkeurstaal is opgegeven voor de doelgebruiker.

   ![](assets/multivariant_push_5.png)

1. De **[!UICONTROL Variant selection]** tab geeft een script om te bepalen met welke taalvoorkeur rekening moet worden gehouden, afhankelijk van de leveringssjabloon. Dit is een out-of-the-box manuscript dat u niet vereist om het even welke veranderingen aan te brengen.
1. Als u meer varianten wilt toevoegen die niet aanwezig zijn in het geïmporteerde bestand, kunt u dit doen door op de knop **[!UICONTROL Add an element]** en voeg zoveel nieuwe taalvarianten toe als nodig is.

   Door andere varianten toe te voegen dan de varianten die uit het bestand zijn geüpload, wordt er geen inhoud aan deze taal gekoppeld. U moet de inhoud rechtstreeks in het dashboard voor levering bewerken.

   ![](assets/multivariant_push_6.png)

1. Klikken **[!UICONTROL Create]** wanneer de configuratie is voltooid. U kunt altijd terugkomen op de **[!UICONTROL Content variant]** en breng enkele wijzigingen aan vanaf het dashboard voor levering.

   ![](assets/multivariant_push_8.png)

U kunt nu uw meertalige pushmelding aanpassen.

## Stap 2: Een pushmelding voorvertonen en voltooien met meertalige inhoudvarianten {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

Nadat u het bestand met de inhoudvarianten hebt geüpload, kunt u nu een voorvertoning weergeven van de verschillende varianten vanaf de levering van het pushbericht.

Het is ook mogelijk om meer varianten te maken en te bewerken naast de varianten die uit het bestand zijn geüpload.

1. In de **[!UICONTROL Content]** kunt u in de vervolgkeuzelijst een voorvertoning van de inhoud van uw pushmelding weergeven, afhankelijk van de gekozen taal.

   ![](assets/multivariant_push_7.png)

1. Als er geen inhoudvariant is opgegeven voor een bepaalde taal, klikt u op het belpictogram onder de voorvertoning om inhoud toe te voegen aan deze taalvariant.

   Klik op de knop **[!UICONTROL Content]** in het venster vertegenwoordigt de pushmelding de inhoud van de taal die is geselecteerd in de vervolgkeuzelijst. Wijzigingen die u in dit venster aanbrengt, zijn slechts van invloed op één taal.

1. U kunt ook op een inhoudvariant klikken om deze verder aan te passen, bijvoorbeeld met verpersoonlijkingsvelden.

   Raadpleeg deze voor meer informatie over het aanpassen van uw pushmelding [sectie](../../channels/using/customizing-a-push-notification.md).

   ![](assets/multivariant_push_9.png)

1. Klik op de knop **[!UICONTROL Content variant]** venster als u taalvarianten wilt toevoegen of verwijderen.

   Door een nieuwe taal toe te voegen, moet u handmatig inhoud toevoegen aan het pushbericht dat aan de toegevoegde taal is gekoppeld.

   ![](assets/multivariant_push_10.png)

Uw meertalige pushmelding kan nu worden verzonden.

## Stap 3: de levering van meertalige pushmeldingen verzenden en analyseren {#step-3--send-and-analyze-multilingual-push-notification-delivery}

Uw meertalige contentvariantpushberichten kunnen nu naar uw gebruikers worden verzonden.

1. Als u het verzenden wilt voorbereiden, klikt u op de knop **[!UICONTROL Prepare]** knop.
1. Wanneer de voorbereiding zonder waarschuwingen wordt gebeëindigd, kunt u klikken op **[!UICONTROL Confirm]** om uw meertalige push te verzenden.

   ![](assets/multivariant_push_12.png)

1. Nadat u de pushmelding hebt verzonden, klikt u op de knop **[!UICONTROL Reports]** pictogram vervolgens **[!UICONTROL Dynamic reports]** om het succes van uw levering te analyseren.

   ![](assets/multivariant_push_13.png)

1. Selecteer **[!UICONTROL Push notification report]**.
1. Sleep de **[!UICONTROL Variant]** dimensie aan uw paneel beginnen uw gegevens te filtreren.

   ![](assets/multivariant_push_11.png)

U kunt nu de impact van uw meertalige pushmelding op uw ontvangers meten.

**Verwante onderwerpen:**

* [Pushmeldingenrapport](../../reporting/using/push-notification-report.md)
* [Een pushmelding verzenden binnen een workflow](../../automating/using/push-notification-delivery.md)
