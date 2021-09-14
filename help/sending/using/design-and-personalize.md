---
title: Gepersonaliseerde content maken
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: Leer hoe u de inhoud van uw bericht ontwerpt en probeer algemene problemen te vermijden die ertoe kunnen leiden dat u de levering niet kunt uitvoeren. 
feature: Deliverability
role: User
level: Intermediate
exl-id: 938989c9-ef19-4297-9b8b-c38eb1cec1f0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 7%

---

# Gepersonaliseerde content maken {#build-personalized-content}

Probeer bij het ontwerpen van de inhoud van uw bericht algemene problemen te vermijden die ertoe kunnen leiden dat u de levering niet kunt uitvoeren. Meestal zijn mogelijke fouten gerelateerd aan [personalisatie](../../designing/using/personalization.md), opmaak wanneer [bestaande inhoud](../../designing/using/using-existing-content.md) - en [converting an HTML content](../../designing/using/using-existing-content.md#converting-an-html-content) - en [images](../../designing/using/images.md) wordt gebruikt.

## Aanpassing optimaliseren {#optimize-personalization}

Om veelvoorkomende problemen te voorkomen die ertoe kunnen leiden dat u uw levering niet kunt uitvoeren en om de ervaring van uw ontvangers te verbeteren, kunt u uw berichten aan uw persoonlijke voorkeur aanpassen.

U kunt de gegevens van ontvangers gebruiken die in de Adobe Campaign-database zijn opgeslagen, of die worden verzameld via tracking, landing pages, subscriptions, etc.
De grondbeginselen van de aanpassing worden voorgesteld in [deze sectie](../../designing/using/personalization.md).

Zorg ervoor dat de inhoud van uw bericht goed is ontworpen om fouten te voorkomen die over het algemeen te maken hebben met personalisatie.

Dynamische inhoud kan handmatig worden toegevoegd om verschillende inhoud weer te geven aan de ontvangers volgens de voorwaarden die zijn gedefinieerd in de expressie-editor. Wanneer u dynamische inhoud toevoegt, moet u altijd een standaardvariant laten voor ontvangers die niet aan de geselecteerde voorwaarden voldoen.
Zie [deze sectie](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) voor meer informatie over dynamische inhoud.

**Tips** : bekijk een voorbeeld van uw e-mail met verschillende testprofielen om te controleren of de dynamische inhoud correct is geconfigureerd.

## Geoptimaliseerde inhoud maken {#optimize-content}

Houd rekening met de onderstaande algemene tips bij het samenstellen van e-mails.

* Ontwerp eenvoudig houden

* Houd mobiele gebruikers in gedachten

* Vermijd e-mails die volledig op afbeeldingen zijn gebaseerd

* E-mailveilige lettertypen gebruiken

* Speciale tekens coderen

### Onderwerpregel

Werk aan [onderwerpregel](../../designing/using/subject-line.md) om open snelheden te verbeteren:

* Vermijd personen die te lang zijn. Gebruik maximaal 50 tekens

* Vermijd het gebruik van herhalende woorden zoals &quot;gratis&quot; of &quot;aanbieding&quot;, die als spam kunnen worden beschouwd

* Vermijd hoofdletters en speciale tekens zoals &quot;!&quot;, &quot;£&quot;, &quot;€&quot;, &quot;$&quot;

### Pagina spiegelen

Neem altijd een koppeling naar een spiegelpagina op. De voorkeurspositie boven aan het e-mailbericht. [Meer informatie](../../designing/using/personalization.md#adding-a-content-block)

### Unsubscription link

De koppeling om uw abonnement op te zeggen is essentieel. Het formulier moet zichtbaar en geldig zijn en moet functioneel zijn. Leer richtlijnen [voor unsubscription-koppelingen in deze sectie](../../designing/using/personalization.md#about-targeting-dimension).

Door gebrek, wanneer het bericht wordt geanalyseerd, controleert een controle [typologieregel](../../sending/using/control-rules.md) of een opt-out verbinding is omvat en produceert een waarschuwing als het mist.

**Tip**: Omdat menselijke fout altijd mogelijk is, controleer dat de opt-out verbinding correct vóór elke keer werkt u verzendt. Als u bijvoorbeeld de proefdruk verzendt, controleert u of de koppeling geldig is, of het formulier online is en of het veld Geen contact meer opnemen met deze ontvanger is gewijzigd in Ja.

Leer hoe te om een opt-out verbinding [in deze sectie ](../../designing/using/personalization.md#adding-a-content-block) op te nemen.

### E-mailformaat {#email-size}

Om problemen met prestaties of leverbaarheid te voorkomen, is de aanbevolen maximale grootte van een e-mailbericht ongeveer **35KB**.

Houd rekening met het volgende om uw e-mailadres onder de limiet te houden:

* Overbodige of ongebruikte stijlen verwijderen

* Enkele e-mailinhoud verplaatsen naar een [bestemmingspagina](../../channels/using/getting-started-with-landing-pages.md)

* Miniatuur uw code

Zorg ervoor om het even welke veranderingen vóór de definitieve verzending te testen.

In Adobe Campaign is de standaardmaximumgrootte van een e-mailbericht ingesteld op **100MB**. <!--This limit enables to prevent any error that could indefinitely increase the size of an email, which can lead to a system crash.-->

Als de limiet is bereikt, mislukt het bericht dat de limiet overschrijdt en wordt een foutbericht weergegeven in de leveringslogboeken. De andere berichten van dezelfde levering worden niet beïnvloed. In dat geval moet u het dynamische gedeelte van de e-mailsjabloon of de inhoudsfragmenten die door de levering worden gebruikt, aanpassen. <!--If you need assistance, or if you have any question or request about the **[!UICONTROL Maximum message size]** option, reach out to your Adobe contact.-->

Adobe raadt aan de standaardwaarde voor de maximale berichtgrootte te behouden. Deze waarde kan echter worden gewijzigd in de optie **[!UICONTROL Maximum message size]** via het menu **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**, alleen door [functionele beheerders](../../administration/using/users-management.md#functional-administrators).

>[!IMPORTANT]
>
>Als u deze waarde op nul instelt, wordt er geen limiet toegepast.

### Sms-lengte

Standaard voldoet het aantal tekens in een sms aan de gsm-standaarden (Global System for Mobile Communications). Sms-berichten met gsm-codering mogen maximaal 160 tekens bevatten of 153 tekens per sms voor berichten die in meerdere delen worden verzonden.

Transliteratie houdt in dat een teken van een sms door een ander teken wordt vervangen wanneer dat teken niet in aanmerking wordt genomen door de gsm-standaard. Als u personalisatievelden in de inhoud van uw SMS-bericht invoegt, kunnen er tekens worden ingevoerd waarmee de GSM-codering geen rekening houdt. U kunt tekentransliteratie toestaan door het corresponderende vak te selecteren op het tabblad met SMPP-kanaalinstellingen van het corresponderende **[!UICONTROL External account]**.
Meer informatie [in deze sectie](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

**Tips**:

* Als u alle tekens in uw SMS-berichten ongewijzigd wilt laten, bijvoorbeeld eigennamen niet wilt wijzigen, moet u transliteratie niet inschakelen.

* Als uw SMS-berichten echter veel tekens bevatten waarmee de GSM-standaard geen rekening houdt, kunt u met transliteratie de verzendkosten van uw berichten beperken.

Meer informatie [in deze sectie](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

### Responsief e-mailontwerp

Het responsieve ontwerp zorgt ervoor dat een e-mail optimaal wordt weergegeven voor het apparaat waarop het wordt geopend.

* Responsieve HTML-e-mail gebruiken in plaats van HTML-webpagina

* Gebruik de voorvertoningsmodus en verzend proefdrukken om de rendering op zoveel mogelijk apparaten te testen. Leer hoe te [voorproefbericht](../../sending/using/previewing-messages.md) alvorens te verzenden.

* Campagne-e-mailontwerper wordt geleverd met responsieve ontwerpsjablonen voor mobiele apparaten. Meer informatie vindt u [op deze pagina](../../designing/using/using-reusable-content.md#content-templates).

## Afbeeldingen beheren {#manage-images}

Volg de onderstaande richtlijnen voor het gebruik van afbeeldingen.

### Afbeeldingen blokkeren voorkomen

Sommige e-mailclients blokkeren afbeeldingen standaard en sommige gebruikers wijzigen hun instellingen om afbeeldingen te blokkeren zodat ze op gegevensgebruik kunnen worden opgeslagen. Als afbeeldingen niet worden gedownload, kan het hele bericht verloren gaan. Om dit te voorkomen:

* Verdeel uw inhoud met afbeelding en tekst. Vermijd e-mails die volledig op afbeeldingen zijn gebaseerd.

* Als er tekst in een afbeelding moet staan, gebruikt u alt- en titeltekst om ervoor te zorgen dat uw bericht overloopt. Maak de alt-/titeltekst op om de weergave te verbeteren.

* Vermijd het gebruik van achtergrondafbeeldingen, omdat deze niet door sommige e-mailclients worden ondersteund.

### Afbeeldingen responsief maken

Probeer afbeeldingen responsief te maken en de grootte ervan te wijzigen. Merk op dat dit een kosteneffect kan hebben aangezien het langer duurt om te bouwen.

### Absolute verwijzingen naar afbeeldingen gebruiken

Om van buitenaf toegankelijk te zijn, moeten de beelden die in e-mail en openbare middelen verbonden aan campagnes worden gebruikt op een extern toegankelijke server aanwezig zijn.

## Een voorbeeld van uw bericht bekijken {#preview-msg}

Adobe raadt u aan een voorbeeld van uw bericht te bekijken om na te gaan wat de personalisatie is en hoe de ontvangers uw bericht zullen bekijken.

Met de knop **[!UICONTROL Preview]** in de e-mailontwerper kunt u de rendering van elke inhoud voor een ontvanger weergeven. De verpersoonlijkingsgebieden en de voorwaardelijke elementen van inhoud worden vervangen met de overeenkomstige informatie voor het geselecteerde profiel. [Meer informatie](../../sending/using/previewing-messages.md)
