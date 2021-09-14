---
title: Problemen oplossen
description: Leer hoe u problemen kunt oplossen bij het delen van bronnen.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 5882ada6-dff4-4fd1-a433-0eb31570f73c
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 1%

---

# Problemen oplossen{#troubleshooting}

Er kunnen fouten optreden tijdens het gebruik van de integratie met Audience Manager of de hoofdservice van Personen.

In dit geval, zorg ervoor dat de volgende elementen correct worden gevormd:

* **Externe accounts**

   Controleer in **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts]** of de volgende externe S3-accounts correct zijn geconfigureerd. De vermelde S3 servers zouden tijdens levering moeten worden gevormd.

   * **[!UICONTROL importSharedAudience]**: S3-account voor het importeren van publiek.
   * **[!UICONTROL exportSharedAudience]**: S3-account voor het exporteren van soorten publiek.

* **Gedeelde gegevensbronnen**

   Controleer in **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]** of de gedeelde gegevensbron juist is ingesteld.

   **[!UICONTROL Priority]** wordt gebruikt wanneer u meerdere gegevensbronnen hebt gedefinieerd. Prioriteit bepaalt welke gegevensbron zal worden gebruikt om met alias aan te passen die in de bepaalde orde wordt ontvangen. **[!UICONTROL Priority]** is alleen nodig voor Triggers-implementatie.

   Controleer of de afstemmingssleutel juist is. Het is de gehashte/gecodeerde waarde van dit gebied dat wordt gebruikt om publiek uit te voeren en in te voeren.

   Als de gedeclareerde id wordt gehasht of versleuteld, controleert u of dezelfde parameters/versleutelingsalgoritmen op uw website worden gebruikt.

   Er wordt slechts één versleutelingsalgoritme ondersteund: AES in CBC-modus met een sleutellengte van 128, 192 of 256 bits, met PKCS-opvulling.

   Als het AES-versleutelingsalgoritme is geselecteerd, moeten de volgende aanvullende velden correct worden ingesteld:

   * **Coderingstoetsen** voor AES
   * **Codering IV**  (initialisatievector) voor AES
   * **Kanaal**  (e-mail/SMS/Overige): Met dit veld kunt u e-mailadressen en SMS-nummers rechtstreeks decoderen. Zorg ervoor dat de verzoeningssleutel het plaatsen van **Kanaal** gebied aanpast. Als u &quot;Andere&quot;selecteert, zal deze specifieke decryptie niet gebeuren en de verzoeningssleutel zal worden gebruikt om de gegevens in overeenstemming te brengen.

   Experience Cloud-publiek wordt mogelijk niet gedeeld omdat de technische workflow is gestopt of gepauzeerd. U opent de **[!UICONTROL Import shared audience]**-workflow door rechtstreeks op de optie **[!UICONTROL Show ImportShared Audience workflow]** in de gegevensbron te klikken.

Het kan voorkomen dat sommige gegevens ontbreken wanneer het delen van een publiek via de de kerndienst van Mensen of wanneer het invoeren van een publiek. Alleen records waarvan de id (&#39;Bezoeker-id&#39; of &#39;Opgegeven ID&#39;) in overeenstemming kan worden gebracht met de profieldimensie, worden overgedragen. IDs van de de kernde dienstsegmenten van Mensen die niet door Adobe Campaign worden erkend worden niet ingevoerd.
