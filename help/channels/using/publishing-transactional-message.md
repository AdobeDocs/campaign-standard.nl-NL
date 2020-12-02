---
solution: Campaign Standard
product: campaign
title: Transactieberichten voor gebeurtenissen
description: Leer hoe u een transactiebericht voor een gebeurtenis maakt en publiceert.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: 4e157a582de836fa325d95593491c756209b205e
workflow-type: tm+mt
source-wordcount: '1352'
ht-degree: 77%

---


# Levenscyclus van transactieberichten {#publishing-transactional-message}

Wanneer het [transactioneel bericht](../../channels/using/editing-transactional-message.md) klaar is om te worden verzonden, kan het worden gepubliceerd.

De stappen voor het testen, publiceren, pauzeren, publiceren en verwijderen van een gebeurtenis worden hieronder beschreven. Deze sectie beschrijft ook het transactionele overseinenproces opnieuw proberen.

## Publicatieproces voor transactieberichten {#transactional-messaging-pub-process}

De grafiek hieronder illustreert het algemene proces van de transactionele berichtpublicatie.

![](assets/message-center_pub-process.png)

Zie [deze sectie](#publishing-a-transactional-message) voor meer informatie over het publiceren van een transactiebericht.
Zie [deze sectie](#suspending-a-transactional-message-publication) voor meer informatie over het pauzeren van een transactiebericht.
Zie [deze sectie](#unpublishing-a-transactional-message) voor meer informatie over het ongedaan maken van het publiceren van een transactiebericht.

Zie [deze sectie](../../channels/using/publishing-transactional-event.md) voor meer informatie over het publiceren en verwijderen van het publiceren van een gebeurtenis.

## Een transactiebericht testen {#testing-a-transactional-message}

Eerst moet u een specifiek testprofiel maken waarmee u het transactiemelding correct kunt controleren.

### Een specifiek testprofiel {#defining-specific-test-profile} definiëren

Definieer een testprofiel dat aan uw gebeurtenis wordt gekoppeld. Hiermee kunt u een voorbeeld van uw bericht bekijken en een relevante proefdruk verzenden.

1. Klik op de knop **[!UICONTROL Create test profile]** van het transactiemelddashboard.

   ![](assets/message-center_test-profile.png)

1. Geef de informatie die u wilt verzenden op in de JSON-indeling in de sectie **[!UICONTROL Event data used for personalization]**. Dit is de content die wordt gebruikt wanneer een voorbeeld van het bericht wordt weergegeven en wanneer het testprofiel de proef ontvangt.

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >U kunt ook de informatie over de profieltabel invoeren. Zie [De gebeurtenis verrijken](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)<!--and [Personalizing a transactional message](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)-->.

1. Zodra gecreeerd, zal het testprofiel vooraf gespecificeerd in het transactiebericht zijn. Klik op het blok **[!UICONTROL Test profiles]** van het bericht om het doel van de proef te controleren.

   ![](assets/message-center_5.png)

U kunt ook een nieuw testprofiel maken of een profiel gebruiken dat al in het menu **[!UICONTROL Test profiles]** staat. Dit doet u als volgt:

1. Klik in de linkerbovenhoek op het logo **[!UICONTROL Adobe Campaign]** en selecteer **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**.
1. Selecteer in de sectie **[!UICONTROL Event]** de gebeurtenis die u zojuist hebt gemaakt. In dit voorbeeld selecteert u Cart abandonment (EVTcartAbandonment).
1. Geef in het tekstvak **[!UICONTROL Event data]** de informatie op die u in de JSON-indeling wilt verzenden.

   ![](assets/message-center_3.png)

1. Sla uw wijzigingen op.
1. Open het bericht dat u hebt gemaakt en selecteer het bijgewerkte testprofiel.

**Verwante onderwerpen:**

* [Testprofielen beheren](../../audiences/using/managing-test-profiles.md)
* [Doelgroepen maken](../../audiences/using/creating-audiences.md)

### De proefdruk {#sending-proof} verzenden

Nadat u een of meer specifieke testprofielen hebt gemaakt en uw transactiebericht hebt opgeslagen, kunt u een proefdruk verzenden om dit te testen.

![](assets/message-center_10.png)

De stappen voor het verzenden van een proefdruk worden beschreven in de sectie [Proofs verzenden](../../sending/using/sending-proofs.md).

## Transactiebericht publiceren {#publishing-a-transactional-message}

Nadat u het transactiebericht hebt gecontroleerd, kunt u het publiceren.

![](assets/message-center_12.png)

Zodra de gebeurtenis ‘Cart abandonment’ wordt geactiveerd, wordt automatisch een bericht verzonden met de titel en de achternaam van de ontvanger, de URL naar de winkelwagen, het laatst geraadpleegde product of een lijst met producten (als u een productvermelding hebt gedefinieerd) en het totale bedrag van de winkelwagen.

Klik op de knop **[!UICONTROL Reports]** voor toegang tot rapporten over uw transactiebericht. Zie [Dynamische rapporten](../../reporting/using/about-dynamic-reports.md).

![](assets/message-center_13.png)

### Opschorting van de publicatie van een transactiebericht {#suspending-a-transactional-message-publication}

U kunt het publiceren van uw transactiebericht opschorten met behulp van de knop **[!UICONTROL Pause]**, bijvoorbeeld als u de data in het bericht wilt wijzigen. De gebeurtenissen worden daarom niet meer verwerkt, maar in plaats daarvan in een wachtrij in de Adobe Campaign-database opgeslagen.

De gebeurtenissen in de wachtrij worden bewaard gedurende een periode die is gedefinieerd in de REST API (zie de [REST API-documentatie](../../api/using/managing-transactional-messages.md) of in de triggergebeurtenis als u de Triggers Core-service gebruikt (zie [Informatie over Adobe Experience Cloud Triggers](../../integrating/using/about-adobe-experience-cloud-triggers.md)).

![](assets/message-center_pause.png)

Na het klikken op **[!UICONTROL Resume]** worden alle gebeurtenissen in de wachtrij verwerkt (op voorwaarde dat deze niet verlopen zijn). Zij bevatten nu alle wijzigingen die zijn uitgevoerd terwijl de publicatie van de sjabloon was opgeschort.

### Het publiceren van een transactiebericht opheffen {#unpublishing-a-transactional-message}

Door op **[!UICONTROL Unpublish]** te klikken, kunt de publicatie van transactionele berichten en de publicatie van de overeenkomstige gebeurtenis annuleren, waardoor de resource overeenkomend aan de eerder aangemaakte gebeurtenis uit de REST API wordt verwijderd.

![](assets/message-center_unpublish-template.png)

Zelfs als de gebeurtenis via uw website wordt geactiveerd, worden de bijbehorende berichten niet meer verzonden en niet opgeslagen in de database.

>[!NOTE]
>
>Als u het bericht opnieuw wilt publiceren, moet u teruggaan naar de corresponderende gebeurtenisconfiguratie, [de gebeurtenis ](../../channels/using/publishing-transactional-event.md) publiceren en vervolgens [het bericht](#publishing-a-transactional-message) publiceren.

Als u de publicatie van een gepauzeerd transactiebericht ongedaan maakt, moet u mogelijk tot 24 uur wachten voordat u het bericht opnieuw kunt publiceren. Zo kan de workflow **[!UICONTROL Database cleanup]** alle gebeurtenissen opschonen die naar de wachtrij zijn verzonden.

De stappen voor het pauzeren van een bericht worden uitgebreid beschreven in de sectie[Opschorting van de publicatie van een transactiebericht](#suspending-a-transactional-message-publication).

De workflow **[!UICONTROL Database cleanup]**, die elke dag om 4.00 uur wordt uitgevoerd, is toegankelijk via **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Workflows]**.

### Transactiebericht verwijderen {#deleting-a-transactional-message}

Als de publicatie van een transactiebericht ongedaan is gemaakt, of als een transactiebericht nog niet is gepubliceerd, kunt u het transactiebericht uit de lijst met transactieberichten verwijderen. Dit doet u als volgt:

1. Klik in de linkerbovenhoek op het logo **[!UICONTROL Adobe Campaign]** en selecteer **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.
1. Houd de muis boven het gewenste bericht.
1. Klik op de knop **[!UICONTROL Delete element]**.

![](assets/message-center_delete-template.png)

Het verwijderen van een transactiebericht kan echter alleen onder bepaalde voorwaarden worden uitgevoerd:

* Zorg ervoor dat het transactiebericht de status **[!UICONTROL Draft]** heeft, anders kunt u het bericht niet verwijderen. De status **[!UICONTROL Draft]** is van toepassing op een bericht dat nog niet is gepubliceerd of waarvan [de publicatie ongedaan is gemaakt](#unpublishing-a-transactional-message) (en niet is [gepauzeerd](#suspending-a-transactional-message-publication)).

* **Transactieberichten**: Tenzij een ander transactiebericht is gekoppeld aan de overeenkomstige gebeurtenis, geldt dat als de publicatie van het transactiebericht ongedaan is gemaakt de publicatie van de gebeurtenisconfiguratie ook ongedaan moet worden gemaakt om uw transactiebericht te kunnen verwijderen. Zie [Publicatie van een gebeurtenis ongedaan maken](../../channels/using/publishing-transactional-event.md#unpublishing-an-event) voor meer informatie.

   >[!IMPORTANT]
   >
   >Als u een transactiebericht verwijdert waarvoor al meldingen zijn verzonden, worden ook de verzendings- en trackinglogboeken verwijderd.

* **Transactieberichten van een kant-en-klare gebeurtenissjabloon (interne transactieberichten)**: Als een intern transactiebericht als enige bericht aan de overeenkomstige interne gebeurtenis is gekoppeld, kan het niet worden verwijderd. U moet eerst een ander transactiebericht maken door het te dupliceren of via het menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Transactional message templates]**.

## Proces voor het opnieuw bezorgen van een transactiebericht {#transactional-message-retry-process}

Er wordt automatisch opnieuw geprobeerd een tijdelijk onbezorgd transactiebericht te verzenden totdat de levering is vervallen. Zie [Parameters voor geldigheidsperiode](../../administration/using/configuring-email-channel.md#validity-period-parameters) voor meer informatie over de leveringsduur.

Wanneer een transactiebericht niet kan worden verzonden, zijn er twee systemen om het opnieuw te proberen:

* Op transactioneel berichtniveau kan een transactiebericht mislukken voordat de gebeurtenis aan een uitvoeringslevering wordt toegewezen, dus tussen de ontvangst van de gebeurtenis en de voorbereiding van de levering. Zie [Proces nieuwe verwerkingspogingen voor gebeurtenissen](#event-processing-retry-process).
* Qua verzendingsproces kan het transactiebericht vanwege een tijdelijke fout mislukken als de gebeurtenis eenmaal aan een uitvoeringslevering is toegewezen. Zie [Proces voor het opnieuw verzenden van een bericht](#message-sending-retry-process).

### Proces nieuwe verwerkingspogingen voor gebeurtenissen {#event-processing-retry-process}

De gebeurtenisverwerking wordt uitgesteld als de gebeurtenis niet aan een uitvoeringslevering kan worden toegewezen. Hernieuwde pogingen worden uitgevoerd tot de gebeurtenis aan een nieuwe uitvoeringslevering wordt toegewezen.

>[!NOTE]
>
>Een uitgestelde gebeurtenis wordt niet weergegeven in de verzendingslogboeken voor transactieberichten, omdat deze gebeurtenis nog niet is toegewezen aan een uitvoeringslevering.

De gebeurtenis kan bijvoorbeeld niet worden toegewezen aan een uitvoeringslevering omdat de content niet correct is, er een probleem is met toegangsrechten of branding, er een fout is ontdekt bij het toepassen van typologische regels, enz. In dit geval kunt u het bericht pauzeren, het bewerken om het probleem op te lossen en het opnieuw publiceren. Het systeem voor hernieuwde pogingen wijst het bericht dan toe aan een nieuwe uitvoeringslevering.

### Proces voor het opnieuw verzenden van een bericht {#message-sending-retry-process}

Zodra de gebeurtenis aan een uitvoeringslevering is toegewezen, kan het transactiebericht wegens een tijdelijke fout mislukken, bijvoorbeeld als de mailbox van de ontvanger vol is. Zie [Hernieuwde pogingen na een tijdelijke leveringsfout](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)voor meer informatie.

>[!NOTE]
>
>Pas wanneer een gebeurtenis aan een uitvoeringslevering wordt toegewezen, verschijnt het in de verzendingslogboeken van deze uitvoeringslevering. De mislukte leveringen worden weergegeven op het tabblad **[!UICONTROL Execution list]** van het transactionele bericht dat logbestanden verzendt.

### Procesbeperkingen {#limitations} opnieuw proberen

**Verzendingslogboeken bijwerken**

Tijdens de hernieuwde pogingen worden de verzendingslogboeken van de nieuwe uitvoeringslevering niet onmiddellijk bijgewerkt (het bijwerken wordt uitgevoerd door een geplande workflow). Dit betekent dat het bericht de status **[!UICONTROL Pending]** kan hebben, zelfs als de transactiegebeurtenis door de nieuwe uitvoeringslevering is verwerkt.

**Uitvoering mislukt**

U kunt een uitvoeringslevering niet stoppen. Als de huidige uitvoeringslevering echter mislukt, wordt er een nieuwe levering gemaakt zodra een nieuwe gebeurtenis wordt ontvangen en worden alle nieuwe gebeurtenissen door deze nieuwe uitvoeringslevering verwerkt. Er worden geen nieuwe gebeurtenissen door de mislukte uitvoeringslevering verwerkt.

Als sommige gebeurtenissen die al aan een uitvoeringslevering zijn toegewezen zijn uitgesteld en als die uitvoeringslevering mislukt, wijst het systeem voor hernieuwde pogingen de uitgestelde gebeurtenissen niet toe aan de nieuwe uitvoeringslevering. Dat betekent dus dat deze gebeurtenissen verloren gaan.