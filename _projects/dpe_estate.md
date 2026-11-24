---
layout: page
title: dpe_estate
description: Estimer l'étiquette DPE de chaque bâtiment de France à partir d'images et de données ouvertes
importance: 1
category: machine learning
---

**En bref.** Prédire l'étiquette énergétique (DPE, de A à G) de chaque bâtiment à partir d'images et de données ouvertes. Le projet part d'un article
scientifique britannique, Mayer et al. (2022), _Estimating building energy efficiency from street view imagery, aerial imagery, and land surface
temperature data_ ([arXiv:2206.02270](https://arxiv.org/abs/2206.02270)). Il reproduit sa méthode en Île-de-France, dépasse son score, puis l'étend à
toute la France.

Projet en équipe, code privé.

## Données, toutes ouvertes

| Source                                   | Ce qu'elle apporte                                   |
| ---------------------------------------- | ---------------------------------------------------- |
| DPE des logements existants (ADEME)      | Les étiquettes à prédire                             |
| Vues de rue Panoramax                    | L'apparence des façades                              |
| Photos aériennes BD ORTHO (IGN)          | Les toitures, vues du dessus                         |
| Température de surface Landsat 8/9       | Les déperditions de chaleur visibles depuis l'espace |
| Base nationale des bâtiments BDNB (CSTB) | Année de construction, matériaux, consommation…      |

## Méthode

- **Images** : les vues de rue et les vues aériennes sont résumées par un modèle de vision pré-entraîné (DINOv3).
- **Modèle** : ces résumés sont combinés aux données de chaque bâtiment dans un mélange de modèles (boosting d'arbres de décision et réseaux de
  neurones).
- **Évaluation** : le modèle est noté sur des zones géographiques jamais vues à l'entraînement, pour qu'il ne puisse pas simplement reconnaître un
  quartier. Tous les choix se font en validation, et le test n'est noté qu'à la fin.

## Résultats en Île-de-France

**Face à l'article**, sur sa tâche (bâtiment « efficace », de A à D, ou « inefficace », de E à G ; F1 macro au test, Paris et petite couronne) :

| Modèle                                          | Article (Royaume-Uni) | Ici (Île-de-France) |
| ----------------------------------------------- | :-------------------: | :-----------------: |
| Méthode de l'article : vues de rue et aériennes |         64,8          |        65,0         |
| Notre modèle, toutes les sources                |           —           |      **69,0**       |

Le gain vient surtout des données sur les bâtiments, que l'article n'utilise pas. Les deux études portent sur des pays différents : la comparaison
reste indicative.

**La lettre exacte, de A à G**, sur toute l'Île-de-France : **70,6 de F1 macro à une lettre près** au test (intervalle de confiance 68,6 à 72,4).
Une prédiction compte comme juste si elle tombe sur la bonne lettre ou sur une lettre voisine.

## Extension à la France

- **96 départements** : 13,3 millions de photos de rue collectées et un jeu de **5,6 millions de bâtiments** avec un DPE, neuf fois l'Île-de-France.
- **Une infrastructure cloud** : stockage objet, préparation des données département par département, et un GPU loué seulement pour les calculs
  lourds.
- **Premier entraînement national le 23/11/2026** : **74,7 de F1 à une lettre près en validation croisée**. Le test n'est pas encore noté.
- **Suite** : noter le test, puis prédire l'étiquette des quelque 20 millions de bâtiments résidentiels de France.

## Limites

- Les lettres extrêmes A et G restent les plus difficiles : l'information qui les distingue manque souvent dans les données.
- À l'échelle nationale, la vue de rue n'apporte pas de gain mesurable une fois les données sur les bâtiments présentes.

## Stack

Python, PyTorch, DINOv3, scikit-learn, Polars, GeoPandas, Rasterio, STAC (Planetary Computer), FastAPI, stockage objet (OVH, Scaleway).
