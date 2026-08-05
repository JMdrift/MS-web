Moje Stavba — web platforma
============================

Obsah (14 stránek):
- index.html            → landing
- zalozit-profil.html   → registrace
- dashboard.html        → účtový přehled projektů
- profil.html           → Nastavení / Profil
- nastenka.html         → nástěnka projektu
- etapy.html            → přehled etap: rozbalitelné položky s náklady/počty, "+ Přidat etapu"
- nova-etapa.html       → výběr z přednastavených etap nebo založení vlastní
- etapa-detail.html     → detail etapy: statistiky + 6 karet (Fotografie, Deník, Výdaje, Nabídky, Dokumenty, Důležité)
- finance.html          → výdaje/příjmy
- denik.html            → stavební deník
- galerie.html          → mřížka fotek (BEZ reálných obrázků — jen šedé
                           placeholder dlaždice, ať zip zůstal malý)
- kalendar.html         → měsíční kalendář + nejbližší události
- dokumenty.html        → dokumenty (složky)
- sdileni.html          → kdo je na projektu
- poptavky.html         → poptávky k projektu
- privacy.html

OPRAVA (4. 8. 2026): Na mobilu se stránka horizontálně roztahovala
mimo obrazovku kvůli chybějícímu min-width:0 na hlavním sloupci — text
byl uřezaný po stranách. Opraveno ve všech stránkách + přidán
overflow-x:hidden jako pojistka.

NAVNIGACE — dvě vrstvy (beze změny oproti minule):
1. Horní lišta — stejná všude: logo, Dashboard, Marketplace, avatar
2. Kontextové menu — uvnitř projektu 9 položek (Nástěnka, Etapy,
   Finance, Deník, Galerie, Kalendář, Dokumenty, Sdílení, Poptávky),
   v Nastavení jen Profil (ostatní "brzy")

CO JEŠTĚ CHYBÍ Z APPKY (screeny v zipu appky, ale zatím nepřevedené
na web — je jich hodně, radši je vypíšu, ať víme, co zbývá):
- screen-newStage.js       → založení nové etapy / "ZAHÁJIT STAVBU"
- screen-stageDetail.js    → detail jedné etapy (fotky, poznámky, výdaje)
- screen-stageExpenses.js  → výdaje vázané na konkrétní etapu
- screen-stagesWheel.js    → kruhový výběr etap (vizuální prvek appky)
- screen-transactions.js   → detail jednotlivé finanční položky
- screen-diaryExport.js    → export deníku do PDF
- screen-onboarding.js     → uvítací tour pro nové uživatele
- screen-premiumLogin.js   → login obrazovka (na webu = zalozit-profil.html,
                             ale appka má i samostatný "jen přihlásit")
- screen-settings.js       → nastavení appky (appka má jiné než web)
- screen-appLock.js        → zámek appky (nedává na webu smysl 1:1)
- screen-legal.js          → právní texty (na webu = privacy.html)
- screen-important.js, screen-misc.js → nevím jistě bez detailního čtení,
  co přesně dělají — mrknu až budeme pokračovat

Doporučuju příště: screen-stageDetail.js (detail etapy — z Etapy.html
se tam dá prokliknout) a screen-newStage.js (bez něj nejde založit
první etapu, podobně jako bez zalozit-profil nešlo založit účet).

Jak nasadit:
1. Nahraj VŠECHNY soubory (i icons/) do GitHub repa pohromadě.
2. Zapni GitHub Pages ve Settings → Pages.

=== ŘEMESLNÍK (první role mimo Stavebníka) ===
- reme-dashboard.html   → jeho Dashboard: aktivní zakázky, poptávky v okolí, moje nabídky
- reme-marketplace.html → přehled poptávek s filtrem podle oboru, "Poslat nabídku" (modal)
- reme-nabidky.html     → moje nabídky se stavem (čeká/přijato/odmítnuto)
- reme-profil.html      → profil s profesními údaji (obor, kde působí) místo kraje/města

Vzorová persona: Tomáš Krejčí — navazuje na nabídku, kterou jsme viděli
v poptavka-detail.html u Sádrokartonářských prací pro Javůrkovi.

reme-dashboard/reme-nabidky/reme-galerie/reme-kalendar mají teď společné
kontextové menu (Přehled/Moje nabídky/Galerie/Kalendář) - sidebar na
desktopu, taby na mobilu, stejný vzor jako u projektových stránek
Stavebníka.
v poptavka-detail.html u Sádrokartonářských prací pro Javůrkovi.

Barva: cihlová #c1553f (přebarvuje --orange v :root, zbytek komponent
se přizpůsobí automaticky — stejný trik jako v registraci).

Registrace teď rozlišuje cíl podle role: Řemeslník → reme-dashboard.html,
ostatní role zatím → dashboard.html (jejich vlastní dashboardy ještě
nejsou postavené).

CHYBÍ pro Řemeslníka: omezený pohled uvnitř projektu (když klikne na
"Javůrkovi — Sádrokartonářské práce", měl by vidět jen to, na co má
práva — zatím vede na poptavka-detail.html, což je ok jako dočasné
řešení, ale reálně by měl mít vlastní omezenou nástěnku projektu).

--- aktualizace: Řemeslník dostal druhou úroveň menu ---
- reme-rozjednane.html      → rozjednané zakázky (kontextové menu)
- reme-zakazka-detail.html → detail rozjednané zakázky + konverzace se stavebníkem
- reme-hotove.html          → hotové zakázky
- reme-hotova-detail.html  → detail hotové zakázky: poznámka, fotky, dokumenty (editovatelné)
- reme-oslovene.html        → oslovené poptávky (nahrazuje reme-nabidky.html)
- reme-firemni-profil.html → VEŘEJNÝ firemní profil pro Marketplace (kontakt, zaměření,
  ukázky práce, text o firmě) — odlišné od reme-profil.html, který je jen soukromé nastavení

Dashboard řemeslníka teď má i "Poslední aktivita".


=== NABÍDKOVÝ MANAGEMENT + FIREMNÍ PROFIL (Řemeslník) ===
- reme-oslovene.html      → poptávky, na které jsem poslal nabídku, čekám na odpověď
- reme-rozjednane.html    → přijaté nabídky, aktivně se řeší (má vlastní detail)
- reme-hotove.html        → dokončené zakázky (má vlastní detail)
- reme-zakazka-detail.html    → detail rozjednané zakázky
- reme-hotova-detail.html     → detail dokončené zakázky
- reme-firemni-profil.html    → veřejný profil viditelný v Marketplace (název,
  kontakt, zaměření, o mně/o firmě, ukázky práce) — dostupný z reme-profil.html

"Moje nabídky" v hlavním menu Řemeslníka vede na reme-oslovene.html, což je
vstup do tříbarevného tabu Oslovené/Rozjednané/Hotové (má svůj vlastní
kontextový pruh, oddělený od hlavního Přehled/Galerie/Kalendář menu — obdoba
toho, jak poptavka-detail.html funguje mimo hlavní projektové menu Stavebníka).

Pozn.: reme-nabidky.html je starší jednodušší verze téhož, teď nikde
neodkazovaná — necháno v build složce, nemazáno (viz poznámka níže).


=== DODAVATEL MATERIÁLU (poslední role) ===
Katalog zrušen (nedával smysl vs. reálné potřebě). Místo něj 4fázový
systém zakázek, obdoba Řemeslníkova Oslovené/Rozjednané/Hotové, jen o
krok jemnější:
- dodavatel-poslane.html        → nabídky, které jsem poslal, čekám
- dodavatel-prijate.html        → nové poptávky, na které mohu reagovat
- dodavatel-rozpracovane.html   → potvrzené objednávky, připravují se
  (+ dodavatel-zakazka-detail.html)
- dodavatel-ukoncene.html       → dodáno, vyfakturováno
  (+ dodavatel-hotova-detail.html)
- dodavatel-dashboard.html      → přehled + rychlé dlaždice na všechny 4 fáze
- dodavatel-profil.html         → firemní profil s IČO, adresou skladu,
  oblastí působnosti (Celá ČR / víc krajů), Premium gate

Barva: fialová #9a7fd1. Vzorová persona: King s.r.o.
Kalendář vynechán — termíny dodání dávají větší smysl u konkrétní objednávky.
Pozn.: dodavatel-katalog.html a dodavatel-oslovene.html (starší verze)
zůstaly v build složce nesmazané, ale nikde neodkazované.

=== KONTAKTY (nová položka, napříč všemi rolemi) ===
"Kontakty" jsou teď v horní liště vedle Marketplace u VŠECH rolí —
kontakty.html (Stavebník), reme-kontakty.html, dozor-kontakty.html,
projektant-kontakty.html, dodavatel-kontakty.html. Každá role vidí lidi,
se kterými na platformě spolupracovala, s barevným štítkem role a
vyhledáváním. Zatím statický seznam (bez skutečného "přidat do kontaktů"
tlačítka u ostatních obrazovek) — to je další krok.

=== VŠECH 5 ROLÍ HOTOVO (na hrubo) ===
Stavebník, Řemeslník, Stavební dozor, Projektant, Dodavatel materiálu.
Všechny mají: registraci, vlastní barvu, Dashboard/Přehled, a odpovídající
sadu podstránek. Detailní ladění formulářů a propojení mezi rolemi (najít-a-
-kontaktovat, sdílení a oprávnění napříč rolemi) je další krok.
