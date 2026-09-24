# Roblox devlog — TikTok + YouTube Shorts (plán série)

Cíl: každý den jedno krátké video v angličtině o tom, jak staví Roblox hru.
Formát je **9:16, 20–40 sekund**, mluvené anglicky + titulky na obrazovce.

---

## 1. Ten jeden nápad, na kterém série stojí

Celá série musí mít **jeden cíl, který se opakuje v každém videu**. Ne "dělám hru",
ale konkrétní meta, na kterou se lidi chtějí vracet:

> "Day 7 of making a Roblox game until it gets 1,000 players."

Vyber si jednu verzi a drž ji celou sérii (mění se jen číslo dne):
- `...until it hits the front page.`
- `...until it gets 1,000 players.`
- `...until it makes $100.`

Proč to funguje: číslo dne + jasný cíl = důvod tě sledovat dál. Bez cíle je to
jen náhodný klip ze Studia, který nikdo nedokouká.

**Napiš si tu větu sem a už ji neměň:**

    Day {N} of making a Roblox game until ______________________.

---

## 2. Anatomie jednoho shortu (30 s)

| Čas | Co se děje | Pravidlo |
|-----|-----------|----------|
| 0–2 s | **Hook** — věta s číslem dne + to nejlepší z videa ukázané hned | Žádné "hey guys, welcome back". Nikdy. |
| 2–6 s | Co je dnes cíl | Jedna věta, jedna featura |
| 6–22 s | Jak to vznikalo — zrychlený záběr, 3–5 střihů | Ukazuj **výsledek ve hře**, ne kód |
| 22–28 s | **Payoff** — funguje to / rozbilo se to | Fail je často lepší než úspěch |
| 28–30 s | CTA | "Day {N+1} tomorrow." |

Tři pravidla, která rozhodují:
1. **Jeden klip = jedna věc.** Jedna featura, jeden bug, jeden fail. Když do
   30 s nacpeš tři věci, nezapamatuje se žádná.
2. **Nikdy neukazuj kód déle než 1,5 s.** Kód je nuda, důsledek kódu je zábava.
   Místo řádků Lua ukaž postavičku, která letí do vzduchu.
3. **Titulky vždy.** Většina lidí to kouká bez zvuku, a u nerodilého přízvuku
   to platí dvojnásob. Titulky zachrání i špatně vyslovené slovo.

---

## 3. Kadence — reálná, ne teoretická

- **Nahrávej denně, ale krátce**: 10–15 minut záznamu ze Studia stačí. Zapni
  OBS vždycky, když jdeš dělat na hře. Nezapnuté OBS = žádné video.
- **Stříhej dávkově**: jednou za 2–3 dny si sedni a udělej 3 shorty. Denní
  stříhání vyhoří po týdnu.
- **Postuj 1× denně na obě platformy.** Na TikToku klidně 2× (dopoledne +
  večer). Pořadí dní musí být plynulé — Day 1, 2, 3... bez děr.
- Nahrávej **zvlášť na TikTok a zvlášť na Shorts** (stejný export, ale bez
  TikTok watermarku — v CapCutu exportuj rovnou, ne přes "save" z TikToku).

Když vynecháš den, nečísluj ho. Den = díl, ne kalendář.

---

## 4. Technika

**Záznam obrazovky (Roblox Studio):**
- OBS Studio, Display/Window Capture, 1080p, 60 fps.
- Nahrávej **na šířku (1920×1080)** a vertikál si vyřízni až ve střihu —
  zoomem na místo, kde se něco děje. Studio ve 9:16 se nedá používat.
- Mikrofon do **samostatné zvukové stopy** (OBS → Settings → Output →
  Advanced → Audio Track 2). Ušetří ti to život, když bude v záběru hudba.

**Komentář (voiceover):**
- Nemluv při stavění. Nahraj si VO **až nad hotový střih**, podle napsaného
  scénáře. Jako nerodilý mluvčí tím vyřadíš "eeeh", opravy a hledání slov.
- Mluv **pomaleji, než ti přijde přirozené**, a dělej pauzy mezi větami.
  Přízvuk nikoho nezajímá, nesrozumitelnost ano.
- Nahrávej na telefon do poznámkového bloku vedle pusy, ne z dálky. Levný
  klopák (i za 300 Kč) je slyšitelný skok v kvalitě.

**Střih:**
- CapCut (zdarma, desktop i mobil) → auto-titulky (Captions → Auto captions),
  pak ručně projdi chyby v anglických slovech.
- Rychlé střihy: každé 1,5–2,5 s změna záběru nebo zoomu.
- Hudba tiše pod hlasem (−18 až −20 dB). Na TikToku použij trending zvuk
  potichu na pozadí — pomáhá to dosahu.

---

## 5. Popisky a hashtagy

**TikTok caption** (krátce, s otázkou nebo cliffhangerem):
> Day 3 and the shop already broke 💀 what should I add next?
> #roblox #robloxdev #gamedev #robloxstudio #devlog

**YouTube Shorts title** (do titulku patří číslo dne a klíčové slovo):
> Day 3 of Making a Roblox Game #shorts #roblox #robloxdev

Nepoužívej 30 hashtagů. 4–6 relevantních.

---

## 6. Co reálně funguje v Roblox devlog short-formu

Poznámka: tohle je řazené podle toho, co se v short-formu obecně dokoukává —
ne podle toho, co je nejtěžší udělat.

1. **Fail / bug** — postava proletí mapou, NPC se zasekne, obchod dá hráči
   −5 mincí. Nahrávej všechny bugy, i když je za minutu opravíš.
2. **Before → after** — šedý blockout vs. hotová mapa, 1 s / 1 s.
3. **"This took me 4 hours"** — malý detail, nečekaně dlouhá práce.
4. **Reakce hráčů** — první cizí lidi ve hře, jejich chat ve záběru. Zlato.
5. **Timelapse stavění** s jednou pointou na konci.

Co nefunguje: vysvětlování kódu, dlouhé úvody, "dneska jsem nic nestihl",
obrazovka plná Studio UI bez zoomu.

---

## 7. Rutina na prvních 14 dní

Každý den ve stejném pořadí — trvá to ~90 minut včetně střihu:

1. Zapni OBS. Teprve pak Studio.
2. Udělej **jednu** věc na hře (viz rozpis níž).
3. Do `devlog/templates/daily-log.md` si zapiš: co jsem udělal, co se rozbilo,
   který moment je klipovatelný a v jakém čase záznamu.
4. Napiš 60–80 slov scénáře podle šablony `devlog/templates/short-script.md`.
5. Střih → VO → titulky → export.
6. Upload na TikTok + Shorts.

**Rozpis prvního týdne hry** (drž se ho, ať máš o čem točit):

| Den | Co stavíš | Co z toho je klip |
|-----|-----------|-------------------|
| 1 | Nápad + baseplate + první prototyp mechaniky | "Day 1, here's the idea" |
| 2 | Hlavní mechanika (to, co hráč dělá pořád) | První funkční verze |
| 3 | Blockout mapy | Before/after šedých kvádrů |
| 4 | UI + shop | UI bug nebo divné tlačítko |
| 5 | Ukládání dat (DataStore) — leaderboard, mince | "I almost deleted everyone's save" |
| 6 | Zvuky, efekty, polish | Before/after se zvukem |
| 7 | První test s reálnými hráči | Reakce a chat hráčů |

Hotové scénáře na dny 1–7 jsou v `devlog/scripts/week01.md` — stačí doplnit
jméno hry a mechaniku a přečíst.

---

## 8. Kdy to začne fungovat

Prvních 10–15 videí bude mít málo zhlédnutí. To je normální a není to signál,
že formát nefunguje — u short-formu se dosah láme skokově, když jedno video
trefí. Měř jediné dvě věci: **dokoukanost** (chceš nad 70 %) a **kolik lidí
přijde na další díl**. Počet sledujících ignoruj první tři týdny.

Neměň formát dřív než po 20 dílech. Nejčastější důvod, proč devlog série
umře, není špatný formát — je to změna formátu každé tři dny.
