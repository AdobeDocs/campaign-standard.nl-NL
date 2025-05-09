---
title: Integratie-app Campagne-dynamiek configureren
description: Leer hoe u de integratie-app Campagne-dynamiek configureert
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 184bc656-2107-4380-9b35-148cb4380547
source-git-commit: c701043cbba22711de1ea7ddc5266e193d771e14
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 2%

---

# Systemen verbinden met de integratieapp

## Referenties toevoegen aan de integratie-app

De **[!UICONTROL Settings]** kunt u Microsoft Dynamics 365 en Adobe API-referenties opgeven. U kunt ook instellingen configureren die betrekking hebben op de Adobe Campaign SFTP-instantie.

### Microsoft Dynamics 365 Credentials

De Referentials van de Dynamica 365 van Microsoft geven de integratietoepassing toestemming om uw gegevens van de Dynamica 365 van Microsoft te trekken.  U moet eerst de stappen op het scherm volgen [Microsoft Dynamics 365 configureren voor integratie van campagnes](../../integrating/using/d365-acs-configure-d365.md) om de waarden te genereren die in dit scherm worden geplakt. De hieronder beschreven ingangen verwijzen naar dit scherm.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**: Leer hoe u naar uw client-id kunt verwijzen in [deze sectie](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Client Secret]**: Leer hoe u uw clientgeheim kunt genereren in [deze sectie](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]**: Meer informatie over het vinden van je huurder-id in [deze sectie](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]**: De URL heeft de notatie `https://&lt;servername&gt;.api.crm.dynamics.com/`

### Adobe API-referenties

De Adobe Campaign-referenties worden gegenereerd met [Adobe I/O](https://www.adobe.io/). U moet het scherm bezoeken [Adobe I/O configureren](../../integrating/using/d365-acs-configure-adobe-io.md) en volgt u de instructies in deze sectie voordat u de invoer kunt invullen.

* Selecteer Auth Type als Oauth aangezien op JWT gebaseerde authentificatie verouderd is.
* In de volgende afbeelding wordt de koppeling tussen de invoer van het Adobe I/O- en het instellingenscherm uitgebreid uitgelegd.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *URL*: Deze waarde past in het patroon https\://mc.adobe.io/&lt;campaign-instance-name>. De koptekst van de integratie-app bevat zowel de &#39;&#39;Org&#39;&#39; als &#39;&#39;Instance&#39;&#39;. Het gedeelte ‘Campagne-instance-name’ van de URL is gewoon de naam die in deze instantiewaarde wordt gevonden.

## Adobe Campaign SFTP-instellingen {#ac-smtp-settings}

Deze instellingen zijn optioneel. U moet ze definiëren als u de Adobe Campaign SFTP-instantie wilt gebruiken voor de uitvoer van logbestanden van de connector. Dit zal nuttig zijn als u problemen ervaart wanneer de integratie loopt en u moet zuiveren waarom de output niet aan uw verwachtingen voldoet.

De andere reden om de SFTP-server in te stellen is als u de workflow voor het in- en uitschakelen van de server wilt gebruiken en er een gegevensstroom is van Adobe Campaign naar Microsoft Dynamics 365, ofwel **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** of **[!UICONTROL Bidirectional]**.

>[!IMPORTANT]
>
>U bent verantwoordelijk voor de informatie die u opent en downloadt van de omslagen SFTP. Als de informatie persoonlijke gegevens bevat, moet u zich aan de toepasselijke privacywetten en -regels houden. [Meer informatie](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).
>

Om de montages van SFTP van de Campagne voor de Integratie van de Dynamica 365 van Microsoft te bepalen, heb toegang tot de volgende sectie:

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

U moet het volgende opgeven:

* **SFTP-host**: dit veld bevat &lt;campaign-instance-name>.campaign.adobe.com. De header van de integratie-app bevat zowel de **Org** en **Instantie**. Het gedeelte ‘Campagne-instance-name’ van de URL is gewoon de naam die in deze instantiewaarde wordt gevonden.

* **SFTP-gebruiker**: Als u de gebruiker SFTP hebt, voeg het hier toe. Anders, verwijs naar [deze sectie](#ac-control-panel-settings). Als onderdeel van het proces wordt de gebruikersnaam weergegeven.

* **SFTP-sleutel**: Als u een SSH-sleutel hebt, voegt u deze hier toe. Anders, verwijs naar [deze sectie](#ac-control-panel-settings).

* De **IP-bereiken** moet worden opgenomen in uw Adobe Campaign SFTP-configuratie. Deze zullen moeten worden gevoegd op lijst van gewenste personen opdat de integratie van het eindpunt SFTP gebruik kan maken.

* De **Wilt u logbestanden exporteren naar uw Adobe Campaign SFTP?** staat u toe om te bepalen als de integratie logboekinformatie aan het eindpunt van SFTP zal uitvoeren. Dit kan worden gebruikt om met het zuiveren te helpen als Adobe Campaign of de Dynamica 365 van Microsoft niet de informatie toont u verwacht.

## SFTP-instelling in Adobe Campaign {#ac-control-panel-settings}

SFTP-beheer detecteren met [Campagne](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=nl) in deze punten:

* [SFTP-beheer](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=nl#sftp-management)

* [SFTP-opslagbeheer](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=nl-NL#installing-ssh-key)

* [IP-bereiken toevoegen](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html?lang=nl-NL#sftp-management)

* [Sleutels beheren](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=nl-NL#sftp-management)

* [Aanmelden bij uw SFTP-server](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html?lang=nl-NL#sftp-management)

Nadat de configuratie is voltooid, meldt u zich met de persoonlijke sleutel aan bij de SFTP-server en maakt u de map &quot;d365_loads/exporting&quot;.

[Bezoek deze pagina](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=nl#sftp-management) voor informatie over de Adobe Campaign Standard SFTP-server.
