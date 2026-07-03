# Python pre dátovú analýzu – materiály z kurzu (Coders Lab)

> 🇬🇧 *Materials for a Python data-analysis course I taught as a lecturer at [Coders Lab](https://coderslab.cz). The course takes students from Python basics to pandas, APIs, web scraping and a final real-data workshop. Materials are in Czech/Slovak.*

Materiály ku kurzu Pythonu pre dátovú analýzu, ktorý som **lektorovala v Coders Lab**. Kurz vedie účastníkov od úplných základov Pythonu až po samostatnú analýzu reálnych dát – vrátane pandas, práce s API, web scrapingu a záverečného projektu.

📚 Doplňujúce poznámky a vysvetlenia nájdete na [wiki tohto repozitára](https://github.com/danakozakova/Python-CodersLab/wiki).

## Osnova kurzu

| Časť | Témy |
|---|---|
| **00 – Prework** | úvod do JupyterLab, premenné a typy, čísla, stringy a zoznamy, vstup/výstup, podmienky, cykly `for` a `while` |
| **Session 1–2 (príprava)** | funkcie, pokročilé dátové typy, objekty, knižnice; načítanie dát, DataFrame a Series, základy deskriptívnej štatistiky |
| **Deň 1** | funkcie, zoznamy a tuples, slovníky, kľúčové slovo `in`, textové reťazce |
| **Deň 2** | úvod do OOP, práca so súbormi, ošetrenie výnimiek, regulárne výrazy |
| **Deň 3** | práca s databázou PostgreSQL z Pythonu |
| **Deň 4** | JSON, volanie API, autentifikácia |
| **Deň 5** | filtrovanie a spracovanie dát v pandas, agregácie (`groupby`) |
| **Deň 6** | spájanie tabuliek (`merge`), dátumy a časy, pivot tabuľky, export do Excelu (`openpyxl`) |
| **Deň 7** | vizualizácia dát: 2D grafy, pokročilé grafy, viacnásobné grafy, anotácie |
| **Deň 8** | web scraping: BeautifulSoup, Selenium |
| **Deň 9** | generovanie PDF reportov z Pythonu |
| **Deň 10** | 🏒 **záverečný workshop: analýza hokejových dát pre stávkovú kanceláriu** – od stiahnutia dát cez spracovanie a analýzu až po biznisové odporúčania |

Okrem toho repo obsahuje **cheatsheety** (Python základy, pandas, grafy) v priečinku `Cheatsheety/`.

## Štruktúra materiálov

- Každý deň má vlastný priečinok (`Day_1` … `Day_10_Workshop`).
- Notebooky existujú v dvoch verziách: **zadanie** (`*.ipynb`) a **riešenie** (`*_reseni.ipynb`) – riešenia odporúčam otvárať až po vlastnom pokuse. 🙂
- Dátové súbory ku cvičeniam sú v priečinkoch `Data/` (spoločné) a `data/` pri jednotlivých dňoch.

## Ako materiály spustiť

```bash
git clone https://github.com/danakozakova/Python-CodersLab.git
cd Python-CodersLab
pip install pandas numpy matplotlib openpyxl beautifulsoup4 selenium requests jupyterlab
jupyter lab
```

Notebooky sú písané pre Python 3.10+.
Poznámka:
Súbory _renamed a _cleaned v Data/ sú zámerne súčasťou repa – slúžia ako vstupné body pre Deň 5 a 6, aby lekcie boli samostatne spustiteľné.

## O mne

Som štatistička a lektorka matematiky, štatistiky a programovania – viac na mojom [GitHub profile](https://github.com/danakozakova) alebo na [hodinovaucitelka.sk](https://hodinovaucitelka.sk).
