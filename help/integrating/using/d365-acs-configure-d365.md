---
title: Microsoft Dynamics 365 configureren voor integratie van campagnes
description: Leer hoe u Microsoft Dynamics 365 voor de integratie van campagnes configureert.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 57e85f8e-65b4-44ea-98e6-0c555acf6dee
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '880'
ht-degree: 0%

---

# Microsoft Dynamics 365 configureren voor integratie met Adobe Campaign Standard

Leer hoe u de integratie met Microsoft Dynamics 365 configureert en uw CRM-gegevens activeert voor communicatie tussen kanalen met Adobe Campaign Standard.

## Overzicht

De algemene beschrijving van de integratie van Adobe Campaign Standard met Microsoft Dynamics 365 wordt beschreven in [ deze pagina ](../../integrating/using/d365-acs-get-started.md).

De veelvoudige toepassingen zullen moeten worden gevormd om de integratie toe te laten, echter, zal dit artikel zich op stappen concentreren die binnen Dynamica 365 worden vereist.

## Vereisten

Voordat u de pre-integratie-instellingen in dit document uitvoert, wordt aangenomen dat u al voorzieningen hebt getroffen en beheerdersrechten hebt voor de Microsoft Dynamics 365-instantie van uw organisatie.  Als dit niet is gebeurd, dan zult u in contact met de klantensteun van Microsoft moeten krijgen om Dynamica 365 levering te voltooien.

Als u de integratie voor zowel het opvoeren als productiemilieu&#39;s vormt, zult u de hieronder stappen voor zowel uw het opvoeren als dynamiek 365 van de productie instanties moeten uitvoeren. Enkele onderstaande instructies variëren enigszins, afhankelijk van het feit of u een werkgebied of een instantie van productiedynamiek 365 configureert (selecteer bijvoorbeeld &quot;prod&quot; voor de productie-instantie `<stage or prod>`)

## Toepassing en machtigingen instellen

Met een OAuth-toegangstoken kan het integratiegereedschap via web-API&#39;s verifiëren met uw Microsoft Dynamics 365-instantie, zodat Campaign Standard-ervaringsgebeurtenissen naar de tijdlijnweergave van de Microsoft Dynamics 365-interface kunnen worden gepost.

De volgende video bevat een overzicht van de belangrijkste stappen:

>[!VIDEO](https://video.tv.adobe.com/v/27637)

Volg de onderstaande stappen om het toegangstoken OAuth te genereren.

### Nieuwe toepassing registreren {#register-a-new-app}

1. Onder uw beheerderlogin, login aan [ portal.azure.com ](https://portal.azure.com){target="_blank"}.

1. Klik op **[!UICONTROL Azure Active Directory]** in het linkerzijmenu en klik vervolgens op **[!UICONTROL App registrations]** in het submenu dat wordt weergegeven.

1. Klik op **[!UICONTROL New registration]** boven aan het scherm.

1. Vul het registratiescherm voor de app in:

   * Naam: adobe-campagne `<stage or prod>`
   * Ondersteund accounttype: **[!UICONTROL Accounts in this organizational directory only]** (standaardwaarde)

Voor meer informatie over het creëren van een nieuwe toepassing, verwijs naar [ deze sectie ](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}.

>[!NOTE]
>
>Microsoft Azure Directory wijst een unieke toepassings-id (client) toe aan uw app. U zult deze identiteitskaart later in het vormen van Dynamiek 365 nodig hebben, evenals wanneer u de opstelling van het integratiehulpmiddel uitvoert.

### Klantgeheim genereren {#generate-a-client-secret}

1. Klik in het overzichtsscherm van de app op het submenu links op **[!UICONTROL Certificates and Secrets > New client secret]**

1. Voer een beschrijving in, stel de duur in en klik op **[!UICONTROL OK]** .

Uw clientgeheim is nu gemaakt. Bewaar de waarde tijdelijk voor de voltooiing van de pre-integratieopstelling van het integratiehulpmiddel.

>[!CAUTION]
>
>Behoud deze waarde zoals u deze nodig hebt om de integratie-tool vóór de integratie te voltooien. Het kan achteraf niet worden opgehaald.


### Machtigingen instellen

1. Klik in dit scherm of in het scherm met het toepassingsoverzicht op **[!UICONTROL API permissions]** in het submenu links.  Nadat u op **[!UICONTROL Add a permission]** hebt geklikt, moet u **[!UICONTROL Dynamics CRM]** selecteren in het menu.

1. Schakel vervolgens het vakje voor **[!UICONTROL user_impersonation]** in en klik op de knop **[!UICONTROL Add permissions]** .

Voor meer informatie over toestemmingsopstelling, verwijs naar [ deze sectie ](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis){target="_blank"}.

### De gebruiker van de app maken

Deze nieuwe gebruiker is een generieke gebruiker. Deze wordt door de toepassing gebruikt: elke wijziging in Microsoft Dynamics 365 met behulp van de API wordt door deze gebruiker uitgevoerd. Voer de volgende stappen uit om het bestand te maken:

1. Navigeer naar de instantie Dynamics 365 en meld u aan als Admin.

1. Klik op het tandwielpictogram in de rechterbovenhoek en klik op **[!UICONTROL Advanced Settings]** . Klik in de bovenste banner op de vervolgkeuzelijst naast **[!UICONTROL Settings]** en klik op **[!UICONTROL Security > Users]** .

1. Klik op het vervolgkeuzemenu om naar **[!UICONTROL Application Users]** te gaan. Klik op **[!UICONTROL New]**.

1. Verzeker drop-down naast gebruikerspictogram zegt **[!UICONTROL USER:APPLICATIONGEBRUIKER]**.

   Vul het scherm voor de nieuwe gebruiker in.  Suggesties voor parameters:

   * **[!UICONTROL User Name]** (email): adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot; (bijvoorbeeld adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**: id van de toepassing die u hebt geregistreerd in Azure AD (dit is verplicht)
   * U kunt de waarden leeg laten **[!UICONTROL Application ID URI]** en **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**: Adobe API `<stage or prod>`
   * **[!UICONTROL Email]**: gelijk aan **[!UICONTROL User Name]** (of desgewenst het e-mailbericht van de beheerder)

   Voor meer informatie over de verwezenlijking van de toepassingsgebruiker, verwijs naar [ deze sectie ](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user){target="_blank"}.

1. Klik op het gebruikerspictogram en upload een Adobe Campaign-pictogram. Dit is het pictogram dat wordt weergegeven in de tijdlijnweergave wanneer nieuwe Adobe-gebeurtenissen verschijnen in Dynamics 365.

1. Open de lijst met gebruikersrollen door op **[!UICONTROL MANAGE ROLES]** in het bovenste lint te klikken.

1. Schuif omlaag en selecteer **[!UICONTROL System administrator]** -toegang voor deze gebruiker.

1. Klik op **[!UICONTROL OK]**.

### De huurder-id ophalen {#get-the-tenant-id}

Volg de instructies [ in deze pagina ](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id) om uw huurdersidentiteitskaart te vinden.  U hebt deze id nodig tijdens de installatie vóór de integratie in het integratieprogramma.

## Campaign Standard installeren voor Microsoft Dynamics 365 {#install-appsource-app}

Volg onderstaande stappen om de Dynamics 365 App te integreren in uw Campaign Standard-omgeving:

1. Blader naar [ Van Bedrijfs Microsoft Apps ](https://appsource.microsoft.com/en-us/marketplace/apps), en onderzoek naar_Adobe Campaign Standard_ in de onderzoeksbar.
Alternatief, kunt u aan deze [ verbinding ](https://appsource.microsoft.com/en-us/product/dynamics-365/adobe.adobe_campaign_d365?tab=Overview){target="_blank"} navigeren.
1. Volg de instructies om app voor uw instantie Dynamics 365 te installeren.
1. Na geïnstalleerd, navigeer aan uw instantie van de Dynamiek 365 en teken binnen als beheerder.
1. Klik op het tandwielpictogram in de rechterbovenhoek en klik op **[!UICONTROL Advanced Settings]** . Klik in de bovenste banner op de vervolgkeuzelijst naast **[!UICONTROL Settings]** en klik op **[!UICONTROL Processes]** onder **[!UICONTROL Process Center]** .
1. Zoek naar **[!UICONTROL Adobe Campaign Email Bounce]** taak en klik het.
1. Wijzig op het tabblad **[!UICONTROL Administration]** de eigenaar in de eerder gemaakte Adobe API-toepassingsgebruiker door op **[!UICONTROL Actions]** te klikken in het bovenste lint en vervolgens de optie **[!UICONTROL Assign to another User]** te selecteren en **[!UICONTROL Adobe API application user]** te selecteren in het vervolgkeuzemenu dat u wilt toewijzen.
1. Activeer het proces opnieuw.
1. Doe het zelfde voor de **[!UICONTROL Adobe Campaign Email Click]** taak.

>[!NOTE]
>
>Als u deze processen op elk gewenst moment wilt deactiveren, kunt u dit op dit **[!UICONTROL Processes]** -scherm doen.

**Verwante onderwerpen**

* [ vorm Adobe Developer voor Microsoft Dynamics 365 integratie ](../../integrating/using/d365-acs-configure-adobe-io.md) is de volgende stap in vestiging de integratie
* [ krijgen begonnen met zelfbedienings integratie app ](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) bevat de volledige lijst van stappen om de integratie in werking te stellen te krijgen.
