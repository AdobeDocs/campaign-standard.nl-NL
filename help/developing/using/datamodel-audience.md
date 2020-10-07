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
source-wordcount: '207'
ht-degree: 5%

---


# Publiek (nms:publiek)

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
                  <td>amMappingId</td>
                  <td>Toewijzing-id Audience Manager</td>
                  <td>tekenreeks (100)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>amcDataSource (amcDataSourceBase)</td>
                  <td>AMC-gegevensbron</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>publiekData</td>
                  <td>Voorvertoning geselecteerde populatie</td>
                  <td>collectie </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>publiekDataSchema</td>
                  <td>Gegevensschema</td>
                  <td>tekenreeks (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>publiekMetadata</td>
                  <td>AudienceMetadata</td>
                  <td>tekenreeks (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>collectLineNumber</td>
                  <td>Een regelnummer als id gebruiken</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>count</td>
                  <td>Aantal</td>
                  <td>integer </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countDate</td>
                  <td>Teldatum</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countPreview</td>
                  <td>CountPreview</td>
                  <td>item </td>
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
                  <td>doNotPerist</td>
                  <td>Deze taak niet historiseren</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>errorLimit</td>
                  <td>Fouten vóór afsluiten</td>
                  <td>integer </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>expirationDate</td>
                  <td>Verloopt op</td>
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
                  <td>hasSchema</td>
                  <td>HasSchema</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isAMC</td>
                  <td>Adobe Marketing Cloud-publiek</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>Is externe bron</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>jobLogs</td>
                  <td>Logboeken</td>
                  <td>collectie </td>
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
                  <td>ignoreFilename</td>
                  <td>Afwijzingsbestand</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sharedAudience</td>
                  <td>Naam van het gedeelde publiek</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>bron</td>
                  <td>Bron</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sourceId</td>
                  <td>Bron-id</td>
                  <td>integer </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>titel</td>
                  <td>Doelgroep</td>
                  <td>tekenreeks (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>type</td>
                  <td>Type</td>
                  <td>opsomming (tekenreeks) (100)</td>
                  <td>
                     <ul>
                        <li>Query - query - query</li>
                        <li>Lijst - lijst - lijst</li>
                        <li>Bestand - bestand - bestand</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>waar</td>
                  <td>Query-definitie</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflow (workflow)</td>
                  <td>Workflow</td>
                  <td>link </td>
                  <td> </td>
               </tr>
            </table>

## Filters

Door dimensie te filteren (doorFilteringResource)

<table>
    <tr>
    <th>Naam</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>filteringResource</td>
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

Op type (byType)

<table>
    <tr>
    <th>Naam</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>type</td>
    <td>opsomming</td>
    </tr>
    <tr>
    <td>isAMC</td>
    <td>string</td>
    </tr>
</table>