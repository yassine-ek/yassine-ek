# Yassine EL KORAICHI

Étudiant en M1 MBFA à l'Université Paris Nanterre, après une licence MIASHS à Grenoble. Je fais de la recherche en trading algorithmique et en finance quantitative.
Mes projets cherchent où se trouve l'avantage d'un desk et comment le mesurer sans se mentir : données de marché réelles, coûts réels, résultats négatifs conservés.

| Projet | Ce que ça fait | Chiffre clé (lu dans le README du projet) | Techno |
|---|---|---|---|
| [monte-carlo-pricing-risk-lab](https://github.com/yassine-ek/monte-carlo-pricing-risk-lab) | Pricing d'options et VaR/ES par Monte Carlo, chaque prix confronté à une référence indépendante | 45 cas validés (Heston QE : z = +1,35) ; 143 tests | Python, NumPy, numba, SciPy |
| [fx-market-making-simulator](https://github.com/yassine-ek/fx-market-making-simulator) ([tableau de bord](https://yassine-ek.github.io/fx-market-making-simulator/)) | Market making FX (Avellaneda-Stoikov, GLFT) simulé puis rejoué sur EURUSD 1 minute réel | Sharpe simulé +5,7 à +36,0, Sharpe rejoué −23,2 à −3,4 sur les 30 variantes | Python, NumPy, numba |
| [fx-optimal-execution-tca](https://github.com/yassine-ek/fx-optimal-execution-tca) ([tableau de bord](https://yassine-ek.github.io/fx-optimal-execution-tca/)) | Exécution optimale (Almgren-Chriss, TWAP) et agrégation de liquidité FX, mesurées par une TCA | Ordre de 50 M EUR en VAL : TWAP 2,6 bps (σ 8,3) contre Almgren-Chriss λ=0,05 5,2 bps (σ 4,8) | Python, pandas, numba |
| [preregistered-alpha-research](https://github.com/yassine-ek/preregistered-alpha-research) ([tableau de bord](https://yassine-ek.github.io/preregistered-alpha-research/)) | 7 stratégies de la littérature testées sous un protocole pré-enregistré (haché SHA-256), jeu de test scellé | Verdict ÉCHEC publié ; DSR de la pile < 0,001 pour 8 essais | Python, pandas, SciPy |
| [cpp-market-engine](https://github.com/yassine-ek/cpp-market-engine) | Carnet d'ordres, file lock-free, simulateur multi-agents et pricer Monte Carlo, sans dépendance | Carnet à tableau plat : p50 42 ns contre 214 ns pour `std::map` ; 134 + 162 vérifications | C++20 |
| [fx-options-vanna-volga](https://github.com/yassine-ek/fx-options-vanna-volga) | Options FX : Garman-Kohlhagen, conventions de delta, smile vanna-volga | Prix GK = Black-Scholes à 1,7e-16 près ; 42 tests | Python, NumPy, SciPy |

**Méthode commune.** Validation contre formules fermées, split temporel strict avec jeu de test scellé, coûts réels par actif, pré-enregistrement, relecture adversariale indépendante du code.

**Stack.** Python, NumPy, numba, SciPy, pandas, C++20, pytest, GitHub Actions.

---

# Yassine EL KORAICHI (English)

First-year master's student (M1 MBFA) at Université Paris Nanterre, after a bachelor's in MIASHS (applied mathematics and computer science) in Grenoble. My research is in algorithmic trading and quantitative finance.
My projects look for where a trading desk's edge actually lies and how to measure it honestly: real market data, real costs, negative results kept.

| Project | What it does | Key figure (from the project's README) | Tech |
|---|---|---|---|
| [monte-carlo-pricing-risk-lab](https://github.com/yassine-ek/monte-carlo-pricing-risk-lab) | Monte Carlo option pricing and VaR/ES, every price checked against an independent reference | 45 validated cases (Heston QE: z = +1.35); 143 tests | Python, NumPy, numba, SciPy |
| [fx-market-making-simulator](https://github.com/yassine-ek/fx-market-making-simulator) ([dashboard](https://yassine-ek.github.io/fx-market-making-simulator/)) | FX market making (Avellaneda-Stoikov, GLFT), simulated then replayed on real EURUSD 1-minute bars | Simulated Sharpe +5.7 to +36.0, replayed Sharpe −23.2 to −3.4 across 30 variants | Python, NumPy, numba |
| [fx-optimal-execution-tca](https://github.com/yassine-ek/fx-optimal-execution-tca) ([dashboard](https://yassine-ek.github.io/fx-optimal-execution-tca/)) | Optimal execution (Almgren-Chriss, TWAP) and FX liquidity aggregation, measured with a TCA | 50 M EUR order, out-of-sample: TWAP 2.6 bps (σ 8.3) vs Almgren-Chriss λ=0.05 5.2 bps (σ 4.8) | Python, pandas, numba |
| [preregistered-alpha-research](https://github.com/yassine-ek/preregistered-alpha-research) ([dashboard](https://yassine-ek.github.io/preregistered-alpha-research/)) | 7 strategies from the literature under a pre-registered protocol (SHA-256 hash), test set sealed | FAIL verdict published; stack DSR < 0.001 over 8 trials | Python, pandas, SciPy |
| [cpp-market-engine](https://github.com/yassine-ek/cpp-market-engine) | Order book, lock-free queue, multi-agent simulator and Monte Carlo pricer, dependency-free | Flat-array book: p50 42 ns vs 214 ns for `std::map`; 134 + 162 checks | C++20 |
| [fx-options-vanna-volga](https://github.com/yassine-ek/fx-options-vanna-volga) | FX options: Garman-Kohlhagen, delta conventions, vanna-volga smile | GK price = Black-Scholes to 1.7e-16; 42 tests | Python, NumPy, SciPy |

**Common method.** Validation against closed forms, strict temporal split with a sealed test set, real per-asset costs, pre-registration, independent adversarial code review.

**Stack.** Python, NumPy, numba, SciPy, pandas, C++20, pytest, GitHub Actions.
