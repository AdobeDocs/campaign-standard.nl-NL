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
source-wordcount: '144'
ht-degree: 4%

---


# Bezoeker (nms:bezoeker)

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
        <td>opmerking</td>
        <td>Opmerking verwijzing</td>
        <td>tekenreeks (255)</td>
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
        <td>levering (levering)</td>
        <td>Levering</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>deliveryId</td>
        <td>ID van de laatste levering</td>
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
        <td>email</td>
        <td>Email</td>
        <td>string (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>externalId</td>
        <td>Externe id</td>
        <td>tekenreeks (64)</td>
        <td> </td>
    </tr>
    <tr>
        <td>firstName</td>
        <td>Voornaam</td>
        <td>tekenreeks (30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>forwardUrl</td>
        <td>Voorwaartse URL</td>
        <td>tekenreeks (255)</td>
        <td> </td>
    </tr>
    <tr>
        <td>geoUnit (geoUnitBase)</td>
        <td>Geografische eenheid</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>lastModified</td>
        <td>Laatst gewijzigd</td>
        <td>date </td>
        <td> </td>
    </tr>
    <tr>
        <td>lastName</td>
        <td>Achternaam</td>
        <td>tekenreeks (50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>modifiedBy (userBase)</td>
        <td>Gewijzigd door</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>orgUnit (orgUnitBase)</td>
        <td>Organisatorische eenheid</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>oorsprong</td>
        <td>Oorsprong</td>
        <td>opsomming (byte) </td>
        <td>
            <ul>
            <li>Niet gedefinieerd - ongedefinieerd - 0</li>
            <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>ontvanger (ontvanger)</td>
        <td>Geïdentificeerd profiel</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>receivingId</td>
        <td>Profiel-id</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>referenceEmail</td>
        <td>E-mail referentie</td>
        <td>string (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referenceFirstName</td>
        <td>Voornaam van verwijzer</td>
        <td>tekenreeks (30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referenceId</td>
        <td>Referrer-id</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>referenceLastName</td>
        <td>Achternaam verwijzende naar</td>
        <td>tekenreeks (50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referenceRcp (ontvanger)</td>
        <td>Referenter</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>titel</td>
        <td>Label</td>
        <td>tekenreeks (255)</td>
        <td> </td>
    </tr>
</table>

## Filters

Op achternaam, voornaam of e-mail (doorTekst)</p>

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