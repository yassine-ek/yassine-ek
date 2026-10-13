# Yassine EL KORAICHI

Étudiant en M1 MBFA (Université Paris Nanterre), après une licence MIASHS à Grenoble. **Je cherche un stage ou une alternance en trading algorithmique ou en recherche quantitative.**
Six projets de finance de marché quantitative (FX, exécution, alpha, C++, options, Monte Carlo) : chacun donne son résultat avec sa réserve, et les résultats négatifs sont publiés.

**Tableaux de bord interactifs :** [market making](https://yassine-ek.github.io/fx-market-making-simulator/) · [exécution](https://yassine-ek.github.io/fx-optimal-execution-tca/) · [recherche d'alpha](https://yassine-ek.github.io/preregistered-alpha-research/)

| Projet | Ce qui est démontré, et sa réserve | Techno |
|---|---|---|
| [Market making FX](https://github.com/yassine-ek/fx-market-making-simulator)<br>[tableau de bord](https://yassine-ek.github.io/fx-market-making-simulator/) | Avellaneda-Stoikov et GLFT : Sharpe de +5,7 à +36,0 en simulation (borne haute : le monde simulé obéit au modèle), négatif sur les 30 variantes rejouées sur EURUSD 1 minute réel (−23,2 à −3,4). *Réserve : le rejeu mesure surtout la convention de remplissage ; une marche aléatoire donne le même ordre de perte.* | Python, NumPy, numba |
| [Exécution optimale et TCA](https://github.com/yassine-ek/fx-optimal-execution-tca)<br>[tableau de bord](https://yassine-ek.github.io/fx-optimal-execution-tca/) | Ordre de 50 M EUR rejoué sur 1 037 jours : Almgren-Chriss (λ = 0,05) divise le risque de prix par 1,7 (écart-type 4,8 contre 8,3 bps) pour environ deux fois le coût (5,2 contre 2,6 bps pour TWAP), soit la frontière coût/risque attendue. *Réserve : l'impact de marché est supposé, pas estimé ; niveaux absolus indicatifs, classement robuste ; l'agrégateur de liquidité utilise 8 fournisseurs fictifs.* | Python, pandas, numba |
| [Moteur de marché C++20](https://github.com/yassine-ek/cpp-market-engine) | Carnet d'ordres à tableau plat : p50 42 ns contre 214 ns pour `std::map` (environ 5 fois plus rapide), test différentiel sur 1,2 M d'opérations sans désaccord ; file SPSC sans verrou, simulateur multi-agents. *Réserve : latences mesurées sur un cœur épinglé d'un PC Windows partagé, flux synthétique.* | C++20 |
| [Recherche d'alpha pré-enregistrée](https://github.com/yassine-ek/preregistered-alpha-research)<br>[tableau de bord](https://yassine-ek.github.io/preregistered-alpha-research/) | 7 stratégies de la littérature sous un protocole figé avant le premier calcul (empreinte SHA-256 vérifiable), coûts réels, jeu de test 2023+ jamais ouvert. Verdict : échec, même à coût nul aucun Sharpe brut de validation ne dépasse 0,15. *Réserve : la période de validation avait déjà été vue lors d'un travail antérieur (les 8 essais comptés sont un plancher) ; l'horodatage n'est pas certifié par un tiers.* | Python, pandas, SciPy |
| [Options FX et smile vanna-volga](https://github.com/yassine-ek/fx-options-vanna-volga) | Garman-Kohlhagen, quatre conventions de delta, smile vanna-volga reconstruit depuis ATM, RR25 et BF25. *Réserve : cohérence interne uniquement, cotations illustratives, aucune donnée de marché ; « GK = Black-Scholes à 1,7e-16 » vérifie la cohérence entre deux écritures, pas une validation externe.* | Python, NumPy, SciPy |
| [Laboratoire Monte Carlo](https://github.com/yassine-ek/monte-carlo-pricing-risk-lab) | Pricing d'options (Heston, asiatiques, barrières, put américain) et VaR/ES : 42 cas validés contre une formule fermée ou une référence indépendante, plus 3 contre-exemples volontaires (la méthode y échoue, montré exprès). Sur 5 méthodes de VaR backtestées sur 3 511 jours, seule la FHS-GARCH passe les trois tests. | Python, NumPy, numba, SciPy |

**Méthode.** Validation contre une formule fermée ou un modèle nul, découpage temporel strict avec jeu de test scellé, coûts réels par actif, protocole figé avant les calculs, contre-vérification des résultats par réimplémentation indépendante. Les résultats négatifs sont gardés.

## Comment ces projets ont été construits

Projets réalisés en octobre 2026 avec un assistant de programmation IA (Claude, Anthropic) que j'ai dirigé : choix des sujets, protocole, vérification des résultats. Tous les chiffres sont régénérés par les scripts du dépôt et contrôlés par les tests et la CI.

<details>
<summary>English version</summary>

First-year master's student (M1 MBFA) at Université Paris Nanterre, after a bachelor's in MIASHS (applied mathematics and computer science) in Grenoble. **I am looking for an internship or apprenticeship in algorithmic trading or quantitative research.**
Six quantitative market-finance projects (FX, execution, alpha, C++, options, Monte Carlo): each reports its result together with its caveat, and negative results are published.

**Interactive dashboards:** [market making](https://yassine-ek.github.io/fx-market-making-simulator/) · [execution](https://yassine-ek.github.io/fx-optimal-execution-tca/) · [alpha research](https://yassine-ek.github.io/preregistered-alpha-research/)

| Project | What is shown, and its caveat | Tech |
|---|---|---|
| [FX market making](https://github.com/yassine-ek/fx-market-making-simulator)<br>[dashboard](https://yassine-ek.github.io/fx-market-making-simulator/) | Avellaneda-Stoikov and GLFT: Sharpe +5.7 to +36.0 in simulation (upper bound: the simulated world follows the model by construction), negative on all 30 variants replayed on real 1-minute EURUSD (−23.2 to −3.4). *Caveat: the replay mostly measures the fill convention; a driftless random walk loses by the same order of magnitude.* | Python, NumPy, numba |
| [Optimal execution and TCA](https://github.com/yassine-ek/fx-optimal-execution-tca)<br>[dashboard](https://yassine-ek.github.io/fx-optimal-execution-tca/) | A 50 M EUR order replayed over 1,037 days: Almgren-Chriss (λ = 0.05) cuts price risk by 1.7× (standard deviation 4.8 vs 8.3 bps) for about twice the cost (5.2 vs 2.6 bps for TWAP), the expected cost/risk frontier. *Caveat: market impact is assumed, not estimated; absolute levels are indicative, the ranking is robust; the liquidity aggregator uses 8 fictitious providers.* | Python, pandas, numba |
| [C++20 market engine](https://github.com/yassine-ek/cpp-market-engine) | Flat-array order book: p50 42 ns vs 214 ns for `std::map` (about 5× faster), differential test over 1.2 M operations with no disagreement; lock-free SPSC queue, multi-agent simulator. *Caveat: latencies measured on a pinned core of a shared Windows PC, synthetic feed.* | C++20 |
| [Pre-registered alpha research](https://github.com/yassine-ek/preregistered-alpha-research)<br>[dashboard](https://yassine-ek.github.io/preregistered-alpha-research/) | 7 strategies from the literature under a protocol frozen before the first computation (verifiable SHA-256 fingerprint), real costs, 2023+ test set never opened. Verdict: failure, even at zero cost no gross validation Sharpe exceeds 0.15. *Caveat: the validation period had already been seen in earlier work (the 8 counted trials are a floor); the timestamp is not certified by a third party.* | Python, pandas, SciPy |
| [FX options and vanna-volga smile](https://github.com/yassine-ek/fx-options-vanna-volga) | Garman-Kohlhagen, four delta conventions, vanna-volga smile rebuilt from ATM, RR25 and BF25. *Caveat: internal consistency only, illustrative quotes, no market data; "GK = Black-Scholes to 1.7e-16" checks consistency between two implementations, not an external validation.* | Python, NumPy, SciPy |
| [Monte Carlo lab](https://github.com/yassine-ek/monte-carlo-pricing-risk-lab) | Option pricing (Heston, Asian, barrier, American put) and VaR/ES: 42 cases validated against a closed form or an independent reference, plus 3 deliberate counter-examples (the method fails there, shown on purpose). Of 5 VaR methods backtested over 3,511 days, only FHS-GARCH passes all three tests. | Python, NumPy, numba, SciPy |

**Method.** Validation against a closed form or a null model, strict temporal split with a sealed test set, real per-asset costs, protocol frozen before the computations, results cross-checked by an independent reimplementation. Negative results are kept.

**How these projects were built.** Projects completed in October 2026 with an AI programming assistant (Claude, Anthropic) that I directed: choice of topics, protocol, verification of results. All figures are regenerated by the scripts in each repository and checked by tests and CI.

</details>
