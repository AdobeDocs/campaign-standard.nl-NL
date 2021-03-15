---
solution: Campaign Standard
product: campaign
title: DataModel
description: Meer informatie over het datamodel
audience: developing
content-type: reference
feature: Gegevensmodel
role: Ontwikkelaar
level: Ervaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 10%

---


# Zaadlid (nms:seedMember)

## Objectbeschrijving

<table>
               <tr>
                  <th>Naam</th>
                  <th>Label</th>
                  <th>Type (lengte)</th>
                  <th>Opsommingswaarden</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>Hoofd-id</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>land (landen)</td>
                  <td>Land</td>
                  <td>link </td>
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
                  <td>desc</td>
                  <td>Beschrijving</td>
                  <td>tekenreeks (512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>email</td>
                  <td>E-mail</td>
                  <td>string (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>emailRendering</td>
                  <td>E-mailweergave</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>fax</td>
                  <td>Fax</td>
                  <td>tekenreeks (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>Geografische eenheid</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>Is externe bron</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>Laatst gewijzigd</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>locatie</td>
                  <td>Locatie</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>marketingCloudId</td>
                  <td>Marketing Cloud-id</td>
                  <td>string (256)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mobileApp</td>
                  <td>Mobiele toepassing</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mobilePhone</td>
                  <td>Mobiel</td>
                  <td>tekenreeks (32)</td>
                  <td> </td>
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
                  <td>nms_ontvanger</td>
                  <td>Profiel</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>nms_rtEvent</td>
                  <td>Gebeurtenis</td>
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
                  <td>telefoon</td>
                  <td>Telefoon</td>
                  <td>tekenreeks (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>bewijs</td>
                  <td>Proef</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushNotification</td>
                  <td>Pushmelding</td>
                  <td>tekenreeks (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>registrationToken</td>
                  <td>Registratietoken</td>
                  <td>string (256)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sampleData</td>
                  <td>Voorbeeldgegevens</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sms</td>
                  <td>Mobiel</td>
                  <td>tekenreeks (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stateLink (status)</td>
                  <td>Staat</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>targetData</td>
                  <td>Extensie</td>
                  <td>string </td>
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
                  <td>Testprofiel</td>
                  <td>tekenreeks (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>val</td>
                  <td>Overvul</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
            </table>

## Filters

Op gebeurtenistype (byEventType)

<table>
        <tr>
        <th>Naam</th>
        <th>Type</th>
        </tr>
        <tr>
        <td>eventType</td>
        <td>string</td>
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
    </table>

Op gebruik (doorGebruik)

<table>
        <tr>
        <th>Naam</th>
        <th>Type</th>
        </tr>
        <tr>
        <td>val</td>
        <td>boolean</td>
        </tr>
        <tr>
        <td>emailRendering</td>
        <td>boolean</td>
        </tr>
        <tr>
        <td>bewijs</td>
        <td>boolean</td>
        </tr>
    </table>

Testprofiel (profiel)

<table>
    <tr>
    <th>Naam</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>zaadMember</td>
    <td>link</td>
    </tr>
</table>