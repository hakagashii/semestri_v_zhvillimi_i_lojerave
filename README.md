# Escape Room: The Locked Lab

## PBT 1 | Java 2

### Ekipi
- Studenti 1: Haka Gashi
- Studenti 2: Anduena Zogaj
- Studenti 3: Blearta Kodraliu
- Studenti 4: Gent Halabaku


## Pershkrimi i projektit
**Escape Room: The Locked Lab** eshte nje loje logjike ku lojtari ndodhet i mbyllur ne nje laborator virtual dhe duhet te zgjidhe nje seri sfidash per te dale para se t'i perfundoje koha ose tentimet.

Loja fokusohet ne logjike, vendimmarrje, zgjidhje problemesh dhe algoritme te thjeshta. Secila dhome permban nje puzzle ose pengese qe ndryshon gjendjen e lojes dhe e afron lojtarin drejt daljes.

## Problemi qe loja shnderron ne gameplay
Problemi kryesor eshte gjetja e nje sekuence te sakte veprimesh per te kaluar nga gjendja fillestare ne gjendjen finale.

Lojtari duhet:
- te analizoje informatat ne dhome;
- te gjeje objekte ose kode;
- te zgjidhe puzzle logjike;
- te zgjedhe veprimin e duhur;
- te menaxhoje kohen dhe tentimet.

Ne aspekt kompjuterik, loja modelon **game state**, tranzicione mes gjendjeve, validim te inputit, kushte fitoreje/humbjeje dhe kontroll te progresit.

## Qellimi i lojtarit
Te zgjidhe te gjitha sfidat dhe te hape deren finale te laboratorit.

## Kushti i fitores
Lojtari fiton kur:
1. i zgjidh te gjitha puzzle-t e detyrueshme;
2. mbledh kodin/celesin final;
3. hap deren finale para perfundimit te kohes ose tentimeve.

## Kushti i humbjes
Lojtari humb kur:
- perfundon koha; ose
- harxhon numrin maksimal te tentimeve ne puzzle kritike.

## Core Mechanic
Cikli kryesor i lojes eshte:

**Eksploro -> Gjej informacion -> Zgjidh puzzle -> Merr kod/objekt -> Hape pjese te re -> Vazhdo**

Ky cikel perseritet deri ne daljen finale.

## Game State
Gjendja e lojes ruan:
- dhomen aktuale;
- puzzle-t e zgjidhura;
- objektet ne inventory;
- kodet e gjetura;
- tentimet e mbetura;
- kohen e mbetur;
- statusin WIN / LOSE / PLAYING.

Shembull:

```java
class GameState {
    int currentRoom;
    int remainingAttempts;
    int remainingTime;
    boolean[] solvedPuzzles;
    List<String> inventory;
    GameStatus status;
}
```

## Rregullat kryesore
1. Lojtari nuk mund te hape nje dere pa zgjidhur puzzle-n perkates.
2. Disa puzzle kerkojne nje objekt ose informacion te gjetur me heret.
3. Inputi i gabuar mund ta zvogeloje numrin e tentimeve.
4. Puzzle-t duhet te zgjidhen sipas varshmerive logjike te lojes.
5. Loja perfundon me fitore vetem kur hapet dera finale.

## Komponenti logjik / algoritmik
Projekti do te kete te pakten nje komponent real algoritmik:

### 1. Kontrolli i progresit si graf
Dhomat/puzzle-t mund te modelohen si nyje ne nje graf.

Shembull:

`Dhoma 1 -> Puzzle A -> Dhoma 2 -> Puzzle B -> Puzzle C -> Dalja`

Sistemi kontrollon nese lojtari i ka plotesuar kushtet per te kaluar ne nyjen tjeter.

### 2. Validimi i puzzle-ve
Puzzle-t mund te perfshijne:
- sekuenca numerike;
- kode binare;
- renditje logjike;
- pattern matching;
- kombinime me kushte;
- gjetje te rruges se sakte ne nje mini-labirint.

### 3. Inventory dhe dependencies
Nje puzzle mund te kerkoje nje objekt te caktuar para se te aktivizohet.

```java
if (inventory.contains("AccessCard") && solvedPuzzles[1]) {
    unlockDoor();
}
```

## MVP - Versioni minimal funksional
Versioni minimal do te kete:
- 3 dhoma;
- 3 puzzle;
- inventory te thjeshte;
- sistem tentimesh ose timer;
- nje dere finale;
- gjendje WIN / LOSE;
- interface console ose GUI shume te thjeshte.

Ky version konsiderohet loje funksionale edhe pa grafike te avancuar.

## Jashte scope-it
Per ta mbajtur projektin realist, nuk do te perfshihen ne versionin fillestar:
- multiplayer;
- online server;
- 3D;
- physics engine;
- open world;
- voice recognition;
- AI gjenerative brenda lojes;
- account system;
- database komplekse;
- animacione te renda.

## Teknologjia
- Java
- OOP
- Collections
- Enums
- Exceptions
- File handling per ruajtje te thjeshte, nese ka kohe
- JavaFX ose Swing vetem nese logjika perfundohet me kohe

## Arkitektura fillestare
```text
src/
  main/
    java/
      game/
        Main.java
        Game.java
        GameState.java
        Room.java
        Door.java
        Player.java
        Inventory.java
        puzzle/
          Puzzle.java
          CodePuzzle.java
          SequencePuzzle.java
          LogicPuzzle.java
```

## Ndarja fillestare e moduleve
- `Game` - kontrollon rrjedhen e lojes.
- `GameState` - ruan gjendjen aktuale.
- `Room` - perfaqeson nje dhome.
- `Puzzle` - interface ose klase abstrakte per sfidat.
- `Inventory` - ruan objektet e lojtarit.
- `Door` - kontrollon kushtet per hapje.
- `Player` - ruan progresin e lojtarit.

## Rreziku kryesor
Rreziku kryesor eshte qe projekti te zgjerohet me shume puzzle, grafike dhe funksione para se te perfundoje logjika baze.

**Zgjidhja:** fillimisht implementohet MVP me 3 dhoma dhe 3 puzzle. Funksionet shtese shtohen vetem pasi MVP punon.

## Qellimi i projektit
Te ndertojme nje loje te vogel por funksionale qe demonstron:
- programim objekt-orientuar;
- menaxhim te gjendjes;
- algoritme dhe kushte logjike;
- validim;
- struktura te dhenash;
- bashkepunim ne GitHub.
