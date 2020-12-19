---
solution: Campaign Standard
product: campaign
title: De integratie van Microsoft Dynamics 365 voor Campaign configureren
description: Leer hoe te om de Dynamica 365 van Microsoft voor de integratie van de Campagne te vormen.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 2%

---


# De integratie van Microsoft Dynamics 365 voor Campaign configureren

Leer hoe te om de integratie van de Dynamica 365 van Microsoft te vormen en uw gegevens van CRM op dwars-kanaalmededeling met Adobe Campaign Standard te activeren.

## Overzicht

Adobe Campaign Standard - Microsoft Dynamics 365-integratie wordt beschreven in [deze pagina](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

Drie systemen die voor deze integratie moeten worden voorzien:

1. Adobe Campaign Standard - [Meer informatie](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
1. Microsoft Dynamics 365 for Sales - Hieronder beschreven
1. Integratiefunctie - eigendom van het Adobe Consulting-team

Zodra provisioned, moeten deze systemen door een Beheerder worden gevormd.

Dit artikel benadrukt de stappen, aan de kant van de Dynamica 365 van Microsoft, die tijdens pre-integratieopstelling worden vereist om een klant toe te laten om de integratie te gebruiken Adobe Campaign Standard - de Dynamica 365 van Microsoft.

>[!NOTE]
>
>Tot UI voor het zelfbedieningshulpmiddel later dit jaar beschikbaar is, zal het onboarding team u in het vormen van de integratie helpen.

## Vereisten

Alvorens de pre-integratieopstelling in dit document uit te voeren, wordt verondersteld dat u reeds provisioned en beheerdertoegang tot de Dynamica 365 instantie van Microsoft van uw organisatie hebt.  Als dit niet is gebeurd, dan zult u in contact met de klantensteun van Microsoft moeten krijgen om Dynamica 365 te voltooien levering.

Als u de integratie voor zowel het opvoeren als productiemilieu&#39;s vormt, zult u de hieronder stappen voor zowel uw het opvoeren als dynamiek 365 van de productie instanties moeten uitvoeren. Enkele instructies hieronder variëren enigszins, afhankelijk van het feit of u een werkgebied of een instantie van de Dynamica 365 van de productie configureert (bijvoorbeeld, voor een productieinstantie selecteert u &quot;prod&quot; voor `<stage or prod>`)

## Toepassing en machtigingen instellen

Een toegangstoken OAuth staat het integratiehulpmiddel toe om met uw instantie van de Dynamica 365 van Microsoft via Web APIs voor authentiek te verklaren om de ervaringsgebeurtenissen van de Campaign Standard aan de chronologiemening van de Dynamica 365 van Microsoft te posten.

De volgende video bevat een overzicht van de belangrijkste stappen:

>[!VIDEO](https://video.tv.adobe.com/v/27637)

Volg de onderstaande stappen om het toegangstoken OAuth te genereren.

### Nieuwe toepassing registreren

1. Meld u aan bij portal.azure.com onder uw beheerdersaanmelding.

1. Klik op **[!UICONTROL Azure Active Directory]** in het linkerzijmenu; Klik vervolgens op **[!UICONTROL App registrations]** in het submenu dat wordt weergegeven.

1. Klik **[!UICONTROL New registration]** bij de bovenkant van het scherm.

   ![](assets/do-not-localize/MSdynACSIntegration-7.png)

1. Vul het registratiescherm voor de app in:

   * Naam: adobe campagne `<stage or prod>`
   * Ondersteund accounttype: **[!UICONTROL Accounts in this organizational directory only]** (standaardwaarde)

Raadpleeg [deze sectie](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app) voor meer informatie over het maken van een nieuwe toepassing.

>[!NOTE]
>
>Azure AD wijst een unieke toepassings`-(client)id toe aan uw app. U zult deze identiteitskaart later in het vormen van Dynamiek 365 nodig hebben, evenals wanneer u pre-integratieopstelling voor het integratiehulpmiddel uitvoert.

### Klantgeheim genereren

1. Klik in het scherm met het overzicht van de app op **[!UICONTROL Certificates and Secrets > New client secret]** in het submenu links

   ![](assets/do-not-localize/MSdynACSIntegration-8.png)

1. Voer een beschrijving in, stel de duur in en klik op **[!UICONTROL OK]**.

Uw clientgeheim is nu gemaakt. Bewaar de waarde tijdelijk voor de voltooiing van de pre-integratieopstelling van het integratiehulpmiddel.

>[!CAUTION]
>
>Behoud deze waarde zoals u deze nodig hebt om de integratie-tool vóór de integratie te voltooien. Het kan achteraf niet worden opgehaald.


### Machtigingen instellen

1. Klik op **[!UICONTROL API permissions]** in het submenu links van dit scherm of het scherm met het toepassingsoverzicht.  Nadat u op **[!UICONTROL Add a permission]** hebt geklikt, moet u **[!UICONTROL Dynamics CRM]** in het menu selecteren.

   ![](assets/do-not-localize/MSdynACSIntegration-9.png)

1. Schakel vervolgens het vakje voor **[!UICONTROL user_impersonation]** in en klik op de knop **[!UICONTROL Add permissions]**.

   ![](assets/do-not-localize/MSdynACSIntegration-10.png)

Voor meer informatie over toestemmingsopstelling, verwijs naar [deze sectie](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis).

### De gebruiker van de app maken

Deze nieuwe gebruiker is een generieke gebruiker. Deze wordt door de toepassing gebruikt: om het even welke verandering in de Dynamiek 365 van Microsoft gebruikend API zal door deze gebruiker worden gedaan. Voer de volgende stappen uit om het bestand te maken:

1. Navigeer naar de instantie Dynamics 365 en meld u aan als Admin.

1. Klik op het tandwielpictogram in de rechterbovenhoek en klik op **[!UICONTROL Advanced Settings]**. Klik in de bovenste banner op de vervolgkeuzelijst naast **[!UICONTROL Settings]** en klik op **[!UICONTROL Security > Users]**.

1. Klik op het drop-down menu ga naar **[!UICONTROL Application Users]**. Klik op **[!UICONTROL New]**.

1. Verzeker drop-down naast gebruikerspictogram zegt **[!UICONTROL USER:APPLICATION USER]**.

   Vul het scherm voor de nieuwe gebruiker in.  Suggesties voor parameters:

   * **[!UICONTROL User Name]** (e-mail): adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot; (bijvoorbeeld adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**: Id van de toepassing die u hebt geregistreerd in Azure AD (dit is verplicht)
   * U kunt lege **[!UICONTROL Application ID URI]** en **[!UICONTROL Azure AD Object ID]** verlaten
   * **[!UICONTROL Full Name]**: Adobe API  `<stage or prod>`
   * **[!UICONTROL Email]**: hetzelfde als  **[!UICONTROL User Name]** (of het e-mailbericht van de beheerder als u dat wenst)

   Raadpleeg [deze sectie](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user) voor meer informatie over het maken van apps.

1. Klik op het gebruikerspictogram en upload een Adobe Campaign-pictogram. Dit is het pictogram dat in de mening van de Chronologie zal worden getoond wanneer de nieuwe gebeurtenissen van de Adobe in Dynamiek 365 verschijnen.

<!-- ***getfile*** adobe campaign logo-->

1. Open de lijst met gebruikersrollen door op **[!UICONTROL MANAGE ROLES]** in het bovenste lint te klikken.

1. Schuif omlaag en selecteer **[!UICONTROL System administrator]** toegang voor deze gebruiker.

1. Klik op **[!UICONTROL OK]**.

### De huurder-id ophalen

Volg de instructies [op deze pagina](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id) om uw huurder te vinden identiteitskaart  U hebt deze id nodig tijdens de installatie vóór de integratie in het integratieprogramma.

## Campaign Standard installeren voor Microsoft Dynamics 365

Volg onderstaande stappen om de Dynamics 365 App te integreren in uw Campaign Standard-omgeving:

1. Ga naar de volgende koppeling: [https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps) en zoek naar _Adobe Campaign for Dynamics 365_ in de zoekbalk.
U kunt ook naar deze [koppeling](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview) navigeren.
1. Volg de instructies om app voor uw instantie Dynamics 365 te installeren.
1. Na geïnstalleerd, navigeer aan uw instantie van de Dynamiek 365 en teken binnen als beheerder.
1. Klik op het tandwielpictogram in de rechterbovenhoek en klik op **[!UICONTROL Advanced Settings]**. Klik in de bovenste banner op de vervolgkeuzelijst naast **[!UICONTROL Settings]** en klik op **[!UICONTROL Processes]** onder **[!UICONTROL Process Center]**.
1. Zoek naar **[!UICONTROL Adobe Campaign Email Bounce]** taak en klik het.
1. Wijzig op het tabblad **[!UICONTROL Administration]** de eigenaar in de eerder gemaakte gebruiker van de Adobe API-toepassing door in het bovenste lint op **[!UICONTROL Actions]** te klikken en selecteer vervolgens **[!UICONTROL Assign to another User]** in het vervolgkeuzemenu **[!UICONTROL Adobe API application user]** om toe te wijzen.
1. Activeer het proces opnieuw.
1. Doe het zelfde voor de **[!UICONTROL Adobe Campaign Email Click]** taak.

>[!NOTE]
>
>Als u deze processen wilt deactiveren, kunt u dit op dit **[!UICONTROL Processes]** scherm doen.

**Verwante onderwerpen**

* [Campaign Standard - Integratie van Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* [De integratie van Adobe IO voor Microsoft Dynamics 365 configureren](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
