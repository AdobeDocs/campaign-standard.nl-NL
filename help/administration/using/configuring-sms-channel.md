---
solution: Campaign Standard
product: campaign
title: Een sms-kanaal configureren
description: '‘Kom meer te weten over sms-configuratiestappen: routering, codering, indelingen en geavanceerde eigenschappen. ’'
audience: administration
content-type: reference
topic-tags: configuring-channels
context-tags: extAccountMobile,overview;extAccount,main;delivery,smsContent,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1625'
ht-degree: 99%

---


# Een sms-kanaal configureren{#configuring-sms-channel}

Een beheerder moet een of meer externe accounts configureren in het menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL SMS]** > **[!UICONTROL SMS accounts]** voor het verzenden van sms-berichten.

De stappen voor het maken en wijzigen van een extern account worden beschreven in de sectie [Externe accounts](../../administration/using/external-accounts.md). Hieronder vindt u de parameters die specifiek zijn voor externe accounts bij het verzenden van sms-berichten.

## Een sms-routering bepalen {#defining-an-sms-routing}

Het externe account **[!UICONTROL SMS routing via SMPP]** wordt standaard opgegeven, maar het kan nuttig zijn om andere accounts toe te voegen.

Als u het SMPP-protocol wilt gebruiken, kunt u ook een nieuw extern account maken. Voor meer informatie over het protocol en instellingen van sms raadpleegt u deze [technische opmerking](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html).

1. Maak een nieuw extern account vanaf **[!UICONTROL Administration > Application settings > External accounts]**.
1. Definieer het accounttype als **[!UICONTROL Routing]**, het kanaal als **[!UICONTROL Mobile (SMS)]** en de leveringsmodus als **[!UICONTROL Bulk delivery]**.

   ![](assets/sms_routing.png)

1. Definieer de verbindingsinstellingen.

   Als u de verbindingsinstellingen wilt invoeren die specifiek zijn voor het verzenden van sms-berichten, neemt u contact op met uw sms-serviceprovider die u zal uitleggen hoe u de verschillende velden voor externe accounts moet invullen.

   ![](assets/sms_connection.png)

   Met de optie **[!UICONTROL Enable TLS over SMPP]** kunt u SMPP-verkeer versleutelen.

   Met **[!UICONTROL Enable verbose SMPP traces in the log file]** kunt u al het SMPP-verkeer in logboekbestanden dumpen. Deze optie moet zijn ingeschakeld om problemen met de connector op te lossen en om vergelijkingen te maken met het verkeer dat door de provider wordt waargenomen.

1. Neem contact op met Adobe om de waarde te verkrijgen die u in het veld **[!UICONTROL SMS-C implementation name]** moet invoeren, afhankelijk van de gekozen provider.
1. Geef de instellingen voor het SMPP-kanaal op. In de sectie [Sms-codering en -indelingen](#sms-encoding-and-formats) vindt u meer informatie.

   Schakel **[!UICONTROL Store incoming MO in the database]** in als u alle binnenkomende sms-berichten in de tabel voor binnenkomende sms-berichten wilt opslaan. Raadpleeg deze [sectie](../../channels/using/managing-incoming-sms.md#storing-incoming-sms) voor meer informatie over het ophalen van uw binnenkomende sms-berichten.

   Met de optie **[!UICONTROL Enable Real-time KPI updates during SR processing]** kunnen de KPI’s voor **[!UICONTROL Delivered]** of **[!UICONTROL Bounces + Errors]** in real time worden bijgewerkt nadat de levering is verzonden. Deze KPI’s vindt u in het venster **[!UICONTROL Deployment]** en ze worden direct herberekend vanaf het SR (statusrapport) dat van de provider wordt ontvangen.

   ![](assets/sms_connection_1.png)

1. Definieer de parameters **[!UICONTROL Throughput and timeouts]**.

   U kunt de maximale doorvoer van uitgaande berichten (‘MT’ of Mobile Terminated) in MT per seconde specificeren. Als u ‘0’ invoert in het overeenkomstige veld, is de doorvoer onbeperkt.

   De waarden van alle velden die corresponderen met een tijdsduur, moeten in seconden worden ingevuld.

1. Definieer de specifieke parameters voor SMSC wanneer u een specifieke coderingstoewijzing moet definiëren. Raadpleeg de sectie met [SMSC-specificaties](#smsc-specifics) voor meer informatie.

   Schakel de optie **[!UICONTROL Send full phone number (send characters other than digits)]** in als u het SMPP-protocol niet wilt naleven en het voorvoegsel **[!UICONTROL +]** wilt overdragen naar de server van de sms-provider (SMSC).

   Aangezien bepaalde providers echter het gebruik van het voorvoegsel **[!UICONTROL +]** vereisen, wordt u geadviseerd contact op te nemen met uw provider, die u zal aanraden om deze optie zo nodig in te schakelen.

1. Definieer zo nodig automatische antwoorden om acties te activeren op basis van de content van een antwoord. Raadpleeg [deze sectie](../../channels/using/managing-incoming-sms.md#managing-stop-sms) voor meer informatie.
1. Sla de configuratie van het externe account voor sms-routering op.

U kunt nu uw nieuwe routering gebruiken om sms-berichten te verzenden met Adobe Campaign.

## Sms-codering en -indelingen {#sms-encoding-and-formats}

### Sms-codering, -lengte en -transliteratie {#sms-encoding--length-and-transliteration}

Standaard voldoet het aantal tekens in een sms aan de gsm-standaarden (Global System for Mobile Communications).

Sms-berichten met gsm-codering mogen maximaal 160 tekens bevatten of 153 tekens per sms voor berichten die in meerdere delen worden verzonden.

>[!NOTE]
>
>Bepaalde tekens tellen als twee tekens: accolades, vierkante haakjes, het euroteken, enzovoort. De lijst met beschikbare gsm-tekens vindt u in de sectie [Tabel met tekens - gsm-standaard](#table-of-characters---gsm-standard).

Desgewenst kunt u tekentransliteratie autoriseren door het betreffende vakje in te schakelen.

![](assets/sms_transliteration.png)

Transliteratie houdt in dat een teken van een sms door een ander teken wordt vervangen wanneer dat teken niet in aanmerking wordt genomen door de gsm-standaard.

* Als transliteratie is **toegestaan**, wordt elk teken dat niet in aanmerking wordt genomen, vervangen door een gsm-teken wanneer het bericht wordt verzonden. De letter ‘ë’ wordt bijvoorbeeld vervangen door ‘e’. Het bericht is daarom enigszins gewijzigd, maar de tekenlimiet blijft hetzelfde.
* Wanneer transliteratie **niet is geautoriseerd**, wordt elk bericht dat tekens bevat die niet in aanmerking worden genomen, verzonden in binaire indeling (Unicode). Dit betekent dat alle tekens worden verzonden zoals ze zijn. De sms-berichten met Unicode zijn echter beperkt tot 70 tekens (of 67 tekens per sms voor berichten die in meerdere delen worden verzonden). Als het maximum aantal tekens wordt overschreden, worden verschillende berichten verzonden, wat extra kosten kan veroorzaken.

>[!IMPORTANT]
>
>Als u personalisatievelden invoegt in de content van uw sms-bericht, worden mogelijk tekens ingevoegd die niet in aanmerking worden genomen door de gsm-codering. Een contentvoorbeeld vindt u in de sectie [Sms-berichten personaliseren](../../channels/using/personalizing-sms-messages.md).

Standaard is transliteratie van tekens uitgeschakeld. Als u alle tekens in uw sms-berichten wilt behouden zoals ze zijn, bijvoorbeeld om geen eigennamen te wijzigen, wordt u aangeraden deze optie niet in te schakelen.

Als uw sms-berichten echter veel tekens bevatten die Unicode-berichten genereren, kunt u deze optie inschakelen om de kosten voor het verzenden van uw berichten te beperken.

### Tabel met tekens - gsm-standaard {#table-of-characters---gsm-standard}

In deze sectie vindt u de tekens die in aanmerking worden genomen door de gsm-standaard. Alle tekens die in de hoofdtekst van het bericht worden ingevoegd, met uitzondering van de onderstaande tekens, converteren het volledige bericht naar de binaire indeling (Unicode) en beperken het tot 70 tekens. Raadpleeg de sectie [Sms-codering, -lengte en -transliteratie](#sms-encoding--length-and-transliteration) voor meer informatie.

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
   <td> “<br /> </td> 
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
   <td> ’<br /> </td> 
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
   <td> Ç<br /> </td> 
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
   <td> Æ<br /> </td> 
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
   <td> Ñ<br /> </td> 
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

CR: Enter-teken

**Geavanceerde tekens (twee keer geteld)**

^ { } [ ~ ] | €

### SMSC-specificaties {#smsc-specifics}

>[!NOTE]
>
>Met deze opties kunt u de connector aanpassen om te werken met niet-standaard-SMSC (dit betekent dat de SMPP 3.4-specificatie niet exact wordt gevolgd) of specifieke coderingsvereisten. Deze opties mogen alleen door gevorderde gebruikers worden geconfigureerd.

Wanneer u een sms-bericht verzendt, kan Adobe Campaign een of meer tekstcoderingen gebruiken. Elke codering heeft een eigen specifieke tekenset en bepaalt het aantal tekens dat in een sms-bericht past.

In het veld **[!UICONTROL DATA_CODING]** kan Adobe Campaign met SMSC communiceren om aan te geven welke codering wordt gebruikt.

>[!NOTE]
>
>De toewijzing tussen de waarde **data_coding** en de werkelijk gebruikte codering wordt gestandaardiseerd. Niettemin hebben bepaalde SMSC’s hun eigen specifieke toewijzing. In dit geval moet uw **Adobe Campaign**-beheerder deze toewijzing declareren. Neem contact op met uw provider om meer informatie te krijgen.

Met de functionaliteit **[!UICONTROL Define a specific mapping of encodings]** kunt u **data_codings** declareren en zo nodig de codering forceren. Hiervoor geeft u één codering in de tabel op.

**Configuratie**

* Wanneer de functionaliteit **[!UICONTROL Define a specific mapping of encodings]** niet is ingeschakeld, vertoont de connector generiek gedrag.

   * Er wordt geprobeerd gsm-codering te gebruiken waaraan de waarde **data_coding = 0** wordt toegewezen.
   * Als gsm-codering mislukt, wordt **UCS2** -codering gebruikt waaraan de waarde **data_coding = 8** wordt toegewezen.

   ![](assets/sms_data_coding.png)

* Wanneer de functionaliteit **[!UICONTROL Define a specific mapping of encodings]** is ingeschakeld, kunt u de gewenste coderingen en de gekoppelde **[!UICONTROL data_coding]**-veldwaarden definiëren. Adobe Campaign probeert de eerste codering in de lijst te gebruiken, en daarna de volgende codering als de eerste codering niet mogelijk is.

   De volgorde van de declaratie is belangrijk. U wordt aangeraden de lijst in oplopende volgorde **van kosten** te plaatsen om voorrang te geven aan de coderingen, zodat u in elk sms-bericht zoveel mogelijk tekens kunt plaatsen.

   Declareer alleen de coderingen die u wilt gebruiken. Als sommige van de coderingen die door SMSC worden verstrekt niet aan uw gebruiksdoel beantwoorden, declareer deze dan niet in de lijst.

   ![](assets/sms_data_coding1.png)

### Automatisch antwoord verzonden naar het MO-bericht {#automatic-reply-sent-to-the-mo}

Wanneer een profiel een sms-bericht beantwoordt dat via Campaign is verzonden, kunt u berichten configureren die automatisch naar het profiel worden teruggestuurd, evenals de actie die moet worden uitgevoerd.

Raadpleeg [deze sectie](../../channels/using/managing-incoming-sms.md) voor meer informatie.

## Sms-eigenschappen configureren {#configuring-sms-properties}

In deze sectie vindt u de lijst met parameters die uniek zijn voor sms in het eigenschappenscherm van een sms-levering of een sms-sjabloon.

De specifieke parameters voor het verzenden van sms-berichten worden opnieuw gegroepeerd in de secties **[!UICONTROL Send]** en **[!UICONTROL Advanced parameters]**.

![](assets/sms_options.png)

From the **[!UICONTROL Advanced parameters]** section:

* Met de optie **[!UICONTROL From]** kunt u de naam van de afzender van het sms-bericht aanpassen met een reeks tekens. Dit is de naam die wordt weergegeven als de afzender van het sms-bericht op de mobiele telefoon van de ontvanger.

   Als dit veld leeg is, wordt het bronnummer gebruikt dat in het externe account is opgegeven. Als er geen bronnummer is opgegeven, wordt de korte code gebruikt. Het externe account specifiek voor sms-levering wordt in de sectie [Een sms-routering bepalen](#defining-an-sms-routing) opgegeven.

   ![](assets/sms_smpp_2.png)

   >[!IMPORTANT]
   >
   >Controleer de wetgeving in uw land met betrekking tot het wijzigen van het adres van de afzender. Neem ook contact op met uw sms-serviceprovider om te controleren of deze deze functionaliteit aanbiedt.

Uit het **[!UICONTROL Send]** gedeelte van een SMS-sjabloon:

* Met de optie **[!UICONTROL Maximum number of SMS per message]** kunt u het aantal sms-berichten definiëren dat moet worden gebruikt om een bericht te verzenden. Als dit aantal wordt overschreden, wordt het bericht niet verzonden.

   >[!IMPORTANT]
   >
   >Als u personalisatievelden of voorwaardelijke tekst in de content van uw sms-bericht hebt ingevoegd, kunnen de lengte van het bericht en daarmee het aantal te verzenden sms-berichten verschillen afhankelijk van de ontvanger. Raadpleeg de sectie [Sms-berichten personaliseren](../../channels/using/personalizing-sms-messages.md) voor meer informatie.

   ![](assets/sms_smpp_3.png)

* In het veld **[!UICONTROL Transmission mode]** kunt u de leveringsmethode voor sms-berichten bepalen:

   * **[!UICONTROL Saved on SIM card]**: Het bericht wordt opgeslagen op de simkaart van de telefoon van de ontvanger.
   * **[!UICONTROL Saved on mobile]**: Het bericht wordt opgeslagen op het interne geheugen van de telefoon.
   * **[!UICONTROL Flash]**: Het bericht wordt op de mobiele telefoon van de ontvanger getoond als een melding en verdwijnt vervolgens zonder dat het wordt opgeslagen.
