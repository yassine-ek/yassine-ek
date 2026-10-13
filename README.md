# Yassine EL KORAICHI

Étudiant en M1 MBFA (Université Paris Nanterre), après une licence MIASHS à Grenoble. **Je cherche un stage ou une alternance en trading algorithmique ou en recherche quantitative.**
Six projets de finance de marché quantitative : chacun donne son résultat avec sa réserve, et les résultats négatifs sont publiés.

**Tableaux de bord interactifs :** [market making](https://yassine-ek.github.io/fx-market-making-simulator/) · [exécution](https://yassine-ek.github.io/fx-optimal-execution-tca/) · [recherche d'alpha](https://yassine-ek.github.io/preregistered-alpha-research/)

### [Market making FX](https://github.com/yassine-ek/fx-market-making-simulator) · Python, numba
Avellaneda-Stoikov et GLFT : Sharpe de +5,7 à +36,0 en simulation (borne haute), négatif sur les 30 variantes rejouées sur EURUSD 1 minute réel (−23,2 à −3,4).
*Réserve : le rejeu mesure surtout la convention de remplissage ; une marche aléatoire perd du même ordre.*

### [Exécution optimale et TCA](https://github.com/yassine-ek/fx-optimal-execution-tca) · Python, pandas
Ordre de 50 M EUR rejoué sur 1 037 jours : Almgren-Chriss divise le risque de prix par 1,7 pour environ deux fois le coût de TWAP (frontière coût/risque retrouvée) ; agrégateur de liquidité avec *last look*.
*Réserve : impact de marché supposé, niveaux absolus indicatifs, classement robuste ; 8 fournisseurs de liquidité fictifs.*

### [Moteur de marché C++20](https://github.com/yassine-ek/cpp-market-engine) · C++20
Carnet d'ordres à tableau plat : p50 42 ns contre 214 ns pour `std::map`, test différentiel sur 1,2 M d'opérations sans désaccord ; file SPSC sans verrou testée sous ThreadSanitizer.
*Réserve : latences mesurées sur un cœur épinglé d'un PC Windows partagé, flux synthétique.*

### [Recherche d'alpha pré-enregistrée](https://github.com/yassine-ek/preregistered-alpha-research) · Python, SciPy
7 stratégies de la littérature sous un protocole figé avant le premier calcul (empreinte SHA-256 vérifiable), coûts réels, test 2023+ jamais ouvert. Verdict : échec, publié et expliqué ; un contrôle positif montre que le pipeline détecte un vrai edge.
*Réserve : la période de validation avait déjà été vue lors d'un travail antérieur ; horodatage non certifié par un tiers.*

### [Options FX et smile vanna-volga](https://github.com/yassine-ek/fx-options-vanna-volga) · Python, SciPy
Garman-Kohlhagen, quatre conventions de delta, smile vanna-volga depuis ATM, RR25 et BF25 (conversion butterfly de marché → smile).
*Réserve : cohérence interne uniquement, cotations illustratives, aucune donnée de marché.*

### [Laboratoire Monte Carlo](https://github.com/yassine-ek/monte-carlo-pricing-risk-lab) · Python, numba
Pricing (Heston, asiatiques, barrières, put américain, MLMC, grecques AAD) : 42 cas validés contre une référence indépendante + 3 contre-exemples volontaires ; VaR/ES par 5 méthodes sur 3 511 jours, seule la FHS-GARCH passe les quatre tests.
*Réserve : la VaR porte sur un portefeuille linéaire de 7 actifs.*

**Méthode.** Validation contre une formule fermée ou un modèle nul, découpage temporel strict avec jeu de test scellé, coûts réels par actif, protocole figé avant les calculs. Les résultats négatifs sont gardés.

## Comment ces projets ont été construits

Projets réalisés en octobre 2026 avec un assistant de programmation IA (Claude, Anthropic) que j'ai dirigé : choix des sujets, protocole, vérification des résultats. Tous les chiffres sont régénérés par les scripts du dépôt et contrôlés par les tests et la CI.

<details>
<summary>English version</summary>

First-year master's student (M1 MBFA) at Université Paris Nanterre, after a bachelor's in MIASHS (applied mathematics and computer science) in Grenoble. **I am looking for an internship or apprenticeship in algorithmic trading or quantitative research.** Six quantitative market-finance projects; each reports its result together with its caveat, and negative results are published.

- **[FX market making](https://github.com/yassine-ek/fx-market-making-simulator)** — Avellaneda-Stoikov and GLFT: Sharpe +5.7 to +36.0 in simulation (upper bound), negative on all 30 variants replayed on real 1-minute EURUSD. *Caveat: the replay mostly measures the fill convention.*
- **[Optimal execution and TCA](https://github.com/yassine-ek/fx-optimal-execution-tca)** — a 50 M EUR order over 1,037 days: Almgren-Chriss cuts price risk by 1.7× for about twice the TWAP cost. *Caveat: market impact is assumed; 8 fictitious liquidity providers.*
- **[C++20 market engine](https://github.com/yassine-ek/cpp-market-engine)** — flat-array order book, p50 42 ns vs 214 ns for `std::map`; lock-free SPSC queue tested under ThreadSanitizer. *Caveat: pinned core on a shared Windows PC.*
- **[Pre-registered alpha research](https://github.com/yassine-ek/preregistered-alpha-research)** — 7 literature strategies under a frozen, verifiable protocol; published failure, plus a positive control. *Caveat: the validation period had been seen in earlier work.*
- **[FX options and vanna-volga smile](https://github.com/yassine-ek/fx-options-vanna-volga)** — Garman-Kohlhagen, four delta conventions, vanna-volga smile. *Caveat: internal consistency only, no market data.*
- **[Monte Carlo lab](https://github.com/yassine-ek/monte-carlo-pricing-risk-lab)** — 42 cases validated against independent references + 3 deliberate counter-examples; 5 VaR/ES methods backtested over 3,511 days. *Caveat: linear 7-asset portfolio.*

**How these projects were built.** Completed in October 2026 with an AI programming assistant (Claude, Anthropic) that I directed: choice of topics, protocol, verification of results. All figures are regenerated by the scripts in each repository and checked by tests and CI.

</details>
