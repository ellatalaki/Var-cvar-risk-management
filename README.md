# Var-cvar-risk-management
Mesure du risque financier — VaR, CVaR, Backtesting sur le S&amp;P 
# Mesure du Risque Financier — VaR & CVaR

Étude comparative de la Value-at-Risk (VaR) et de la Conditional Value-at-Risk (CVaR) 
appliquée à l'indice S&P 500.

**Université de Lorraine — Master 2 Expertise Statistique pour l'Économie et la Finance — Janvier 2026**

## Contexte

Face aux limites de la VaR classique révélées par les crises financières, ce projet 
analyse empiriquement la complémentarité entre VaR et CVaR (Expected Shortfall), 
dans le cadre des exigences réglementaires Bâle III (FRTB).

## Démarche

- Données : prix de clôture journaliers S&P 500 — Yahoo Finance (2010–2025)
- Rendements logarithmiques, statistiques descriptives
- Calcul de la VaR et CVaR par deux méthodes :
  - Approche paramétrique (loi normale)
  - Approche Cornish-Fisher (correction asymétrie + kurtosis)
- Backtesting : validation empirique du modèle sur 3 773 observations
- Discussion réglementaire : adoption de la CVaR dans Bâle III / FRTB

## Résultats

| Méthode | VaR (95%) | CVaR (95%) |
|---|---|---|
| Normale | -1.75 % | -2.20 % |
| Cornish-Fisher | -1.67 % | -2.69 % |

- Fréquence de dépassements observée : **4.51 %** (théorique : 5 %)
- CVaR empirique (backtesting) : **-2.79 %**
- La CVaR Cornish-Fisher capture mieux les queues épaisses 
  (skewness = -0.73, kurtosis = 16.2)

## Conclusions clés

La VaR seule sous-estime le risque extrême. La CVaR, mesure cohérente 
au sens d'Artzner et al. (1999), offre une vision plus prudente et complète — 
ce qui justifie son adoption par les régulateurs bancaires.

## Stack technique

R · QuantLib · PerformanceAnalytics · ggplot2 · Yahoo Finance API
