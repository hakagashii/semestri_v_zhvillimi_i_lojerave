# Plani i zhvillimit në Unity

**Projekti:** Escape Room: The Locked Lab  
**Teknologjia:** Unity dhe C#  
**Paraqitja:** Ambient 3D me pamje nga personi i parë

Ky plan shpjegon si do ta realizojmë [idenë e lojës](README.md). Do të fillojmë me një dhomë funksionale dhe pastaj do të shtojmë pjesët e tjera. Në këtë mënyrë do të provojmë lëvizjen, ndërveprimin dhe një puzzle përpara se të ndërtojmë të gjithë laboratorin.

## 1. Përgatitja e projektit

Do të krijojmë një projekt 3D në Unity dhe do të zgjedhim një version të përbashkët për të gjithë ekipin. Projektin do ta ruajmë në GitHub, që secili të mund të punojë në pjesën e vet dhe ndryshimet të bashkohen rregullisht.

Skedarët do t’i ndajmë në dosje për skenat, skriptet C#, modelet, materialet, tingujt dhe prefab-et. Prefab-et janë objekte të përgatitura që mund t’i përdorim disa herë, si një derë, një shënim ose një terminal. Për modelet dhe tingujt e marrë nga burime të jashtme do të ruajmë burimin dhe licencën.

## 2. Ndërtimi i laboratorit 3D

Në fillim do t’i ndërtojmë dhomat me forma të thjeshta, si kube për muret, dyshemenë dhe tavolinat. Kjo na lejon të kontrollojmë madhësinë e dhomave, gjerësinë e dyerve dhe vendosjen e objekteve përpara se të merremi me pamjen përfundimtare.

Tri dhomat do të lidhen me dyer në një skenë të vetme. Lojtari do të ecë fizikisht nga njëra dhomë në tjetrën pasi të hapet dera. Muret, dyshemeja dhe dyert e mbyllura do të kenë collider-a, që pengojnë kalimin përmes tyre.

Më pas do të shtojmë modelet laboratorike, materialet dhe ndriçimin. Dhomat mund të kenë pamje pak të ndryshme, por objektet kryesore duhet të mbeten të dukshme. Tavolinat dhe pajisjet nuk duhet të bllokojnë rrugën ose t’i bëjnë objektet e nevojshme të paarritshme.

## 3. Lëvizja dhe kamera

Për lojtarin do të përdorim një objekt me `CharacterController` dhe një kamerë në lartësinë e syve. Do të programojmë ecjen me W, A, S, D, shikimin me miun dhe gravitetin për ta mbajtur lojtarin në dysheme. `CharacterController` do të na ndihmojë ta kufizojmë lëvizjen sipas përplasjeve me ambientin. [Dokumentacioni i Unity](https://docs.unity.com/en-us/engine/6000.0/manual/physics-section/physics-overview/character-control-section).

Për versionin e parë mjafton ecja normale. Nuk kemi nevojë të shtojmë kërcim apo vrapim, sepse sfida kryesore është eksplorimi dhe zgjidhja e puzzle-ve.

Kur hapet një panel për të shkruar përgjigje, inventory ose menuja, do të ndalet lëvizja dhe rrotullimi i kamerës dhe do të shfaqet kursori. Pas mbylljes së panelit, kontrolli do t’i kthehet lojtarit. Kjo shmang lëvizjen e personazhit gjatë përdorimit të ndërfaqes.

## 4. Ndërveprimi me objektet

Do të përdorim një `raycast`, pra një kontroll në drejtimin ku shikon kamera, për të dalluar objektin përballë lojtarit. Ai do të kontrollojë goditjen e parë në një distancë të shkurtër, për shembull dy metra. Në këtë mënyrë lojtari duhet t’i afrohet objektit dhe nuk mund ta përdorë përmes murit. [Dokumentacioni i Unity për Raycast](https://docs.unity.com/en-us/engine/6000.5/script-reference/unityengine/physics/raycast).

Kur objekti mund të përdoret, do të shfaqet një tekst si “E – Merr kartelën” ose “E – Përdor terminalin”. Shtypja e E do të kryejë veprimin përkatës:

- Shënimi hap tekstin për lexim.
- Kartela shtohet në inventory dhe largohet nga vendi ku ishte.
- Terminali hap panelin e puzzle-it.
- Leva ndryshon pozicion dhe regjistron rendin e aktivizimit.
- Dera kontrollon kushtet dhe hapet ose jep mesazhin për kushtin që mungon.

## 5. Logjika e lojës dhe puzzle-t

Do të kemi një vend qendror ku ruhet progresi: dhoma aktuale, puzzle-t e zgjidhura, objektet e mbledhura, tentimet dhe gjendja e lojës. Dyert dhe ndërfaqja do t’i përdorin këto të dhëna për të vendosur çfarë lejohet dhe çfarë duhet të shfaqet.

Pjesët kryesore të kodit do të ndahen kështu:

| Skripti                 | Përgjegjësia                                 |
| ----------------------- | -------------------------------------------- |
| `PlayerController`      | Ecja, graviteti dhe shikimi me kamerë        |
| `InteractionController` | Dallimi i objektit përballë dhe veprimi me E |
| `GameState`             | Të dhënat e progresit dhe tentimet           |
| `GameManager`           | Nisja, fitorja, humbja dhe rifillimi         |
| `PuzzleController`      | Kontrolli i përgjigjeve dhe rendit të levave |
| `InventoryController`   | Mbledhja dhe shfaqja e objekteve             |
| `DoorController`        | Kushtet për hapjen e secilës derë            |
| `UIController`          | Panelet, mesazhet dhe treguesit në ekran     |

Për shembull, pas zgjidhjes së puzzle-it të parë do të mundësohet hapja e dollapit. Lojtari duhet ta marrë kartelën prej tij. Vetëm atëherë dera e parë mund të hapet. Kështu puzzle, objekti dhe dera lidhen në një rrjedhë të kuptueshme.

Puzzle-t do të kontrollojnë nëse përgjigjja është e saktë dhe nëse janë përfunduar më herët. Një puzzle i zgjidhur nuk do të japë shpërblim të dytë. Në puzzle-in e levave, kontrolli bëhet pasi aktivizohen të tri levat; një renditje e gabuar heq një tentim dhe lejon një provë të re.

Kur tentimet arrijnë në zero, loja kalon në humbje. Kur zgjidhen të tri puzzle-t dhe hapet dalja me kodin e saktë, kalon në fitore. Pas përfundimit ndalen lëvizja dhe ndërveprimet. Rifillimi do të rikthejë edhe pozicionin e lojtarit, dyert, objektet dhe levat në gjendjen fillestare.

## 6. Ndërfaqja dhe feedback-u

Në ekran do të shfaqen tentimet e mbetura, dhoma aktuale dhe progresi, për shembull `1/3 puzzle të zgjidhura`. Në qendër do të ketë një shenjë të vogël për të treguar drejtimin ku shikon lojtari. Inventory do të hapet me I dhe do të tregojë objektet me emrin dhe përshkrimin e tyre.

Mesazhet do të jenë të shkurtra dhe konkrete. Për shembull: “Të mbeten 4 tentime”, “Kartela u shtua në inventory” ose “Duhet ta zgjidhësh panelin e levave për të aktivizuar tastierën”. Këto zbatojnë kërkesat e PBT2 për feedback dhe progres të qartë.

Do të shtojmë menunë fillestare, udhëzimet e kontrolleve, pauzën dhe ekranin e fitores ose humbjes. Shënimet do të mund të lexohen përsëri, që lojtari të mos ketë nevojë t’i mbajë mend të gjitha informacionet.

## 7. Organizimi dhe koha e punës

Ndarja e propozuar e punës është:

| Anëtari              | Pjesa kryesore                                                                                                                |
| -------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| **Haka Gashi**       | Menaxhimi i gjendjes së lojës (GameState), tentimet, kushtet e fitores/humbjes, rifillimi dhe logjika e hapjes së dyerve.     |
| **Anduena Zogaj**    | Implementimi i tri puzzle-ve, kontrollimi i përgjigjeve, renditja e levave dhe sistemi i shënimeve (hints).                   |
| **Blearta Kodraliu** | Krijimi i menyve, HUD-it, sistemit të inventory-t (mbledhja dhe përdorimi i objekteve), mesazhet dhe feedback-u për lojtarin. |
| **Gent Halabaku**    | Krijimi i ambientit 3D, organizimi i dhomave, implementimi i lëvizjes së lojtarit dhe ndërveprimi me objektet.                |

Pjesa 3D do të kërkojë punë edhe gjatë integrimit, prandaj anëtarët do ta ndihmojnë njëri-tjetrin sipas nevojës. Të gjithë do të marrim pjesë në testim.

Si plan fillestar propozojmë katër javë, që do t’i përshtatim me afatin e lëndës:

| Java   | Puna e planifikuar                                         | Çfarë duhet të funksionojë në fund                                        |
| ------ | ---------------------------------------------------------- | ------------------------------------------------------------------------- |
| Java 1 | Projekti 3D, dhoma e parë, lëvizja, kamera dhe ndërveprimi | Lojtari ecën, lexon një shënim, zgjidh puzzle-in e parë dhe merr kartelën |
| Java 2 | Dhoma 2 dhe 3, inventory, dyert, levat dhe tentimet        | Mund të luhet e gjithë rrjedha deri në fitore ose humbje                  |
| Java 3 | Menutë, feedback-u, rifillimi, modelet dhe ndriçimi        | Loja ka udhëzime të qarta dhe pamje të njëtrajtshme                       |
| Java 4 | Testimi, korrigjimet dhe build-i përfundimtar              | Loja punon në kompjuterin e demonstrimit dhe materialet janë gati         |

## 8. Testimi dhe dorëzimi

Testimin do ta bëjmë gjatë gjithë zhvillimit. Përveç përgjigjeve të puzzle-ve, në versionin 3D duhet të kontrollojmë edhe lëvizjen dhe vendosjen e objekteve.

Do të provojmë nëse lojtari kalon përmes mureve, ngec pranë mobilieve ose arrin të përdorë objekte nga larg dhe përmes dyerve të mbyllura. Do të kontrollojmë edhe që panelet e ndalin kamerën dhe kontrolli rikthehet siç duhet kur mbyllen.

Për logjikën do të kontrollojmë tentimet, kushtet e dyerve, ruajtjen e inventory-t gjatë kthimit në dhomat e mëparshme dhe rifillimin e plotë. Do të provojmë si rrugën e fitores, ashtu edhe humbjen me përgjigje të gabuara.

Disa persona që nuk i njohin zgjidhjet do ta luajnë pa udhëzime nga ne. Do të vërejmë nëse i gjejnë objektet, i kuptojnë shënimet dhe e dinë hapin e ardhshëm. Nëse ngecin nga udhëzimet e paqarta, do t’i përmirësojmë ato.

Në fund do të përgatisim projektin Unity, një build për kompjuter, udhëzimet e nisjes dhe disa pamje të lojës. Build-in do ta provojmë edhe jashtë Unity Editor, në kompjuterin ku do të demonstrohet.

Nëse koha nuk mjafton, do të thjeshtojmë modelet, efektet dhe tingujt. Përparësi do të kenë ambienti 3D funksional, tri puzzle-t dhe mundësia për ta përfunduar lojën pa gabime.
