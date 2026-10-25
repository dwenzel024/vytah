# 3IT KYME – Simulace výtahu (Běžný den ve škole)

Tento projekt řeší školní úlohu simulace a optimalizace řídicího algoritmu výtahu v 8patrové budově na základě zadání `zadani-bezny-den-ve-skole-B746-8C6D.json` (400 lidí).

## 🚀 O projektu a cíle
Hlavním cílem bylo nahradit původní hloupý „panelákový“ výtah efektivnějším řídicím algoritmem tak, aby:
- **Lidé nečekali tak dlouho** (minimalizace průměrné i maximální doby čekání a jízdy).
- **Výtah ujel výrazně méně vzdálenosti v metrech** (úspora energie).

---

## 🧠 Popis algoritmu (SCAN / LOOK)

Vzhledem k parametru `destVisible: false` (výtah na chodbách zná pouze požadovaný směr jízdy, nikoliv cílové patro) byl implementován **SCAN / LOOK algoritmus s prioritizací směrů**:

1. **Směrová plynulost:** Výtah projíždí budovu v ucelených cyklech (nahoru / dolů). Cestou zastavuje v patrech, kde vykládá cestující nebo nakládá čekající, kteří chtějí jet stejným směrem.
2. **Selektivní nástup (`nastup` logika):** Do kabiny nastupují pouze lidé jedoucí ve směru aktuální jízdy výtahu (pokud je v kabině kapacita).
3. **Dynamické otáčení:** Výtah nejezdí zbytečně do nejvyššího či nejnižšího patra, pokud tam nikdo nechce – otáčí se na nejvzdálenějším aktivním požadavku.
4. **Adaptivní návrat:** Při nečinnosti v ranní fázi preferuje čekání v přízemí (patro 0), kde vzniká největší nával.

---

## 👥 Matice odpovědnosti (Kdo co dělal)

### David Wenzel
- **Počáteční analýza zadání a architektura:** Prostudování datové sady JSON, návrh strategie řešení a výběr vhodného algoritmu (SCAN/LOOK).
- **Implementace algoritmu:** Napsání hlavní řídicí logiky ve funkcích `rozhodni()` a `nastup()` v souboru `vytah.html`.
- **Optimalizace směrového filtrování:** Návrh pravidla pro správný nástup lidí podle směru tlačítka (reakce na omezení `destVisible: false`).
- **Příprava dokumentace a kódu:** Finální úprava skriptů, kontrola funkčnosti a vytvoření `README.md`.

### Alex Marek Levandovský
- **Testování a analýza datových fází:** Sledování průběhu simulace v jednotlivých časových úsecích (ranní nával z přízemí vs. odpolední odliv z pater) a ověřování chování výtahu.
- **Měření efektivity a ujeté dráhy:** Porovnávání naměřených výsledků (ujeté metry, průměrné čekání lidí, nejdelší čas čekání) před a po nasazení nového algoritmu.
- **Validace a kontrola hraničních stavů:** Testování vytížení kapacity kabiny (max. 6 osob) a kontrola plynulosti otáčení výtahu v nejvyšším požadovaném patře.

---

## 💻 Jak simulaci spustit

1. Klonujte nebo stáhněte tento repozitář.
2. Otevřete soubor `index.html` v libovolném webovém prohlížeči.
3. Klikněte na tlačítko **▶ Spustit**.
