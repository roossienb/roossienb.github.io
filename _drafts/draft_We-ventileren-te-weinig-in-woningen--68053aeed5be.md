---
title: We ventileren te weinig in woningen.
description: >-
  Recentelijk kwam het vraagstuk bij ons thuis op of we wel genoeg ventileerden
  met ons balansventilatiesysteem. Na aankoop van een Trotec…
date: ''
categories: []
keywords: []
slug: ''
---

Recentelijk kwam het vraagstuk bij ons thuis op of we wel genoeg ventileerden met ons balansventilatiesysteem. Na aankoop van een [Trotec BZ30](https://nl.trotec.com/producten-en-diensten/meetinstrumenten/klimaat/klimaatgegevenslogger/bz30-co2-luchtkwaliteit-datalogger/) CO2 datalogger kon ik op onderzoek uit. Als snel werd duidelijk dat met name onze slaapkamer vrij snel boven de 2.000 ppm CO2 concentratie uit kwam. Een waarde die als uitermate ongezond wordt geacht. 

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\1__fWdyUSAPE8nP9XAknSaR9w.png)

ASHRAE adviseert bijvoorbeeld een maximale waarde van 1.000 ppm. De algemene opvatting van verschillende Nederlandse instanties is dat 1.200 ppm het maximum is, hoewel exacte grenzen en onderbouwingen niet terug te vinden is. 2.000 ppm Is in ieder geval veel te veel is. Maar hoe komen dit soort hoge waarden in onze woning? We ventileren toch?

![](D:\Documents\Blog\Medium archive\Posts\md_1694113268620\img\0__9gUKHWUR9KFEuxcM.png)

### Bouwbesluit

De wetgever heeft eisen opgesteld met betrekking tot ventilatie in de woning. Deze ventilatie-eisen zijn gebaseerd op een advies van de Gezondheidsraad uit 1984, waarin de minimum ventilatie-eis 25 m3/h per persoon is.

In het bouwbesluit Afdeling 3.6, artikel 3.28 lid 1 en 2 is het minimale ventilatiedebiet voor een woonfunctie per verblijfsgebied vastgesteld op 0,9 dm3/s/m2, oftewel 3,2 m3/h/m2), met een minimum van 7 dm3/s/m2 (25 m3/h/m2).

Een verblijfsgebied is bijvoorbeeld een slaapkamer, woonkamer, keuken en hobbyruimte. Een badkamer, hal, technische ruimte of toilet is geen verblijfsruimte.

Neem ik mijn eigen huis als voorbeeld (138 m2, drie verdiepingen, bouwjaar 2005), dan kom ik op de volgende ventilatie-eisen per verblijfsgebied.

TK dit is gewijzigd

TK keuken is normaal afzuiging

GEBIED                          OPPERVLAK (m2)        VENTILATIE (m3/h)  
\=======================================================================  
Slaapkamer 1                         13,0                   46,8  
Slaapkamer 2 (kantoor)               11,2                   40.3  
Slaapkamer 3 (kantoor)                6,1                   25,2  
Woonkamer/keuken                     39,5                  142,4   
Hobbyruimte                          20,5                   73,8  
\-----------------------------------------------------------------------  
TOTAAL                                                     328.5  
  
  
AFZUIGING                            
Badkamer                                                    75.6  
Toilet                                                      25.2  
Keuken (oud)                                                75.6  
Wasruimte                                                   50.4  
\-----------------------------------------------------------------------  
TOTAAL                                                     226.8  
  

### CO2 concentratie

Mensen ademen in rust ongeveer 20 liter per uur aan CO2 uit. Stel dat er N aantal personen in een ruimte met volume V zijn. Elk uur neemt de concentratie CO2 dan toe met

(0.02 \* N / V) \* 1,000,000 ppm

De ruimte wordt geventileerd met een debiet D (in m3/h). De hoeveelheid CO2 die wordt afgevoerd hangt af van de CO2 concentratie C (in ppm) in deze ruimte. Er wordt namelijk een hoeveelheid lucht met concentratie C vervangen door buitenlucht met een CO2 concentratie van ongeveer 400 ppm. Elk uur neemt de concentratie daardoor af met

(C — 400) \* D / V ppm

In een steady-state toestand, blijft de CO2 concentratie in de ruimte gelijk. De toename van CO2 is dan gelijk aan de afname van CO2. Daar volgt uit dat de concentratie CO2 in steady-state toestand gelijk is aan

C = 20,000 \* N / D + 400

Wat daarbij opvalt is de het volume van de ruimte er niet toe doet. Alleen het debiet en het aantal personen bepalen de CO2 concentratie.

Een steady-state situatie wordt niet direct bereikt. Het kan enkele uren duren voordat de berekende concentratie in bovenstaande formule wordt bereikt. Typische omstandigheden waarbij steady-state bereikt wordt zijn slapen en werken.

#### PPMs berekenen

Wordt deze formule toegepast op mijn woning, dan komen we op de volgende steady-state concentraties uit.

GEBIED                           PERSONEN       Steady-state CO2 (ppm)  
\=======================================================================  
Slaapkamer 1                            2                   1.361  
Slaapkamer 2 (kantoor)                  1                     959  
Slaapkamer 3 (kantoor)                  1                   1.200  
Woonkamer + keuken                      2                     716   
Hobbyruimte                             2                   1.009  
\-----------------------------------------------------------------------  
Woning gemiddeld                        2                     536

Wat direct opvalt is dat 3 ruimten boven de aanbevolen 1,000 ppm komen. Maar geen van de ruimten komt boven de 2.000 ppm uit zoals gemeten. Hoe komt dit?

### Werkelijk ventilatiedebiet ligt lager

De wetgever stelt dat het nominaal debiet van het ventilatiesysteem moet tenminste gelijk zijn aan het minimaal benodigde ventilatiedebiet. Voor onze woning is deze eis 294,4 m3/h. Wij hebben een Zehnder WHR91 met een nominale ventilatiecapaciteit van 300 m3/h. Dat klopt dus aardig.

Echter, dit ventilatiesysteem komt met drie standen die elk voorgeprogrammeerd zijn op 30% (stand 1), 50% (stand 2) en 90% (stand 3). In de [specificaties](https://zehndernl.zendesk.com/hc/nl/article_attachments/115009949649/Technische_documentatie_WHR_90_en_WHR_91.pdf) is terug te vinden wat het werkelijk debiet is. Reken we dit om naar de steady-state ppm, dan komen we op de volgende 

GEBIED                     STAND 1 (30%)   STAND 2 (50%)   STAND 3 (90%)  
\=======================================================================  
Slaapkamer 1                 3,338           2,201           1,410  
Slaapkamer 2 (kantoor)       2,352           1,551             994  
Slaapkamer 3 (kantoor)       2,944           1,941           1,244  
Woonkamer + keuken           1,756           1,158             742   
Hobbyruimte                  2,475           1,632           1,046  
\-----------------------------------------------------------------------  
Woning gemiddeld             1,315             867             555

En daarmee zijn de eerdergenoemde metingen prima te verklaren. Doordat wij lang in een de slaapkamers aanwezig zijn, wordt de steady-state situatie bereikt en daarmee de hoge concentratie aan CO2.

Daarbij is het algemeen advies dat je ventileert op stand 2, tenzij je iets doet met veel CO2 productie (feestje) of vochtproductie (douchen, koken). We adviseren huishoudens dus niet om met het debiet in het Bouwbesluit te ventileren, maar slechts met de helft.