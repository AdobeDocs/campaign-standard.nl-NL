---
title: De integratie van Microsoft Dynamics 365 voor Campaign configureren
description: Leer hoe u Microsoft Dynamics 365 for Campaign-integratie configureert.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 57e85f8e-65b4-44ea-98e6-0c555acf6dee
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 1%

---

# Microsoft Dynamics 365 configureren voor integratie met Adobe Campaign Standard

Leer hoe u de integratie van Microsoft Dynamics 365 configureert en uw CRM-gegevens activeert voor communicatie tussen kanalen met Adobe Campaign Standard.

## Overzicht

De algemene beschrijving van de integratie van Adobe Campaign Standard met Microsoft Dynamics 365 wordt beschreven in [deze pagina](../../integrating/using/d365-acs-get-started.md).

De veelvoudige toepassingen zullen moeten worden gevormd om de integratie toe te laten, echter, zal dit artikel zich op stappen concentreren die binnen Dynamica 365 worden vereist.

## Vereisten

Voordat u de instellingen voor de pre-integratie uitvoert in dit document, wordt aangenomen dat u al voorzieningen hebt getroffen en beheerdersrechten hebt voor de Microsoft Dynamics 365-instantie van uw organisatie.  Als dit niet is gebeurd, dan zult u in contact met de klantensteun van Microsoft moeten krijgen om Dynamica 365 levering te voltooien.

Als u de integratie voor zowel het opvoeren als productiemilieu&#39;s vormt, zult u de hieronder stappen voor zowel uw het opvoeren als dynamiek 365 van de productie instanties moeten uitvoeren. Enkele instructies hieronder variëren enigszins, afhankelijk van het feit of u een werkgebied of een instantie van de productietynamiek van 365 configureert (bijvoorbeeld, voor een productieinstantie selecteert u &quot;prod&quot; voor `<stage or prod>`)

## Toepassing en machtigingen instellen

Met een OAuth-toegangstoken kan het integratiegereedschap via web-API&#39;s verifiëren met uw Microsoft Dynamics 365-instantie om Campaign Standard-ervaringsgebeurtenissen te posten naar de tijdlijnweergave van de Microsoft Dynamics 365-interface.

De volgende video bevat een overzicht van de belangrijkste stappen:

>[!VIDEO](https://video.tv.adobe.com/v/27637)

Volg de onderstaande stappen om het toegangstoken OAuth te genereren.

### Nieuwe toepassing registreren {#register-a-new-app}

1. Meld u aan bij [portal.azure.com](https://portal.azure.com){target="_blank"}.

1. Klikken op **[!UICONTROL Azure Active Directory]** in het linkerzijmenu; klik vervolgens op **[!UICONTROL App registrations]** in het submenu dat wordt weergegeven.

1. Klikken **[!UICONTROL New registration]** boven aan het scherm.

1. Vul het registratiescherm voor de app in:

   * Naam: adobe-campagne `<stage or prod>`
   * Ondersteund accounttype: **[!UICONTROL Accounts in this organizational directory only]** (standaardwaarde)

Voor meer informatie over het maken van een nieuwe toepassing raadpleegt u [deze sectie](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}.

>[!NOTE]
>
>Microsoft Azure Directory wijst een unieke toepassings-id (client) toe aan uw app. U zult deze identiteitskaart later in het vormen van Dynamiek 365 nodig hebben, evenals wanneer u de opstelling van het integratiehulpmiddel uitvoert.

### Klantgeheim genereren {#generate-a-client-secret}

1. Klik in het scherm met het overzicht van de toepassing op het submenu links op **[!UICONTROL Certificates and Secrets > New client secret]**

1. Voer een beschrijving in, stel de duur in en klik op **[!UICONTROL OK]**.

Uw clientgeheim is nu gemaakt. Bewaar de waarde tijdelijk voor de voltooiing van de pre-integratieopstelling van het integratiehulpmiddel.

>[!CAUTION]
>
>Behoud deze waarde zoals u deze nodig hebt om de integratie-tool vóór de integratie te voltooien. Het kan achteraf niet worden opgehaald.


### Machtigingen instellen

1. Klik in dit scherm of in het overzichtsscherm van de app op **[!UICONTROL API permissions]** in het submenu links.  Na klikken **[!UICONTROL Add a permission]** moet u **[!UICONTROL Dynamics CRM]** in het menu.

1. Schakel vervolgens het selectievakje in voor **[!UICONTROL user_impersonation]** en klik op de knop **[!UICONTROL Add permissions]** knop.

Raadpleeg voor meer informatie over het instellen van machtigingen de [deze sectie](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis){target="_blank"}.

### De gebruiker van de app maken

Deze nieuwe gebruiker is een generieke gebruiker. Deze wordt door de toepassing gebruikt: Elke wijziging in Microsoft Dynamics 365 met behulp van de API wordt uitgevoerd door deze gebruiker. Voer de volgende stappen uit om het bestand te maken:

1. Navigeer naar de instantie Dynamics 365 en meld u aan als Admin.

1. Klik op het tandwielpictogram in de rechterbovenhoek en klik op **[!UICONTROL Advanced Settings]**. Klik in de bovenste banner op de vervolgkeuzelijst naast **[!UICONTROL Settings]**, klikt u op **[!UICONTROL Security > Users]**.

1. Klik op de vervolgkeuzelijst en ga naar **[!UICONTROL Application Users]**. Klik op **[!UICONTROL New]**.

1. Vervolgkeuzelijst naast de tekst van het gebruikerspictogram controleren **[!UICONTROL USER:APPLICATION USER]**.

   Vul het scherm voor de nieuwe gebruiker in.  Suggesties voor parameters:

   * **[!UICONTROL User Name]** (e-mail): adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot; (bijv. adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**: Id van de toepassing die u hebt geregistreerd in Azure AD (dit is verplicht)
   * U kunt leeg laten **[!UICONTROL Application ID URI]** en **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**: Adobe API `<stage or prod>`
   * **[!UICONTROL Email]**: gelijk aan **[!UICONTROL User Name]** (of het e-mailbericht van de beheerder als u dat wenst)

   Raadpleeg voor meer informatie over het maken van apps door gebruikers [deze sectie](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user){target="_blank"}.

1. Klik op het gebruikerspictogram en upload een Adobe Campaign-pictogram. Dit is het pictogram dat in de mening van de Chronologie zal worden getoond wanneer de nieuwe gebeurtenissen van de Adobe in Dynamiek 365 verschijnen.

1. Open de lijst met gebruikersrollen door te klikken **[!UICONTROL MANAGE ROLES]** in het bovenste lint.

1. Omlaag schuiven en selecteren **[!UICONTROL System administrator]** toegang voor deze gebruiker.

1. Klik op **[!UICONTROL OK]**.

### De huurder-id ophalen {#get-the-tenant-id}

Volg de instructies [op deze pagina](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id) om je huurder-id te vinden.  U hebt deze id nodig tijdens de installatie vóór de integratie in het integratieprogramma.

## Campaign Standard installeren voor Microsoft Dynamics 365 {#install-appsource-app}

Volg onderstaande stappen om de Dynamics 365 App te integreren in uw Campaign Standard-omgeving:

1. Ga naar de volgende koppeling: [https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps) en zoek naar _Adobe Campaign for Dynamics 365_ in de zoekbalk.
U kunt ook naar dit item navigeren [link](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview)
{target="_blank"}.
1. Volg de instructies om app voor uw instantie Dynamics 365 te installeren.
1. Na geïnstalleerd, navigeer aan uw instantie van de Dynamiek 365 en teken binnen als beheerder.
1. Klik op het tandwielpictogram in de rechterbovenhoek en klik op **[!UICONTROL Advanced Settings]**. Klik in de bovenste banner op de vervolgkeuzelijst naast **[!UICONTROL Settings]**, klikt u op **[!UICONTROL Processes]** krachtens **[!UICONTROL Process Center]**.
1. Zoeken naar **[!UICONTROL Adobe Campaign Email Bounce]** en klik erop.
1. Op de **[!UICONTROL Administration]** , wijzigt u de eigenaar in de eerder gemaakte Adobe API-toepassingsgebruiker door op **[!UICONTROL Actions]** in het bovenste lint selecteert u vervolgens **[!UICONTROL Assign to another User]** selecteert u **[!UICONTROL Adobe API application user]** van de vervolgkeuzelijst om toe te wijzen.
1. Activeer het proces opnieuw.
1. Doe het zelfde voor **[!UICONTROL Adobe Campaign Email Click]** taak.

>[!NOTE]
>
>Als u deze processen op elk gewenst moment wilt deactiveren, kunt u dit in deze **[!UICONTROL Processes]** scherm.

**Verwante onderwerpen**

* [Integratie van Adobe Developer for Microsoft Dynamics 365 configureren](../../integrating/using/d365-acs-configure-adobe-io.md) is de volgende stap bij het opzetten van de integratie
* [Aan de slag met de zelfbedieningsintegratie-app](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) bevat de volledige lijst met stappen om de integratie op gang te brengen.
