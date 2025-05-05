---
title: Integratie-app Campagne-dynamiek configureren
description: Leer hoe u de integratie-app Campagne-dynamiek configureert
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: e0fb289a-6b6e-473d-80af-50f6d0d72af1
source-git-commit: abdcd3f9f7f709818dee794b4c830e486fefa290
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 1%

---

# Referentiekenmerken migreren van JWT naar OAuth server-naar-server

De referentie van de Rekening van de Dienst (JWT) is afgekeurd ten gunste van de nieuwe referentie van OAuth server-aan-Server. De nieuwe referentie maakt het voor u gemakkelijker om Adobe toepassingen te handhaven. Het verwijdert ook de behoefte om certificaten periodiek te roteren en werkt uit-van-de-doos gebruikend standaardOAuth2 bibliotheken.

Terwijl de geloofsbrieven van de Rekening van de Dienst (JWT) zoals afgekeurd zijn gemerkt, zullen zij tot 1 jan. 2025 blijven werken. Daarom moet u uw integratie migreren om de nieuwe server-aan-server referentie OAuth vóór 1 Jan, 2025 te gebruiken. Controleer [tijdlijnen voor afschrijving](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/#deperecation-timelines) voor meer informatie

## Stappen om geloofsbrieven van JWT aan OAuth server-aan-server te migreren

De migratie naar de referentie van OAuth Server-aan-Server is een eenvoudig proces dat een nul onderbreking migratie voor uw toepassing toelaat. U kunt de onderstaande stappen volgen om de gegevens te migreren.

1. Aanmelden bij de [Adobe Developer Console](https://developer.adobe.com/console)
2. Van het het filtreren menu op de linkerkant, selecteer de optie heeft de referentie van de Rekening van de Dienst (JWT). Op deze manier worden alle projecten weergegeven die een JWT-referentie (Service Account) hebben. Klik in de lijst met projecten op het project dat u wilt migreren.

   ![](assets/JwtToOAuthMigration1.png)

3. Open het tabblad Servicerekening (JWT) voor referentie vanaf de linkernavigatie en bekijk de migratiekaart. Klik op de migratiekaart op de knop **Nieuwe referentie toevoegen** om equivalente OAuth Server-aan-Server referentie toe te voegen. Het toevoegen van een Server-aan-Server referentie OAuth aan uw project zal de migratie beginnen.
   ![](assets/JwtToOAuthMigration2.png)
4. De nieuwe referentie **OAuth Server-to-Server** wordt toegevoegd aan de linkernavigatie.
   * Klik op Migratie annuleren als u de migratie wilt annuleren.
   * Klik pas op de knop Reviseren en verwijderen als u controleert of de nieuwe referentie-OAuth Server-to-Server werkt.

     ![](assets/JwtToOAuthMigration3.png)

5. Referenties in Microsoft Dynamics 365 bijwerken naar de Adobe Campaign Standard-app
   * Meld u aan bij de integratie-app en navigeer naar de pagina Instellingen.
   * Selecteer OAuth als authentificatietype.
   * Aangezien de nieuwe referentie van OAuth Server-aan-Server de zelfde geloofsbrieven gebruikt zoals de oude referentie van de Rekening van de Dienst (JWT), zullen de meeste gebieden reeds worden ingevuld.
   * Voer de client-id en het clientgeheim in. Deze vindt u in het project in Adobe Developer Console.
   * Klik op Opslaan om de instellingen op te slaan.

     ![](assets/JwtToOAuthMigration4.png)

6. Controleren of de nieuwe gegevens werken
   * Meld u aan bij de integratie-app en navigeer naar de pagina Workflows.
   * Stop de actieve workflows. Wacht tot de workflows zijn gestopt.
   * Start de workflows. Wacht tot de werkschema&#39;s in RUNNING staat zijn.
   * Controleer de workflows gedurende een paar minuten om ervoor te zorgen dat de workflows correct werken. U kunt de gegevens ook controleren in Adobe Campaign Standard en Microsoft Dynamics 365 om ervoor te zorgen dat de gegevens correct worden gesynchroniseerd.

7. De JWT-referentie verwijderen om de migratie te voltooien
   * Aanmelden bij de [Adobe Developer Console](https://developer.adobe.com/console)
   * Klik op de projecten en selecteer het project dat u hebt gemigreerd.
   * Klik op het tabblad Service Account (JWT) voor referentie aan de linkerkant van de navigatie.
   * Klik op de knop Revisie en Verwijderen.

     ![](assets/JwtToOAuthMigration5.png)
   * Controleer de tijdstempel van de laatste toegang of het laatst gebruikte menu om te controleren of de integratie-app toegangstokens genereert met de nieuwe OAuth-referentie of nog steeds de oude JWT-referentie gebruikt.

     ![](assets/JwtToOAuthMigration6.png)
   * Wanneer is geverifieerd dat de integratie-app de nieuwe OAuth-referentie gebruikt en de JWT-referentie niet meer gebruikt, kunt u doorgaan met het verwijderen van de oude referentie door op de knop **Bevestigen en doorgaan** om de migratie te voltooien.

     ![](assets/JwtToOAuthMigration7.png)
