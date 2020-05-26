---
title: Gecodeerde gegevens beheren
description: Leer hoe u gecodeerde gegevens beheert.
page-status-flag: never-activated
uuid: d909d26a-cf50-46af-ae09-f0fd7258ca27
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 75b83165-dcbd-4bb7-b703-ed769f489b16
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---


# Gecodeerde gegevens beheren {#managing-encrypted-data}

In sommige gevallen moeten de gegevens die u wilt importeren, mogelijk worden gecodeerd, bijvoorbeeld als deze PII-gegevens bevatten.

Als u gecodeerde bestanden wilt importeren of exporteren, moet u eerst contact opnemen met de klantenservice van Adobe, zodat deze uw instantie de benodigde opdrachten voor versleuteling/ontsleuteling kunnen geven.

Hiertoe dient u een verzoek in met de volgende gegevens:

* Het **label** dat in de interface van de Campagne zal tonen om het bevel te gebruiken. Bijvoorbeeld &quot;Bestand versleutelen&quot;.
* De **opdracht** om op uw instantie te installeren.
Als u bijvoorbeeld een bestand wilt decoderen met PGP, is de opdracht:

   ```
   <path-to_pgp_if-not_global_or_server/>pgp.exe --decrypt --input nl6/var/vp/import/filename.pgp --passphrase "your password" --recipient recipient @email.com --verbose --output nl6/var/vp/import/filename
   ```

Zodra het verzoek wordt verwerkt, zullen de encryptie/decryptiebevelen op het **[!UICONTROL Pre-processing stage]** gebied van de **[!UICONTROL Load file]** en **[!UICONTROL Extract file]** activiteiten beschikbaar zijn. U kunt deze gebruiken om de bestanden te decoderen of te coderen die u wilt importeren of exporteren.

![](assets/preprocessing-encryption.png)

**Verwante onderwerpen:**

* [Bestand laden](../../automating/using/load-file.md)
* [Bestand uitpakken](../../automating/using/extract-file.md)
