# Ideja e lojës – Escape Room: The Locked Lab

**Lënda:** Zhvillimi i Lojërave  
**Ekipi:** Haka Gashi, Anduena Zogaj, Blearta Kodraliu, Gent Halabaku  
**Zhvillimi:** Unity, C#, lojë 3D për kompjuter

## Përshkrimi i idesë

Ideja jonë është një lojë escape room ku lojtari mbetet i mbyllur në një laborator. Sistemi i sigurisë i ka bllokuar dyert dhe, për të dalë, ai duhet të eksplorojë tri dhoma dhe të zgjidhë nga një puzzle në secilën. Gjatë eksplorimit do të gjejë shënime, kartela dhe kode që e ndihmojnë të hapë rrugën drejt daljes.

Loja bazohet në vëzhgim dhe logjikë. Lojtari duhet t’i lidhë informacionet që gjen me objektet dhe pajisjet në laborator. Për shembull, një shënim mbi tavolinë mund të shpjegojë si zgjidhet kodi i terminalit, ndërsa zgjidhja e tij mund të hapë një dollap me kartelën e derës tjetër.

Koncepti vazhdon idenë e paraqitur në [PBT1](../PBT1/README.md) dhe kërkesat për përvojën e lojtarit nga [PBT2](../PBT2/README.md). Në ato faza kishim paraparë Java dhe një paraqitje më të thjeshtë. Tani loja do të zhvillohet **në 3D me Unity dhe C#**, duke ruajtur tri dhomat, tri puzzle-t dhe mekanikat kryesore.

## Si do të luhet?

Për paraqitjen 3D propozojmë pamje nga personi i parë: lojtari e sheh laboratorin përmes kamerës së personazhit dhe ecën brenda tij. Kjo e bën eksplorimin pjesë të lojës, sepse duhet t’u afrohet tavolinave, terminaleve dhe dyerve për t’i kontrolluar.

Kontrollet e propozuara janë:

| Kontrolli | Veprimi |
|---|---|
| W, A, S, D | Lëvizja nëpër laborator |
| Miu | Shikimi përreth |
| E | Leximi i një shënimi, marrja e një objekti ose përdorimi i një pajisjeje |
| I | Hapja dhe mbyllja e inventory-t |
| Esc | Mbyllja e panelit të hapur ose hapja e menusë së pauzës |

Kur lojtari afrohet dhe shikon një objekt që mund të përdoret, do të shfaqet një udhëzim i shkurtër, si “Shtyp E për të lexuar”. Përgjigjet e puzzle-ve do të jepen në një panel, ndërsa levat do të aktivizohen drejtpërdrejt në ambientin 3D.

Rrjedha kryesore është:

**Eksploro → Gjej informacion → Zgjidh puzzle → Merr objekt ose kod → Hap derën → Vazhdo.**

Loja do të jetë individuale dhe e përshtatshme për lojtarë fillestarë deri mesatarë. Nuk kërkohen njohuri programuese, sepse shpjegimet e nevojshme do të gjenden brenda lojës.

## Dhomat dhe puzzle-t

### Dhoma 1 – Hyrja në laborator

Kjo dhomë e njeh lojtarin me lëvizjen dhe përdorimin e objekteve. Do të ketë një tavolinë me shënim, një terminal, një dollap dhe derën për dhomën tjetër.

Shënimi paraqet vargun `2, 4, 8, 16, ?` dhe tregon se çdo numër dyfishohet. Lojtari fut përgjigjen `32` në terminal. Pas zgjidhjes hapet dollapi, ku mund të marrë një kartelë. Me kartelën në inventory, ai mund të përdorë lexuesin pranë derës dhe të vazhdojë.

### Dhoma 2 – Dhoma e kontrollit

Në dhomën e dytë do të ketë pajisje laboratorike, një ekran me kodin binar `1011` dhe një tabelë shpjeguese në mur. Tabela do të tregojë vlerat `8, 4, 2, 1`, që lojtari të kuptojë si bëhet llogaritja edhe nëse nuk e njeh sistemin binar.

Përgjigjja është `11`, nga mbledhja `8 + 2 + 1`. Pasi jepet përgjigjja e saktë, zhbllokohet dera tjetër dhe në inventory shtohet një shënim me kodin `731`. Ky kod duhet të ruhet për daljen finale.

### Dhoma 3 – Dalja

Dhoma e fundit do të përmbajë tri leva, një shënim dhe derën finale. Shënimi thotë: “E kuqja para së gjelbrës dhe e gjelbra para së kaltrës”. Lojtari duhet t’i aktivizojë levat sipas këtij rendi. Ato do të kenë edhe etiketa me emra, që puzzle të mos mbështetet vetëm te ngjyrat.

Pas renditjes së saktë aktivizohet tastiera e derës. Lojtari fut kodin `731` nga dhoma e dytë dhe hap daljen. Përdorimi i kodit përfundon rrjedhën e lojës; nuk është një puzzle shtesë.

Këta janë shembujt e propozuar për puzzle-t dhe mund t’i përshtatim gjatë testimit.

## Rregullat kryesore

Për versionin e parë propozojmë pesë tentime të përbashkëta, pa timer. Një përgjigje e gabuar heq një tentim. Te levat, një renditje e plotë e gabuar llogaritet si një tentim dhe levat rivendosen për provën tjetër. Fusha bosh ose shkrimi në format të gabuar jep një udhëzim pa penalizim.

Dyert hapen vetëm kur plotësohen kushtet e tyre. Objektet e mbledhura ruhen në inventory dhe nuk humben gjatë kalimit mes dhomave. Lojtari mund të kthehet në dhomat e hapura për të kontrolluar sërish shënimet.

Lojtari fiton kur zgjidh të tri puzzle-t dhe hap derën finale me kodin e saktë. Humb kur i harxhon tentimet. Në të dyja rastet do të ketë mundësi ta rifillojë lojën nga fillimi.

## Pamja dhe versioni i parë

Laboratori do të ketë mure, tavolina, dollapë, terminale dhe ndriçim të thjeshtë. Synojmë një ambient të besueshëm, ku objektet e rëndësishme dallohen dhe shënimet lexohen lehtë. Do të përdorim modele të thjeshta ose modele të gatshme që lejohet t’i përdorim.

Versioni i parë do të përmbajë tri dhomat 3D, lëvizjen, ndërveprimin me objektet, tri puzzle-t, inventory-n, tentimet dhe menutë. Siç kemi përcaktuar në PBT2, do të japim mesazhe të qarta për përgjigjet, objektet e marra dhe kushtet e dyerve.

Nuk planifikojmë multiplayer, luftim apo ambient të madh të hapur. Fillimisht do të përfundojmë të gjithë rrjedhën e lojës; pastaj do të përmirësojmë modelet, ndriçimin dhe tingujt.

Hapat e realizimit janë në [Planin e zhvillimit në Unity](PLANI_ZHVILLIMIT_UNITY.md).
