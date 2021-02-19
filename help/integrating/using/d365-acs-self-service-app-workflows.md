---
title: Workflows voor integratietoepassingen
description: Workflows voor integratie van campagnes en dynamiek
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: efa30d7ed4a0caf929da6f485681078318849cda
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 0%

---


# Campagne - de integratiewerkschema&#39;s van de Dynamica 365 van Microsoft

Op de pagina **[!UICONTROL Workflows]** staan de technische workflows en hun status.

De integratietoepassing wordt geleverd met drie workflows:

![](assets/do-not-localize/d365-to-acs-ui-page-workflows.png)

**Microsoft Dynamics 365 to Campaign**
* Verzend *contacten* van de Dynamica 365 van Microsoft naar Adobe Campaign
* *Aangepaste entiteiten*: Breng douanetabellen van de Dynamica 365 van Microsoft aan Adobe Campaign. [Meer informatie](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* Dit wordt ook genoemd als **Ingress** (verwijzend naar de ingang van gegevens van de Dynamica 365 van Microsoft aan Adobe Campaign)

**Campagne aan de Dynamica 365 van Microsoft**
* E-mailmarketinggebeurtenissen van Adobe Campaign Standard worden verzonden naar Dynamics 365 (e-mail verzenden, openen, klikken, stuiteren). [Meer informatie](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* Dit wordt ook genoemd als **Egress** (verwijzend naar de uitgang van gegevens van Adobe Campaign aan de Dynamica 365 van Microsoft)

**In-/uitschakelen**

De opt-uit statussen (b.v., lijst van gewezen personen) kunnen van de Dynamica 365 van Microsoft aan Adobe Campaign of van Adobe Campaign aan de Dynamica 365 van Microsoft worden gesynchroniseerd. De gegevens kunnen ook in twee richtingen worden gesynchroniseerd (dat wil zeggen gegevensstromen in beide richtingen). [Meer informatie](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!IMPORTANT]
>
>Het wordt sterk geadviseerd dat u **de Dynamica 365 van Microsoft aan Campaign** werkschema alvorens veranderingen in of de Dynamica 365 van Adobe Campaign Standard of van Microsoft te publiceren tegenhoudt. Deze wijzigingen omvatten updates van bronnen/entiteiten (en de bijbehorende velden), koppelingen, id-kolommen enz. die momenteel door de integratie worden gebruikt. Als u dit niet doet, kunnen er gegevens verloren gaan en/of kan de workflow onverwacht stoppen.

## Workflowachterstand

Deze integratietoepassing leest eerst in gegevens en schrijft dan gegevens aan de bestemming. De **[!UICONTROL Backlog]** kolom wijst op het aantal verslagen die in een rij zijn gevormd en wachten om worden geschreven. Deze waarde zal naar verwachting toenemen wanneer u een grote hoeveelheid gegevens hebt die moet worden verwerkt (u voert de integratie bijvoorbeeld voor het eerst uit, u speelt de gegevens opnieuw af, enz.).

>[!NOTE]
>Als uw Dynamiek 365 van Microsoft en/of verslagen van de Campagne niet bijwerken, zou u eerst moeten controleren om te zien of is er een groot aantal verslagen wachtend om aan de bestemming worden geschreven.


## Workflowstatus {#workflow-status}

De kolom **[!UICONTROL Status]** geeft de status aan van de achtergrondprocessen die aan de workflow zijn gekoppeld. Mogelijke waarden zijn:

* **UITVOEREN**: Het proces is momenteel actief en uw gegevens moeten worden gesynchroniseerd.
* **GESTOPT**: Het proces is momenteel niet actief, dus u mag niet verwachten dat uw gegevens moeten worden gesynchroniseerd.
* **STARTEN**: U hebt gevraagd dat de workflowprocessen worden gestart. De toepassing is nog niet begonnen met het synchroniseren van de gegevens die aan deze workflow zijn gekoppeld, maar u kunt verwachten dat dit na een paar minuten gebeurt (wanneer de status van **RUNNING** wordt weergegeven)
* **MISLUKT**: De workflowprocessen werden uitgevoerd, maar er zijn fouten opgetreden en deze kunnen niet worden hersteld.

## Beschikbare acties

Mogelijke acties worden hieronder vermeld.

* **Bewerken**: Als u op het potloodpictogram klikt, gaat u naar een andere pagina waarop u de workflow kunt bijwerken. Houd er rekening mee dat wijzigingen die u aanbrengt, NIET van kracht worden totdat u de workflow stopt en deze vervolgens opnieuw opstart.

* **Begin**: Met de knop Start wordt gevraagd om een stopworkflow te starten. Deze knop wordt alleen weergegeven wanneer de processen die aan de workflow zijn gekoppeld, momenteel zijn gestopt. De processen veranderen eerst in &quot;STARTING&quot; en daarna in &quot;RUNNING&quot;. De gegevens die aan de workflow zijn gekoppeld, worden pas gesynchroniseerd als de status &quot;RUNNING&quot; is ingeschakeld.

   De startknop is een schakelknop. Als de werkstroomprocessen al zijn gestart, verandert de knop in een **Stop**-knop.

* **Stoppen**: Een  **** stopknop vraagt dat een actieve workflow wordt gestopt. Deze knop wordt alleen weergegeven wanneer de processen die aan de workflow zijn gekoppeld, actief zijn.

Wanneer u een workflow bewerkt, worden uw updates NIET direct opgenomen in de regels voor actieve processen, totdat u de workflow stopt en vervolgens op de knop **Start** klikt. Dan worden uw updates opgenomen in de lopende processen (zodra het proces aan een **RUNNING** staat terugkeert).

Er wordt een waarschuwingsbericht toegevoegd aan de knop **Stop** om u te laten weten wanneer u (a) updates hebt aangebracht aan de workflow, maar (b) deze workflow niet hebt gestopt/gestart.

![](assets/do-not-localize/d365-to-acs-icon-stop-with-changes.png)
