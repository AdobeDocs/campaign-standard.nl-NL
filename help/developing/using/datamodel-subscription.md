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
source-wordcount: '77'
ht-degree: 6%

---


# Subscription Event (nms:rtEvent)

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
        <td>ctx</td>
        <td>Gebeurteniscontext</td>
        <td>item </td>
        <td> </td>
    </tr>
    <tr>
        <td>email</td>
        <td>Email</td>
        <td>string (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>emailFormat</td>
        <td>E-mailindeling</td>
        <td>opsomming (byte) </td>
        <td>
            <ul>
            <li>Tekst - tekst - 1</li>
            <li>HTML - html - 2</li>
            <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
            <li>Onbekend - onbekend - 0</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>eventHistoId</td>
        <td>Gearchiveerde gebeurtenis-id</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>mobilePhone</td>
        <td>Mobiel nummer</td>
        <td>tekenreeks (32)</td>
        <td> </td>
    </tr>
    <tr>
        <td>serverUrl</td>
        <td>ServerUrl</td>
        <td>string </td>
        <td> </td>
    </tr>
</table>

## Filters

Per e-mail (via e-mail)

<table>
    <tr>
    <th>Naam</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>email</td>
    <td>string</td>
    </tr>
</table>

Op status of type (byStatusOrType)

<table>
        <tr>
        <th>Naam</th>
        <th>Type</th>
        </tr>
        <tr>
        <td>status</td>
        <td>opsomming</td>
        </tr>
        <tr>
        <td>type</td>
        <td>string</td>
        </tr>
    </table>