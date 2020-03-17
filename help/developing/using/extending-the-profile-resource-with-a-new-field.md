---
title: De profielbron uitbreiden met een nieuw veld
description: Leer hoe u de profielbron kunt uitbreiden.
page-status-flag: never-activated
uuid: 9b99e95c-93ff-4187-90f7-db0baf5369ad
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
discoiquuid: 1e0f8945-fc3c-46a9-a8e5-b181a1f5ffcb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 07d68b5bf8d800ebd95919f491e98f1b7a015705

---


# De profielbron uitbreiden met een nieuw veld{#extending-the-profile-resource-with-a-new-field}

## Profielen uitbreiden {#about-extending-profiles}

In dit geval wordt beschreven hoe u een profiel en een testprofiel kunt uitbreiden met een specifiek veld.

Hier willen we onze profielen bijwerken met het nieuwe veld met behulp van een bestemmingspagina en vervolgens profielen aanwijzen met een nieuwsbrief die specifiek is voor hun belangen.

Hiervoor voert u de volgende stappen uit:

* [Stap 1: De profielbron uitbreiden](#step-1--extend-the-profile-resource)
* [Stap 2: Het testprofiel uitbreiden](#step-2--extend-the-test-profile)
* [Stap 3: Uw aangepaste bron publiceren](#step-3--publish-your-custom-resource)
* [Stap 4: Profielen bijwerken en als doel instellen met een workflow](#step-4--update-and-target-profiles-with-a-workflow)

Het volgende veld wordt vervolgens toegevoegd aan onze profielen en kan worden gebruikt in een levering:

![](assets/schema_extension_uc20.png)

Verwante onderwerpen:

* [Informatie over aangepaste bronnen](../../developing/using/data-model-concepts.md)
* [Profielen beheren](../../audiences/using/about-profiles.md)
* [Testprofielen beheren](../../audiences/using/managing-test-profiles.md)

## Stap 1: De profielbron uitbreiden {#step-1--extend-the-profile-resource}

Om het nieuwe gebied van de **Belang** voor onze profielen tot stand te brengen, moet u eerst de uit-van-de-doos **[!UICONTROL Profiles (profile)]** middel uitbreiden.

1. Selecteer in het geavanceerde menu via het Adobe Campagne-logo **[!UICONTROL Administration]** > **[!UICONTROL Development]** en **[!UICONTROL Custom resources]**.
1. Als u de **[!UICONTROL Profiles]** bron nog niet hebt uitgebreid, klikt u **[!UICONTROL Create]**.
1. Kies de **[!UICONTROL Extend an existing resource]** optie.
1. Selecteer de **[!UICONTROL Profile (profile)]** bron.
1. Klik op **[!UICONTROL Create]**.

   ![](assets/schema_extension_uc5.png)

1. Klik in de **[!UICONTROL Fields]** categorie van het **[!UICONTROL Data structure]** tabblad op **[!UICONTROL Create element]**.

   >[!NOTE]
   >
   >Als u de **[!UICONTROL Profile]** bron al hebt uitgebreid voor eerdere doeleinden, kunt u bij deze stap beginnen door op **[!UICONTROL Add field]** te klikken.

   ![](assets/schema_extension_uc6.png)

1. Voeg een **[!UICONTROL Label]** en een **[!UICONTROL ID]**. Selecteer het **[!UICONTROL Text]** type en klik **[!UICONTROL Add]**.

   ![](assets/schema_extension_uc9.png)

1. Als u uw veld wilt configureren, klikt u op het tabblad **[!UICONTROL Data structure]** onder de vervolgkeuzelijst **[!UICONTROL Fields]** op ![](assets/schema_extension_uc8.png) en vervolgens op ![](assets/schema_extension_uc7.png) vanaf het eerder gemaakte veld.
1. In dit voorbeeld willen wij specifieke waarden toevoegen, om dit te doen klik **[!UICONTROL Specify a list of authorized values]**.

   ![](assets/schema_extension_uc10.png)

1. Klik **[!UICONTROL Add an element]** en voeg dan zo veel waarde toe zoals nodig door een **[!UICONTROL Label]** en een **[!UICONTROL ID]** en een klik toe te voegen **[!UICONTROL Add]**.

   Hier, zullen wij de Boeken, Exhiisions, Movies en N.v.t. waarden voor profielen tot stand brengen om tussen deze opties te kiezen.

   ![](assets/schema_extension_uc11.png)

1. Als u dit veld op het **[!UICONTROL Profile]** scherm wilt toevoegen, klikt u op de **[!UICONTROL Screen definition]** tab.
1. Klik in de **[!UICONTROL Detail screen configuration]** vervolgkeuzelijst op **[!UICONTROL Add a personalized fields section]** en klik op **[!UICONTROL Create element]**.

   ![](assets/schema_extension_uc12.png)

1. Selecteer een **[!UICONTROL Type]**. Hier willen we een invoerveld toevoegen. Selecteer vervolgens het eerder gemaakte veld en klik op **[!UICONTROL Add]**.

   ![](assets/schema_extension_uc2.png)

1. Als u een scheidingsteken wilt toevoegen om uw profielvenster beter te organiseren, klikt u **[!UICONTROL Create an element]** en selecteert u **[!UICONTROL Separator]** in de **[!UICONTROL Type]** vervolgkeuzelijst.

   ![](assets/schema_extension_uc19.png)

Uw veld is nu geconfigureerd. We moeten het nu uitbreiden naar het testprofiel.

>[!NOTE]
>
>Als u niet de middelen van het testprofiel moet uitbreiden, kunt u aan de het Publiceren stap springen.

## Stap 2: Het testprofiel uitbreiden {#step-2--extend-the-test-profile}

Om te testen of het nieuwe gecreeerde gebied correct wordt gevormd, kunt u het testen door uw levering naar uw testprofielen te verzenden. Ten eerste moet het nieuwe veld ook worden toegepast op de testprofielen.

1. Selecteer in het geavanceerde menu via het Adobe Campagne-logo **[!UICONTROL Administration]** > **[!UICONTROL Development]** en **[!UICONTROL Custom resources]**.
1. Als u de **[!UICONTROL Profiles]** bron nog niet hebt uitgebreid, klikt u **[!UICONTROL Create]**.
1. Kies de **[!UICONTROL Extend an existing resource]** optie.
1. Selecteer de **[!UICONTROL Test profile (seedMember)]** bron.
1. Klik op **[!UICONTROL Create]**.

   ![](assets/schema_extension_uc13.png)

1. In the **[!UICONTROL Data structure]** tab, click **[!UICONTROL Create element]**.

   ![](assets/schema_extension_uc15.png)

1. Selecteer het bronveld dat u eerder hebt gemaakt en klik op **[!UICONTROL Add]**.

   ![](assets/schema_extension_uc16.png)

1. Voer dezelfde stappen uit van stap 11 tot en met 13 als de procedure voor het uitbreiden van het profiel hierboven om dit veld op het **[!UICONTROL Test profile]** scherm toe te voegen.
1. Klik op **[!UICONTROL Save]**.

Het nieuwe veld is nu beschikbaar voor zowel profielen als testprofielen. Voor het correct worden gevormd, moet u uw douanemiddel publiceren.

## Stap 3: Uw aangepaste bron publiceren {#step-3--publish-your-custom-resource}

Om de veranderingen toe te passen die op de middelen worden uitgevoerd en het te kunnen gebruiken, moet u een gegevensbestandupdate uitvoeren.

1. Kies in het menu Geavanceerd de optie **Beheer** > **Ontwikkeling** en **Publiceren**.
1. De optie **[!UICONTROL Determine modifications since the last publication]** is standaard ingeschakeld, wat betekent dat alleen de wijzigingen worden toegepast die zijn uitgevoerd sinds de laatste update.

   ![](assets/schema_extension_uc14.png)

1. Klik **[!UICONTROL Prepare publication]** om de analyse te starten waarmee uw database wordt bijgewerkt.
1. Nadat de publicatie is uitgevoerd, klikt u op de knop **Publiceren** om de nieuwe configuraties toe te passen.

   ![](assets/schema_extension_uc17.png)

1. Zodra gepubliceerd, wijst de ruit van de **Samenvatting** van elke middel erop dat de status nu **Gepubliceerd** is en specificeert de datum van de laatste publicatie.

   ![](assets/schema_extension_uc18.png)

1. Selecteer het **[!UICONTROL Profiles]** tabblad en klik **[!UICONTROL New]** om te controleren of de wijzigingen correct zijn geïmplementeerd.

   ![](assets/schema_extension_uc20.png)

Uw nieuwe middelgebied is nu klaar om in een levering bijvoorbeeld worden gebruikt en worden gericht.

## Stap 4: Profielen bijwerken en als doel instellen met een workflow {#step-4--update-and-target-profiles-with-a-workflow}

Als u profielen wilt bijwerken met gegevens voor het nieuwe aangepaste veld, kunt u een bestemmingspagina maken met de **[!UICONTROL Profile acquisition]** sjabloon. Raadpleeg deze [pagina](../../channels/using/getting-started-with-landing-pages.md)voor meer informatie over bestemmingspagina&#39;s.

Hier, willen wij in een werkschemaprofielen richten die dit gebied niet vulden. Ze zullen een e-mail ontvangen waarin ze worden gevraagd hun profielen bij te werken en persoonlijke nieuwsbrieven en aanbiedingen te ontvangen. Elk profiel ontvangt vervolgens een gepersonaliseerde nieuwsbrief afhankelijk van de door hen gekozen belangen.

Ten eerste moeten we een bestemmingspagina maken die de velden **Interesse** van de beoogde profielen bijwerkt:

1. Klik in het **[!UICONTROL Marketing activities]** dialoogvenster op **[!UICONTROL Create]** en selecteer **[!UICONTROL Landing page]**.
1. Selecteer een type openingspagina. Hier, aangezien wij onze profielen willen bijwerken, selecteren **[!UICONTROL Profile acquisition]**.
1. Klik op **[!UICONTROL Create]**.
1. Klik op het **[!UICONTROL Content]** blok om de inhoud van de bestemmingspagina te bewerken.

   ![](assets/schema_extension_uc21.png)

1. Pas de openingspagina naar wens aan.
1. Klik op het veld dat voor uw profielen is geconfigureerd om te kiezen tussen de selectie van belangen. In de linkerruit, selecteer uw eerder gecreeerde **Interesse** douanemiddel.

   ![](assets/schema_extension_uc22.png)

1. Sla de openingspagina op en test deze om te controleren of de velden correct zijn geconfigureerd.
1. Klik **[!UICONTROL Publish]** wanneer uw openingspagina klaar is.

Uw openingspagina is nu klaar. Als u de profielen wilt bijwerken, kunt u een workflow maken waarin een speciale aanbieding wordt verzonden, afhankelijk van de gekozen interesse.

1. Klik op het **[!UICONTROL Marketing activities]** tabblad **[!UICONTROL Create]** en selecteer **[!UICONTROL Workflow]**.
1. Sleep een **[!UICONTROL Query]** activiteit om de profielen of het publiek te richten u nodig hebt.
1. Sleep een **[!UICONTROL Email delivery]** activiteit om uw e-mail te configureren die een koppeling naar de bestemmingspagina bevat. Selecteer de **[!UICONTROL Add an outbound transition with the population]**.

   ![](assets/schema_extension_uc3.png)

1. Maak en ontwerp uw e-mail naar wens. Raadpleeg deze [pagina](../../designing/using/quick-start.md)voor meer informatie over het aanpassen van e-mailadressen.
1. Voeg een knop toe aan uw e-mail waarmee profielen worden omgeleid naar uw bestemmingspagina.
1. Selecteer de toegevoegde knop en klik in ![](assets/schema_extension_uc7.png) de **[!UICONTROL Link]** sectie in het linkerdeelvenster.

   ![](assets/schema_extension_uc23.png)

1. Selecteer in het **[!UICONTROL Insert link]** venster **[!UICONTROL Landing page]** de **[!UICONTROL Link type]** vervolgkeuzelijst en selecteer de eerder gemaakte bestemmingspagina.

   ![](assets/schema_extension_uc24.png)

1. Klik op **[!UICONTROL Save]**. Uw e-mail is nu klaar, u kunt terugkeren naar uw werkstroom.
1. Voeg een **[!UICONTROL Wait]** activiteit toe zodat uw profielen enige tijd de landingspagina kunnen vullen.
1. Voeg een **[!UICONTROL Segmentation]** activiteit toe om de uitgaande overgang afhankelijk van hun **Belangen** te verdelen.
1. Creeer een uitgaand segment voor elke **Rente**.

   ![](assets/schema_extension_uc4.png)

1. Voeg na elke overgang een **[!UICONTROL Email delivery]** activiteit toe en maak een gepersonaliseerde e-mail afhankelijk van de gekozen **Interesse**.
1. Start de workflow wanneer de configuratie is voltooid.

   ![](assets/schema_extension_uc25.png)

Profielen ontvangen nu een e-mail met de vraag of ze dit renteveld willen invullen, gevolgd door een persoonlijke e-mail, afhankelijk van de gekozen waarde.
