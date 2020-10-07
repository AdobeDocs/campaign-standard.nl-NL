---
title: Leveringssjablonen gebruiken
seo-title: Leveringssjablonen gebruiken
page-status-flag: never-activated
uuid: a540efc7-105d-4c7f-a2ee-ade4d22b3445
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
discoiquuid: 0cbc4e92-482f-4dac-a1fb-b738e7127938
index: y
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 9%

---


# Sjablonen gebruiken {#use-templates}

De malplaatjes van de levering staan voor verhoogde efficiency toe door kant-en-klare scenario&#39;s voor de meeste gemeenschappelijke soorten activiteiten te verstrekken. Met malplaatjes, kunnen de marketers nieuwe campagnes met minimale aanpassing in een kortere hoeveelheid tijd opstellen.

Meer informatie over leveringssjablonen vindt u in [deze sectie](../../start/using/marketing-activity-templates.md).

## Aan de slag met leveringssjablonen {#gs-templates}

Een [leveringsmalplaatje](../../start/using/marketing-activity-templates.md#creating-a-new-template) laat u toe om eens een reeks technische en functionele eigenschappen te bepalen die aan uw behoeften aanpassen en die voor toekomstige leveringen kunnen worden opnieuw gebruikt. U kunt dan tijd besparen en leveringen standaardiseren wanneer dat nodig is.

Als u meerdere merken beheert in Adobe Campaign, raadt Adobe aan één subdomein per merk te hebben. Een bank kan bijvoorbeeld verschillende subdomeinen hebben die overeenkomen met elk van haar regionale agentschappen. Als een bank eigenaar is van het domein bluebank.com, kunnen de subdomeinen @ny.bluebank.com, @ma.bluebank.com, @ca.bluebank.com, enz. zijn. Als u één leveringssjabloon per subdomein hebt, kunt u altijd de juiste vooraf geconfigureerde parameters voor elk merk gebruiken. Hierdoor worden fouten voorkomen en bespaart u tijd.

**Tip**:  Om configuratiefouten in Campagne te vermijden, adviseren wij dat u een inheemse malplaatje dupliceert en zijn eigenschappen verandert eerder dan een nieuw malplaatje tot stand te brengen.

## Adressen configureren

* Het adres van de afzender is verplicht om het verzenden van een e-mail toe te staan.

* Sommige ISPs (de Dienstverleners van Internet) controleren de geldigheid van het afzenderadres alvorens berichten goed te keuren.

* Een slecht geformuleerd adres kan ertoe leiden dat het door de ontvangende server wordt verworpen. U moet ervoor zorgen een correct adres wordt gegeven.

* Het adres moet de afzender uitdrukkelijk identificeren. Het domein moet eigendom zijn van en geregistreerd zijn bij de afzender.

* Adobe raadt u aan e-mailaccounts te maken die overeenkomen met de adressen die zijn opgegeven voor leveringen en antwoorden. Vraag de beheerder van het berichtensysteem om advies.

In het **[!UICONTROL Advanced parameters]** gedeelte van de eigenschappen van een e-mailsjabloon komt het **[!UICONTROL From (email address)]** veld overeen met het adres van de afzender.

![](assets/template-parameters.png)

Het adresdomein moet hetzelfde zijn als het subdomein dat u aan Adobe hebt gedelegeerd.

De **[!UICONTROL Reply to]** velden komen overeen met het e-mailadres en de naam die worden gebruikt voor reacties.

**Tip** - Adobe raadt u aan een bestaand reëel adres te gebruiken, zoals de klantenservice van uw merk. In dit geval, als een ontvanger een antwoord verzendt, zal de klantenzorg het kunnen behandelen.

Als u de naam wilt wijzigen van de afzender die wordt weergegeven in de koptekst van de verzonden berichten, gaat u naar het **[!UICONTROL Properties]** tabblad van de introductiepagina E-mail Designer (toegankelijk via het introductiepictogram) en klikt u op het **[!UICONTROL Default sender name]** blok.

![](assets/template-content.png)

Om de openingssnelheid van uw leveringen te verhogen, raadt Adobe u aan een naam te gebruiken die gemakkelijk kan worden herkend door de ontvangers, zoals de naam van uw merk.

**Tip** - Als u de ervaring van de ontvanger verder wilt verbeteren, kunt u de naam van een persoon toevoegen, bijvoorbeeld &#39;Emma van Megastore&#39;.

Zie [E-mailafzender](../../designing/using/subject-line.md#email-sender)voor meer informatie over het aanpassen van de naam van de afzender.

## De naam van de SMS-afzender aanpassen

In de **Geavanceerde parametersectie** van de eigenschappen van een malplaatje van SMS, staat de optie **van** u toe om de naam van de SMS berichtafzender te personaliseren gebruikend een koord van karakters. Dit is de naam die wordt weergegeven als de afzender van het sms-bericht op de mobiele telefoon van de ontvanger.

Als dit veld leeg is, wordt het bronnummer gebruikt dat in het externe account is opgegeven. Als er geen bronnummer is opgegeven, wordt de korte code gebruikt. Zie [Sms-configuratie ](../../administration/using/configuring-sms-channel.md) voor meer informatie.

**Tip** - Controleer de wetgeving in je land met betrekking tot het wijzigen van het adres van de afzender. Neem ook contact op met uw sms-serviceprovider om te controleren of deze deze functionaliteit aanbiedt.

## Een controlegroep instellen

Nadat de levering is verzonden, kunt u het gedrag van de uitgesloten ontvangers vergelijken met de ontvangers die de levering wel hebben ontvangen. Vervolgens kunt u de efficiëntie van uw campagnes meten. Meer informatie over controlegroepen vindt u in [deze sectie](../../sending/using/control-group.md).

## Typologieën gebruiken om filters of controleregels toe te passen

Een typologie bevat controleregels die tijdens de analysefase worden toegepast, alvorens om het even welk bericht te verzenden.

Wijzig de standaardtypologie naar wens in de sectie **[!UICONTROL Advanced parameters]** > **[!UICONTROL Preparation]** van de eigenschappen van de sjabloon.

Bijvoorbeeld, om het uitgaande verkeer beter te controleren, kunt u bepalen welke IP adressen kunnen worden gebruikt door één affiniteit per subdomein te bepalen en één typologie per affiniteit te creëren. De affiniteiten worden gedefinieerd in het configuratiebestand van de instantie. Neem contact op met uw Adobe Campaign-beheerder.

For more on typologies, refer to [this section](../../sending/using/managing-typologies.md).

## Een merk koppelen aan een sjabloon

De parameters van verzonden e-mails die verband houden met de identiteit van een merk (zoals het merklogo of het adres van de afzender) worden centraal beheerd in Adobe Campaign. U kunt een of meerdere merken maken en deze koppelen aan leveringssjablonen.

Zie Branding voor meer informatie over het gebruik en configureren van merken in Adobe Campaign.

Als u het merk wilt weergeven of wijzigen dat aan een leveringssjabloon is toegewezen, selecteert u de knop Eigenschappen bewerken van de sjabloon en bladert u naar de details van het merk.

![](assets/template-brand.png)

Zie Een merk [toewijzen aan een e-mail](../../administration/using/branding.md#assigning-a-brand-to-an-email)voor meer informatie over het koppelen van een merk aan een sjabloon.

Leer hoe u een merk kunt maken en configureren [in deze sectie](../../administration/using/branding.md#creating-a-brand).
