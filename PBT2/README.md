# PBT 2 | Java 3 – Lojërat dhe Shoqëria

# Escape Room: The Locked Lab

## Faza I – Zbulimi dhe Përcaktimi i Përdoruesit

---

## 1. Informacioni i projektit

**Emri i lojës:** Escape Room: The Locked Lab

**Lënda:** Zhvillimi i Lojërave

**PBT:** PBT 2 – Java 3

**Faza:** Faza I – Zbulimi dhe Përcaktimi i Përdoruesit

### Ekipi

- Haka Gashi
- Anduena Zogaj
- Blearta Kodraliu
- Gent Halabaku

---

# 2. Përmbledhje e lojës

**Escape Room: The Locked Lab** është një lojë puzzle/escape room ku lojtari gjendet i mbyllur në një laborator dhe duhet të zgjidhë një seri puzzle-sh për të vazhduar nëpër dhoma dhe për të arritur te dalja finale.

Loja fokusohet në:

- zgjidhjen e problemeve;
- logjikën;
- eksplorimin;
- analizimin e informacionit;
- përdorimin e objekteve;
- menaxhimin e progresit;
- vendimmarrjen.

Në projektin e përcaktuar në PBT 1, loja përmban 3 dhoma dhe 3 puzzle kryesore, inventory, sistem tentimesh ose timer dhe një derë finale.

Cikli kryesor i lojës është:

**Eksploro → Gjej informacion → Zgjidh puzzle → Merr kod/objekt → Hape pjesë të re → Vazhdo**

Qëllimi i lojtarit është të përdorë informacionin dhe objektet që gjen për të zgjidhur puzzle-t dhe për të arritur te dera finale.

---

# 3. Profili funksional i lojtarit

## 3.1 Lloji i lojtarit

Lojtari kryesor është një përdorues që pëlqen lojërat puzzle dhe përvojat ku duhet të mendojë, të analizojë informacionin dhe të gjejë zgjidhje.

Profili i lojtarit përcaktohet në mënyrë funksionale dhe jo vetëm në bazë të moshës.

---

## 3.2 Niveli i aftësisë

Loja synon lojtarë me nivel **fillestar deri mesatar** në lojërat puzzle.

Lojtari nuk duhet të ketë njohuri programuese për të luajtur.

Për të përfunduar lojën, lojtari duhet të jetë në gjendje të:

- lexojë dhe analizojë informacionin;
- identifikojë objekte të rëndësishme;
- lidhë informacione të ndryshme;
- përdorë logjikën;
- provojë zgjidhje;
- kuptojë feedback-un e sistemit.

---

## 3.3 Motivimi

Motivimi kryesor i lojtarit është:

- sfida;
- zgjidhja e problemeve;
- eksplorimi;
- zbulimi;
- ndjenja e progresit;
- arritja e daljes.

Lojtari duhet të ketë një qëllim të qartë: **të dalë nga laboratori duke zgjidhur puzzle-t dhe duke hapur rrugën drejt derës finale.**

---

## 3.4 Pritshmëritë e lojtarit

Lojtari pritet që:

- të kuptojë çfarë duhet të bëjë;
- të kuptojë qëllimin e puzzle-it;
- të marrë feedback pas veprimeve;
- të kuptojë kur një përgjigje është e saktë;
- të kuptojë kur një përgjigje është e gabuar;
- të dijë sa tentime i kanë mbetur nëse përdoret sistemi i tentimeve;
- të kuptojë pse një derë është e mbyllur;
- të kuptojë progresin e tij në lojë.

---

## 3.5 Platforma

Loja është e zhvilluar në **Java**.

Sipas scope-it të përcaktuar në PBT 1, logjika bazë e lojës ka prioritet.

GUI mund të zhvillohet nëse logjika kryesore e lojës përfundon me sukses.

---

## 3.6 Konteksti i përdorimit

Loja është menduar për përdorim individual.

Sesioni i lojës duhet të jetë relativisht i shkurtër dhe lojtari duhet të ketë mundësi të fokusohet në puzzle dhe në informacionin që paraqitet.

Për shkak të natyrës së Escape Room-it, feedback-u duhet të jetë i qartë dhe i kuptueshëm në mënyrë që lojtari të mos mbetet pa ditur se çfarë duhet të bëjë më pas.

---

# 4. Player & Use Context Canvas

| Elementi | Përshkrimi |
|---|---|
| **Lojtari** | Përdorues që pëlqen puzzle, logjikë dhe sfida |
| **Niveli i aftësisë** | Fillestar deri mesatar |
| **Motivimi** | Sfidë, zgjidhje problemesh, eksplorim dhe arritja e daljes |
| **Qëllimi** | Të zgjidhë puzzle-t dhe të hapë derën finale |
| **Pritshmëritë** | Feedback i qartë, progres i kuptueshëm dhe puzzle të realizueshme |
| **Platforma** | Java; GUI vetëm nëse logjika bazë përfundon |
| **Konteksti** | Lojë individuale dhe sesion relativisht i shkurtër |
| **Veprimet kryesore** | Eksplorim, mbledhje objektesh, zgjidhje puzzle-sh, futje kodesh dhe hapje dyersh |
| **Informacioni i nevojshëm** | Informacionet e gjetura, objektet, kodet, gjendja e puzzle-ve, tentimet dhe koha |
| **Feedback-u** | Mesazhe për përgjigje të sakta/gabuara, objekte, dyer, puzzle dhe statusin e lojës |
| **Rreziku kryesor** | Konfuzioni rreth veprimit të ardhshëm |
| **Rreziqe të tjera** | Frustrimi, ndjenja e padrejtësisë dhe mosvërejtja e objekteve |
| **Rezultati i dëshiruar** | Lojtari e kupton progresin dhe arrin WIN përmes zgjidhjes së puzzle-ve |

---

# 5. Player Stories

## Player Story 1 – Feedback gjatë zgjidhjes së puzzle-it

> **Si lojtar fillestar, dua të marr feedback të qartë kur jap një përgjigje të saktë ose të gabuar, në mënyrë që ta kuptoj nëse jam duke ndjekur rrugën e duhur.**

### Lidhja me mekanikën e lojës

Kjo Player Story lidhet me mekanikën e **Puzzle Validation**.

Kur lojtari jep një përgjigje:

1. sistemi kontrollon inputin;
2. nëse përgjigjja është e saktë, puzzle shënohet si i zgjidhur;
3. nëse përgjigjja është e gabuar, sistemi jep feedback;
4. nëse përdoret sistemi i tentimeve, tentimi përditësohet.

### Mekanika

**Puzzle Validation + GameState**

### Kërkesa e sistemit

Sistemi duhet të tregojë qartë nëse përgjigjja ishte:

- e saktë;
- e gabuar;
- dhe, kur është e nevojshme, sa tentime kanë mbetur.

---

# 6. Player Story 2 – Inventory dhe objektet

> **Si lojtar, dua të kuptoj se cilat objekte në inventory mund të përdoren për të zhbllokuar pjesët e laboratorit, në mënyrë që të mund të vazhdoj progresin në lojë.**

### Lidhja me mekanikën e lojës

Kjo Player Story lidhet me **Inventory** dhe **Dependencies**.

Gjatë lojës, lojtari mund të gjejë objekte që nevojiten për të vazhduar.

Një objekt mund të përdoret për:

- zgjidhjen e një puzzle;
- hapjen e një dere;
- aktivizimin e një mekanike;
- vazhdimin në dhomën tjetër.

### Mekanika

**Inventory + Dependencies + Door Unlocking**

### Kërkesa e sistemit

Kur lojtari merr një objekt:

- objekti duhet të shtohet në inventory;
- sistemi duhet të japë feedback;
- lojtari duhet të jetë në gjendje të kuptojë kur objekti është i nevojshëm për progres.

Kur lojtari provon të hapë një derë pa kushtin e nevojshëm, sistemi duhet të tregojë se dera është ende e bllokuar.

---

# 7. Player Story 3 – Kuptimi i progresit

> **Si lojtar, dua të kuptoj se cilat dhoma dhe puzzle janë përfunduar, në mënyrë që të di çfarë më duhet të bëj për të arritur te dera finale.**

### Lidhja me mekanikën e lojës

Kjo Player Story lidhet me **GameState**, **Room Dependencies** dhe **Final Door**.

Sistemi duhet të ruajë gjendjen e lojës dhe të kontrollojë progresin e lojtarit.

GameState mund të përfshijë:

- dhomën aktuale;
- puzzle-t e zgjidhura;
- objektet në inventory;
- kodet e gjetura;
- tentimet;
- kohën;
- statusin e lojës.

### Mekanika

**GameState + Room Dependencies + Final Door**

### Kërkesa e sistemit

Lojtari duhet të mund të kuptojë:

- në cilën dhomë ndodhet;
- cilat puzzle janë zgjidhur;
- cilat objekte ka;
- çfarë kushti i mungon për të vazhduar;
- kur mund të hapë derën finale.

---

# 8. Lidhja e Player Stories me sistemin

| Player Story | Mekanika | Kërkesa reale e lojës |
|---|---|---|
| Story 1 – Feedback | Puzzle Validation | Kontrollimi i përgjigjeve dhe feedback-u |
| Story 2 – Inventory | Inventory / Dependencies | Përdorimi i objekteve për progres |
| Story 3 – Progresi | GameState / Room Dependencies | Kontrollimi i dhomave, puzzle-ve dhe derës finale |

Të tre Player Stories lidhen me mekanika dhe kërkesa reale të projektit.

---

# 9. Minimal System Feedback

Feedback-u minimal që sistemi duhet të japë për veprimet kryesore është:

| Veprimi i lojtarit | Feedback-u minimal |
|---|---|
| Përgjigje e saktë | Tregohet që puzzle është zgjidhur |
| Përgjigje e gabuar | Tregohet që përgjigjja është e gabuar |
| Humbje e tentimit | Tregohet numri i tentimeve të mbetura |
| Marrje e objektit | Tregohet që objekti është shtuar në inventory |
| Përdorim i objektit | Tregohet nëse objekti mund të përdoret |
| Derë e bllokuar | Tregohet që kushti nuk është plotësuar |
| Derë e hapur | Tregohet që lojtari mund të vazhdojë |
| Puzzle e përfunduar | Tregohet që puzzle është përfunduar |
| WIN | Tregohet që loja është fituar |
| LOSE | Tregohet që loja ka përfunduar |

Feedback-u duhet të jetë i drejtpërdrejtë dhe të mos e lërë lojtarin pa informacion.

---

# 10. Rreziqet e përvojës v0.1

## Rreziku 1 – Konfuzioni

### Përshkrimi

Lojtari mund të mos kuptojë se çfarë duhet të bëjë më pas.

### Masa e zvogëlimit

Të përdoret feedback i qartë për veprimet kryesore dhe për kushtet e dyerve.

### Mënyra e testimit

Një testues që nuk e njeh lojën luan pa ndihmë direkte nga ekipi.

Kontrollohet nëse ai mund të identifikojë veprimin e ardhshëm.

---

## Rreziku 2 – Frustrimi nga puzzle-t

### Përshkrimi

Një puzzle mund të jetë shumë i vështirë dhe lojtari mund të ngecë për një kohë të gjatë.

### Masa e zvogëlimit

Puzzle-t testohen me lojtarë fillestarë ose mesatarë.

Nëse lojtari nuk e kupton qëllimin e puzzle-it, përmirësohet feedback-u ose mënyra e paraqitjes së informacionit.

### Mënyra e testimit

Testuesi duhet të kuptojë se çfarë kërkohet nga puzzle pa marrë drejtpërdrejt zgjidhjen nga ekipi.

---

## Rreziku 3 – Ndjenja e padrejtësisë nga sistemi i tentimeve

### Përshkrimi

Nëse një input i gabuar humb një tentim, lojtari mund ta konsiderojë sistemin të padrejtë nëse nuk e kupton pasojën.

### Masa e zvogëlimit

Sistemi duhet të tregojë:

- që inputi ishte i gabuar;
- që një tentim është humbur;
- sa tentime kanë mbetur.

### Mënyra e testimit

Testuesi provon inpute të gabuara dhe kontrollohet nëse e kupton menjëherë pasojën.

---

## Rreziku 4 – Mosvërejtja e objekteve të rëndësishme

### Përshkrimi

Lojtari mund të mos e vërejë një objekt që është i nevojshëm për progres.

### Masa e zvogëlimit

Objektet e rëndësishme duhet të jenë të dallueshme dhe të kenë feedback kur merren.

### Mënyra e testimit

Një testues që nuk e njeh lojën duhet të jetë në gjendje t'i identifikojë objektet kryesore pa ndihmë direkte.

---

# 11. Mësimi nga analiza e Serious/Educational Game

Në analizën e mëparshme të **Duolingo** u identifikua rëndësia e feedback-ut dhe e paraqitjes së progresit të përdoruesit.

Ky përfundim përdoret në **Escape Room: The Locked Lab** për të bërë gjendjen e lojës më të kuptueshme për lojtarin.

### Si u transferua ky përfundim në projekt?

Në vend që lojtari të marrë vetëm një rezultat nga sistemi, loja duhet të japë feedback pas veprimeve kryesore.

Kjo përfshin:

- përgjigje të sakta;
- përgjigje të gabuara;
- puzzle të përfunduara;
- objekte të marra;
- dyer të hapura;
- dyer të bllokuara;
- tentime të mbetura;
- WIN / LOSE.

### Vendimi i projektit

Ky përfundim **konfirmon vendimin** që feedback-u duhet të jetë pjesë e dizajnit të lojës dhe jo vetëm një element teknik.

Qëllimi nuk është t'i jepet lojtarit zgjidhja e puzzle-it, por t'i jepet informacion i mjaftueshëm për të kuptuar gjendjen e lojës.

---

# 12. Ndikimi në dizajn

Bazuar në profilin e lojtarit dhe analizën e kontekstit, ekipi konfirmon:

1. MVP-ja mbetet me 3 dhoma dhe 3 puzzle.
2. Logjika e GameState mbetet prioritet.
3. Feedback-u bëhet kërkesë e rëndësishme e ndërveprimit.
4. Inventory duhet të jetë i kuptueshëm.
5. Dependencies mes puzzle-ve dhe dhomave duhet të jenë të qarta.
6. Puzzle-t duhet të testohen për konfuzion dhe frustrim.
7. GUI mbetet dytësore ndaj funksionalitetit bazë.
8. Nuk shtohen funksionalitete të reja në këtë fazë.

---

# 13. Përfundimi

PBT 2 e zgjeron analizën e projektit nga përshkrimi i lojës në kuptimin e lojtarit që do ta përdorë atë.

Për **Escape Room: The Locked Lab**, lojtari duhet të jetë në gjendje të:

- kuptojë qëllimin;
- eksplorojë;
- mbledhë informacion;
- zgjidhë puzzle;
- përdorë objektet;
- kuptojë progresin;
- marrë feedback;
- arrijë te dera finale.

Tre Player Stories të përcaktuara në këtë dokument lidhen drejtpërdrejt me mekanikat e lojës:

1. **Puzzle Validation**
2. **Inventory dhe Dependencies**
3. **GameState dhe Room Dependencies**

Rreziqet kryesore të identifikuara janë:

- konfuzioni;
- frustrimi;
- ndjenja e padrejtësisë nga tentimet;
- mosvërejtja e objekteve të rëndësishme.

Për secilin rrezik është përcaktuar një masë zvogëlimi dhe një mënyrë testimi.

---

# 14. Evidenca e PBT 2

Për PBT 2 në repository ruhen:

- Player & Use Context Canvas;
- 3 Player Stories;
- lidhja e Player Stories me mekanikat;
- Minimal System Feedback;
- Experience Risks v0.1;
- masat e zvogëlimit/testimit;
- Project Charter v0.2;
- shënimi mbi transferimin e mësimit nga Serious/Educational Game.

Ndryshimet ruhen në repository dhe dokumentohen përmes commit-it të PBT 2.
