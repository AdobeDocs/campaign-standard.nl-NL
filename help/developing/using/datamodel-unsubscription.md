---
title: DataModel
description: Meer informatie over het datamodel
uuid: 99277e46-e4f7-49a9-ba27-b878780f90da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
discoiquuid: 6e21db35-daf9-4edb-977a-6ef606db0e4d
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
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