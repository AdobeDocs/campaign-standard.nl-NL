---
title: Kwalificatie van niet-bezorging bijwerken na een ISP-uitval
description: Leer hoe te om stuitkwalificatie na een ISP stroomonderbreking bij te werken.
audience: delivery
hidefromtoc: true
exl-id: b06e9009-70c7-459f-8a9f-d5b7020d662f
source-git-commit: f81b8a3b076a6e29b697f21ea4d99fa7d5b6788c
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 2%

---

# Bounce-kwalificatie bijwerken na een ISP-uitgang {#update-bounce-qualification.md}

## Context

Als een internetprovider buiten beschouwing blijft, kunnen e-mails die via Campagne worden verzonden niet succesvol aan de ontvanger worden bezorgd: deze e-mails worden ten onrechte gemarkeerd als steunkleuren.

In december 2020 resulteerde een wereldwijde uitgave bij Gmail in een onjuiste opgave van sommige e-mailberichten die naar geldige Gmail-adressen werden verzonden, door Gmail-servers met de volgende bounce: *&quot;550-5.1.1 Het e-mailaccount dat u probeerde te bereiken, bestaat niet.&quot;*

Google heeft verklaard dat de Gmail-storingen en -storingen die deze kwestie hebben veroorzaakt, op 14 december om 6:55 zijn begonnen en op 15 december om 18:09 uur zijn geëindigd. Uit onze gegevensanalyse bleek ook dat Gmail op 16 december om 2:06u EST een zeer korte spiraal heeft doorgemaakt, waarbij de meerderheid op 15 december tussen 2:00 uur EST en 18:30 uur EST heeft plaatsgevonden.

>[!NOTE]
>
>U kunt het Google Workspace Status Dashboard inschakelen [deze pagina](https://www.google.com/appsstatus#hl=en&amp;v=status).


Volgens de standaardlogica voor stuitverwerking heeft Adobe Campaign deze ontvangers automatisch aan de quarantainelijst toegevoegd met een **[!UICONTROL Status]** instellen van **[!UICONTROL Quarantine]**. Om dit te verbeteren, moet u uw quarantainetabel in Campagne bijwerken door deze ontvangers te vinden en te verwijderen, of hun te veranderen **[!UICONTROL Status]** tot **[!UICONTROL Valid]** zodat de nachtelijke schoonmaakworkflow ze verwijdert.

Om de ontvangers te vinden die door deze Gmail- kwestie werden beïnvloed, of in het geval dat dit opnieuw met een andere ISP gebeurt, gelieve de instructies hieronder te zien.

## Proces voor bijwerken

U zult een vraag op uw quarantainelijst moeten in werking stellen om alle ontvangers uit te filteren Gmail (of andere ISP) die potentieel door de stroomonderbreking werden beïnvloed zodat kunnen zij uit de quarantainelijst worden verwijderd, en inbegrepen in toekomstige e-mailleveringen van de Campagne.

Gebaseerd op het tijdkader van het incident, hieronder zijn de geadviseerde richtlijnen voor deze vraag.

>[!IMPORTANT]
>
>Deze datums/tijden zijn gebaseerd op de tijdzone van de Oost-Standard (EST). Pas de tijdzone van de instantie aan.

Voor Campagne-instanties met SMTP-responsgegevens voor stuiteren in het dialoogvenster **[!UICONTROL Error text]** veld van de quarantainelijst:

* **Fouttekst (quarantainetekst)** bevat &quot;550-5.1.1 Het e-mailaccount dat u probeerde te bereiken, bestaat niet&quot; EN **Fouttekst (quarantainetekst)** bevat &quot;support.google.com&quot; **
* **Status bijwerken (@lastModified)** op of na 12/14/2020 6:55:00
* **Status bijwerken (@lastModified)** op of vóór 12/16/2020 6:00:00

Als u de lijst met betrokken ontvangers hebt, kunt u deze instellen op de status **[!UICONTROL Valid]** zodat zij uit de quarantainelijst worden verwijderd door **[!UICONTROL Database cleanup]** of deze uit de tabel verwijderen.

**Verwante onderwerpen:**
* [Leveringsfouten begrijpen](../../sending/using/understanding-delivery-failures.md)
* [Bounce mail-kwalificatie](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)
