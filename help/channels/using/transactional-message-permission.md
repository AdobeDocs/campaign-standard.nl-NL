---
title: Toestemming voor Transactieberichten
description: Meer informatie over machtigingen die zijn gekoppeld aan transactiegebeurtenissen.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 995da330-6c86-444b-86b2-61d887f37db4
source-git-commit: 7247fe596494690ac0676196fbb72c6139aeb0c7
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 1%

---

# Verbeteringen voor Transactiegebeurtenissen {#transactional-event-improvements}

>[!AVAILABILITY]
>
>Deze functies zijn momenteel alleen beschikbaar voor een aantal organisaties (beperkte beschikbaarheid). Neem voor meer informatie contact op met uw Adobe-vertegenwoordiger.

Momenteel kunnen gebruikers in Adobe Campaign Standard zonder de beveiligingsgroep Beheerder geen toegang krijgen tot transactiegebeurtenissen, deze maken of publiceren. Dit leidt tot problemen voor zakelijke gebruikers die gebeurtenissen moeten configureren en publiceren, maar geen beheerdersrechten hebben. Ook, is het niet mogelijk om transactionele gebeurtenissen te dupliceren.

We hebben de volgende verbeteringen geïmplementeerd in de toegangscontrole voor transactieberichten:

* Een nieuwe **[!UICONTROL Role]**, aangeroepen **MC-gebruiker**, is toegevoegd om gebruikers zonder beheerdersrechten toe te staan de configuratie van transactionele gebeurtenissen te beheren. De **MC-gebruiker** rol verleent deze gebruikers de capaciteit om tot transactiegebeurtenissen en berichten toegang te hebben tot, tot stand te brengen, te publiceren en unpublish.

* De leveringen van de uitvoering (d.w.z. technische berichten die worden gecreeerd telkens als een transactiemelding wordt uitgegeven en opnieuw gepubliceerd, of eens per maand door gebrek) worden nu geplaatst aan **[!UICONTROL Organizational unit]** van de beveiligingsgroep waartoe de gebruiker die de gebeurtenis maakt, behoort, en niet alleen tot de groep **[!UICONTROL Organizational unit]** van de **Message Center-agent (mcExec)** beveiligingsgroep.

* **Beheerders** kan nu gepubliceerde transactiefouten en gebruikers dupliceren met de **MC-gebruiker** rol mits zij zich in dezelfde **Organisatorische eenheid** een hiërarchie instellen als de gebruiker die de gebeurtenis heeft gemaakt.

## De gebruikersrol van MC toewijzen {#assign-role}

Om het **MC-gebruiker** rol voor uw veiligheidsgroep:

1. Een nieuwe **[!UICONTROL Security group]** of een bestaande versie bijwerken. [Meer informatie](../../administration/using/managing-groups-and-users.md).

1. Klikken **[!UICONTROL Create element]** om rollen aan uw veiligheidsgroep toe te wijzen.

   ![](assets/event_access_1.png)

1. De MC-gebruiker selecteren **[!UICONTROL Role]** en klik op **[!UICONTROL Confirm]**.

   >[!IMPORTANT]
   >
   > Ga met voorzichtigheid te werk wanneer het toewijzen van de rol van de Gebruiker MC aan exploitanten, aangezien dit hen de capaciteit verleent om gebeurtenissen unpublish.

   ![](assets/event_access_2.png)

1. Zodra gevormd, klik **[!UICONTROL Save]**.

Aan deze **[!UICONTROL Security group]** U kunt nu transactiegebeurtenissen en berichten openen, maken en publiceren.

## De gebruikersbeveiligingsgroep MC toewijzen {#assign-group}

1. Selecteer in de Admin Console de optie **Producten** tab.

1. Selecteren **Adobe Campaign Standard** kiest u vervolgens de gewenste instantie.

1. Van de **Productprofielen** Selecteer de **MC-gebruiker** groep.

1. Klikken **Gebruiker toevoegen** en voer de naam, gebruikersgroep of het e-mailadres in van het profiel dat u aan dit productprofiel wilt toevoegen.

1. Klik op **Opslaan**.

Gebruikers toegevoegd aan deze **[!UICONTROL Security group]** U kunt nu transactiegebeurtenissen en berichten openen, maken en publiceren.

## Transactiegebeurtenissen dupliceren {#duplicate-transactional-events}

Een gebruiker met de **Beheerder** beveiligingsgroep<!--([Functional administrators](../../administration/using/users-management.md#functional-administrators)?)--> kan nu een gebeurtenisconfiguratie dupliceren als de gebeurtenis **gepubliceerd**.

Bovendien hebben gebruikers die geen beheerder zijn met de **MC-gebruiker** de rol kan tot gebeurtenisconfiguraties nu toegang hebben, maar hun toestemming om te dupliceren wordt bepaald door **Organisatorische eenheid** ze horen tot. Als de huidige gebruiker en de gebruiker die de gebeurtenis heeft gemaakt tot dezelfde hiërarchie van de organisatie behoren, is duplicatie toegestaan.

Als een gebruiker van de organisatie &#39;France Sales&#39; bijvoorbeeld een gebeurtenisconfiguratie maakt:

* Een andere gebruiker van wie de organisatorische eenheid &quot;verkoop van Parijs&quot;is zal deze gebeurtenis kunnen dupliceren, omdat &quot;verkoop van Parijs&quot;deel van de organisatorische eenheid van de Verkoop van Frankrijk uitmaakt.

* Een gebruiker met de organisatie &#39;San Francisco Sales&#39; kan dit echter niet doen, omdat &#39;San Francisco Sales&#39; onder de organisatie &#39;US Sales&#39; valt, die los staat van de organisatie &#39;France Sales&#39;.

Voer de onderstaande stappen uit om een gebeurtenisconfiguratie te dupliceren.

1. Klik op de knop **Adobe** logo, in de linkerbovenhoek, en selecteer **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.

1. Houd de muis boven de gepubliceerde gebeurtenisconfiguratie van uw keuze en selecteer de optie **[!UICONTROL Duplicate element]** knop.

   ![](assets/message-center_duplicate-button.png)

   >[!CAUTION]
   >
   >U kunt geen gebeurtenisconfiguratie dupliceren die niet is gepubliceerd. [Meer informatie](publishing-transactional-event.md)

1. De gedupliceerde gebeurtenis wordt automatisch weergegeven. Het bevat dezelfde configuratie die u voor de oorspronkelijke gebeurtenis hebt gedefinieerd, maar het heeft de **[!UICONTROL Draft]** status.

   ![](assets/message-center_duplicated-draft-event.png)

1. Het overeenkomstige transactiemelding wordt automatisch gecreeerd. Ga naar **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_duplicated-message.png)

1. Open het zojuist gedupliceerde bericht. Het bevat hetzelfde ontwerp dat u voor het oorspronkelijke bericht hebt gedefinieerd, maar het bevat de **[!UICONTROL Draft]** status, zelfs als het oorspronkelijke transactiebericht werd gepubliceerd.

   ![](assets/message-center_duplicated-draft-message.png)

1. U kunt dit bericht nu bewerken en aanpassen. Zie [Transactieberichten bewerken](../../channels/using/editing-transactional-message.md).

## Gevolgen {#impacts}

In de onderstaande tabel wordt het effect van deze verbeteringen beschreven:

| Objecten | Voor deze wijziging | Na deze wijziging |
|:-: | :--: | :-:|
| Transactionele gebeurtenissen | Alleen gebruikers binnen de **Beheerder** beveiligingsgroepen kunnen gebeurtenissen maken en publiceren. | De **MC-gebruiker** Met deze rol kunnen gebruikers gebeurtenissen maken en publiceren. |
| Transactieberichten | Transactieberichten worden ingesteld op de **Organisatorische eenheid** van de **Message Center-agent (mcExec)** beveiligingsgroep. | Transactieberichten worden ingesteld op de **Organisatorische eenheid** van de beveiligingsgroep waartoe de gebruiker die de transactiegebeurtenis/het bericht maakt, behoort. |
| Leveringen uitvoeren | Leveringen van uitvoering worden ingesteld op de **Organisatorische eenheid** van de **Message Center-agent (mcExec)** beveiligingsgroep. | Leveringen van uitvoering worden ingesteld op de **Organisatorische eenheid** van de beveiligingsgroep waartoe de gebruiker die de transactiegebeurtenis/het bericht maakt, behoort. |
| Gepubliceerde transactiegebeurtenissen | Duplicatie is voor geen enkele gebruiker mogelijk. | <ul><li>Gebruikers met de **Beheerder** beveiligingsgroep kan gepubliceerde gebeurtenissen dupliceren.</li> <li>Gebruikers met de **MC-gebruiker** de rol kan gepubliceerde gebeurtenissen dupliceren op voorwaarde dat zij in het zelfde **Organisatorische eenheid** een hiërarchie instellen als de gebruiker die de gebeurtenis heeft gemaakt.</li></ul> |


<!--Transactional Message Templates| Transactional Message templates are set to the Organizational unit **All**. | Transaction Message Template will be set to the **Organizational unit** of the security group to which the user creating the message template belongs.-->