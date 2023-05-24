---
title: Workflows voor integratietoepassingen
description: Workflows voor integratie van campagnes en dynamiek
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 51f07f08-5d57-4c4c-aff2-d03e5956ec6f
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 0%

---

# Campagne - Microsoft Dynamics 365-integratieworkflows

De **[!UICONTROL Workflows]** op de pagina staan de technische workflows en hun status.

De integratietoepassing wordt geleverd met drie workflows:

![](assets/do-not-localize/d365-to-acs-ui-page-workflows.png)

**Microsoft Dynamics 365 to Campaign**
* Verzenden *contactpersonen* van Microsoft Dynamics 365 naar Adobe Campaign
* *Aangepaste entiteiten*: Breng aangepaste tabellen van Microsoft Dynamics 365 naar Adobe Campaign. [Meer informatie](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* Dit wordt ook wel bekend als **Ingress** (onder verwijzing naar de toegang tot gegevens van Microsoft Dynamics 365 tot Adobe Campaign)

**Campagne voor Microsoft Dynamics 365**
* E-mailmarketinggebeurtenissen van Adobe Campaign Standard worden verzonden naar Dynamics 365 (e-mail verzenden, openen, klikken, stuiteren). [Meer informatie](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* Dit wordt ook wel bekend als **Egress** (onder verwijzing naar de vooruitgang van gegevens van Adobe Campaign naar Microsoft Dynamics 365)

**In-/uitschakelen**

De status van de optie-uit (b.v., lijst van gewezen personen) kan van de Dynamica 365 van Microsoft aan Adobe Campaign of van Adobe Campaign aan de Dynamica 365 van Microsoft worden gesynchroniseerd. De gegevens kunnen ook in twee richtingen worden gesynchroniseerd (dat wil zeggen gegevensstromen in beide richtingen). [Meer informatie](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!IMPORTANT]
>
>Het wordt ten zeerste aanbevolen om het **Microsoft Dynamics 365 to Campaign** workflow voordat wijzigingen in Adobe Campaign Standard of Microsoft Dynamics 365 worden gepubliceerd. Deze wijzigingen omvatten updates van bronnen/entiteiten (en de bijbehorende velden), koppelingen, id-kolommen enz. die momenteel door de integratie worden gebruikt. Als u dit niet doet, kunnen er gegevens verloren gaan en/of kan de workflow onverwacht stoppen.

## Workflowachterstand

Deze integratietoepassing leest eerst in gegevens en schrijft dan gegevens aan de bestemming. De **[!UICONTROL Backlog]** de kolom wijst op het aantal verslagen die een rij zijn gevormd en wachten om worden geschreven. Deze waarde zal naar verwachting toenemen wanneer u een grote hoeveelheid gegevens hebt die moet worden verwerkt (u voert de integratie bijvoorbeeld voor het eerst uit, u speelt de gegevens opnieuw af, enz.).

>[!NOTE]
>Als uw Microsoft Dynamics 365- en/of Campagne-records niet worden bijgewerkt, moet u eerst controleren of er een groot aantal records wacht om naar de bestemming te worden geschreven.

## Workflowstatus {#workflow-status}

De **[!UICONTROL Status]** de staat van de achtergrondprocessen die aan de workflow zijn gekoppeld. Mogelijke waarden zijn:

* **UITVOEREN**: Het proces is momenteel actief en uw gegevens moeten worden gesynchroniseerd.
* **GESTOPT**: Het proces is momenteel niet actief, dus u mag niet verwachten dat uw gegevens moeten worden gesynchroniseerd.
* **STARTEN**: U hebt gevraagd dat de workflowprocessen worden gestart. De toepassing is nog niet begonnen met het synchroniseren van de gegevens die aan deze workflow zijn gekoppeld, maar u kunt verwachten dat dit na een paar minuten gebeurt (wanneer vervolgens de status van **UITVOEREN**)
* **MISLUKT**: De workflowprocessen werden uitgevoerd, maar er zijn fouten opgetreden en deze kunnen niet worden hersteld.

## Beschikbare acties

Mogelijke acties worden hieronder vermeld.

* **Bewerken**: Als u op het potloodpictogram klikt, gaat u naar een andere pagina waarop u de workflow kunt bijwerken. Houd er rekening mee dat wijzigingen die u aanbrengt, NIET van kracht worden totdat u de workflow stopt en deze vervolgens opnieuw opstart.

* **Start**: Met de knop Start wordt gevraagd om een stopworkflow te starten. Deze knop wordt alleen weergegeven wanneer de processen die aan de workflow zijn gekoppeld, momenteel zijn gestopt. De processen veranderen eerst in &quot;STARTING&quot; en daarna in &quot;RUNNING&quot;. De gegevens die aan de workflow zijn gekoppeld, worden pas gesynchroniseerd als de status &quot;RUNNING&quot; is ingeschakeld.

   De startknop is een schakelknop. Als de workflowprocessen al zijn gestart, verandert de knop in een **Stoppen** knop.

* **Stoppen**: A **Stoppen** om een actieve workflow te stoppen. Deze knop wordt alleen weergegeven wanneer de processen die aan de workflow zijn gekoppeld, actief zijn.

Wanneer u een workflow bewerkt, worden de updates NIET direct opgenomen in de regels van het actieve proces, totdat u de workflow stopt en vervolgens op de knop **Start** knop. Dan worden uw updates opgenomen in de lopende processen (zodra het proces aan **UITVOEREN** status).

Aan de **Stoppen** om u te laten weten wanneer u (a) updates van de workflow hebt aangebracht, maar (b) geen Stop/Begin van deze workflow hebt uitgevoerd.

![](assets/do-not-localize/d365-to-acs-icon-stop-with-changes.png)
