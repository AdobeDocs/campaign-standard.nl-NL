---
title: Externe accounts
description: Leer hoe u externe accounts configureert voor het instellen van verbindingen met externe systemen, zoals SFTP-servers
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 747e82ff-d3e6-4945-8f29-80e4a190c96f
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '1766'
ht-degree: 80%

---

# Externe accounts{#external-accounts}

Een extern account is een configuratie waarmee u de toegang tot een externe server voor Adobe Campaign kunt configureren en testen.

Deze externe accounts kunnen in Campaign-workflows worden gebruikt voor toegang tot en beheer van data.

U kunt de volgende typen externe accounts instellen:

* SFTP. Zie [deze sectie](#sftp-external-account) voor meer informatie.
* Amazon Storage Service (S3). Zie [deze sectie](#amazon-s3-external-account) voor meer informatie.
* Adobe Experience Manager. Zie [deze sectie](#adobe-experience-manager-external-account) voor meer informatie.
* Adobe Analytics. Zie [deze sectie](../../integrating/using/configure-campaign-analytics-integration.md) voor meer informatie.
* Google reCAPTCHA. Zie [deze sectie](#google-recaptcha-external-account) voor meer informatie.
* Microsoft Azure Blob-opslag. Zie [deze sectie](#microsoft-azure-external-account) voor meer informatie.
* OAuth 2.0. Raadpleeg voor meer informatie hierover [deze sectie](#oauth-account).

>[!NOTE]
>
>Andere typen externe accounts worden door Adobe gebruikt tijdens het proces van productprovisioning. Vanaf versie 17.9 van Campaign Standard kunnen externe FTP-accounts nog steeds worden gedefinieerd, maar ze zijn niet meer bruikbaar in nieuwe workflowactiviteiten. Als u al een verbinding had ingesteld, is deze nog steeds ingeschakeld.

Externe accounts kunnen door beheerders worden geconfigureerd via het menu **[!UICONTROL Administration > Application settings > External accounts]**.

## Een extern account maken {#creating-an-external-account}

Adobe Campaign wordt geleverd met een set vooraf gedefinieerde externe accounts. Om verbindingen met externe systemen zoals FTP-servers voor bestandsoverdracht in te stellen, kunt u uw eigen externe accounts aanmaken.

Externe accounts worden gebruikt door technische processen, zoals technische workflows of workflows voor campagnes. Wanneer u een bestandsoverdracht instelt in een workflow of een data-uitwisseling met een andere applicatie (Adobe Target, Experience Manager, enz.), moet u een extern account selecteren.

1. Klik op de knop **[!UICONTROL Create]**.
1. Voer een label in. Het label en de id worden gebruikt bij het selecteren van externe accounts in workflows.
1. Selecteer het type account dat u wilt maken.
1. Configureer de toegang tot het account door het opgeven van aanmeldingsgegevens, serveradres, poortnummer en sleutels indien relevant.

   De benodigde informatie wordt meestal verstrekt door de provider van de server waarmee u verbinding maakt.

1. Sla uw account op.

Het externe account wordt gemaakt en toegevoegd aan de lijst met accounts. Het is nu beschikbaar voor uw data-/bestandsoverdrachten of routeringconfiguraties in workflowactiviteiten en leveringseigenschappen.

## Extern SFTP-account {#sftp-external-account}

Voor verschillende typen externe accounts moeten verschillende data worden opgegeven.

Geef voor een extern SFTP-account de volgende data op:

* Serveradres. Bijvoorbeeld **ftp.domain.com**.
* Poortnummer. Bijvoorbeeld **22**.
* Aanmeldingsgegevens SFTP-server: accountnaam en wachtwoord waarmee verbinding wordt gemaakt met de server.

### Aanbevelingen voor door Adobe gehoste SFTP-servers {#adobe-hosted-sftp-server-recommendations}

Als u bestanden en data beheert voor ETL-doeleinden, worden deze bestanden opgeslagen op een gehoste SFTP-server die door Adobe wordt geleverd. Deze SFTP is ontworpen als een tijdelijke opslagruimte waarop u het bewaren en verwijderen van bestanden kunt regelen.

Wanneer deze ruimte niet correct wordt gebruikt of gecontroleerd, kan deze snel de fysieke ruimte op de server vullen en ernstige problemen veroorzaken. Dit kan leiden tot verlies of beschadiging van de data op uw platform.

Om dergelijke problemen te voorkomen, wordt u aangeraden de onderstaande best practices op te volgen:

* Beperk het aantal data tot een minimum.
* Gebruik op sleutels gebaseerde verificatie om te voorkomen dat het wachtwoord vervalt. Ondersteunde indelingen zijn alleen **OpenSSH** en **SSH2**. U zult de publieke sleutel aan het Adobe-supportteam moeten verstrekken zodat deze naar de Campaign-server kan worden geüpload.
* Bewaar de data slechts zolang als nodig is. 15 dagen is de maximale tijdslimiet.
* Gebruik workflows om de data op de juiste manier te verwijderen (beheer de retentie van workflows die de data verbruiken).
* Gebruik batchverwerking in SFTP-uploads en in workflows.
* Verwerk fouten/uitzonderingen.
* Meld u af en toe aan bij de SFTP om de content rechtstreeks te controleren.
* Vergeet niet dat SFTP-schijfbeheer in de eerste plaats uw verantwoordelijkheid is.

Ook, merk op dat openbare IPs waarvan u probeert om de verbinding in werking te stellen SFTP aan de lijst van gewenste personen op de instantie van de Campagne moet worden toegevoegd. Het toevoegen van IP adressen aan de lijst van gewenste personen kan via worden gevraagd [ondersteuningsticket](https://helpx.adobe.com/nl/enterprise/using/support-for-experience-cloud.html), samen met het verstrekken van de openbare sleutel voor authentificatie te gebruiken.

SFTP-servers kunnen worden beheerd via het Configuratiescherm. Zie de [Configuratiescherm-documentatie](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html) voor meer informatie.

>[!NOTE]
>
>Het configuratiescherm is toegankelijk voor alle gebruikers met beheerdersrechten. De stappen om toegang met beheerdersrechten aan een gebruiker te verlenen worden gedetailleerd beschreven op [deze pagina](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=nl#discover-control-panel).

## OAuth 2.0-account {#oauth-account}

Geef voor een externe OAuth 2.0-rekening de volgende gegevens:

* A **Type subsidie**: alleen **clientgegevens** wordt ondersteund.
* A **Beveiligde API-URL**: Voer het eindpunt van de vergunning in.
* **OAuth 2.0 gevoelige geloofsbrieven**: Deze sectie is bedoeld voor geloofsbrieven die van nature gevoelig zijn. Referentiewaarden worden op het scherm gemaskeerd nadat ze zijn toegevoegd. op dat moment zijn ze niet leesbaar of bewerkbaar . Als voor het eindpunt van de autorisatie een bepaalde referentie moet worden ingevoegd in de HTTP-autorisatieheader in plaats van in de hoofdtekst van de POST, kunt u de optie Opnemen in koptekst voor die referentie selecteren.
* **Niet-gevoelige OAuth 2.0-gegevens**: Deze sectie is bedoeld voor geloofsbrieven die in aard niet gevoelig zijn. De referentie-waarden zijn zichtbaar op het scherm nadat ze zijn toegevoegd. zij zullen ook bewerkbaar zijn .  Als voor het eindpunt van de autorisatie een bepaalde referentie moet worden ingevoegd in de HTTP-autorisatieheader in plaats van in de hoofdtekst van de POST, kunt u de optie Opnemen in koptekst voor die referentie selecteren.

Nadat u de accountgegevens hebt ingevoerd, klikt u op **Verbinding testen** om te controleren of de externe account correct is geconfigureerd.

![](assets/external_accounts_OAuth.png)

>[!NOTE]
>
>De referenties &quot;Content-Type: application/x-www-form-urlencoded&quot; en &quot;Grant_type=client_credentials&quot; worden automatisch toegevoegd aan de API-aanroep; daarom zult u niet hen in de geloofsbrieven sectie hoeven toe te voegen.

## Extern Amazon S3-account {#amazon-s3-external-account}

Het Amazon S3-serverveld moet als volgt worden ingevuld:

```
<S3 bucket name>.s3.amazonaws.com/<s3 object path>
```

Om uw bestand in de gecodeerde S3-modus op te slaan, vinkt u het vakje **[!UICONTROL Keep files in S3 encrypted]** aan.

![](assets/external_accounts_2.png)

De benodigde informatie wordt meestal verstrekt door de provider van de server waarmee u verbinding maakt.

Specificeer de **[!UICONTROL AWS Region]** voor uw eindpunt. U kunt de ondersteunde regio&#39;s en handtekeningversies controleren in de officiële [Amazon S3-documentatie](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region).

>[!NOTE]
>
>Uw **[!UICONTROL Receiver server]** moet zonder uw AWS-regio worden ingevoerd. De data worden later automatisch aan uw URL toegevoegd.

### Aanbevelingen voor Amazon S3-accounts {#amazon-s3-account-recommendations}

We raden u aan de volgende aanbevelingen te volgen om u te helpen bij het instellen van uw Amazon S3-account:

* Creëer een strikt bucketbeleid om de toegang tot S3-buckets te beperken. Het bucketbeleid kan worden geconfigureerd tijdens het maken van een bucket. Zie de [Amazon S3-documentatie](https://docs.aws.amazon.com/AmazonS3/latest/dev//example-bucket-policies.html) voor meer informatie.
* Schakel tijdens het maken van een extern account codering in voor het opslaan van gevoelige data in het S3-bucket door het selectievakje **[!UICONTROL Keep files in S3 encrypted]** aan te vinken.
* Verleen bucketmachtigingen om aan te geven wie toegang heeft tot het object in een bucket. Zie de [Amazon S3-documentatie](https://docs.aws.amazon.com/AmazonS3/latest/dev//access-control-overview.html) voor meer informatie over bucketmachtigingen.

## Extern Adobe Experience Manager-account {#adobe-experience-manager-external-account}

De externe accounts van Adobe Experience Manager worden gebruikt bij de integratie van Campaign met Experience Manager.

De processen en vereisten met betrekking tot deze integratie zijn beschikbaar in [dit document](../../integrating/using/get-started-campaign-integrations.md).

Wanneer u deze nieuwe externe account instelt, moet u de volgende gegevens opgeven:

* Server: Voer de URL van de Adobe Experience Manager-server in. Bijvoorbeeld:

   ```
   http://aem.domain.com:4502
   ```

* Aanmeldingsgegevens voor AEM-account: gebruik het account dat toegang nodig heeft tot de Adobe Experience Manager-instantie. Het zou een accountonderdeel moeten zijn van de groep campaign-remote in Experience Manager.

## Extern Google reCAPTCHA-account {#google-recaptcha-external-account}

>[!NOTE]
>
>Voor de Google reCAPTCHA-configuratie is een Google-account vereist.

Met het Google reCAPTCHA-mechanisme kunt u uw landingspagina beschermen tegen spam en misbruik door bots. Dit is niet opdringerig voor uw klanten omdat het geen enkele interactie van hen vereist en gebaseerd is op interacties met uw site. Raadpleeg deze [pagina](https://www.google.com/recaptcha/admin/create) om uw site te registreren. U moet het type V3 reCAPTCHA kiezen.

Als u de Google reCAPTCHA V3 aan u landingspagina wilt toevoegen, configureert u deze in uw externe account. Raadpleeg deze [sectie](../../channels/using/configuring-landing-page.md#setting-google-recaptcha) voor meer informatie over het toevoegen van reCAPTCHA V3 aan de landingspagina.

Geef voor een extern Google reCAPTCHA V3-account de volgende data op:

* Een **[!UICONTROL Label]** en **[!UICONTROL ID]** van uw externe account
* **[!UICONTROL Type]**: Google reCAPTCHA
* Uw **[!UICONTROL Site key]** en **[!UICONTROL Site secret]**
* Een **[!UICONTROL Threshold]** tussen 0 en 1

   Een waarde van 0,0 bij **[!UICONTROL Threshold]** betekent dat het waarschijnlijk een bot is en 1,0 geeft een waarschijnlijk goede interactie aan. Standaard kunt u een drempel van 0,5 gebruiken.

![](assets/external_accounts_3.png)

## Extern Microsoft Azure Blob-opslagaccount {#microsoft-azure-external-account}

>[!NOTE]
>
>U vindt de informatie die nodig is om uw externe account in Adobe Campaign Standard te configureren in de Azure Portal door **[!UICONTROL Settings]** > **[!UICONTROL Access keys]** te selecteren.

De Azure Blob-opslagconnector kan worden gebruikt voor het importeren of exporteren van data naar Adobe Campaign via een **[!UICONTROL Transfer file]** workflowactiviteit. Raadpleeg [deze sectie](../../automating/using/transfer-file.md#azure-blob-configuration-wf) voor meer informatie.

Geef de volgende data op voor een extern account voor Microsoft Azure Blob-opslag:

* Een **[!UICONTROL Label]** en **[!UICONTROL ID]** van uw externe account
* **[!UICONTROL Type]**: Microsoft Azure Blob-opslag
* Uw **[!UICONTROL Account name]** en **[!UICONTROL Account key]**. Als u wilt weten waar u de naam en sleutel van uw account vindt, raadpleeg dan deze [pagina](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage).
* Uw **[!UICONTROL Endpoint suffix]**. Deze staat in de **[!UICONTROL Connection string]** van het menu **[!UICONTROL Access keys]** in de Azure Portal. Raadpleeg [deze pagina](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage) voor meer informatie.
* Uw **[!UICONTROL Container]**-naam. Als u meerdere containers wilt gebruiken, maakt u zoveel externe accounts als containers.
* Met de optie **[!UICONTROL Concurrency]** kunt u de snelheid van de bestandsoverdracht afstemmen.

![](assets/external_accounts_4.png)

Als de configuratie voltooid is, klikt u op **[!UICONTROL Test connection]** om Adobe Campaign te koppelen aan Microsoft Azure Blob-opslag.

### Aanbevelingen voor Microsoft Azure Blob-opslag {#azure-blob-recommendations}

**Codering**

Adobe Campaign gebruikt een beveiligde verbinding (HTTPS) om toegang te krijgen tot uw Microsoft Azure Blob-opslagaccount.

**Accountsleutel**

Bij het configureren van uw externe account moet u gebruik maken van een van de **[!UICONTROL Account key]** die beschikbaar is in de Azure Portal. Raadpleeg deze [pagina](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage#view-access-keys-and-connection-string) voor meer informatie over waar u uw accountsleutels kunt vinden.

**De bestandsoverdrachtsnelheid optimaliseren**

Met de optie **[!UICONTROL Concurrency]** kunt u de snelheid van de bestandsoverdracht afstemmen.
Deze staat voor het aantal threads dat zal worden gebruikt om de bestandsoverdracht uit te voeren. Elk van deze threads zal een gedeelte van ongeveer 1 MB van de blob downloaden. Ze worden dan in de wachtrij gezet om naar schijf te worden geschreven. Door het aantal threads te verhogen, verhoogt u ook de belasting van de bronnen die door de applicatie worden gebruikt tijdens de bestandsoverdracht.

Na afronding van de bestandsoverdracht kunt u de statistische prestatiegegevens teruglezen in de workflowlogboeken.

**Hernieuwde pogingen**

Standaard beschikt de bestandsoverdracht voor Azure Blob over vier hernieuwde pogingen.  Als de Azure Storage-service een foutcode retourneert zoals 503 (server bezet) of 500 (time-out van bewerking), kan dit erop wijzen dat u de schaalbaarheid van uw opslagaccount nadert of overschrijdt. Dit kan gebeuren als u een nieuw account gebruikt of tests uitvoert.

Als de fout zich blijft voordoen, kunt u het aantal hernieuwde pogingen verhogen door een optie te creëren onder het geavanceerde menu **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**.

Als de optie wordt geïmplementeerd, dient deze als volgt te worden gemaakt:

```
ID:        AzureBlob_Max_Retries
Date type: Integer
Default:   <the number of retries needed>
```
