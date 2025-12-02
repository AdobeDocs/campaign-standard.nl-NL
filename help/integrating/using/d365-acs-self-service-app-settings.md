---
title: Integratie-app Campagne-dynamiek configureren
description: Leer hoe u de integratie-app Campagne-dynamiek configureert
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 184bc656-2107-4380-9b35-148cb4380547
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 2%

---

# Systemen verbinden met de integratieapp

## Referenties toevoegen aan de integratie-app

In het scherm **[!UICONTROL Settings]** kunt u Microsoft Dynamics 365- en Adobe API-referenties opgeven. U kunt ook instellingen configureren die betrekking hebben op de Adobe Campaign SFTP-instantie.

### Microsoft Dynamics 365 Credentials

De Microsoft Dynamics 365 Credentials geven de integratietoepassing toestemming om uw gegevens van Microsoft Dynamics 365 te trekken.  U moet de stappen op het scherm [&#x200B; eerst volgen vormen Microsoft Dynamics 365 voor de integratie van de Campagne &#x200B;](../../integrating/using/d365-acs-configure-d365.md) om de waarden te produceren die in dit scherm zullen worden gekleefd. De hieronder beschreven ingangen verwijzen naar dit scherm.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**: Leer hoe te om uw identiteitskaart van de Cliënt in [&#x200B; te verwijzen deze sectie &#x200B;](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Client Secret]**: Leer hoe te om uw Geheim van de Cliënt in [&#x200B; te produceren deze sectie &#x200B;](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]**: Leer hoe te om uw identiteitskaart van de Huurder in [&#x200B; te vinden deze sectie &#x200B;](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]**: De URL heeft de indeling `https://&lt;servername&gt;.api.crm.dynamics.com/`

### Adobe API-referenties

De geloofsbrieven van Adobe Campaign worden geproduceerd gebruikend [&#x200B; Adobe I/O &#x200B;](https://www.adobe.io/). U zult het scherm [&#x200B; moeten bezoeken vormt Adobe I/O &#x200B;](../../integrating/using/d365-acs-configure-adobe-io.md) en volgt de instructies daar alvorens u de input in deze sectie zult kunnen invullen.

* Selecteer Auth Type als Oauth aangezien op JWT gebaseerde authentificatie verouderd is.
* In de volgende afbeelding wordt de toewijzing tussen Adobe I/O en de invoer van het instellingenscherm uitgebreid uitgelegd.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *URL*: Deze waarde zal het patroon https \://mc.adobe.io/&lt;campagne-instance-name> passen. De koptekst van de integratie-app bevat zowel de &#39;&#39;Org&#39;&#39; als &#39;&#39;Instance&#39;&#39;. Het gedeelte ‘Campagne-instance-name’ van de URL is gewoon de naam die in deze instantiewaarde wordt gevonden.

## Adobe Campaign SFTP-instellingen {#ac-smtp-settings}

Deze instellingen zijn optioneel. U moet ze definiëren als u de Adobe Campaign SFTP-instantie wilt gebruiken voor de uitvoer van logbestanden van de connector. Dit zal nuttig zijn als u problemen ervaart wanneer de integratie loopt en u moet zuiveren waarom de output niet aan uw verwachtingen voldoet.

De andere reden om de SFTP-server in te stellen is als u de workflow voor het in- en uitschakelen van de server wilt uitvoeren en er een gegevensstroom is van Adobe Campaign naar Microsoft Dynamics 365, **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** of **[!UICONTROL Bidirectional]** .

>[!IMPORTANT]
>
>U bent verantwoordelijk voor de informatie die u opent en downloadt van de omslagen SFTP. Als de informatie persoonlijke gegevens bevat, moet u zich aan de toepasselijke privacywetten en -regels houden. [Meer informatie](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).
>

Als u de instellingen voor Campagne SFTP voor de Microsoft Dynamics 365-integratie wilt definiëren, opent u de volgende sectie:

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

U moet het volgende opgeven:

* **gastheer SFTP**: dit gebied zal &lt;campagne-instantie-name>.campaign.adobe.com bevatten. De kopbal van de integratie app omvat zowel **Org** als **Instantie**. Het gedeelte ‘Campagne-instance-name’ van de URL is gewoon de naam die in deze instantiewaarde wordt gevonden.

* **Gebruiker SFTP**: Als u de gebruiker SFTP hebt, voeg het hier toe. Anders, verwijs naar [&#x200B; deze sectie &#x200B;](#ac-control-panel-settings). Als onderdeel van het proces wordt de gebruikersnaam weergegeven.

* **Sleutel SFTP**: Als u een Sleutel SSH hebt, voeg het hier toe. Anders, verwijs naar [&#x200B; deze sectie &#x200B;](#ac-control-panel-settings).

* De **IP Waaier** zal nodig zijn om in uw configuratie van Adobe Campaign SFTP worden omvat. Deze zullen moeten worden gevoegd op lijst van gewenste personen opdat de integratie van het eindpunt SFTP gebruik kan maken.

* **wilt u logboeken naar uw Adobe Campaign SFTP uitvoeren?** staat u toe om te bepalen als de integratie registrereninformatie aan het eindpunt van SFTP zal uitvoeren. Dit kan worden gebruikt om met het zuiveren te helpen als Adobe Campaign of Microsoft Dynamics 365 niet de informatie toont u verwacht.

## SFTP-instelling in Adobe Campaign {#ac-control-panel-settings}

Ontdek het beheer SFTP met [&#x200B; het Controlebord van de Campagne &#x200B;](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=nl) in deze secties:

* [SFTP-beheer](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=nl#sftp-management)

* [SFTP-opslagbeheer](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html#installing-ssh-key)

* [&#x200B; voeg IP waaiers &#x200B;](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html#sftp-management) toe

* [&#x200B; beheert sleutels &#x200B;](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html#sftp-management)

* [&#x200B; Logon aan uw server SFTP &#x200B;](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html#sftp-management)

Nadat de configuratie is voltooid, meldt u zich met de persoonlijke sleutel aan bij de SFTP-server en maakt u de map &quot;d365_loads/exporting&quot;.

[&#x200B; Bezoek deze pagina &#x200B;](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=nl#sftp-management) voor informatie over de server van Adobe Campaign Standard SFTP.
