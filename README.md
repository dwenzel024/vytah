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

## 📋 Matice odpovědnosti (Kdo co dělal)

| Člen týmu | Analýza dat a zadání | Návrh algoritmu (SCAN/LOOK) | Implementace v JS (`vytah.html`) | Testování, kontrola metrů & statistik | Dokumentace |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **David Wenzel** | **R / A** | **R / A** | **R / A** | **R** | **R / A** |
| **Alex Marek Levandovský** | **C** | **C** | **I** | **R / A** | **R** |

*Vysvětlivky (RACI):*
- **R (Responsible):** Osoba, která danou část vypracovala / realizovala.
- **A (Accountable):** Osoba nesoucí konečnou odpovědnost za správnost.
- **C (Consulted):** Osoba, která poskytla konzultaci nebo zkoumala chování (např. analýza odpolední špičky a sběr statistik ujeté dráhy).
- **I (Informed):** Osoba informovaná o průběhu a změnách v kódu.

---

## 💻 Jak simulaci spustit

1. Klonujte nebo stáhněte tento repozitář.
2. Otevřete soubor `vytah.html` (nebo `index.html`) v libovolném webovém prohlížeči.
3. Načtěte přiložený soubor zadání `zadani-bezny-den-ve-skole-B746-8C6D.json` (tlačítkem nebo přetažením drag-and-drop).
4. Klikněte na tlačítko **▶ Spustit**.
