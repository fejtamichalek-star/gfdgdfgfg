# OBS + Roblox Studio — nastavení, aby to nelagovalo

Cíl: nahrávat Studio bez toho, aby Studio sekalo nebo aby OBS zahazoval framy.
Na short-formu (9:16, 25–35 s) nepotřebuješ maximální kvalitu — potřebuješ
**plynulý záznam**, protože sekání je ve výsledném klipu vidět víc než rozlišení.

---

## 1. Jediné pravidlo, které rozhoduje: hardwarový enkodér

OBS musí kódovat video **na grafice**, ne na procesoru. Když necháš výchozí
softwarový `x264`, sebere ti to procesor, který zároveň běží Roblox Studio —
a to je 90 % případů "lagů" při nahrávání.

**OBS → Settings → Output → Output Mode: Simple**
- **Recording Quality:** `High Quality, Medium File Size`
- **Recording Format:** `MP4` (nebo `MKV`, když se bojíš pádu PC — MKV se
  nepoškodí, jde pak "Remux" na MP4)
- **Encoder:** vyber podle své grafiky, v tomto pořadí:

| Grafika | Vyber v OBS |
|---------|-------------|
| NVIDIA (GTX 900 a novější, RTX) | `NVIDIA NVENC H.264` |
| AMD (RX 400 a novější) | `AMD HW H.264 (AVC)` |
| Intel (UHD 620, Iris Xe, Arc) | `QuickSync H.264` |
| Nic z toho v seznamu není | `Software (x264)` → viz sekce 5 |

Když je v seznamu hardwarová volba, **vždycky** ji použij.

---

## 2. Rozlišení a FPS

**OBS → Settings → Video**
- Base (Canvas) Resolution: `1920×1080`
- Output (Scaled) Resolution: `1920×1080`
- **FPS: `30`**

Ano, 30. V plánu mám 60 fps jako ideál, ale pro devlog ze Studia je 30 fps
úplně dost — stavění, UI a menu nejsou střílečka. Šetří to procesor, grafiku
i místo na disku. Na 60 jdi až když ti test v sekci 4 vyjde čistě a chceš
ukazovat rychlý pohyb (parkour, závody).

Nahrávej **na šířku**. Vertikál 9:16 si vyřízneš až ve střihu zoomem na místo,
kde se něco děje — Studio se v 9:16 nedá používat.

---

## 3. Zvuk do samostatné stopy

**OBS → Settings → Output → Recording → Audio Track: zaškrtni `1` a `2`**
- Stopa 1 = zvuk hry
- Stopa 2 = mikrofon (v mixeru: Mic → ozubené kolo → Advanced Audio
  Properties → Tracks → jen `2`)

Proč: když bude ve hře hudba nebo zvuk, můžeš hlas zesílit zvlášť. Bez toho
jsi ztracený.

---

## 4. Co udělat na straně Roblox Studia

1. **Zavři prohlížeč.** Vážně. Chrome s deseti kartami je nejčastější skrytý
   důvod, proč nahrávání seká — sebere 2–4 GB RAM a kus procesoru.
2. **File → Studio Settings → Rendering → Quality Level:** přepni z `Auto`
   na pevnou střední hodnotu. Auto se během nahrávání přepíná a v záběru je
   vidět, jak se grafika skokem mění.
3. **Nahrávej na SSD.** Když máš projekt i záznam na jednom pomalém HDD,
   budou padat framy. Cesta k záznamu: OBS → Settings → Output → Recording Path.
4. **Zapni OBS dřív než Studio**, ne naopak — capture pak spolehlivěji chytne
   okno.
5. **Capture:** `Window Capture` na okno Studia (ne Display Capture, ať ti do
   záběru nespadne Discord nebo notifikace).

---

## 5. Když je PC slabý (nebo v OBS není hardwarový enkodér)

Postupuj odshora, dokud test v sekci 6 neproběhne čistě:

1. FPS z 30 na `30` (ne níž — pod 30 to vypadá trhaně) a rozlišení na
   `1600×900`. Pro vertikální výřez je to pořád dost.
2. V Simple Output přepni Recording Quality na `Indistinguishable` → ne,
   naopak: dej `High Quality, Medium File Size`. Vyšší kvalita = víc práce.
3. Zkus **Windows Game Bar** místo OBS: `Win+Alt+R` nahrává aktivní okno a je
   výrazně lehčí než OBS. Nevýhoda: žádné oddělené zvukové stopy a méně
   kontroly. Na start je to plně použitelné.
4. Nahrávej **bez mikrofonu** a hlas dodej až ve střihu jako voiceover (což
   podle plánu děláš tak jako tak) — ubere to jednu vrstvu práce za běhu.
5. Nahrávej **krátce**. 10 minut záznamu na jeden klip stačí. Slabý PC zvládne
   10 minut čistě, i když by po hodině začal zahazovat framy.

---

## 6. Test na dvě minuty — tady zjistíš, jestli to utáhne

Nehádej to z parametrů, změř to:

1. V OBS: **Docks → Stats** (zapne panel se statistikami).
2. Zapni nahrávání, běž do Studia a **dvě minuty normálně pracuj** — postav
   pár částí, dej Play, proběhni se po mapě, zastav.
3. Stopni nahrávání a v panelu Stats se podívej na dvě čísla:

| Údaj | Co chceš vidět |
|------|----------------|
| `Frames missed due to rendering lag` | 0, max jednotky |
| `Skipped frames due to encoding lag` | 0, max jednotky |

Když jsou obě čísla pod ~0,5 %, tvůj PC to utáhne a dál to neřeš.
Když jsou vysoká, jdi na sekci 5 a uber o jeden bod.

4. **Pusť si ten dvouminutový soubor.** Finální kontrola je oko, ne číslo —
   pokud je záznam plynulý a zvuk nedrhne, je hotovo.

Navíc si během testu otevři **Správce úloh (Ctrl+Shift+Esc) → Výkon**:
- CPU dlouhodobě na 100 % → chybí hardwarový enkodér, nebo je zapnutý x264
- RAM na 100 % → zavři prohlížeč; pod 8 GB to bude vždycky těsné
- Disk na 100 % → nahráváš na pomalý HDD

---

## 7. Orientační hranice

Tohle je hrubé vodítko, ne záruka — rozhoduje test v sekci 6:

| | Bez problémů | Těsné, ale jde to | Očekávej sekání |
|---|---|---|---|
| **CPU** | 6 jader, 2019+ | 4 jádra, 2017+ | 2 jádra, Pentium/Celeron |
| **RAM** | 16 GB | 8 GB (se zavřeným prohlížečem) | 4 GB |
| **GPU** | cokoli s NVENC / AMF / QuickSync | Intel UHD 620+ | starší iGPU bez enkodéru |
| **Disk** | SSD | SSD | HDD |

Roblox Studio samo o sobě není žrout — bere ~2–3 GB RAM u malé mapy a při
playtestu tlačí hlavně na jedno jádro. OBS s hardwarovým enkodérem přidá
~0,5 GB RAM a pár procent výkonu. Problém skoro vždy vzniká jednou ze tří
věcí: **softwarový enkodér, otevřený prohlížeč, nebo 4 GB RAM.**
