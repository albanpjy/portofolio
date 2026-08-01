# 📊 Analyse de Portefeuille — Rapport Pédagogique

Rapport quantitatif complet d'analyse et d'optimisation de portefeuille, construit en **R / Quarto**, appliqué à 15 instruments (ETF + actions françaises).

**[👉 Voir le rapport complet en ligne](https://albanpjy.github.io/portofolio/)**

---

## Objectif

Ce projet illustre une démarche de **gestion de portefeuille** de bout en bout : collecte de données de marché, analyse de risque/performance par instrument, optimisation selon la théorie moderne du portefeuille (Markowitz), et construction de recommandations d'allocation selon le profil investisseur.

## Méthodologie

- **Données** : cours ajustés (dividendes + splits) via Yahoo Finance (`quantmod`), période 2008 → aujourd'hui pour capturer plusieurs cycles de marché (crise 2008, Covid, 2022).
- **Métriques de risque/performance** : rendement annualisé, volatilité, ratio de Sharpe, ratio de Sortino, Maximum Drawdown, VaR et CVaR (paramétrique).
- **Analyse de diversification** : matrice de corrélation statique et corrélations glissantes à 60 jours (mise en évidence de la hausse des corrélations en période de crise).
- **Optimisation de portefeuille** : simulation Monte Carlo de la frontière efficiente, identification du portefeuille à variance minimale (MVP) et du portefeuille à Sharpe maximal (MSP).
- **Scoring composite** : 40 % Sharpe + 30 % rendement + 20 % volatilité + 10 % Max Drawdown, pour classer les 15 instruments.
- **Recommandations** : trois allocations cibles (défensif / équilibré / croissance) avec simulation rétrospective de performance.

## Instruments couverts

15 instruments cotés en euros (Euronext Paris) : ETF actions monde et thématiques (dont CW8, PANX), ETF or (SGLD), et actions françaises de qualité (Air Liquide, L'Oréal, Sanofi, BNP Paribas, Carrefour...).

## Stack technique

| Domaine | Outils |
|---|---|
| Langage | R |
| Données financières | `quantmod`, `xts`, `zoo`, `TTR` |
| Métriques de risque | `PerformanceAnalytics`, `moments` |
| Visualisation | `ggplot2`, `patchwork`, `plotly`, `DT` |
| Rapport | Quarto (HTML auto-contenu, code repliable) |

## Contenu du repo

- [`rapport_portefeuille_html.qmd`](rapport_portefeuille_html.qmd) — code source Quarto/R complet (téléchargement des données, calculs, graphiques, optimisation, recommandations)
- [`styles_portefeuille.css`](styles_portefeuille.css) — thème visuel du rapport
- [`docs/index.html`](docs/index.html) — rapport final rendu, publié via GitHub Pages

## ⚠️ Avertissement

Ce document est produit à des fins **éducatives et analytiques uniquement**. Il ne constitue pas un conseil en investissement au sens des articles L. 321-1 et suivants du Code monétaire et financier. Les performances passées ne préjugent pas des performances futures.

---

*Auteur : Alban Videloup*
