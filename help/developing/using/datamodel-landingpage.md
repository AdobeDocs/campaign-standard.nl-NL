---
solution: Campaign Standard
product: campaign
title: DataModel
description: Meer informatie over het datamodel
audience: designing
content-type: reference
topic-tags: editing-sms-and-push-content
context-tags: delivery,smsContent,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1727'
ht-degree: 1%

---


# landingPage (nms:landingPage)

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
         <td>additionalData</td>
         <td>Aanvullende data</td>
         <td>collectie </td>
         <td> </td>
      </tr>
      <tr>
         <td>additionalLanguages</td>
         <td>Overige talen</td>
         <td>item </td>
         <td> </td>
      </tr>
      <tr>
         <td>allowNonIdentifiedTarget</td>
         <td>Niet-geïdentificeerde bezoekers autoriseren</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>branding (brandingBase)</td>
         <td>Merk</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>builtIn</td>
         <td>Ingebouwd toepassingsobject</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>cachegeheugen</td>
         <td>Cache</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>campagne (campagneBase)</td>
         <td>Campaign</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>closedLog</td>
         <td>Logbestand 'Openingspagina gesloten'</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>contextResourceType</td>
         <td>ContextResourceType</td>
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
         <td>cryptKey</td>
         <td>AES-coderingssleutel</td>
         <td>tekenreeks (64)</td>
         <td> </td>
      </tr>
      <tr>
         <td>defaultLanguage</td>
         <td>Standaardtaal</td>
         <td>opsomming (tekenreeks) (255)</td>
         <td>
            <ul>
               <li>Grieks - el - el</li>
               <li>Engels - en - nl</li>
               <li>Chinees - zh - zh</li>
               <li>Frans (Frankrijk) - fr_FR - fr_FR</li>
               <li>Vietnamees - vi - vi</li>
               <li>Portugees (Portugal) - pt_PT - pt_PT</li>
               <li>Italiaans (Italië) - it_IT - it_IT</li>
               <li>Italiaans - it - it</li>
               <li>Nederlands (België) - nl_BE - nl_BE</li>
               <li>Noors (Noorwegen) - no_NO - no_NO</li>
               <li>Nederlands (Nederland) - nl_NL - nl_NL</li>
               <li>Arabisch - ar - ar</li>
               <li>Engels (Verenigde Staten) - en_US - en_US</li>
               <li>Iers - ga - ga</li>
               <li>Tsjechisch - cs - cs</li>
               <li>Ests - et - et</li>
               <li>Indonesisch - id - id</li>
               <li>Spaans - es - es</li>
               <li>Russisch - ru - ru</li>
               <li>Nederlands - nl - nl</li>
               <li>Waalse - wa - wa</li>
               <li>Portugees - pt</li>
               <li>Frans (België) - fr_BE - fr_BE</li>
               <li>Lets - lv - lv</li>
               <li>Litouws - lt - lt</li>
               <li>Thai - th - th</li>
               <li>Engels (Verenigd Koninkrijk) - en_GB - en_GB</li>
               <li>Frans - fr - fr</li>
               <li>Portugees (Brazilië) - pt_BR - pt_BR</li>
               <li>Duits - de</li>
               <li>Deens - da - da</li>
               <li>Fins - fi - fi</li>
               <li>Hongaars - hu - hu</li>
               <li>Zweeds (Finland) - sv_FI - sv_FI</li>
               <li>Japans - ja - ja</li>
               <li>Hebreeuws - hij -</li>
               <li>Koreaans - ko - ko</li>
               <li>Zweeds - sv - sv</li>
               <li>Zweden (Zweeds) - sv_SE - sv_SE</li>
               <li>Slowaaks - sk - sk</li>
               <li>Maltees - mt - mt</li>
               <li>Italiaans (Zwitserland) - it_CH - it_CH</li>
               <li>Pools - pl - pl</li>
               <li>Sloveens - sl - sl</li>
               <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>defaultOrigin (delivery)</td>
         <td>Verkeersbron</td>
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
         <td>designLanguage</td>
         <td>Ontwerptaal</td>
         <td>opsomming (tekenreeks) (255)</td>
         <td>
            <ul>
               <li>Grieks - el - el</li>
               <li>Engels - en - nl</li>
               <li>Chinees - zh - zh</li>
               <li>Frans (Frankrijk) - fr_FR - fr_FR</li>
               <li>Vietnamees - vi - vi</li>
               <li>Portugees (Portugal) - pt_PT - pt_PT</li>
               <li>Italiaans (Italië) - it_IT - it_IT</li>
               <li>Italiaans - it - it</li>
               <li>Nederlands (België) - nl_BE - nl_BE</li>
               <li>Noors (Noorwegen) - no_NO - no_NO</li>
               <li>Nederlands (Nederland) - nl_NL - nl_NL</li>
               <li>Arabisch - ar - ar</li>
               <li>Engels (Verenigde Staten) - en_US - en_US</li>
               <li>Iers - ga - ga</li>
               <li>Tsjechisch - cs - cs</li>
               <li>Ests - et - et</li>
               <li>Indonesisch - id - id</li>
               <li>Spaans - es - es</li>
               <li>Russisch - ru - ru</li>
               <li>Nederlands - nl - nl</li>
               <li>Waalse - wa - wa</li>
               <li>Portugees - pt</li>
               <li>Frans (België) - fr_BE - fr_BE</li>
               <li>Lets - lv - lv</li>
               <li>Litouws - lt - lt</li>
               <li>Thai - th - th</li>
               <li>Engels (Verenigd Koninkrijk) - en_GB - en_GB</li>
               <li>Frans - fr - fr</li>
               <li>Portugees (Brazilië) - pt_BR - pt_BR</li>
               <li>Duits - de</li>
               <li>Deens - da - da</li>
               <li>Fins - fi - fi</li>
               <li>Hongaars - hu - hu</li>
               <li>Zweeds (Finland) - sv_FI - sv_FI</li>
               <li>Japans - ja - ja</li>
               <li>Hebreeuws - hij -</li>
               <li>Koreaans - ko - ko</li>
               <li>Zweeds - sv - sv</li>
               <li>Zweden (Zweeds) - sv_SE - sv_SE</li>
               <li>Slowaaks - sk - sk</li>
               <li>Maltees - mt - mt</li>
               <li>Italiaans (Zwitserland) - it_CH - it_CH</li>
               <li>Pools - pl - pl</li>
               <li>Sloveens - sl - sl</li>
               <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>dynamicService</td>
         <td>Dynamische service</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>end</td>
         <td>Vervaldatum</td>
         <td>date </td>
         <td> </td>
      </tr>
      <tr>
         <td>errorContextResourceType</td>
         <td>ErrorContextResourceType</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>errorPage</td>
         <td>Foutpagina</td>
         <td>item </td>
         <td> </td>
      </tr>
      <tr>
         <td>geoUnit (geoUnitBase)</td>
         <td>Geografische eenheid</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>htmlPage</td>
         <td>Pagina's</td>
         <td>collectie </td>
         <td> </td>
      </tr>
      <tr>
         <td>identificationByUrlParam</td>
         <td>Identificatie via URL-parameters</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>inactiveUrlRedirection</td>
         <td>URL omleiden</td>
         <td>string (4096)</td>
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
         <td>loadingFilter (queryFilterBase)</td>
         <td>Sleutel laden</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>loadingFilterMapping</td>
         <td>Parameters van de ladingssleutel</td>
         <td>collectie </td>
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
         <td>messageAction</td>
         <td>Bericht verzenden starten</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>messageActionDelivery (deliveryMCTemplateBase)</td>
         <td>Transactiebericht</td>
         <td>link </td>
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
         <td>prefill</td>
         <td>Gegevens bezoeker vooraf laden</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>programma (programBase)</td>
         <td>Programma</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>publicUrl</td>
         <td>Openbare URL</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>publicationDate</td>
         <td>Publicatiedatum</td>
         <td>date </td>
         <td> </td>
      </tr>
      <tr>
         <td>connectionFilter (queryFilterBase)</td>
         <td>Afstemmingssleutel</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>connectionFilterMapping</td>
         <td>Parameters van de afstemmingssleutel</td>
         <td>collectie </td>
         <td> </td>
      </tr>
      <tr>
         <td>connectionUpdateStrategy</td>
         <td>Update-strategie</td>
         <td>opsomming (byte) </td>
         <td>
            <ul>
               <li>Update - updateTarget - 1</li>
               <li>Niet-geautoriseerd - niet-geautoriseerd - 0</li>
               <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>service (serviceBase)</td>
         <td>Abonnementsservice</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>specificAction</td>
         <td>Specifieke actie</td>
         <td>opsomming (byte) </td>
         <td>
            <ul>
               <li>Blacklist - blackList - 3</li>
               <li>Geen specifieke actie - geen - 0</li>
               <li>Abonnement opzeggen - abonnement opgezegd - 2</li>
               <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
               <li>Abonnement - abonnement - 1</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>start</td>
         <td>Datum van implementatie</td>
         <td>date </td>
         <td> </td>
      </tr>
      <tr>
         <td>state</td>
         <td>Status</td>
         <td>opsomming (byte) </td>
         <td>
            <ul>
               <li>Bewerken - Bewerken - 0</li>
               <li>Publiceren mislukt - mislukt - 99</li>
               <li>Gesloten - gesloten - 20</li>
               <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
               <li>Online - geopend - 10</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>targetResource</td>
         <td>Doeldimensie</td>
         <td>tekenreeks (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>template (landingPage)</td>
         <td>Landingspagina-sjabloon</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>testUrl</td>
         <td>URL testen</td>
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
         <td>tijdzone</td>
         <td>Tijdzone</td>
         <td>opsomming (tekenreeks) (64)</td>
         <td>
            <ul>
               <li>(GMT-02:00) Centraal-Atlantische - Atlantische_Zuid_Georgië - Atlantische/Zuid_Georgië</li>
               <li>(GMT+02:00) Amman - Asia_Amman - Azië/Amman</li>
               <li>(GMT-03:00) Brasi - America_Sao_Paulo - America/Sao_Paulo</li>
               <li>(GMT+06:00) Astana, Dhaka - Asia_Dhaka - Azië/Dhaka</li>
               <li>(GMT+06:00) Novossibirsk - Asia_Novosibirsk - Azië/Novosibirsk</li>
               <li>(GMT+02:00) Windhoek - Afrika_Windhoek - Afrika/Windhoek</li>
               <li>(GMT+04:00) Kaukasus, Erevan - Azië_Jerevan - Azië/Jerevan</li>
               <li>(GMT-04:00) Manaus - America_Manaus - Amerika/Manaus</li>
               <li>(GMT+03:30) Teheran - Azië_Teheran - Azië/Teheran</li>
               <li>(GMT+12:00) Auckland, Wellington - Pacific_Auckland - Pacific/Auckland</li>
               <li>(GMT+02:00) Jeruzalem - Azië_Jeruzalem - Azië/Jeruzalem</li>
               <li>(GMT+03:00) Moskou, St. Petersburg, Volgograd - Europa_Moskou - Europa/Moskou</li>
               <li>(GMT+09:30) Adelaïde - Australia_Adelaide - Australia/Adelaide</li>
               <li>(GMT+10:00) Canberra, Melbourne, Sydney - Australia_Canberra - Australia/Canberra</li>
               <li>(GMT+08:00) Perth - Australia_Perth - Australia/Perth</li>
               <li>(GMT+09:00) Yakoutsk - Azië_Yakutsk - Azië/Yakutsk</li>
               <li>(GMT-10:00) Hawai - Pacific_Honolulu - Pacific/Honolulu</li>
               <li>(GMT+04:00) Bakoe - Azië_Bakoe - Azië/Bakoe</li>
               <li>(GMT+10:00) Vladivostok - Azië_Vladivostok - Azië/Vladivostok</li>
               <li>(GMT+09:00) Seoul - Asia_Seoul - Azië/Seoul</li>
               <li>(GMT+01:00) Sarajevo, Skoplje, Sofia, Warschau, Zagreb - Europe_Sarajevo - Europe/Sarajevo</li>
               <li>Tijdzone server - _server_ - _server_</li>
               <li>(GMT+04:00) Abu Dhabi, Muscat - Asia_Muscat - Azië/Muscat</li>
               <li>(GMT+08:00) Kuala Lumpur, Singapore - Azië_Kuala_Lumpur - Azië/Kuala_Lumpur</li>
               <li>(GMT+09:00) Osaka, Sapporo, Tokio - Azië_Tokio - Azië/Tokio</li>
               <li>(GMT+10:00) Brisbane - Australië_Brisbane - Australië/Brisbane</li>
               <li>(GMT+05:30) Sri Jayawardenepura - Asia_Colombo - Azië/Colombo</li>
               <li>(GMT+02:00) Harare, Pretoria - Afrika_Harare - Afrika/Harare</li>
               <li>(GMT+08:00) Oulan-Bator - Asia_Ulan_Bator - Asia/Ulan_Bator</li>
               <li>(GMT-02:00) Greenwich Mean Time minus 2 uur - Gmt_m2 - Etc/GMT+2</li>
               <li>(GMT-03:00) Greenwich Mean Time minus 3 uur - Gmt_m3 - Etc/GMT+3</li>
               <li>(GMT-01:00) Greenwich Mean Time minus 1 uur - Gmt_m1 - EC/GMT+1</li>
               <li>(GMT-06:00) Greenwich Mean Time minus 6 uur - Gmt_m6 - EC/GMT+6</li>
               <li>(GMT-07:00) Greenwich Mean Time minus 7 uur - Gmt_m7 - Etc/GMT+7</li>
               <li>(GMT-04:00) Greenwich Mean Time minus 4 uur - Gmt_m4 - Etc/GMT+4</li>
               <li>(GMT) Casablanca - Africa_Casablanca - Afrika/Casablanca</li>
               <li>(GMT+05:30) Kolkata, Chennai, Mumbai, New Delhi - Asia_Kolkata - Asia/Kolkata</li>
               <li>(GMT-11:00) Greenwich Mean Time minus 11 uur - Gmt_m11 - Etc/GMT+11</li>
               <li>(GMT-09:00) Greenwich Mean Time minus 9 uur - Gmt_m9 - EC/GMT+9</li>
               <li>(GMT-03:30) Newfoundland - America_St_Johns - America/St_Johns</li>
               <li>Standaard - _inherit_ - _inherit_</li>
               <li>(GMT+03:00) Greenwich Mean Time plus 3 uur - Gmt_p3 - Etc/GMT-3</li>
               <li>(GMT-04:30) Caracas - America_Caracas - America/Caracas</li>
               <li>(GMT+01:00) Amsterdam, Berlijn, Bern, Rome, Stockholm, Wenen - Europa_Berlijn - Europa/Berlijn</li>
               <li>(GMT-07:00) Chihuahua, La Paz, Mazatlan - America_Chihuahua - America/Chihuahua</li>
               <li>(GMT+03:00) Nairobi - Africa_Nairobi - Afrika/Nairobi</li>
               <li>(GMT-04:00) Asunción - America_Asuncion - America/Asuncion</li>
               <li>(GMT+03:00) Bagdad - Asia_Bagdad - Azië/Bagdad</li>
               <li>(GMT-10:00) Greenwich Mean Time minus 10 uur - Gmt_m10 - Etc/GMT+10</li>
               <li>(GMT-03:00) Groenland - America_Godthab - Amerika/Godthab</li>
               <li>(GMT+02:00) Damas - Asia_Damascus - Asia/Damascus</li>
               <li>(GMT-11:00) Samoa - Pacific_Samoa - Pacific/Samoa</li>
               <li>(GMT-05:00) Bogota, Lima, Quito - America_Bogota - America/Bogota</li>
               <li>(GMT+01:00) Brussel, Kopenhagen, Madrid, Parijs - Europa_Parijs - Europa/Parijs</li>
               <li>(GMT+08:00) Beijing, Chongqing, Hongkong, Urumqi - Asia_Shanghai - Azië/Shanghai</li>
               <li>(GMT+12:00) Fidji - Pacific_Fiji - Pacific/Fiji</li>
               <li>(GMT+02:00) Athene, Istanboel, Minsk - Europa_Athene - Europa/Athene</li>
               <li>(GMT+04:00) Tbilissi - Asia_Tbilisi - Azië/Tbilisi</li>
               <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
               <li>(GMT+05:45) Katmandu - Asia_Katmandu - Azië/Katmandu</li>
               <li>(GMT-05:00) Indiana (Oost) - America_Indianapolis - Amerika/Indianapolis</li>
               <li>(GMT-01:00) Kaapverdische eilanden - Atlantic_Kaapverdië - Atlantic/Kaapverdië</li>
               <li>(GMT+04:00) Port Louis - Indian_Mauritius - Indian/Mauritius</li>
               <li>(GMT+08:00) Taipei - Azië_Taipei - Azië/Taipei</li>
               <li>Tijdzone van de database - _wdbc_ - _wdbc_</li>
               <li>(GMT+06:30) Rangoon - Asia_Rangoon - Azië/Rangoon</li>
               <li>(GMT+11:00) Magadan, de Salomonseilanden, Nieuw-Caledonië - Pacific_Guadalcanal - Pacific/Guadalcanal</li>
               <li>(GMT+02:00) Caïro - Afrika_Caïro - Afrika/Caïro</li>
               <li>(GMT+05:00) Iekaterinburg - Azië_Jekaterinburg - Azië/Jekaterinburg</li>
               <li>(GMT+08:00) Irkoutsk - Azië_Irkutsk - Azië/Irkutsk</li>
               <li>(GMT+10:00) Guam, Port Moresby - Pacific_Guam - Pacific/Guam</li>
               <li>(GMT-04:00) Atlantic Standard Time (Canada) - America_Halifax - America/Halifax</li>
               <li>(GMT) Greenwich Mean Time - GMT - GMT</li>
               <li>(GMT-04:00) La Paz - America_La_Paz - America/La_Paz</li>
               <li>Tijdzone operator - _login_ - _login_</li>
               <li>(GMT-06:00) Guadalajara, Mexico, Monterrey - America_Mexico_City - America/Mexico_City</li>
               <li>(GMT+09:30) Darwin - Australia_Darwin - Australia/Darwin</li>
               <li>(GMT-05:00) Est (Verenigde Staten en Canada) - America_New_York - America/New_York</li>
               <li>(GMT-05:00) Greenwich Mean Time minus 5 uur - Gmt_m5 - EC/GMT+5</li>
               <li>(GMT+05:00) Islamabad, Karachi, Tachkent - Asia_Karachi - Asia/Karachi</li>
               <li>(GMT+03:00) Koweït, Riyad - Asia_Riyad - Asia/Riyad</li>
               <li>(GMT-08:00) Greenwich Mean Time minus 8 uur - Gmt_m8 - Etc/GMT+8</li>
               <li>(GMT-01:00) De Azoren - Atlantic_Azoren - Atlantische Oceaan/Azoren</li>
               <li>(GMT+07:00) Bangkok, Hanoi, Djakarta - Asia_Bangkok - Azië/Bangkok</li>
               <li>(GMT) Monrovia - Afrika_Monrovia - Afrika/Monrovia</li>
               <li>(GMT-09:00) Alaska - America_Anchorage - America/Anchorage</li>
               <li>(GMT+01:00) Belgrado, Bratislava, Boedapest, Ljubljana, Praag - Europa_Belgrado - Europa/Belgrado</li>
               <li>(GMT) Reykjavik - Atlantic_Reykjavik - Atlantic/Reykjavik</li>
               <li>(GMT+02:00) Boekarest - Europa_Boekarest - Europa/Boekarest</li>
               <li>(GMT+05:00) Greenwich Mean Time plus 5 uur - Gmt_p5 - Etc/GMT-5</li>
               <li>(GMT+04:00) Greenwich Mean Time plus 4 uur - Gmt_p4 - Etc/GMT-4</li>
               <li>(GMT+07:00) Greenwich Mean Time plus 7 uur - GMT_p7 - Etc/GMT-7</li>
               <li>(GMT+06:00) Greenwich Mean Time plus 6 uur - Gmt_p6 - Etc/GMT-6</li>
               <li>(GMT+01:00) Greenwich Mean Time plus 1 uur - Gmt_p1 - Etc/GMT-1</li>
               <li>(GMT-08:00) Pacific (Verenigde Staten en Canada) - America_Los_Angeles - America/Los_Angeles</li>
               <li>(GMT+02:00) Greenwich Mean Time plus 2 uur - Gmt_p2 - Etc/GMT-2</li>
               <li>(GMT+07:00) Krasnoïarsk - Azië_Krasnoyarsk - Azië/Krasnoyarsk</li>
               <li>(GMT+09:00) Greenwich Mean Time plus 9 uur - Gmt_p9 - EC/GMT-9</li>
               <li>(GMT+08:00) Greenwich Mean Time plus 8 uur - Gmt_p8 - Etc/GMT-8</li>
               <li>(GMT+10:00) Hobart - Australië_Hobart - Australië/Hobart</li>
               <li>(GMT+13:00) Nuku'alofa - Pacific_Tongatapu - Pacific/Tongatapu</li>
               <li>(GMT-06:00) Midden-Amerika - Amerika_Regina - Amerika/Regina</li>
               <li>(GMT-03:00) Buenos Aires, Cayenne, Fortaleza - America_Buenos_Aires - America/Buenos_Aires</li>
               <li>(GMT-07:00) Rocky Mountains (Verenigde Staten en Canada) - America_Denver - America/Denver</li>
               <li>(GMT+01:00) Centraal-Afrika - West - Afrika_Luanda - Afrika/Luanda</li>
               <li>(GMT+02:00) Helsinki, Kiev, Riga, Sofia, Tallinn, Vilnius - Europa_Helsinki - Europa/Helsinki</li>
               <li>(GMT) Greenwich Mean Time: Dublin, Edinburgh, Lissabon, Londen - Europe_London - Europe/London</li>
               <li>(GMT-07:00) Arizona - America_Phoenix - America/Phoenix</li>
               <li>(GMT+02:00) Beiroet - Asia_Beiroet - Azië/Beiroet</li>
               <li>(GMT+04:30) Kabul - Asia_Kabul - Azië/Kabul</li>
               <li>(GMT-06:00) Center (Verenigde Staten en Canada) - America_Chicago - America/Chicago</li>
               <li>(GMT+11:00) Greenwich Mean Time plus 11 uur - GMT_p11 - Etc/GMT-11</li>
               <li>(GMT+10:00) Greenwich Mean Time plus 10 uur - GMT_p10 - Etc/GMT-10</li>
               <li>(GMT+13:00) Greenwich Mean Time plus 13 uur - Gmt_p13 - Etc/GMT-13</li>
               <li>(GMT+12:00) Greenwich Mean Time plus 12 uur - Gmt_p12 - Etc/GMT-12</li>
               <li>(GMT-04:00) Santiago - America_Santiago - America/Santiago</li>
               <li>(GMT-03:00) Montevideo - America_Montevideo - America/Montevideo</li>
               <li>(GMT-04:00) Cuiaba - America_Cuiaba - America/Cuiaba</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>titel</td>
         <td>Landingspagina</td>
         <td>tekenreeks (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>trackingEnabled</td>
         <td>Antwoorden in logboek</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>trackingUrlName</td>
         <td>URL-naam bijhouden</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>type</td>
         <td>Type</td>
         <td>opsomming (byte) </td>
         <td>
            <ul>
               <li>Algemeen, algemeen, 0</li>
               <li>Abonnement op een service opzeggen - geen abonnement - 3</li>
               <li>Blacklist - blackList - 4</li>
               <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
               <li>Overname - overname - 1</li>
               <li>Abonnement op een service - Abonnement - 2</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>uuid</td>
         <td>Beveiligings-id</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>webTrackingEnabled</td>
         <td>Webtracering inschakelen</td>
         <td>boolean </td>
         <td> </td>
      </tr>
   </table>

## Filters

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

Geavanceerde bestemmingspagina&#39;s opnemen (metGeavanceerd)

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

Gepubliceerd tijdens een bepaalde periode (perPlanning)

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
