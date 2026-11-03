# Simulace řízení výtahu (3IT KYME)

Projekt zaměřený na optimalizaci plynulosti vertikální dopravy v budově pomocí algoritmus SCAN/LOOK s ochranou proti hladovění.

## 🛠️ Zpracování

* **David Wenzel** — Vývoj algoritmu & logika řízení
* **Alex Marek Levandovský** — Testování & dokumentace

## 📂 Struktura

* `vytah.html` — Samostatná aplikace obsahující vizualizaci, simulátor a řídicí algoritmus.
* `zadani-bezny-den-ve-skole-B746-8C6D.json` — Vstupní datová sada pro simulaci (400 lidí, 8 pater).

## 💻 Spuštění

1. Otevřete soubor `vytah.html` v prohlížeči.
2. Vložte soubor se zadáním (`.json`).
3. Spusťte simulaci tlačítkem **Spustit**.

## 📈 Zhodnocení výsledků

Optimalizace výrazně snížila celkovou dobu čekání cestujících a zvýšila efektivitu provozu.

### Doba zpracování (celkový průměr)

* **Původní systém (FIFO):** `[====================]` 1 262,1 s
* **Náš algoritmus (LOOK):**  `[===]` 196,8 s *(Úspora času: ~84,4 %)*

### Přehled klíčových ukazatelů

| Parametr | Původní verze | Naše řešení | Zlepšení |
| :--- | :---: | :---: | :---: |
| **Průměrný čas v systému** | 1 262,1 s | **196,8 s** | **-84,4 %** |
| **Průměrné čekání na patře** | 1 250,7 s | **176,2 s** | **-85,9 %** |
| **Maximální doba čekání** | 58,2 min | **14,2 min** | **-75,6 %** |
| **Ujetá vzdálenost** | 2 922 m | **2 175 m** | **-747 m** |
| **Odbaveno lidí** | 400 / 400 | **400 / 400** | **100 %** |
