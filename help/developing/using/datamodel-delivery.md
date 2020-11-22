---
solution: Campaign Standard
product: campaign
title: DataModel
description: Meer informatie over het datamodel
audience: developing
content-type: reference
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 6%

---


# Levering (nms:levering)

## Objectbeschrijving

<table>
               <tr>
                  <th>Naam</th>
                  <th>Label</th>
                  <th>Type (lengte)</th>
                  <th>Opsommingswaarden</th>
               </tr>
               <tr>
                  <td>FCP</td>
                  <td>Proef</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>Hoofd-id</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>abTesting</td>
                  <td>A/B-tests</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geavanceerd</td>
                  <td>Geavanceerde levering</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>advancedParameters</td>
                  <td>Geavanceerde parameters</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>aemContents</td>
                  <td>Adobe Experience Manager-inhoud</td>
                  <td>collectie </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>alertMessage</td>
                  <td>Waarschuwingsbericht</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>alertMode</td>
                  <td>Type waarschuwing</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>bijlage</td>
                  <td>Bijgevoegde bestanden</td>
                  <td>collectie </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>branding (brandingBase)</td>
                  <td>Merk</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>wideLogs</td>
                  <td>Leveringslogboeken</td>
                  <td>collectie </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>builtIn</td>
                  <td>Ingebouwd toepassingsobject</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>campagne (campagneBase)</td>
                  <td>Campaign</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cmsAccount (extAccountAEMBase)</td>
                  <td>Adobe Experience Manager-account</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>opdrachten</td>
                  <td>Opdrachten</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>content</td>
                  <td>Inhoud</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>contentSource</td>
                  <td>Inhoudsbron</td>
                  <td>opsomming (byte) </td>
                  <td>
                     <ul>
                        <li>Adobe Experience Manager - em - 1</li>
                        <li>Adobe Campaign - campagne - 0</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>contextResourceType</td>
                  <td>Het type Resource</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>gemaakt</td>
                  <td>Gemaakt</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>createdBy (userBase)</td>
                  <td>Gemaakt door</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>deliveryMode</td>
                  <td>Leveringsmodus</td>
                  <td>opsomming (byte) </td>
                  <td>
                     <ul>
                        <li>Levering in bulk - bulkgoederen - 1</li>
                        <li>Midden-sourcing - Midden-sourcing - 4</li>
                        <li>Beschrijving - beschrijvend - 2</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                        <li>Extern - extern - 0</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>deliveryProvider (extAccountBase)</td>
                  <td>Routering</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>desc</td>
                  <td>Beschrijving</td>
                  <td>tekenreeks (512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>emailPreview</td>
                  <td>E-mailvoorbeeld</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>excludeLogs</td>
                  <td>Uitsluitingslogboeken</td>
                  <td>collectie </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>uitsluitingen</td>
                  <td>Uitsluitingsoorzaken</td>
                  <td>collectie </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>uitvoering</td>
                  <td>Uitvoeringsparameters van de levering</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>executeType</td>
                  <td>Type uitvoering</td>
                  <td>opsomming (byte) </td>
                  <td>
                     <ul>
                        <li>Uniek - één keer - 0</li>
                        <li>Continu - continu - 1</li>
                        <li>Berichtencentrum - messageCenter - 2</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>voorspellingLogs</td>
                  <td>ForecastLog</td>
                  <td>collectie </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>Geografische eenheid</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>hasAttachments</td>
                  <td>Gekoppelde bestanden toevoegen</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pictogram</td>
                  <td>Pictogram</td>
                  <td>opsomming (byte) </td>
                  <td>
                     <ul>
                        <li>Transactionele e-mail - e-mailbliksem - 60</li>
                        <li>Fax: 4</li>
                        <li>Mobiel (SMS) - sms - 1</li>
                        <li>E-mail terugsturen - emailVernieuwen - 30</li>
                        <li>Direct mail - papier - 3</li>
                        <li>Telefoon - telefoon - 2</li>
                        <li>Overige — overige — 120</li>
                        <li>Terugkerende SMS - smsRefresh - 31</li>
                        <li>Mobiele toepassing - pushNotification - 40</li>
                        <li>Transactionele SMS - smsLightning - 61</li>
                        <li>E-mail - e-mail - 0</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>Is externe bron</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isMaster</td>
                  <td>Master</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isTemplate</td>
                  <td>Sjabloon</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>herhalingen</td>
                  <td>Leveringen</td>
                  <td>collectie </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>baan</td>
                  <td>Taak</td>
                  <td>collectie </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>jobLogs</td>
                  <td>Logboeken</td>
                  <td>collectie </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>kpis</td>
                  <td>Indicatoren</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>label</td>
                  <td>Label</td>
                  <td>string (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>Laatst gewijzigd</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>logicalStatus</td>
                  <td>Uitvoerstatus</td>
                  <td>opsomming (tekenreeks) (255)</td>
                  <td>
                     <ul>
                        <li>In uitvoering - gestart - gestart</li>
                        <li>Bewerken - editie - editie</li>
                        <li>Voltooid - voltooid - voltooid</li>
                        <li>Waarschuwing - waarschuwing - waarschuwing</li>
                        <li>Onjuist - fout - fout</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>mailParameters</td>
                  <td>E-mailheaderparameters</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mainDate</td>
                  <td>Datum</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mapping (deliveryMapping)</td>
                  <td>Doeltoewijzing</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>master (deliveryBase)</td>
                  <td>Master instantie</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>masterKpis</td>
                  <td>Master indicatoren</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>messageType</td>
                  <td>Kanaal</td>
                  <td>opsomming (byte) </td>
                  <td>
                     <ul>
                        <li>Fax: 4</li>
                        <li>Mobiel (SMS) - sms - 1</li>
                        <li>E-mail - e-mail - 0</li>
                        <li>Telefoon - telefoon - 2</li>
                        <li>Direct mail - papier - 3</li>
                        <li>Mobiele toepassing - pushNotification - 40</li>
                        <li>Overige — overige — 120</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>modifiedBy (userBase)</td>
                  <td>Gewijzigd door</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>name</td>
                  <td>Id</td>
                  <td>tekenreeks (64)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>offerManagement</td>
                  <td>Aanbiedingsbeheer</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit (orgUnitBase)</td>
                  <td>Organisatorische eenheid</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>parent (deliveryBase)</td>
                  <td>Bovenliggende levering</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>prioriteit</td>
                  <td>Leveringsprioriteit</td>
                  <td>opsomming (byte) </td>
                  <td>
                     <ul>
                        <li>Hoog - hoog - 20</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                        <li>Normaal - normaal - 10</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>programma (programBase)</td>
                  <td>Programma</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>proefdrukken</td>
                  <td>Proefdrukken</td>
                  <td>collectie </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushNotificationPreview</td>
                  <td>Voorvertoning van pushmelding</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushNotificationParameters</td>
                  <td>PushNotification-parameters</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>Realtime rapporten</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>resourceVersion</td>
                  <td>Bronversie</td>
                  <td>tekenreeks (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ribbonMessage</td>
                  <td>Lint</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>scenario</td>
                  <td>Parameters van de leveringssjabloon</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>plannen</td>
                  <td>Leveringsplanning</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsParameters</td>
                  <td>SMS-parameters</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsPreview</td>
                  <td>SMS-voorvertoning</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>state</td>
                  <td>Status</td>
                  <td>opsomming (byte) </td>
                  <td>
                     <ul>
                        <li>Begin in behandeling - startPending - 51</li>
                        <li>Klaar voor levering - klaar - 45</li>
                        <li>Opnieuw in behandeling - Opnieuw proberenIn behandeling - 61</li>
                        <li>Opnieuw bezig - Opnieuw proberenInProgress - 62</li>
                        <li>Mislukt - mislukt - 87</li>
                        <li>In uitvoering - gestart - 55</li>
                        <li>Doelgericht in behandeling - targetPrepPending - 11</li>
                        <li>Aanpassing aangevraagd - messagePrepPending - 21</li>
                        <li>Gepauzeerd - gepauzeerd - 75</li>
                        <li>Bewerken - editie - 0</li>
                        <li>Voltooid - voltooid - 95</li>
                        <li>Telling bezig - targetSelection - 12</li>
                        <li>Bericht afgerond - messageReady - 25</li>
                        <li>Personalisatie of telling mislukt - voorbereidingsfout - 37</li>
                        <li>Gestopt - geannuleerd - 85</li>
                        <li>Personalisatie in uitvoering - messagePreparation - 22</li>
                        <li>Klaar voor doel - targetReady - 15</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                        <li>Arbitrage in uitvoering - targetArbitrage - 13</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>streefdoelen</td>
                  <td>Doelpopulatie van de levering</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>template (deliveryTemplateSummary)</td>
                  <td>Afleveringssjabloon</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>miniatuur</td>
                  <td>Miniatuur van levering</td>
                  <td>tekenreeks (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>titel</td>
                  <td>Levering</td>
                  <td>tekenreeks (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>bijhouden</td>
                  <td>Parameters voor tracking</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trackingLogs</td>
                  <td>Logboeken bijhouden</td>
                  <td>collectie </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trackingUrls</td>
                  <td>Bijgehouden URL's</td>
                  <td>collectie </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>triggerMessage</td>
                  <td>Parameters van het transactiebericht</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>typologie (typologyBase)</td>
                  <td>Typologie</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflow (workflowBase)</td>
                  <td>Doelworkflow</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflowStatus</td>
                  <td>Workflowstatus</td>
                  <td>opsomming (tekenreeks) (255)</td>
                  <td>
                     <ul>
                        <li>In uitvoering - gestart - gestart</li>
                        <li>Bewerken - editie - editie</li>
                        <li>Voltooid - voltooid - voltooid</li>
                        <li>Waarschuwing - waarschuwing - waarschuwing</li>
                        <li>Onjuist - fout - fout</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
            </table>

## Filters

Op kanaaltype (byChannel)

<table>
    <tr>
    <th>Naam</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>kanaal</td>
    <td>opsomming</td>
    </tr>
</table>

Op uitvoeringstype (byExecutionType)

<table>
    <tr>
    <th>Naam</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>executeType</td>
    <td>opsomming</td>
    </tr>
</table>

Op logische status (byLogicalStatus)

<table>
    <tr>
    <th>Naam</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>state</td>
    <td>opsomming</td>
    </tr>
</table>

Op naam of label (doorText)

<table>
    <tr>
    <th>Naam</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>text</td>
    <td>string</td>
    </tr>
    <tr>
    <td>mc</td>
    <td>string</td>
    </tr>
</table>

Naar periode (per periode)

<table>
    <tr>
    <th>Naam</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>timePeriod</td>
    <td>string</td>
    </tr>
</table>

Op punt (doorStartPeriod)

<table>
    <tr>
    <th>Naam</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>timePeriod</td>
    <td>string</td>
    </tr>
</table>

Op publicatiestatus (byPublicationStatus)

<table>
    <tr>
    <th>Naam</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>pStatus</td>
    <td>opsomming</td>
    </tr>
</table>

Op status (per staat)

<table>
    <tr>
    <th>Naam</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>state</td>
    <td>opsomming</td>
    </tr>
</table>

Vervolgberichten (showFollow-up)

<table>
    <tr>
    <th>Naam</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>follow-up</td>
    <td>boolean</td>
    </tr>
</table>

Geavanceerde leveringen opnemen (metGeavanceerd)

<table>
    <tr>
    <th>Naam</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>geavanceerd</td>
    <td>boolean</td>
    </tr>
</table>

Inclusief doorlopende leveringen van een heterogene lijst (met doorlopende leveringen)

<table>
    <tr>
    <th>Naam</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>withContinuous</td>
    <td>boolean</td>
    </tr>
</table>

Inclusief proefdrukken (met FCP)

<table>
    <tr>
    <th>Naam</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>withFCP</td>
    <td>boolean</td>
    </tr>
</table>

Gepland tijdens de gegeven periode (doorPlanning)

<table>
    <tr>
    <th>Naam</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>date</td>
    </tr>
</table>

Aanwezigheid tijdens een bepaalde periode (volgens kalender)

<table>
    <tr>
    <th>Naam</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>date</td>
    </tr>
</table>

Uit-de-doos tonen (showOob)

<table>
    <tr>
    <th>Naam</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>oob</td>
    <td>boolean</td>
    </tr>
</table>