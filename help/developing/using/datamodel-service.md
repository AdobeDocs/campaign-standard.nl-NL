---
title: DataModel Service
description: Meer informatie over het datamodel
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: a326b38f-ca88-4a44-a7c2-b6e34497a364
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 7%

---

# Service (nms:service)

## Objectbeschrijving

<table>
               <tr>
                  <th>Naam</th>
                  <th>Label</th>
                  <th>Type (lengte)</th>
                  <th>Enumeration values</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>Hoofd-id</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>builtIn</td>
                  <td>Ingebouwd toepassingsobject</td>
                  <td>boolean </td>
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
                  <td>cusPrice</td>
                  <td>Prijs</td>
                  <td>integer </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>desc</td>
                  <td>Beschrijving</td>
                  <td>tekenreeks (512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>end</td>
                  <td>Einddatum</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>Geografische eenheid</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>history</td>
                  <td>Subscription history</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>Is externe bron</td>
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
                  <td>limitedDuration</td>
                  <td>Limited duration</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mainDate</td>
                  <td>Datum</td>
                  <td>datum (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>messageType</td>
                  <td>Kanaal</td>
                  <td>opsomming (byte) </td>
                  <td>
                     <ul>
                        <li>Mobile (SMS) - sms - 1</li>
                        <li>E-mail - e-mail - 0</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>mode</td>
                  <td>Modus</td>
                  <td>opsomming (byte) </td>
                  <td>
                     <ul>
                        <li>Viral - 1</li>
                        <li>Nieuwsbrief - nieuwsbrief - 0</li>
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
                  <td>orgUnit (orgUnitBase)</td>
                  <td>Organisatorische eenheid</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>publicLabel</td>
                  <td>Servicelabel</td>
                  <td>string (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>start</td>
                  <td>Begindatum</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subLandingPage (landingPageSubscriptionBase)</td>
                  <td>bestemmingspagina voor abonnement</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subScenario (deliveryMCTemplateBase)</td>
                  <td>Bevestiging van abonnement</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subScenarioEventType</td>
                  <td>SubScenarioEventType</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>abonnementen</td>
                  <td>Lidmaatschappen</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>targetResource</td>
                  <td>Doeldimensie</td>
                  <td>tekenreeks (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>template (service)</td>
                  <td>Servicesjabloon</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>miniatuur</td>
                  <td>Miniatuur</td>
                  <td>tekenreeks (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>title</td>
                  <td>Service</td>
                  <td>tekenreeks (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubLandingPage (landingPageUnsubscriptionBase)</td>
                  <td>Landingspagina voor abonnement opzeggen</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubScenario (deliveryMCTemplateBase)</td>
                  <td>Abonnementsbevestiging</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubScenarioEventType</td>
                  <td>UnsubScenarioEventType</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>validityDuration</td>
                  <td>Validity duration</td>
                  <td>getal </td>
                  <td> </td>
               </tr>
            </table>

## Filters

Beschikbaar tijdens de opgegeven periode (perPlanning)

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

By name or label (byText)

<table>
<tr>
<th>Naam</th>
<th>Type</th>
</tr>
<tr>
<td>text</td>
<td>string</td>
</tr>
</table>

Door resource aan te wijzen (byTargetResource)

<table>
<tr>
<th>Naam</th>
<th>Type</th>
</tr>
<tr>
<td>targetResource</td>
<td>string</td>
</tr>
</table>
