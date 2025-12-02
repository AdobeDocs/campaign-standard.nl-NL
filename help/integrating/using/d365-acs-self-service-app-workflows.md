---
title: Workflows voor integratietoepassingen
description: Workflows voor integratie van campagnes en dynamiek
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 51f07f08-5d57-4c4c-aff2-d03e5956ec6f
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 0%

---

# Campagne - Microsoft Dynamics 365-integratieworkflows

De pagina **[!UICONTROL Workflows]** bevat een overzicht van de technische workflows en hun status.

De integratietoepassing wordt geleverd met drie workflows:

![](assets/do-not-localize/d365-to-acs-ui-page-workflows.png)

**Microsoft Dynamics 365 aan Campagne**
* Verzend *contacten* van Microsoft Dynamics 365 in Adobe Campaign
* *Eigen entiteiten van de Douane*: Breng in douanetabellen van Microsoft Dynamics 365 aan Adobe Campaign. [Meer informatie](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* Dit is ook gekend als **Ingress** (verwijzend naar het binnendringen van gegevens van Microsoft Dynamics 365 aan Adobe Campaign)

**Campagne aan Microsoft Dynamics 365**
* E-mailmarketinggebeurtenissen van Adobe Campaign Standard worden verzonden naar Dynamics 365 (e-mail verzenden, openen, klikken, stuiteren). [Meer informatie](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* Dit is ook gekend als **Vangst** (verwijzend naar het uitgang van gegevens van Adobe Campaign aan Microsoft Dynamics 365)

**Opt-binnen/uit**

De status van de optie-uit (b.v., lijst van gewezen personen) kan van Microsoft Dynamics 365 aan Adobe Campaign of van Adobe Campaign aan Microsoft Dynamics 365 worden gesynchroniseerd. De gegevens kunnen ook in twee richtingen worden gesynchroniseerd (dat wil zeggen gegevensstromen in beide richtingen). [Meer informatie](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!IMPORTANT]
>
>Het wordt sterk geadviseerd dat u **Microsoft Dynamics 365 aan het werkschema van de Campagne** alvorens veranderingen in of Adobe Campaign Standard of Microsoft Dynamics 365 te publiceren tegenhoudt. Deze wijzigingen omvatten updates van bronnen/entiteiten (en de bijbehorende velden), koppelingen, id-kolommen enz. die momenteel door de integratie worden gebruikt. Als u dit niet doet, kunnen er gegevens verloren gaan en/of kan de workflow onverwacht stoppen.

## Workflowachterstand

Deze integratietoepassing leest eerst in gegevens en schrijft dan gegevens aan de bestemming. De kolom **[!UICONTROL Backlog]** geeft het aantal records aan dat in een wachtrij is geplaatst en wacht op schrijven. Deze waarde zal naar verwachting toenemen wanneer u een grote hoeveelheid gegevens hebt die moet worden verwerkt (u voert de integratie bijvoorbeeld voor het eerst uit, u speelt de gegevens opnieuw af, enz.).

>[!NOTE]
>Als uw Microsoft Dynamics 365- en/of Campagne-records niet worden bijgewerkt, moet u eerst controleren of er een groot aantal records wacht om naar de bestemming te worden geschreven.
>

## Workflowstatus {#workflow-status}

De kolom **[!UICONTROL Status]** geeft de status aan van de achtergrondprocessen die aan de workflow zijn gekoppeld. Mogelijke waarden zijn:

* **DIE** WERKT: Het proces loopt momenteel en uw gegevens zouden moeten worden gesynchroniseerd.
* **GESTOPT**: Het proces loopt momenteel niet, zodat zou u niet uw gegevens moeten verwachten worden gesynchroniseerd.
* **BEGINNEND**: U hebt verzocht dat het werkschemaproces om te beginnen. De toepassing is nog niet begonnen om de gegevens te synchroniseren verbonden aan dit werkschema, maar u kunt het na een paar notulen verwachten (wanneer het dan het statuut van **RUNNING** zal tonen)
* **MISLUKT**: De werkschemaprocessen waren lopend maar zij ontmoetten fout(en) en zij konden niet van deze terugkrijgen.

## Beschikbare acties

Mogelijke acties worden hieronder vermeld.

* **geeft** uit: Het klikken van het potloodpictogram zal u naar een andere pagina verzenden die u zal toestaan om updates aan het werkschema te maken. Houd er rekening mee dat wijzigingen die u aanbrengt, NIET van kracht worden totdat u de workflow stopt en deze vervolgens opnieuw opstart.

* **Begin**: Een knoop van het Begin verzoekt dat een gestopt werkschema is begonnen. Deze knop wordt alleen weergegeven wanneer de processen die aan de workflow zijn gekoppeld, momenteel zijn gestopt. De processen veranderen eerst in &quot;STARTING&quot; en daarna in &quot;RUNNING&quot;. De gegevens die aan de workflow zijn gekoppeld, worden pas gesynchroniseerd als de status &quot;RUNNING&quot; is ingeschakeld.

  De startknop is een schakelknop. Als de werkschemaprocessen reeds zijn begonnen, zal de knoop in a **knoop van het Einde** veranderen.

* **Einde**: De 3&rbrace; knoopverzoeken van het a **Einde &lbrace;dat een lopend werkschema wordt tegengehouden.** Deze knop wordt alleen weergegeven wanneer de processen die aan de workflow zijn gekoppeld, actief zijn.

Wanneer u een werkschema uitgeeft, worden uw updates NIET onmiddellijk opgenomen in de lopende procesregels, tot u het werkschema ophoudt en dan de **knoop van het Begin** klikt. Dan worden uw updates opgenomen in de lopende processen (zodra het proces aan a **RUNNING** staat terugkeert).

Een waarschuwingsaanwijzing wordt toegevoegd aan de **knoop van het Einde** om u te laten weten wanneer u (a) updates aan werkschema hebt gemaakt, maar (b) geen Einde/Begin van dit werkschema hebben gedaan.

![](assets/do-not-localize/d365-to-acs-icon-stop-with-changes.png)
