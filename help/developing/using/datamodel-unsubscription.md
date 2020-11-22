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
source-wordcount: '53'
ht-degree: 5%

---


# Unsubscription-gebeurtenis (nms:rtEvent)

## Objectbeschrijving

<table>
               <tr>
                  <th>Naam</th>
                  <th>Alleen-lezen</th>
                  <th>Type</th>
                  <th>Vereist</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>Onwaar</td>
                  <td>string</td>
                  <td>Onwaar</td>
               </tr>
               <tr>
                  <td>ctx</td>
                  <td>Onwaar</td>
                  <td>item</td>
                  <td>Onwaar</td>
               </tr>
               <tr>
                  <td>email</td>
                  <td>Onwaar</td>
                  <td>string</td>
                  <td>Onwaar</td>
               </tr>
               <tr>
                  <td>emailFormat</td>
                  <td>Onwaar</td>
                  <td>opsomming</td>
                  <td>Onwaar</td>
               </tr>
               <tr>
                  <td>mobilePhone</td>
                  <td>Onwaar</td>
                  <td>string</td>
                  <td>Onwaar</td>
               </tr>
               <tr>
                  <td>serverUrl</td>
                  <td>Waar</td>
                  <td>string</td>
                  <td>Onwaar</td>
               </tr>
            </table>

## Filters

byEmail

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

byStatusOrType

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