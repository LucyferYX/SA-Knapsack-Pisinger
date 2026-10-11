# 0/1 mugursomas problēma ar Simulated Annealing – RPG varoņa inventārs

*English version below.*

## Par projektu

Praktiskais darbs kombinatorikā. RPG spēles varonim no daudziem priekšmetiem jāizvēlas tādi, lai viņš vienā gājienā pie tirgotāja aiznestu **pēc iespējas vērtīgāku inventāru**, nepārsniedzot inventāra ietilpību. Tiek rēķināta **0/1 mugursomas problēma** (*0/1 Knapsack Problem*), kas risināta ar **Simulated Annealing (SA)** algoritmu (bez gatavām optimizācijas bibliotēkām).

Lai rezultāti būtu interesantāki, katram priekšmetam algoritmiski tiek piešķirts ticams nosaukums un retums (piem., *Dwarven Mithril Sword of Frost*, `Rare`), un tiek pētīts jautājums: **Vai optimālais inventārs izmanto retākus priekšmetus?**

## Datu kopas

21 [Pisinger](https://www.dcs.gla.ac.uk/~pat/cpM/jchoco/knapsack/papers/hardInstances.pdf) *large_scale* datu kopa: 3 tipi (nekorelētas, vāji korelētas, stipri korelētas) × 7 izmēri (`n = 100 … 10000` priekšmetu), katrai ir zināms optimālais risinājums. Datu kopas iegūtas no repozitorija [dnlfm/knapsack-01-instances](https://github.com/dnlfm/knapsack-01-instances).

## Rezultāti (īsumā)

- Visās datu kopās vidējā atšķirība no optimālā risinājuma ir **≤ 0,11%**.
- 14 no 21 datu kopām SA vismaz vienā palaišanā atrod optimālo risinājumu, bet stipri korelētajās datu kopās – vienmēr.
- Izpildes laiks vienai palaišanai: no < 1 s (`n = 100`) līdz ~26–51 s (`n = 10000`).

## Struktūra

| Fails / mape | Saturs |
|---|---|
| `code.ipynb` | Viss kods, skaidrojumi (latviešu valodā) un rezultāti |
| `dataset/large_scale/` | Pisinger datu kopas (priekšmeti un optimālais risinājums) |
| `dataset/large_scale-optimum/` | Optimālās vērtības `z` |
| `results/param_runs.csv` | Saglabātie parametru eksperimenta rezultāti |
| `info.txt` | Uzdevuma apraksts |

## Palaišana

Nepieciešams Python 3 ar `pandas` un `matplotlib`. Atver `code.ipynb` un palaid visas šūnas (*Run All*). Ja `results/param_runs.csv` eksistē, eksperimenta rezultāti tiek ielādēti no faila (dažas minūtes). Lai eksperimentu veiktu no jauna (~2,5 h), šis fails ir jāizdzēš.

---

# 0/1 Knapsack Problem with Simulated Annealing – RPG Hero Inventory

## About

A practical work in combinatorics. An RPG hero has to choose items so that a single trip to the trader brings in **the most valuable inventory possible** without exceeding the carry capacity. A **0/1 Knapsack Problem** is solved with a **Simulated Annealing (SA)** algorithm (no ready-made optimisation libraries).

To make the results more interesting, every item is algorithmically given a believable name and rarity (e.g. *Dwarven Mithril Sword of Frost*, `Rare`), and the notebook explores the question: **does the optimal inventory use rarer items?**

## Datasets

21 [Pisinger](https://www.dcs.gla.ac.uk/~pat/cpM/jchoco/knapsack/papers/hardInstances.pdf) *large_scale* instances: 3 types (uncorrelated, weakly correlated, strongly correlated) × 7 sizes (`n = 100 … 10000` items), each with a known optimal solution. The instances come from the [dnlfm/knapsack-01-instances](https://github.com/dnlfm/knapsack-01-instances) repository.

## Results (summary)

- On every instance the average gap to the optimum is **≤ 0.11%**.
- SA finds the optimum in at least one run on 14 of 21 instances, and always on the strongly correlated ones.
- Time per run: from < 1 s (`n = 100`) to ~26–51 s (`n = 10000`).

## Structure

| File / folder | Contents |
|---|---|
| `code.ipynb` | All code, explanations (in Latvian) and results |
| `dataset/large_scale/` | Pisinger instances (items and optimal solution) |
| `dataset/large_scale-optimum/` | Optimal values `z` |
| `results/param_runs.csv` | Saved results of the parameter experiment |
| `info.txt` | Assignment description |

## Running

Requires Python 3 with `pandas` and `matplotlib`. Open `code.ipynb` and run all cells (*Run All*). If `results/param_runs.csv` exists, the experiment results are loaded from the file (a few minutes). To rerun the experiment from scratch (~2.5 h), delete that file.
