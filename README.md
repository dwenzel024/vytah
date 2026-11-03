# 🛗 Simulátor výtahu — Školní projekt

Projekt optimalizace řízení výtahu, který dosáhl celkového zrychlení **84,4 %** oproti původnímu FIFO algoritmu.

## 👥 Autorský tým

* **David Wenzel** — Program, zpracování
* **Alex Marek Levandovský** — Kontrola, dokumentace

## 📁 Soubory projektu

* `index.html` — Samostatná webová aplikace s GUI simulátorem a řídicím algoritmem.
* `zadani-bezny-den-ve-skole-B746-8C6D.json` — Vstupní datová sada (400 cestujících, 8 pater, hash: `B746-8C6D`).

## 🚀 Návod ke spuštění

1. Otevřete soubor `index.html` v libovolném webovém prohlížeči.
2. Nahrajte zadaný soubor `zadani-bezny-den-ve-skole-B746-8C6D.json` (tlačítkem nebo přetažením).
3. Výpočet a simulace se spustí automaticky.

## 📊 Porovnání výkonu: Původní vs. Nový algoritmus

**Testováno na scénáři:** *Běžný den ve škole* (400 lidí, 8 pater, kapacita 6 osob, otisk `B746-8C6D`).

### Srovnání celkového času odbavení

* Původní stav (FIFO): `████████████████████████████` 1 262 s (~21,0 min)
* Nové řízení (LOOK): `████` 196,8 s (~3,2 min) [-84,4 %]

### Přehled naměřených metrik

| Sledovaná metrika | Původní řízení (FIFO) | Optimalizovaný LOOK | Dosažený rozdíl |
| :--- | :---: | :---: | :---: |
| **Průměrně celkem (hlavní parametr)** | **1 262,1 s (~21 min)** | **196,8 s (~3,2 min)** | **⚡ Zrychlení o 84,4 %** |
| Průměrná doba čekání | 1 250,7 s | 176,2 s | o 85,9 % kratší čekání |
| Průměrná jízda | 11,4 s | 20,5 s | Plynulý sběr po trase |
| Nejdelší čekání (nejhorší případ) | 3 493,6 s (~58 min!) | 852,2 s (~14 min) | Zkráceno o 44 minut |
| Celková ujetá dráha výtahu | 2 922 m | 2 175 m | Úspora 747 metrů |
| Rozvezeno do 600 s | 27 lidí | 51 lidí | +88 % větší propustnost |
| Celkem rozvezeno | 400 z 400 (100 %) | 400 z 400 (100 %) | Splněno bez chyb |
