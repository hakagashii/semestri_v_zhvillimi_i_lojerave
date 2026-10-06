# Project Charter v0.1

## Emri i projektit
**Escape Room: The Locked Lab**

## Problemi
Shume lojera bazohen ne nje sekuence vendimesh ku veprimet e lojtarit ndryshojne gjendjen e sistemit. Projekti yne e shnderron kete ne nje Escape Room ku lojtari duhet te analizoje informacion, te zgjidhe puzzle dhe te hape dhoma ne rend logjik.

Ne aspekt kompjuterik, problemi eshte te menaxhohet gjendja e lojes, varshmeria mes puzzle-ve dhe kalimi nga nje gjendje ne tjetren vetem kur kushtet jane plotesuar.

Loja duhet te percaktoje sakte kur nje veprim eshte valid, kur nje dere mund te hapet dhe kur lojtari fiton ose humb.

## Qellimi i lojtarit
Te dale nga laboratori duke zgjidhur te gjitha puzzle-t e detyrueshme dhe duke hapur deren finale.

## Core Mechanic
**Eksploro -> Analizo -> Zgjidh -> Zhblloko -> Vazhdo**

## Kushti i fitores
Lojtari fiton kur zgjidh puzzle-t kryesore, merr kodin final dhe hap deren e daljes.

## Kushti i humbjes
Lojtari humb nese perfundon koha ose harxhon tentimet e lejuara.

## Rregullat kryesore
1. Dera e nje dhome hapet vetem pasi plotesohet kushti i saj.
2. Disa puzzle kerkojne objekte ose informata nga dhoma tjera.
3. Inputet e gabuara mund te kushtojne nje tentim.
4. Progresi ruhet ne GameState.
5. Loja perfundon vetem me statusin WIN ose LOSE.

## Komponenti logjik / algoritmik
Dhomat dhe puzzle-t modelohen si nje graf i vogel me varshmeri. Sistemi kontrollon cilat nyje jane te hapura sipas puzzle-ve te zgjidhura dhe inventory-t.

Puzzle-t do te perdorin validim algoritmik, si:
- sekuenca numerike;
- pattern matching;
- kode binare;
- kombinime logjike;
- mini-pathfinding.

## MVP
- 3 dhoma
- 3 puzzle
- inventory
- tentime ose timer
- nje dere finale
- WIN / LOSE
- console ose GUI minimal

## Cfare nuk perfshihet
- multiplayer
- 3D
- open world
- server online
- AI gjenerative
- voice recognition
- database komplekse
- animacione te avancuara

## Pse eshte realist
Projekti mund te ndahet ne module te vogla dhe te punohet paralelisht nga 3 studente. Logjika kryesore mund te perfundohet ne console dhe GUI mund te shtohet vetem nese ka kohe.

## Rreziku kryesor
Scope creep: shtimi i shume dhomave, puzzle-ve dhe grafikes para perfundimit te logjikes baze.

## Strategjia
Fillimisht ndertohet MVP. Cdo funksion shtese konsiderohet bonus vetem pasi versioni bazik te jete stabil.
