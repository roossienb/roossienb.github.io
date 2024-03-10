---
title: Er is nog Genoeg Ruimte op het Elektriciteitsnet!
description: >-
  Hoe dynamische allocatie van capaciteit de bestaande netten optimaler kan
  benutten.
date: '2022-06-13T13:59:07.619Z'
categories: []
keywords: []
slug: /@bartroossien/er-is-nog-genoeg-ruimte-op-het-elektriciteitsnet-346fbca0912d
---

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\1__3__nszkDiGhJ__yAEWr3__0MQ.png)

Inmiddels staat er bijna wekelijks een bericht in de krant dat het elektriciteitsnet vol is. Vorige week ging het over [Limburg](https://www.venray.nl/schaarste-op-het-elektriciteitsnetwerk) en Noord-Brabant, waar in korte tijd 800 MW aan capaciteit is gealloceerd en Tennet aangeeft geen nieuwe allocaties meer toe te kennen.

Congestie speelt lang niet alleen bij grote zonneparken zoals wel eens gedacht wordt. Ook bij afname van elektriciteit zijn er problemen. Het gaat dan lang niet altijd om bijvoorbeeld datacenters. Het is soms zo nijpend dat [zelfs een nieuwbouwschool niet aangesloten kan worden](https://nos.nl/artikel/2401489-netbeheerder-heeft-geen-stroom-nieuwbouw-school-op-de-tocht).

Het elektriciteit zit echter helemaal niet zo vol als wordt beweerd. Het elektriciteitsnet is met voornamelijk of papier vol, fysisch is er nog meer dan genoeg ruimte.

### Administratief alloceren

Administratief vraag je capaciteit aan bij een netbeheerder. Dat kan afname, invoeding of een combinatie van beiden zijn. Deze capaciteit is het maximale vermogen wat je (op papier) mag afnemen.

Deze capaciteit wordt vervolgens gereserveerd op het onderstation. Een onderstation kan zowel voorzien in afname (het leveren van elektriciteit) als invoeding (het terugleveren van elektriciteit). Afname en invoeding worden los van elkaar geadministreerd.

Stel dat klant A 2 MW capaciteit wil voor afname, klant B wil 5 MW afname en 1 MW invoeding en klant C wil 3 MW invoeding. De capaciteit gereserveerd op het onderstation is dan 2 + 5 = 7 MW voor afname en 3 + 1 = 4 MW voor invoeding. Heeft het onderstation een maximale capaciteit van bijvoorbeeld 8 MW, dan is er dus nog 1 MW beschikbaar voor afname en 4 MW voor invoeding.

#### Gelijktijdigheid

Er wordt echter niet gekeken naar gelijktijdigheid. Klant A heeft de 2 MW misschien alleen dagelijks in de ochtend nodig, terwijl klant B de maximale capaciteit van 5 MW op de woensdagmiddag bereikt. Dit betekent dat de gereserveerde piek van 7 MW nooit bereikt wordt. Als klant A in de ochtenden op haar piek van 2 MW zit, zit klant B onder haar piek van 5 MW. Andersom, als klant B haar piek van 5 MW bereikt op de woensdagmiddag, zit klant A onder haar piek van 2 MW.

Er wordt op dit moment bij het reserveren van capaciteit op het onderstation ervan uitgegaan dat er 100% gelijktijdigheid is van de pieken waarvoor klanten de capaciteit hebben gereserveerd. In de praktijk zal deze gelijktijdigheidsfactor veel lager liggen.

Ook tussen gelijktijdigheid van afname en invoeding wordt nog onvoldoende meegenomen. Stel dat een zonneweide van 30 MW wil aansluiten op een onderstation dat nog maar 15 MW aan invoedingscapaciteit over heeft. Dit zou betekenen dat de zonneweide geen aansluiting zou kunnen krijgen (in ieder geval niet voor de gewenste 30 MW). Stel dat er op datzelfde onderstation een datacenter van 20 MW is aangesloten. Doordat een datacenter 24/7 op ongeveer dezelfde capaciteit draait, is er altijd afname van het onderstation. Er vindt, op dagen met veel zon, dus zowel afname als invoeding plaats, waardoor er op onderstation niveau een directe uitwisseling plaats vindt van productie en consumptie. De werkelijke capaciteit die dan nodig is, is 30 MW invoeding — 20 MW afname = 10 MW invoeding.

#### Ongebruikte reservering

Verder wordt er capaciteit gereserveerd die niet gebruikt wordt. De op het onderstation gereserveerde capaciteit is dan hoger, dan de hoogste vermogenspiek van bijvoorbeeld een klant.

Ik heb in het verleden energiebesparingsonderzoeken uitgevoerd, waarbij geregeld naar voren kwam dat de administratieve vermogenspiek hoger lag dan de gemeten vermogenspiek. Dit kost een klant (veel) geld. Bij kleinere vermogens (< 2 MW) kan dit met een telefoontje naar de netbeheerder aangepast worden. Makkelijker geld verdienen is er niet.

Ook reserveren klanten bewust capaciteit om strategische redenen, bijvoorbeeld zodat men in de toekomst uit te kunnen breiden. Dit houdt echter wel waardevolle capaciteit bezet die niet gebruikt wordt.

### Dynamische capaciteitsuitgifte

Fysisch gezien kunnen de huidige elektriciteitsnetten veel meer energie transporteren dan op papier op dit moment mogelijk is. Elektriciteitsnetten worden dus suboptimaal gebruikt. Daarom moeten we het allocatieproces significant verbeteren.

Capaciteit wordt nu voor het hele jaar gereserveerd, ook al komt de piek maar 1 keer in het jaar voor. Door capaciteit dynamisch te reserveren, bijvoorbeeld per uur, kunnen klanten capaciteit reserveren wanneer zij dat werkelijk nodig hebben, maar komt capaciteit vrij (die nu nog gereserveerd is) op moment dat zij het niet nodig hebben. Daardoor is ook de uitdaging van gelijktijdigheid direct verholpen.

Om te voorkomen dat klanten alsnog capaciteit gaan ‘vasthouden’, bijvoorbeeld om op zeker te spelen of dat men geen moeite wil steken in het plannen van capaciteit, is een boete voor niet-gebruikte capaciteit een pressiemiddel.

Op uren waarbij er meer capaciteit gevraagd wordt dan beschikbaar is, kan capaciteit bij opbod worden gealloceerd, bijvoorbeeld via een biedproces. De capaciteitsmarkt lijkt dan veel op de huidige EPEX/ENDEX waarop de volumes (MWh) worden verhandeld.

### Conclusie

Het elektriciteitsnet speelt een zeer belangrijke rol in de energietransitie. We moeten voorkomen dat de infrastructuur de bottleneck gaat worden. De congestie van vandaag is voornamelijk administratief, er is voldoende (fysische) capaciteit beschikbaar. Door over te stappen op een andere wijze van capaciteitsallocatie, bijvoorbeeld via een dynamische capaciteitsmarkt, komt waardevolle capaciteit vrij en is er een economische impuls voor het toepassen van bijvoorbeeld peak-shaving en vermogensreductie.