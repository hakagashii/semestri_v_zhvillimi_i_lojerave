# PROJECT CHARTER v0.2

## Escape Room: The Locked Lab

**Lënda:** Zhvillimi i Lojërave

**PBT:** PBT 2 – Java 3

**Faza:** Faza I – Zbulimi dhe Përcaktimi i Përdoruesit

---

# 1. Informacioni i projektit

## Emri i projektit

**Escape Room: The Locked Lab**

## Ekipi

- Haka Gashi
- Anduena Zogaj
- Blearta Kodraliu
- Gent Halabaku

## Versioni

**v0.2**

Ky version është përditësim i Project Charter v0.1 në kuadër të PBT 2 – Java 3.

---

# 2. Përshkrimi i projektit

**Escape Room: The Locked Lab** është një lojë puzzle/escape room ku lojtari gjendet i mbyllur në një laborator dhe duhet të zgjidhë puzzle për të vazhduar nëpër dhoma dhe për të arritur te dalja finale.

Loja bazohet në:

- eksplorim;
- zgjidhje problemesh;
- logjikë;
- puzzle;
- inventory;
- dependencies;
- GameState;
- menaxhim të progresit;
- kushtet WIN / LOSE.

Core mechanic është:

**Eksploro → Gjej informacion → Zgjidh puzzle → Merr kod/objekt → Hape pjesë të re → Vazhdo**

---

# 3. Qëllimi

Qëllimi i lojës është që lojtari të arrijë te dera finale duke zgjidhur puzzle-t dhe duke përdorur informacionet dhe objektet që mbledh gjatë lojës.

Projekti synon të krijojë një përvojë ku lojtari duhet të mendojë, të analizojë dhe të marrë vendime për të avancuar.

---

# 4. Scope i MVP-së

MVP-ja përmban:

- 3 dhoma;
- 3 puzzle;
- inventory;
- tentime ose timer;
- dependencies mes pjesëve të lojës;
- derë finale;
- GameState;
- WIN / LOSE;
- logjikën bazë të lojës;
- console ose GUI minimal nëse logjika përfundon me sukses.

---

# 5. Lojtari i synuar

Lojtari i synuar është një përdorues me nivel fillestar deri mesatar në lojërat puzzle.

Nuk kërkohet njohuri programuese.

Lojtari duhet të jetë në gjendje të:

- analizojë informacionin;
- zgjidhë probleme;
- lidhë të dhëna;
- përdorë objekte;
- ndjekë progresin;
- kuptojë feedback-un e sistemit.

---

# 6. Motivimi i lojtarit

Motivimet kryesore janë:

- sfida;
- zgjidhja e problemeve;
- eksplorimi;
- zbulimi;
- progresi;
- arritja e daljes.

Lojtari duhet të ketë një qëllim të qartë dhe të kuptueshëm:

**Të dalë nga laboratori duke zgjidhur puzzle-t dhe duke hapur derën finale.**

---

# 7. Player Stories

## Story 1

**Si lojtar fillestar, dua të marr feedback të qartë kur jap një përgjigje të saktë ose të gabuar, në mënyrë që ta kuptoj nëse jam duke ndjekur rrugën e duhur.**

### Mekanika

**Puzzle Validation + GameState**

### Kërkesa

Sistemi kontrollon inputin dhe jep feedback për rezultatet.

---

## Story 2

**Si lojtar, dua të kuptoj se cilat objekte në inventory mund të përdoren për të zhbllokuar pjesët e laboratorit, në mënyrë që të mund të vazhdoj progresin në lojë.**

### Mekanika

**Inventory + Dependencies + Door Unlocking**

### Kërkesa

Sistemi ruan objektet dhe kontrollon nëse ato plotësojnë kushtet për progres.

---

## Story 3

**Si lojtar, dua të kuptoj se cilat dhoma dhe puzzle janë përfunduar, në mënyrë që të di çfarë më duhet të bëj për të arritur te dera finale.**

### Mekanika

**GameState + Room Dependencies + Final Door**

### Kërkesa

GameState ruan progresin dhe sistemi kontrollon kushtet për të kaluar në pjesët e ardhshme.

---

# 8. Player & Use Context

| Elementi | Vendimi |
|---|---|
| Lojtari | Fillestar deri mesatar në puzzle |
| Motivimi | Sfidë, problem solving, eksplorim dhe progres |
| Platforma | Java |
| Konteksti | Lojë individuale |
| Kohëzgjatja | Sesion relativisht i shkurtër |
| Qëllimi | Dalja nga laboratori |
| Veprimet | Eksplorim, puzzle, inventory, kode dhe dyer |
| Feedback | I qartë dhe i menjëhershëm |
| Rreziku kryesor | Konfuzioni |
| Rezultati | Arritja në WIN |

---

# 9. Core Gameplay Loop

Gameplay loop është:

```text
Eksploro
   ↓
Gjej informacion
   ↓
Zgjidh puzzle
   ↓
Merr kod/objekt
   ↓
Hape pjesë të re
   ↓
Vazhdo