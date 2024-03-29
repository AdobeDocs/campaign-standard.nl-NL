---
title: Hot clicks
description: Met het Hete klikt uit-van-de-doos rapport, leer waar uw klant op uw levering klikte.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryHotClicksReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 5af37156-e93b-4ae9-9856-053364f211ef
source-git-commit: d0ef11f26a52603107af28231d70821b44753abb
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 0%

---

# Hot clicks{#hot-clicks}

>[!IMPORTANT]
>
>In het rapport Hot Clicks wordt alleen de HTML-versie van het e-mailbericht weergegeven en wordt de tekstversie niet ondersteund.

Dit rapport is toegankelijk via de **[!UICONTROL Reports]** in elk bezorgings- of transactiebericht.

![](assets/delivery_reports_hot-clicks_4.png)

Het stelt de berichtinhoud met het percentage van kliks op elke verbinding voor.

![](assets/delivery_reports_10.png)

Als u dynamische inhoud hebt gemaakt voor levering, kunt u de percentages bekijken voor elke voorwaarde die u hebt gedefinieerd. Zie voor meer informatie over het invoegen van voorwaardelijke inhoud in een levering [Dynamische inhoud definiëren](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

Stel dat u een levering hebt gemaakt met de volgende voorwaarden:

* Het verband op het belangrijkste beeld is verschillend als de ontvanger een man of een vrouw is.
* Je hebt ook een link toegevoegd naar een speciale aanbieding die alleen zichtbaar is voor ontvangers ouder dan 25 jaar.

Als uw bericht is verzonden, selecteert u **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** van het leveringsdashboard.

Standaard is er geen profiel geselecteerd. Alleen klikken voor ontvangers waarvan het geslacht onbekend is en voor ontvangers die jonger zijn dan 25 jaar of waarvan de leeftijd onbekend is, worden weergegeven.

![](assets/delivery_reports_hot-clicks_1.png)

Klik op de knop **[!UICONTROL Change profile]** en selecteer een vrouwelijk testprofiel. Als u klikken voor mannen wilt weergeven, gaat u op dezelfde manier te werk en selecteert u een mannelijk testprofiel.

![](assets/delivery_reports_hot-clicks_2.png)

Klik op de knop **[!UICONTROL Change profile]** en selecteer een testprofiel waarvan de geboortedatum overeenkomt met deze voorwaarde.

Zie voor meer informatie over testprofielen [Testprofielen](../../audiences/using/managing-test-profiles.md).

>[!NOTE]
>
>Het aantal klikken op een specifieke verbinding is een percentage van het totale kliks voor alle voorwaardelijke inhoud in een levering. Daarom als u dynamische inhoud bepaalde, zou het totaal van de percentages die voor een specifiek testprofiel worden getoond niet kunnen gelijk 100 zijn.

Op dezelfde manier kunt u voor terugkerende leveringen en transactieberichten het testprofiel selecteren dat overeenkomt met de dynamische inhoud die u wilt weergeven, maar u kunt ook de klikpercentages weergeven op basis van de geselecteerde uitvoeringslevering.

Een uitvoering is een niet-activeerbaar en niet-functioneel technisch bericht dat in de volgende gevallen wordt gecreëerd:

* Telkens wanneer een terugkerende levering wordt uitgevoerd of bijgewerkt.

  Als de workflow die deze levering beheert eenmaal per maand wordt uitgevoerd, is er bijvoorbeeld één levering per maand. Bovendien wordt telkens wanneer de inhoud van de levering wordt bijgewerkt, een extra levering voor de uitvoering gemaakt.

  Zie voor meer informatie over terugkerende e-mailleveringen [E-maillevering](../../automating/using/email-delivery.md).

* Door gebrek eens per maand voor transactionele berichten, en telkens als een transactiebericht wordt uitgegeven en opnieuw gepubliceerd.

  Zie voor meer informatie over transactieberichten [Aan de slag met transactieberichten](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>Omdat de id&#39;s van de bijgehouden URL&#39;s voor elke uitvoering verschillend zijn, kunnen de &#39;hot click&#39;-gegevens niet worden geaggregeerd voor alle uitgevoerde leveringen van een bepaald bericht. Deze kan slechts voor één uitvoeringslevering tegelijk worden weergegeven.

Als uw bericht is verzonden, selecteert u **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** van het leveringsdashboard.

Standaard is de laatste levering van de uitvoering geselecteerd. Klik op de knop **[!UICONTROL Change execution delivery]** om een andere te selecteren.

![](assets/delivery_reports_hot-clicks_3.png)

Alleen de klikpercentages voor de geselecteerde uitvoering van de levering worden weergegeven.
