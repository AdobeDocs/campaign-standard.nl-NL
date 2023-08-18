---
title: Leveringssjablonen gebruiken
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: "De malplaatjes van de levering staan voor verhoogde efficiency toe door kant-en-klare scenario's voor de meeste gemeenschappelijke soorten activiteiten te verstrekken."
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

Meer informatie over leveringssjablonen vindt u in [deze sectie](../../start/using/marketing-activity-templates.md).

## Aan de slag met leveringssjablonen {#gs-templates}

A [leveringssjabloon](../../start/using/marketing-activity-templates.md#creating-a-new-template) kunt u een reeks technische en functionele eigenschappen definiëren die aan uw behoeften voldoen en die opnieuw kunnen worden gebruikt voor toekomstige leveringen. U kunt dan tijd besparen en leveringen standaardiseren wanneer dat nodig is.

Wanneer u meerdere merken beheert in Adobe Campaign, raadt Adobe aan één subdomein per merk te hebben. Een bank kan bijvoorbeeld verschillende subdomeinen hebben die overeenkomen met elk van haar regionale agentschappen. Als een bank eigenaar is van het bluebank.com-domein, kunnen de subdomeinen @ny.bluebank.com, @ma.bluebank.com, @ca.bluebank.com enzovoort zijn. Als u één leveringssjabloon per subdomein hebt, kunt u altijd de juiste vooraf geconfigureerde parameters voor elk merk gebruiken. Hierdoor worden fouten voorkomen en bespaart u tijd.

**Tip**: Om configuratiefouten in Campagne te vermijden, adviseren wij dat u een inheemse malplaatje dupliceert en zijn eigenschappen verandert eerder dan tot een nieuw malplaatje te leiden.

## Adressen configureren

* Het adres van de afzender is verplicht om het verzenden van een e-mail toe te staan.

* Sommige ISPs (de Dienstverleners van Internet) controleren de geldigheid van het afzenderadres alvorens berichten goed te keuren.

* Een slecht geformuleerd adres kan ertoe leiden dat het door de ontvangende server wordt verworpen. U moet ervoor zorgen een correct adres wordt gegeven.

* Het adres moet de afzender uitdrukkelijk identificeren. Het domein moet eigendom zijn van en geregistreerd zijn bij de afzender.

* Adobe raadt u aan e-mailaccounts te maken die overeenkomen met de adressen die zijn opgegeven voor leveringen en antwoorden. Vraag de beheerder van het berichtensysteem om advies.

In de **[!UICONTROL Advanced parameters]** van de eigenschappen van een e-mailsjabloon, de **[!UICONTROL From (email address)]** komt overeen met het adres van de afzender.

![](assets/template-parameters.png)

Het adresdomein moet het zelfde als subdomein zijn dat u vormde.

De **[!UICONTROL Reply to]** de velden komen overeen met het e-mailadres en de naam die voor reacties worden gebruikt.

**Tip** - Adobe raadt u aan een bestaand reëel adres te gebruiken, zoals de klantenservice van uw merk. In dit geval, als een ontvanger een antwoord verzendt, zal de klantenzorg het kunnen behandelen.

Als u de naam van de afzender wilt wijzigen die wordt weergegeven in de koptekst van de verzonden berichten, gaat u naar **[!UICONTROL Properties]**  tabblad van de introductiepagina E-mail Designer (toegankelijk via het introductiepictogram) en klik op de knop **[!UICONTROL Default sender name]** blokkeren.

![](assets/template-content.png)

Om de openingssnelheid van uw leveringen te verhogen, raadt de Adobe aan een naam te gebruiken die gemakkelijk door de ontvangers kan worden herkend, zoals de naam van uw merk.

**Tip** - Om de ervaring van de ontvanger verder te verbeteren, kunt u de naam van een persoon toevoegen, bijvoorbeeld &quot;Emma van Megastore&quot;.

Voor meer bij het personaliseren van de afzendernaam, zie [E-mailafzender](../../designing/using/subject-line.md#email-sender).

## De naam van de SMS-afzender aanpassen

In de **Geavanceerde parameters** van de eigenschappen van een SMS-sjabloon, de **Van** kunt u de naam van de afzender van het SMS-bericht aanpassen met een reeks tekens. Dit is de naam die wordt weergegeven als de afzender van het sms-bericht op de mobiele telefoon van de ontvanger.

Als dit veld leeg is, wordt het bronnummer gebruikt dat in het externe account is opgegeven. Als er geen bronnummer is opgegeven, wordt de korte code gebruikt. Zie [Sms-configuratie ](../../administration/using/configuring-sms-channel.md) voor meer informatie.

**Tip** - Controleer de wetgeving in uw land met betrekking tot het wijzigen van het adres van de afzender. Neem ook contact op met uw sms-serviceprovider om te controleren of deze deze functionaliteit aanbiedt.

## Een controlegroep instellen

Nadat de levering is verzonden, kunt u het gedrag van de uitgesloten ontvangers vergelijken met de ontvangers die de levering wel hebben ontvangen. Vervolgens kunt u de efficiëntie van uw campagnes meten. Meer informatie over controlegroepen [deze sectie](../../sending/using/control-group.md).

## Typologieën gebruiken om filters of controleregels toe te passen

Een typologie bevat controleregels die tijdens de analysefase worden toegepast, alvorens om het even welk bericht te verzenden.

In de **[!UICONTROL Advanced parameters]** > **[!UICONTROL Preparation]** van de eigenschappen van de sjabloon, wijzigt u de standaardtypologie naar wens.

Bijvoorbeeld, om het uitgaande verkeer beter te controleren, kunt u bepalen welke IP adressen kunnen worden gebruikt door één affiniteit per subdomein te bepalen en één typologie per affiniteit te creëren. De affiniteiten worden gedefinieerd in het configuratiebestand van de instantie. Neem contact op met uw Adobe Campaign-beheerder.

Raadpleeg voor meer informatie over typologieën [deze sectie](../../sending/using/managing-typologies.md).

## Een merk koppelen aan een sjabloon

De parameters van verzonden e-mails die verband houden met de identiteit van een merk (zoals het merklogo of het adres van de afzender) worden centraal beheerd in Adobe Campaign. U kunt een of meerdere merken maken en deze koppelen aan leveringssjablonen.

Zie Branding voor meer informatie over het gebruik en configureren van merken in Adobe Campaign.

Als u het merk wilt weergeven of wijzigen dat aan een leveringssjabloon is toegewezen, selecteert u de knop Eigenschappen bewerken van de sjabloon en bladert u naar de details van het merk.

![](assets/template-brand.png)

Zie voor meer informatie over het koppelen van een merk aan een sjabloon [Een merk toewijzen aan een e-mail](../../administration/using/branding.md#assigning-a-brand-to-an-email).

Leer hoe u een merk kunt maken en configureren [in deze sectie](../../administration/using/branding.md#creating-a-brand).
