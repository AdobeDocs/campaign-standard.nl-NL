---
title: Een landingspagina configureren
description: Ontdek hoe u de eigenschappen van een landingspagina configureert.
page-status-flag: never-activated
uuid: 5b222ea2-6628-457f-a618-bfc0e5eb93dd
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: 899c7152-f415-4df9-b4b4-5ff3470a4e32
context-tags: landingPage,main
internal: n
snippet: y
translation-type: ht
source-git-commit: 95e01eb33097fc76caac3f4dd5f5591461b887cf
workflow-type: ht
source-wordcount: '687'
ht-degree: 100%

---


# Een landingspagina configureren {#configuring-landing-page}

## Verzending van een landingspagina bevestigen {#confirm-a-landing-page-submission}

Wanneer een landingspagina door een bezoeker wordt verzonden, kunt u de geactiveerde acties configureren. Dit doet u als volgt:

1. Bewerk de eigenschappen van de landingspagina die u via het pictogram ![](assets/edit_darkgrey-24px.png) in het dashboard van de landingspagina opent en geef de parameters voor **[!UICONTROL Job]** weer.

   ![](assets/lp_edit_properties_button.png)

1. Selecteer onder de sectie **[!UICONTROL Specific actions]** de optie **[!UICONTROL Start sending message]** om te bepalen of een automatisch bericht wordt verzonden, bijvoorbeeld om een abonnement op een service te bevestigen. Vervolgens moet u een sjabloon voor e-maillevering selecteren.

   Merk op dat als een bevestigingsbericht al op het serviceniveau is geconfigureerd, u er dan geen in dit scherm moet selecteren om te voorkomen dat meerdere bevestigingsberichten worden verzonden. Raadpleeg [Een service configureren](../../audiences/using/creating-a-service.md).

1. Maak **[!UICONTROL Additional data]** om aanvullende data op te slaan wanneer de landingspagina wordt verzonden. Deze data zijn niet zichtbaar voor personen die de pagina bezoeken. Alleen constante waarden worden in aanmerking genomen.

   ![](assets/lp_parameters_6.png)

## Een landingspagina koppelen aan een service {#linking-a-landing-page-to-a-service}

U kunt een formulier koppelen aan een service, zodat profielen zich kunnen inschrijven voor een specifieke service bij het valideren van de landingspagina’s.

Met de parameters voor het koppelen van een landingspagina kunt u het uitgevoerde actietype opgeven en kunt u opgeven of de landingspagina specifiek is gekoppeld aan één service of algemeen is.

Voer de volgende stappen uit om de service die u wilt koppelen, te selecteren:

1. Bewerk de eigenschappen van de landingspagina die u via het pictogram ![](assets/edit_darkgrey-24px.png) in het dashboard van de landingspagina opent en geef de parameters voor **[!UICONTROL Job]** weer.

   ![](assets/lp_edit_properties_button.png)

1. Kies **[!UICONTROL Subscription]** in de vervolgkeuzelijst **[!UICONTROL Specific actions]**.

   ![](assets/lp_parameters_5.png)

1. Selecteer **[!UICONTROL Specific service]** om de landingspagina aan één service te koppelen. Selecteer deze optie niet als u verschillende services wilt gebruiken op de landingspagina.

   Gebruik de optie **[!UICONTROL Specified service in the URL]** om toe te staan dat de landingspagina voor verschillende services wordt gebruikt. Daarom moet u naar de landingspagina verwijzen wanneer u de service configureert.

## Machtigingen instellen en data vooraf laden {#setting-permissions-and-pre-loading-data}

De toegang tot een landingspagina kan worden beperkt tot geïdentificeerde bezoekers, die afkomstig zijn van een koppeling in een bericht dat bijvoorbeeld door Campaign wordt verzonden, of tot een specifieke organisatorische eenheid.
In het geval van geïdentificeerde bezoekers kunt u hun data vooraf in de landingspagina laden. Dit doet u als volgt:

1. Bewerk de eigenschappen van de landingspagina die u via het pictogram ![](assets/edit_darkgrey-24px.png) in het dashboard van de landingspagina opent en geef de parameters voor **[!UICONTROL Access & loading]** weer.

   ![](assets/lp_edit_properties_button.png)

1. Selecteer **[!UICONTROL Preload visitor data]**.

   Als een bezoeker van de pagina overeenkomt met een profiel in de database, worden de data van de bezoeker weergegeven in de velden van het formulier die zijn gekoppeld aan de databasedata en worden de personalisatie-elementen van de landingspagina in aanmerking genomen.

   ![](assets/lp_parameters_3.png)

U kunt ook het volgende doen:

* De URL-parameters gebruiken om de bezoekers te identificeren met behulp van de optie **[!UICONTROL Authorize visitor identification via URL parameters]**. Vervolgens moet u de laadsleutel kiezen en de filterparameters toewijzen met de parameters van de overeenkomstige URL.
* Een bezoeker toegang verlenen tot de landingspagina met de optie **[!UICONTROL Authorize unidentified visitors]**.

Landingspagina’s kunnen ook aan een organisatorische eenheid worden gekoppeld. Hiermee definieert u de toegang van gebruikers tot de verschillende landingspagina’s. U kunt als volgt een organisatorische eenheid toewijzen:

1. Open de eigenschappen van de landingspagina via het pictogram **[!UICONTROL Edit properties]**.

   ![](assets/lp_parameters_google3.png)

1. Vouw **[!UICONTROL Access authorization]** uit.

1. Klik op het vervolgkeuzemenu en selecteer uw organisatorische eenheid. Raadpleeg deze [pagina](../../administration/using/organizational-units.md) voor meer informatie over het maken van organisatorische eenheden.

   ![](assets/lp_org_unit_2.png)

1. De velden **[!UICONTROL Created by]**, **[!UICONTROL Created]**, **[!UICONTROL Access authorization]** en **[!UICONTROL Last modified]** worden automatisch ingevuld.

1. Klik op **[!UICONTROL Confirm]** en vervolgens op **[!UICONTROL Save]**.

De landingspagina kan nu alleen worden geopend en beheerd door gebruikers binnen de gekozen organisatorische eenheid.

![](assets/lp_org_unit_3.png)

## Google reCAPTCHA instellen {#setting-google-recaptcha}

U kunt Google reCAPTCHA V3 instellen met uw landingspagina om deze te beschermen tegen ongewenste e-mails en misbruik door bots. Als u dit met uw landingspagina wilt gebruiken, moet u eerst een extern account maken. Raadpleeg deze [sectie](../../administration/using/external-accounts.md#google-recaptcha-external-account) voor meer informatie over de configuratie.

Zodra uw externe Google reCAPTCHA V3-account is ingesteld, kunt u dit toevoegen aan uw landingspagina:

1. Voordat u de landingspagina publiceert, opent u de pagina-eigenschappen via het pictogram ![](assets/edit_darkgrey-24px.png) op het dashboard van de landingspagina.

   ![](assets/lp_parameters_google3.png)

1. Vouw het menu **[!UICONTROL Access & loading]** uit.
1. Schakel de optie **[!UICONTROL Use reCAPTCHA to protect your site from spam and abuse]** in.
1. Selecteer uw eerder gemaakte externe Google reCAPTCHA-account.

   ![](assets/lp_parameters_google.png)

1. Klik op **[!UICONTROL Confirm]**.

Uw landingspagina is nu ingesteld met Google reCAPTCHA en dit wordt onderaan de pagina weergegeven.

![](assets/lp_parameters_google2.png)

Google reCAPTCHA retourneert vervolgens een score op basis van gebruikersinteracties met uw pagina. Maak verbinding met uw [Google-beheerconsole](https://g.co/recaptcha/admin) om uw score te controleren.
