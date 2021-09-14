---
title: Vroege aanvullende informatie
description: Vroege aanvullende informatie
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 100%

---

# Vroege aanvullende informatie {#new-release}

Op deze pagina worden nieuwe functies, verbeteringen en oplossingen beschreven die in de volgende release van Campaign Standard zijn opgenomen.

>[!CAUTION]
>
> Deze content kan zonder voorafgaande kennisgeving worden gewijzigd tot de upgradedatum van de werkgebiedomgevingen. Meer informatie vindt u op de [releaseplanningspagina](../../rn/using/release-planning.md).

## Release 21.3 - september 2021 {#release-21-3---sept-2021}


**Nieuwe functies**


<table> 
<thead> 
<tr> 
<th> <strong>Uniforme Experience Cloud-interface</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>De kopbalk van Adobe Campaign is veranderd voor een uniforme, verbeterde ervaring voor alle Experience Cloud-producten en -services. Deze wijzigingen maken het u als volgt gemakkelijker:</p>
<ul>
<li>Eenvoudiger overschakelen tussen uw organisaties of naar een andere applicatie.</li>
<li>Verbeterde Help voor gebruikers - De Experience League is in het product opgenomen, zodat de zoekresultaten ook resultaten van communityforums en meer videocontent omvatten; hierdoor krijgt u gemakkelijker toegang tot meer content om optimaal te profiteren van de applicatie. We hebben ook een feedbackmechanisme toegevoegd aan het menu Help, waardoor het gemakkelijker is om problemen te melden of uw ideeën te delen.</li>
<li>Verbeterde meldingen - De vervolgkeuzelijst Meldingen bevat nu twee tabbladen: één voor uw eigen productmeldingen en één voor meer algemene productmeldingen.</li>
</ul>
<!--<p>For more information refer to the <a href="../../start/using/interface-description.md#top-bar">detailed documentation</a>.
</p>-->
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Audittrail</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Met de nieuwe functie Audittrail wordt in real time een uitgebreide lijst met acties en gebeurtenissen in Adobe Campaign vastgelegd. Het bevat een manier om zelf toegang te krijgen tot een geschiedenis van gegevens om vragen te beantwoorden zoals:</p>
<ul>
<li>Wat is er gebeurd met deze workflow en wie heeft deze voor het laatst bijgewerkt?</li>
<li>Wie heeft de laatste wijzigingen doorgevoerd?</li>
<li>Wat was de vorige staat?</li>
</ul>
<p>Adobe Campaign controleert nu de acties voor het maken, bewerken en verwijderen van: workflows, opties, aangepaste bronnen. Wijzigingen van deze items worden ook bijgehouden.</p>
<!--<p>For more information refer to the <a href="../../administration/using/audit.md">detailed documentation</a>.
</p>-->
</td> 
</tr> 
</tbody> 
</table>


<table> 
<thead> 
<tr> 
<th> <strong>Diagnostische modus voor workflows</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>U kunt de workflows van Campaign nu uitvoeren in de diagnostische modus. In deze modus wordt informatie geregistreerd om problemen met de uitvoering van probleemoplossingen te helpen oplossen. Het volledige uitvoeringsplan wordt geregistreerd als een workflowquery standaard meer dan één minuut duurt.</p>
<!--<p>For more information refer to the <a href="../../administration/using/audit.md">detailed documentation</a>.
</p>-->
</td> 
</tr> 
</tbody> 
</table>

**Verbeteringen**

* Wanneer u een terugkerende levering maakt in een workflow die is gekoppeld aan inhoud van Adobe Experience Manager, wordt de goedkeuringsstatus van de inhoud nu gecontroleerd voordat deze wordt verzonden.
* De verbindingslimiet voor databases wordt nu uitgelijnd met het Campaign-pakket om verbindingsfouten te voorkomen.
* Er is een consistentiecontrole toegevoegd tijdens het maken van indexen in aangepaste bronnen en de foutberichten zijn verbeterd.

**Patches**

* Er is een probleem met time-out verholpen bij het importeren van e-mailinhoud van een URL. (CAMP-49054)
* Er is een fout (-69) verholpen die werd veroorzaakt door het einde van de sessie bij het openen van een URL gemarkeerd met een bladwijzer of bij het vernieuwen van een pagina vanuit de browser. (CAMP-49003, CAMP-48930, CAMP-48894)
* Er is een probleem verholpen bij het synchroniseren van regels van de verouderde bezorgingsserver naar de nieuwe bezorgingsserver. (CAMP-48923)
* Er is een probleem verholpen bij het laden van een e-mailsjabloon met HTML-tags in de e-mailontwerper. (CAMP-48243)
