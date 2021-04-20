---
title: Integratie-app Campagne-dynamiek configureren
description: Leer hoe u de integratie-app Campagne-dynamiek configureert
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 2%

---


# Systemen verbinden met de integratieapp

## Referenties toevoegen aan de integratie-app

Met het scherm **[!UICONTROL Settings]** kunt u de referenties voor Microsoft Dynamics 365 en Adobe API opgeven. U kunt ook instellingen configureren die betrekking hebben op de Adobe Campaign SFTP-instantie.

### Microsoft Dynamics 365 Credentials

De Dynamica 365 van Microsoft Referentials geeft de toestemming van de integratietoepassing om uw gegevens van de Dynamica 365 van Microsoft te trekken.  U moet eerst de stappen op het scherm [Vorm de Dynamica 365 van Microsoft voor de integratie van de Campagne ](../../integrating/using/d365-acs-configure-d365.md) om de waarden te produceren die in dit scherm zullen worden gekleefd. De hieronder beschreven ingangen verwijzen naar dit scherm.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**: Leer hoe u in  [deze sectie kunt verwijzen naar uw client-id](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Client Secret]**: Leer hoe u uw clientgeheim genereert in  [deze sectie](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]**: Meer informatie over het zoeken naar je huurder-id in  [deze sectie](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]**: De URL heeft de notatie https://&lt;servername>.api.crm.dynamics.com/

### Adobe API-referenties

De Adobe Campaign-referenties worden gegenereerd met [Adobe I/O](https://www.adobe.io/). U zult het scherm [Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md) moeten bezoeken en de instructies daar volgen alvorens u de input in deze sectie zult kunnen invullen.

In de volgende afbeelding wordt de koppeling tussen de invoer van het Adobe I/O- en het instellingenscherm uitgebreid uitgelegd.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *Persoonlijke sleutel*: het proces om dit te bepalen begint door &quot;te klikken produceert openbare/privé sleutelpaar&quot;knoop. Hiermee maakt u een ZIP-bestand dat u moet downloaden. Als u het bestand hebt gedownload, decomprimeert u het bestand. Dit resulteert in twee bestanden met de naam certificate_pub.crt en private.key. Zorg ervoor dat u private.key op een veilige plaats plaatst en deze niet deelt. Open het bestand private.key in een teksteditor. Kopieer de gehele waarde in de teksteditor (ctrl-A en ctrl-C op een pc, of cmd-A en vervolgens cmd-C op een Mac). Dit moet de regels omvatten met &quot;BEGIN PRIVATE KEY&quot; en &quot;END PRIVATE KEY&quot; in hun geheel. Plak deze volledige tekst met meerdere regels in de invoer Persoonlijke sleutel in het scherm Instellingen.

* *URL*: Deze waarde past in het patroon https\://mc.adobe.io/&lt;campaign-instance-name>. De header van de integratie-app bevat zowel de &#39;&#39;Org&#39;&#39; als &#39;&#39;Instance&#39;&#39;. Het gedeelte ‘Campagne-instance-name’ van de URL is gewoon de naam die in deze instantiewaarde wordt gevonden.

## Adobe Campaign SFTP-instellingen {#ac-smtp-settings}

Deze instellingen zijn optioneel. U moet ze definiëren als u de Adobe Campaign SFTP-instantie wilt gebruiken voor de uitvoer van logbestanden van de connector. Dit zal nuttig zijn als u problemen ervaart wanneer de integratie loopt en u moet zuiveren waarom de output niet aan uw verwachtingen voldoet.

De andere reden om de SFTP-server in te stellen is als u de workflow voor het in- en uitschakelen van de server wilt gebruiken en er een gegevensstroom is van Adobe Campaign naar Microsoft Dynamics 365, ofwel **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** of **[!UICONTROL Bidirectional]**.

>[!IMPORTANT]
>
>U bent verantwoordelijk voor de informatie die u opent en downloadt van de omslagen SFTP. Als de informatie persoonlijke gegevens bevat, moet u zich aan de toepasselijke privacywetten en -regels houden. [Meer informatie](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).


Om de montages van SFTP van de Campagne voor de Integratie van de Dynamica 365 van Microsoft te bepalen, heb toegang tot de volgende sectie:

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

U moet het volgende opgeven:

* **SFTP-host**: dit veld bevat  &lt;campaign-instance-name>.campagne.adobe.com. De koptekst van de integratie-app bevat zowel **Org** als **Instance**. Het gedeelte ‘Campagne-instance-name’ van de URL is gewoon de naam die in deze instantiewaarde wordt gevonden.

* **SFTP-gebruiker**: Als u de gebruiker SFTP hebt, voeg het hier toe. Verwijs anders naar [deze sectie](#ac-control-panel-settings). Als onderdeel van het proces wordt de gebruikersnaam weergegeven.

* **SFTP-sleutel**: Als u een SSH-sleutel hebt, voegt u deze hier toe. Verwijs anders naar [deze sectie](#ac-control-panel-settings).

* De **IP-bereiken** moeten worden opgenomen in uw Adobe Campaign SFTP-configuratie. Deze zullen moeten worden gevoegd op lijst van gewenste personen opdat de integratie van het eindpunt SFTP gebruik kan maken.

* De **Wilt u logbestanden exporteren naar uw Adobe Campaign SFTP?** staat u toe om te bepalen als de integratie logboekinformatie aan het eindpunt van SFTP zal uitvoeren. Dit kan worden gebruikt om met het zuiveren te helpen als Adobe Campaign of de Dynamica 365 van Microsoft niet de informatie toont u verwacht.

## SFTP-instelling in Adobe Campaign {#ac-control-panel-settings}

Ontdek beheer SFTP met [Campagne Controlebord](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=nl) in deze secties:

* [SFTP-beheer](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=en#sftp-management)

* [SFTP-opslagbeheer](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#installing-ssh-key)

* [IP-bereiken toevoegen](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html?lang=en#sftp-management)

* [Sleutels beheren](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#sftp-management)

* [Aanmelden bij uw SFTP-server](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html?lang=en#sftp-management)

Nadat de configuratie is voltooid, meldt u zich met de persoonlijke sleutel aan bij de SFTP-server en maakt u de map &quot;d365_loads/exporting&quot;.

[Ga naar deze ](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=en#sftp-management) pagina voor informatie over de Adobe Campaign Standard SFTP-server.
