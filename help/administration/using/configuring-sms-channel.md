---
title: SMS-kanaal configureren
description: '"Ontdek de de configuratiestappen van SMS: routering, codering, indelingen en geavanceerde eigenschappen. "'
page-status-flag: never-activated
uuid: 5f13dbd5-9522-4199-8d9a-44c397cb2458
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 356d4d4f-3d5a-468c-bff8-96767cd8fff6
context-tags: extAccountMobile,overview;extAccount,main;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 10339aa3a5d16bb995a763b6d846e234c5f1325a
workflow-type: tm+mt
source-wordcount: '1625'
ht-degree: 1%

---


# SMS-kanaal configureren{#configuring-sms-channel}

Voor het verzenden van SMS-berichten moet een of meer externe accounts zijn geconfigureerd door een beheerder in het menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL SMS]** > **[!UICONTROL SMS accounts]** .

De stappen voor het maken en wijzigen van een externe account worden beschreven in de sectie [Externe accounts](../../administration/using/external-accounts.md) . Hieronder vindt u de parameters die specifiek zijn voor externe accounts bij het verzenden van SMS-berichten.

## Het bepalen van een Verpletteren van SMS {#defining-an-sms-routing}

De externe account **[!UICONTROL SMS routing via SMPP]** wordt standaard verschaft, maar het kan handig zijn om andere accounts toe te voegen.

Als u het SMPP-protocol wilt gebruiken, kunt u ook een nieuwe externe account maken. Voor meer informatie over het protocol en de montages van SMS, verwijs naar deze [technische nota](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html).

1. Maak een nieuw extern account van **[!UICONTROL Administration > Application settings > External accounts]**.
1. Definieer het accounttype als **[!UICONTROL Routing]**, het kanaal als **[!UICONTROL Mobile (SMS)]** en de leveringsmodus als **[!UICONTROL Bulk delivery]**.

   ![](assets/sms_routing.png)

1. Definieer de verbindingsinstellingen.

   Als u de verbindingsinstellingen wilt invoeren die specifiek zijn voor het verzenden van SMS-berichten, neemt u contact op met uw SMS-serviceprovider die u zal uitleggen hoe de verschillende velden voor externe accounts moeten worden ingevuld.

   ![](assets/sms_connection.png)

   De **[!UICONTROL Enable TLS over SMPP]** optie staat u toe om verkeer te coderen SMPP.

   **[!UICONTROL Enable verbose SMPP traces in the log file]** staat u toe om al verkeer SMPP in logboekdossiers te dumpen. Deze optie moet worden toegelaten om de schakelaar problemen op te lossen en met het verkeer te vergelijken dat door de leverancier wordt gezien.

1. Neem contact op met Adobe, dat u de waarde geeft die u in het **[!UICONTROL SMS-C implementation name]** veld wilt invoeren, afhankelijk van de gekozen provider.
1. Geef de instellingen voor het SMPP-kanaal op. Meer informatie vindt u in het gedeelte [SMS-codering en -indelingen](#sms-encoding-and-formats) .

   Schakel het selectievakje in **[!UICONTROL Store incoming MO in the database]** als u alle inkomende SMS-berichten in de tabel in InSMS wilt opslaan. Raadpleeg deze [sectie](../../channels/using/managing-incoming-sms.md#storing-incoming-sms)voor meer informatie over het ophalen van uw inkomende SMS.

   Met de **[!UICONTROL Enable Real-time KPI updates during SR processing]** optie kunnen de **[!UICONTROL Delivered]** of **[!UICONTROL Bounces + Errors]** KPI&#39;s in real-time worden bijgewerkt nadat de levering is verzonden. Deze KPIs kan in het **[!UICONTROL Deployment]** venster worden gevonden en wordt direct herberekend van SR (het Rapport van de Status) die van de leverancier wordt ontvangen.

   ![](assets/sms_connection_1.png)

1. Definieer de **[!UICONTROL Throughput and timeouts]** parameters.

   U kunt de maximumproductie van uitgaande berichten (&quot;MT&quot;, Mobiel geëindigd) in MT per seconde specificeren. Als u &quot;0&quot;op het overeenkomstige gebied ingaat, zal de productie onbeperkt zijn.

   De waarden van alle velden die overeenkomen met de tijdsduur moeten in seconden worden ingevuld.

1. Definieer de specifieke parameters voor SMS-C voor het geval u een specifieke coderingstoewijzing moet definiëren. Raadpleeg de specifieke [sectie](#smsc-specifics) SMSC voor meer informatie.

   Schakel de **[!UICONTROL Send full phone number (send characters other than digits)]** optie in als u het SMPP-protocol niet wilt respecteren en het **[!UICONTROL +]** voorvoegsel wilt overbrengen naar de server van de SMS-provider (SMS-C).

   Aangezien bepaalde providers echter het gebruik van het **[!UICONTROL +]** voorvoegsel vereisen, wordt u geadviseerd contact op te nemen met uw provider en wordt u aangeraden deze optie indien nodig in te schakelen.

1. Definieer, indien nodig, automatische antwoorden om acties te activeren op basis van de inhoud van een antwoord. Raadpleeg [deze sectie](../../channels/using/managing-incoming-sms.md#managing-stop-sms) voor meer informatie.
1. Sparen de configuratie van SMS die externe rekening verplettert.

Je kunt nu je nieuwe routering gebruiken om SMS-berichten te verzenden met Adobe Campaign.

## SMS-codering en -indelingen {#sms-encoding-and-formats}

### SMS-codering, -lengte en -transliteratie {#sms-encoding--length-and-transliteration}

Standaard voldoet het aantal tekens in een SMS aan de GSM-standaarden (Global System for Mobile Communications).

SMS-berichten die gebruikmaken van GSM-codering mogen maximaal 160 tekens bevatten, of 153 tekens per SMS voor berichten die in meerdere onderdelen worden verzonden.

>[!NOTE]
>
>Bepaalde tekens tellen als twee tekens (accolades, vierkante haken, het euroteken, enz.). De lijst met beschikbare GSM-tekens wordt weergegeven in de sectie [Teksttabel - GSM-standaard](#table-of-characters---gsm-standard) .

Desgewenst kunt u tekentransliteratie autoriseren door het desbetreffende vak in te schakelen.

![](assets/sms_transliteration.png)

Vertaling bestaat erin een teken van een SMS door een ander te vervangen wanneer dat teken niet in aanmerking wordt genomen door de GSM-standaard.

* Als transliteratie is **toegestaan**, wordt elk teken dat niet in aanmerking wordt genomen, vervangen door een GSM-teken wanneer het bericht wordt verzonden. De letter &quot;ë&quot; wordt bijvoorbeeld vervangen door &quot;e&quot;. Het bericht is daarom enigszins gewijzigd, maar de tekenlimiet blijft ongewijzigd.
* Wanneer transliteratie **niet is geautoriseerd**, wordt elk bericht dat tekens bevat waarmee geen rekening wordt gehouden, verzonden in binaire notatie (Unicode): alle tekens worden daarom naar behoren verzonden. De SMS-berichten met Unicode zijn echter beperkt tot 70 tekens (of 67 tekens per SMS voor berichten die in meerdere delen worden verzonden). Als het maximumaantal tekens wordt overschreden, worden verschillende berichten verzonden, wat extra kosten kan veroorzaken.

>[!IMPORTANT]
>
>Als u personalisatievelden invoegt in de inhoud van uw SMS-bericht, worden mogelijk tekens ingevoegd waarmee de GSM-codering geen rekening houdt. Een inhoudsvoorbeeld wordt aangeboden in de sectie [SMS-berichten](../../channels/using/personalizing-sms-messages.md) personaliseren.

Standaard is tekentransliteratie uitgeschakeld. Als u alle tekens in uw SMS-berichten wilt behouden zoals ze zijn, wordt u aangeraden deze optie niet in te schakelen om bijvoorbeeld eigennamen te wijzigen.

Als uw SMS-berichten echter veel tekens bevatten die Unicode-berichten genereren, kunt u deze optie inschakelen om de kosten voor het verzenden van uw berichten te beperken.

### Tekenlijst - GSM-standaard {#table-of-characters---gsm-standard}

In dit deel worden de tekens weergegeven waarmee rekening wordt gehouden door de GSM-standaard. Alle karakters die in het berichtlichaam worden opgenomen, buiten die hieronder vermeld, zetten het volledige bericht in binair formaat (Unicode) om en beperken daarom het tot 70 karakters. Raadpleeg voor meer informatie de sectie [SMS-codering, -lengte en -transliteratie](#sms-encoding--length-and-transliteration) .

**Standaardtekens**

<table> 
 <tbody> 
  <tr> 
   <td> @<br /> </td> 
   <td> <img height="21px" src="assets/delta.png" /> <br /> </td> 
   <td> SP<br /> </td> 
   <td> 0<br /> </td> 
   <td> ¡<br /> </td> 
   <td> P<br /> </td> 
   <td> ¿<br /> </td> 
   <td> P<br /> </td> 
  </tr> 
  <tr> 
   <td> £<br /> </td> 
   <td> _<br /> </td> 
   <td> !<br /> </td> 
   <td> 1<br /> </td> 
   <td> A<br /> </td> 
   <td> Q<br /> </td> 
   <td> a<br /> </td> 
   <td> q<br /> </td> 
  </tr> 
  <tr> 
   <td> $<br /> </td> 
   <td> <img height="21px" src="assets/phi.png" /> <br /> </td> 
   <td> "<br /> </td> 
   <td> 2<br /> </td> 
   <td> B<br /> </td> 
   <td> R<br /> </td> 
   <td> b<br /> </td> 
   <td> r<br /> </td> 
  </tr> 
  <tr> 
   <td> ¥<br /> </td> 
   <td> <img height="21px" src="assets/gamma.png" /> <br /> </td> 
   <td> #<br /> </td> 
   <td> 3<br /> </td> 
   <td> C<br /> </td> 
   <td> S<br /> </td> 
   <td> c<br /> </td> 
   <td> s<br /> </td> 
  </tr> 
  <tr> 
   <td> è<br /> </td> 
   <td> <img height="21px" src="assets/delta.png" /> <br /> </td> 
   <td> ¤<br /> </td> 
   <td> 4<br /> </td> 
   <td> D<br /> </td> 
   <td> T<br /> </td> 
   <td> d<br /> </td> 
   <td> t<br /> </td> 
  </tr> 
  <tr> 
   <td> é<br /> </td> 
   <td> <img height="21px" src="assets/omega.png" /> <br /> </td> 
   <td> %<br /> </td> 
   <td> 5<br /> </td> 
   <td> E<br /> </td> 
   <td> U<br /> </td> 
   <td> e<br /> </td> 
   <td> u<br /> </td> 
  </tr> 
  <tr> 
   <td> ù<br /> </td> 
   <td> <img height="21px" src="assets/pi.png" /> <br /> </td> 
   <td> &amp;<br /> </td> 
   <td> 6<br /> </td> 
   <td> F<br /> </td> 
   <td> V<br /> </td> 
   <td> f<br /> </td> 
   <td> v<br /> </td> 
  </tr> 
  <tr> 
   <td> ì<br /> </td> 
   <td> <img height="21px" src="assets/psi.png" /> <br /> </td> 
   <td> '<br /> </td> 
   <td> 7<br /> </td> 
   <td> G<br /> </td> 
   <td> W<br /> </td> 
   <td> g<br /> </td> 
   <td> w<br /> </td> 
  </tr> 
  <tr> 
   <td> ò<br /> </td> 
   <td> <img height="21px" src="assets/sigma.png" /> <br /> </td> 
   <td> (<br /> </td> 
   <td> 8<br /> </td> 
   <td> H<br /> </td> 
   <td> X<br /> </td> 
   <td> h<br /> </td> 
   <td> x<br /> </td> 
  </tr> 
  <tr> 
   <td> C<br /> </td> 
   <td> <img height="21px" src="assets/theta.png" /> <br /> </td> 
   <td> )<br /> </td> 
   <td> 9 </td> 
   <td> I<br /> </td> 
   <td> Y<br /> </td> 
   <td> i<br /> </td> 
   <td> y<br /> </td> 
  </tr> 
  <tr> 
   <td> LF<br /> </td> 
   <td> <img height="21px" src="assets/xi.png" /> <br /> </td> 
   <td> *<br /> </td> 
   <td> :<br /> </td> 
   <td> J<br /> </td> 
   <td> Z<br /> </td> 
   <td> j<br /> </td> 
   <td> z<br /> </td> 
  </tr> 
  <tr> 
   <td> Ø<br /> </td> 
   <td> ESC<br /> </td> 
   <td> +<br /> </td> 
   <td> ;<br /> </td> 
   <td> K<br /> </td> 
   <td> Ä<br /> </td> 
   <td> k<br /> </td> 
   <td> ä<br /> </td> 
  </tr> 
  <tr> 
   <td> ø<br /> </td> 
   <td> AE<br /> </td> 
   <td> ,<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> L<br /> </td> 
   <td> Ö<br /> </td> 
   <td> l<br /> </td> 
   <td> ö<br /> </td> 
  </tr> 
  <tr> 
   <td> CR<br /> </td> 
   <td> æ<br /> </td> 
   <td> -<br /> </td> 
   <td> = </td> 
   <td> M<br /> </td> 
   <td> -<br /> </td> 
   <td> m<br /> </td> 
   <td> ñ<br /> </td> 
  </tr> 
  <tr> 
   <td> Å<br /> </td> 
   <td> ß<br /> </td> 
   <td> .<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> N<br /> </td> 
   <td> Ü<br /> </td> 
   <td> n<br /> </td> 
   <td> ü<br /> </td> 
  </tr> 
  <tr> 
   <td> å<br /> </td> 
   <td> É<br /> </td> 
   <td> /<br /> </td> 
   <td> ?<br /> </td> 
   <td> O<br /> </td> 
   <td> §<br /> </td> 
   <td> o<br /> </td> 
   <td> à<br /> </td> 
  </tr> 
 </tbody> 
</table>

SP: Spatie

ESC: Escape

LF: Nieuwe regel

CR: Enter

**Geavanceerde tekens (twee keer geteld)**

^ { } [ ~ ] | €

### SMSC-specificaties {#smsc-specifics}

>[!NOTE]
>
>Met deze opties kunt u de aansluiting aanpassen om te werken met niet-standaard SMSC (d.w.z. niet exact de SMPP 3.4-specificatie volgen) of specifieke coderingsvereisten en moeten alleen door gevorderde gebruikers worden geconfigureerd.

Bij het verzenden van een SMS-bericht kan Adobe Campaign een of meer tekstcoderingen gebruiken. Elke codering heeft een eigen specifieke tekenset en bepaalt het aantal tekens dat in een SMS-bericht past.

In het **[!UICONTROL DATA_CODING]** veld kan Adobe Campaign communiceren met SMS-C welke codering wordt gebruikt.

>[!NOTE]
>
>De toewijzing tussen de werkelijk gebruikte **data_coding** -waarde en de codering wordt gestandaardiseerd. Niettemin hebben bepaalde SMS-C hun eigen specifieke kaart: in dit geval moet uw **Adobe Campaign** -beheerder deze toewijzing declareren. Vraag uw provider om meer informatie.

Met de **[!UICONTROL Define a specific mapping of encodings]** functionaliteit kunt u **data_codings** declareren en zo nodig de codering forceren: Hiervoor geeft u één codering in de tabel op.

**Configuratie**

* Wanneer de **[!UICONTROL Define a specific mapping of encodings]** functionaliteit niet wordt gecontroleerd, neemt de schakelaar een generisch gedrag over:

   * Er wordt geprobeerd GSM-codering te gebruiken waaraan de waarde **data_coding = 0** wordt toegewezen.
   * Als GSM-codering mislukt, wordt **UCS2** -codering gebruikt waaraan de waarde **data_coding = 8** wordt toegewezen.

   ![](assets/sms_data_coding.png)

* Wanneer de **[!UICONTROL Define a specific mapping of encodings]** functionaliteit is ingeschakeld, kunt u de gewenste coderingen definiëren en de gekoppelde **[!UICONTROL data_coding]** veldwaarden. Adobe Campaign probeert de eerste codering in de lijst te gebruiken. Als de eerste codering niet mogelijk is, volgt u het volgende.

   De volgorde van de verklaringen is belangrijk: U wordt aangeraden de lijst in oplopende volgorde **van kosten** te plaatsen om de coderingen te bevorderen, zodat u in elk SMS-bericht zoveel mogelijk tekens kunt plaatsen.

   Declareer alleen de coderingen die u wilt gebruiken. Als sommige van de coderingen die door SMS-C worden verstrekt niet aan uw doel van gebruik zouden moeten beantwoorden, verklaar hen niet in de lijst.

   ![](assets/sms_data_coding1.png)

### Automatisch antwoord verzonden aan de MO {#automatic-reply-sent-to-the-mo}

Wanneer een profiel op een SMS-bericht reageert dat via Campagne is verzonden, kunt u berichten configureren die automatisch naar hem worden teruggestuurd, evenals de actie die moet worden uitgevoerd.

For more information, refer to [this section](../../channels/using/managing-incoming-sms.md).

## Eigenschappen van SMS configureren {#configuring-sms-properties}

Deze sectie detailleert de lijst van parameters uniek aan SMS in het eigenschappen scherm van een levering van SMS of een malplaatje van SMS.

De specifieke parameters voor het verzenden van SMS-berichten worden opnieuw gegroepeerd in de **[!UICONTROL Send]** sectie en in de **[!UICONTROL Advanced parameters]** secties.

![](assets/sms_options.png)

In het **[!UICONTROL Advanced parameters]** gedeelte:

* Met de **[!UICONTROL From]** optie kunt u de naam van de SMS-berichtenafzender aanpassen met een reeks tekens. Dit is de naam die wordt weergegeven als de naam van de afzender van het SMS-bericht op de mobiele telefoon van de ontvanger.

   Als dit veld leeg is, wordt het bronnummer van de externe account gebruikt. Als geen bronaantal wordt verstrekt, zal het de korte code zijn die zal worden gebruikt. De externe rekening specifiek voor levering van SMS wordt voorgesteld in het [Bepalen van een SMS verpletterend](#defining-an-sms-routing) sectie.

   ![](assets/sms_smpp_2.png)

   >[!IMPORTANT]
   >
   >Controleer de wetgeving in uw land met betrekking tot het wijzigen van het adres van de afzender. Neem ook contact op met uw SMS-serviceprovider om te zien of deze deze functionaliteit aanbiedt.

Uit het **[!UICONTROL Send]** gedeelte van een SMS-sjabloon:

* Met de **[!UICONTROL Maximum number of SMS per message]** optie kunt u het aantal SMS-berichten definiëren dat moet worden gebruikt om een bericht te verzenden. Als dit aantal wordt overschreden, zal het bericht niet worden verzonden.

   >[!IMPORTANT]
   >
   >Als u verpersoonlijkingsgebieden of voorwaardelijke tekst in de inhoud van uw SMS bericht hebt opgenomen, kan de lengte van het bericht en, dientengevolge, het aantal te verzenden SMS berichten van één ontvanger aan een andere variëren. Raadpleeg de sectie [SMS-berichten](../../channels/using/personalizing-sms-messages.md) personaliseren voor meer informatie hierover.

   ![](assets/sms_smpp_3.png)

* In het **[!UICONTROL Transmission mode]** veld kunt u de leveringsmethode voor SMS-berichten bepalen:

   * **[!UICONTROL Saved on SIM card]**: het bericht wordt opgeslagen op de telefoonSIM kaart van de ontvanger.
   * **[!UICONTROL Saved on mobile]**: het bericht wordt opgeslagen op het interne geheugen van de telefoon.
   * **[!UICONTROL Flash]**: het bericht wordt op de mobiele telefoon van de ontvanger als bericht getoond, dan verdwijnt het zonder wordt bewaard.
