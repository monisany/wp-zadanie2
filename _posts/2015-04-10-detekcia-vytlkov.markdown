---
layout: post
title:  "Detekcia výtlkov"
date:   2015-04-10 16:05:00
categories: ['hlavna','detekcia']
---

Našou úlohou je implementácia novej funkcionality do navigácie, ktorá bude počas jazdy
sledovať, či nastal stret automobilu s výtlkom. Pokiaľ áno, mal by sa tento výtlk zobraziť
od tohto momentu na mape nielen vodičovi, ktorý naň narazil, ale ktorémukoľvek
používateľovi našej aplikácie. Výtlk sa zobrazí na mape ako varovný signál pre ostatných.
Využitím takéhoto sociálneho prvku v navigácií sa naša navigácia stáva sociálnou. Vodiči
sa tak nepriamo a nevedomky stávajú súčasťou kolaborujúcej skupiny, ktorá obohacuje
obyčajnú navigáciu o možnosť predchádzania zbytočným nárazom. Jazda je tak pre
cestujúcich pohodlnejšia.

**EXISTUJÚCE RIEŠENIE**

V americkom meste Boston vznikla myšlienka, ako využiť technológie na zlepšenie
pozemných komunikácií. Správa mesta ponúka občanom mobilnú aplikáciu s názvom
Street Bump 26 , ktorá dokáže pomocou akcelerometra detegovať výtlky a iné nerovnosti na
vozovke. Túto aplikáciu poskytuje mesto Boston občanom zadarmo.

Stačí, ak ju používateľ zapne pri jazde po meste a ona sama vysiela informácie
o existujúcich výtlkoch na server. Jej nevýhodou je, že nedokáže „bežať“ na pozadí, preto
ak chce napríklad používateľ volať, musí aplikáciu najskôr zastaviť a potom opätovne
spustiť.

Ak je na jednom mieste detegovaný výtlk viac ako trikrát, mesto tento výtlk skontroluje
a zaradí ho na zoznam cestných opráv.

Táto aplikácia samozrejme nefunguje vždy. Môže sa stať, že aplikácia zaznamená výtlk, aj
keď reálne žiaden neexistuje. Takisto sa môže stať, že používateľ narazí na výtlk, ale
aplikácia tento pohyb nevyhodnotí ako výtlk. Takýto prípad môže nastať hlavne v prípade,
ak sa automobil pohybuje malou rýchlosťou.

Akcelerometre na zariadeniach so systémom Android sa veľmi líšia, pokiaľ ide o presnosť.
Pri vývoji tejto aplikácia je snaha normalizovať akcelerometre rozdielnych zariadení.
[Nigel Jacob, hovorca mesta Boston]

Aplikáciu programátori vyvinuli tak, aby bola dostatočne citlivá na detegovanie aj menších
nerovností, ktoré by sa časom mohli stať obrovskými jamami v zemi.

Pre podobnú aplikáciu, ktorá sa bude používať na slovenských cestách, by bolo vhodné
použiť menšiu citlivosť.