# Market Risk Analysis 

## Description
Ce projet analyse le risque de marché en utilisant diverses méthodes, notamment l'estimation du Value at Risk (VaR), la modélisation des extrêmes et l'analyse des stratégies de liquidation. Il répond aux consignes du projet ESILV pour l'année 2024-2025 et couvre plusieurs aspects de l'analyse du risque financier.

## Fonctionnalités
- **Estimation du VaR historique** à l'aide d'une distribution non paramétrique (Kernel Logistique)
- **Analyse des dépassements de seuil** pour valider la pertinence du VaR
- **VaR par Monte-Carlo** pour une option d'achat sur l'action Natixis
- **Analyse des extrêmes (Extreme Value Theory - EVT)** avec estimation des paramètres GEV et de l'indice extrémal
- **Stratégie de liquidation optimisée** via le modèle d'Almgren et Chriss
- **Analyse des corrélations multi-résolutions** entre taux de change avec ondelettes de Haar
- **Calcul des exposants de Hurst** et estimation de la volatilité annualisée

## Méthodes et Implémentations

### **VaR non-paramétrique et validation**
- Estimation du **VaR historique** sur les rendements journaliers de Natixis (2015-2016)
- Utilisation d'un **noyau logistique** pour l'estimation de la distribution empirique
- Analyse des dépassements du seuil VaR sur la période 2017-2018

### **VaR par Monte-Carlo pour une option call**
- Estimation des **paramètres du mouvement brownien** sur la période 2015-2018
- Simulation de **1000 scénarios de prix** sur un horizon d'un jour
- Transformation des prix simulés en **prix d'une option call** à maturité 1 mois
- Calcul du **VaR empirique** sur ces simulations

### **Analyse des extrêmes (EVT)**
- Estimation des **paramètres GEV** des queues de distribution des rendements via Pickands
- Analyse des extrêmes pour identifier la nature des pertes/gains extrêmes
- Calcul de **l'indice extrémal** via le dé-clustering par blocs

### **Modèle d'Almgren et Chriss**
- Estimation des **paramètres du modèle**
- Validation du modèle et analyse de sa pertinence
- Implémentation d'une **stratégie de liquidation optimale** avec transactions horaires

### **Analyse en ondelettes et volatilité**
- Estimation des **corrélations multi-résolutions** entre paires de devises FX (GBPEUR, SEKEUR, CADEUR)
- Analyse de l'effet **Epps** et discussion des résultats
- Calcul des **exposants de Hurst** et estimation de la volatilité annualisée
