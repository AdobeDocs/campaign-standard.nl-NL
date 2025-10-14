---
title: Leveringssjablonen gebruiken
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: De malplaatjes van de levering staan voor verhoogde efficiency toe door kant-en-klare scenario's voor de meeste gemeenschappelijke soorten activiteiten te verstrekken.
feature: Deliverability
role: User
level: Intermediate
exl-id: ca134a7f-9035-4885-b4cb-1170b6ec10cc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 10%

---

# Sjablonen gebruiken {#use-templates}

De malplaatjes van de levering staan voor verhoogde efficiency toe door kant-en-klare scenario&#39;s voor de meeste gemeenschappelijke soorten activiteiten te verstrekken. Met malplaatjes, kunnen de marketers nieuwe campagnes met minimale aanpassing in een kortere hoeveelheid tijd opstellen.

Leer meer over leveringsmalplaatjes in [&#x200B; deze sectie &#x200B;](../../start/using/marketing-activity-templates.md).

## Aan de slag met leveringssjablonen {#gs-templates}

A [&#x200B; leveringsmalplaatje &#x200B;](../../start/using/marketing-activity-templates.md#creating-a-new-template) laat u toe om eens een reeks van technische en functionele eigenschappen te bepalen die uw behoeften aanpassen en die voor toekomstige leveringen kunnen worden opnieuw gebruikt. U kunt dan tijd besparen en leveringen standaardiseren wanneer dat nodig is.

Wanneer u meerdere merken beheert in Adobe Campaign, raadt Adobe aan één subdomein per merk te hebben. Een bank kan bijvoorbeeld verschillende subdomeinen hebben die overeenkomen met elk van haar regionale agentschappen. Als een bank eigenaar is van het bluebank.com-domein, kunnen de subdomeinen @ny.bluebank.com, @ma.bluebank.com, @ca.bluebank.com enzovoort zijn. Als u één leveringssjabloon per subdomein hebt, kunt u altijd de juiste vooraf geconfigureerde parameters voor elk merk gebruiken. Hierdoor worden fouten voorkomen en bespaart u tijd.

**Uiteinde**: Om configuratiefouten in Campagne te vermijden, adviseren wij dat u een inheems malplaatje dupliceert en zijn eigenschappen verandert eerder dan een nieuw malplaatje tot stand te brengen.

## Adressen configureren

* Het adres van de afzender is verplicht om het verzenden van een e-mail toe te staan.

* Sommige ISPs (de Dienstverleners van Internet) controleren de geldigheid van het afzenderadres alvorens berichten goed te keuren.

* Een slecht geformuleerd adres kan ertoe leiden dat het door de ontvangende server wordt verworpen. U moet ervoor zorgen een correct adres wordt gegeven.

* Het adres moet de afzender uitdrukkelijk identificeren. Het domein moet eigendom zijn van en geregistreerd zijn bij de afzender.

* Adobe raadt u aan e-mailaccounts te maken die overeenkomen met de adressen die zijn opgegeven voor leveringen en antwoorden. Vraag de beheerder van het berichtensysteem om advies.

In de sectie **[!UICONTROL Advanced parameters]** van de eigenschappen van een e-mailsjabloon komt het veld **[!UICONTROL From (email address)]** overeen met het adres van de afzender.

![](assets/template-parameters.png)

Het adresdomein moet het zelfde als subdomein zijn dat u vormde.

De velden **[!UICONTROL Reply to]** komen overeen met het e-mailadres en de naam die worden gebruikt voor reacties.

**Uiteinde** - de Adobe adviseert gebruikend een bestaand echt adres zoals de klantenzorg van uw merk. In dit geval, als een ontvanger een antwoord verzendt, zal de klantenzorg het kunnen behandelen.

Als u de naam wilt wijzigen van de afzender die wordt weergegeven in de koptekst van de verzonden berichten, gaat u naar het tabblad **[!UICONTROL Properties]** van de homepage van E-mail Designer (toegankelijk via het homepictogram) en klikt u op het blok **[!UICONTROL Default sender name]** .

![](assets/template-content.png)

Om de openingssnelheid van uw leveringen te verhogen, raadt de Adobe aan een naam te gebruiken die gemakkelijk door de ontvangers kan worden herkend, zoals de naam van uw merk.

**Uiteinde** - om de ervaring van de ontvanger verder te verbeteren, kunt u de naam van een persoon, bijvoorbeeld &quot;Emma van Megastore&quot;toevoegen.

Voor meer bij het personaliseren van de afzendernaam, zie [&#x200B; E-mailafzender &#x200B;](../../designing/using/subject-line.md#email-sender).

## De naam van de SMS-afzender aanpassen

In de **Geavanceerde parameters** sectie van de eigenschappen van een malplaatje van SMS, **van** optie staat u toe om de naam van de SMS berichtafzender te personaliseren gebruikend een koord van karakters. Dit is de naam die wordt weergegeven als de afzender van het sms-bericht op de mobiele telefoon van de ontvanger.

Als dit veld leeg is, wordt het bronnummer gebruikt dat in het externe account is opgegeven. Als er geen bronnummer is opgegeven, wordt de korte code gebruikt. Zie [Sms-configuratie &#x200B;](../../administration/using/configuring-sms-channel.md) voor meer informatie.

**Uiteinde** - controleer de wetgeving in uw land betreffende het wijzigen van het afzenderadres. Neem ook contact op met uw sms-serviceprovider om te controleren of deze deze functionaliteit aanbiedt.

## Een controlegroep instellen

Nadat de levering is verzonden, kunt u het gedrag van de uitgesloten ontvangers vergelijken met de ontvangers die de levering wel hebben ontvangen. Vervolgens kunt u de efficiëntie van uw campagnes meten. Leer meer over controlegroepen [&#x200B; deze sectie &#x200B;](../../sending/using/control-group.md).

## Typologieën gebruiken om filters of controleregels toe te passen

Een typologie bevat controleregels die tijdens de analysefase worden toegepast, alvorens om het even welk bericht te verzenden.

Wijzig in de sectie **[!UICONTROL Advanced parameters]** > **[!UICONTROL Preparation]** van de sjablooneigenschappen de standaardtypologie naar wens.

Bijvoorbeeld, om het uitgaande verkeer beter te controleren, kunt u bepalen welke IP adressen kunnen worden gebruikt door één affiniteit per subdomein te bepalen en één typologie per affiniteit te creëren. De affiniteiten worden gedefinieerd in het configuratiebestand van de instantie. Neem contact op met uw Adobe Campaign-beheerder.

Voor meer op typologieën, verwijs naar [&#x200B; deze sectie &#x200B;](../../sending/using/managing-typologies.md).

## Een merk koppelen aan een sjabloon

De parameters van verzonden e-mails die verband houden met de identiteit van een merk (zoals het merklogo of het adres van de afzender) worden centraal beheerd in Adobe Campaign. U kunt een of meerdere merken maken en deze koppelen aan leveringssjablonen.

Zie Branding voor meer informatie over het gebruik en configureren van merken in Adobe Campaign.

Als u het merk wilt weergeven of wijzigen dat aan een leveringssjabloon is toegewezen, selecteert u de knop Eigenschappen bewerken van de sjabloon en bladert u naar de details van het merk.

![](assets/template-brand.png)

Voor meer bij het verbinden van een merk met een malplaatje, zie [&#x200B; Toewijzend een merk aan e-mail &#x200B;](../../administration/using/branding.md#assigning-a-brand-to-an-email).

Leer hoe te om een merk [&#x200B; in deze sectie &#x200B;](../../administration/using/branding.md#creating-a-brand) tot stand te brengen en te vormen.
