---
layout: page
title: Terralow
description: Repérer les biens en vente sous leur valeur, d'après les ventes réelles de chaque immeuble
importance: 2
category: machine learning
---

**En bref.** Un site en production, [terralow.com](https://terralow.com), qui estime ce que vaut chaque logement et met en avant les biens en vente
nettement sous leur valeur. Il couvre huit territoires (Paris, Lyon, Lille, Bordeaux, Montpellier et la petite couronne). L'extension à toute la
France est en cours.

## Ce que fait le site

- **Une carte de référence** : Chaque immeuble est colorié d'après les ventes réelles, avec la part de logements classés F ou G par commune et par
  quartier.
- **Les biens sous leur valeur** : Une liste mise à jour chaque jour, avec une fourchette de prix plutôt qu'une valeur unique.
- **Estimer une annonce** : Il suffit de coller le lien d'une annonce (SeLoger, Leboncoin, PAP…) pour obtenir son estimation.
- **Des dossiers d'aide à la décision** : Pour un bien, un immeuble ou un quartier, avec les points à vérifier avant de faire une offre.

## Données et modèles

Les modèles s'appuient sur les ventes réelles (DVF), les DPE, la base nationale des bâtiments (BDNB), les transports, les revenus et les loyers. Une
IA lit aussi le texte de chaque annonce et répond à une trentaine de questions fermées (état, travaux, extérieur…), pour quelques centimes par nuit.

|                | Estimation des annonces                             | Carte de référence                         |
| -------------- | --------------------------------------------------- | ------------------------------------------ |
| Apprend sur    | Les prix demandés, rapportés au prix de vente local | Les ventes réelles                         |
| Modèle         | XGBoost, 439 variables dont le texte des annonces   | Modèle hédonique                           |
| Erreur médiane | 8,6 %                                               | 12,3 % sur les ventes de 2025, jamais vues |

Un bien n'est signalé que s'il est à plus de 15 % sous sa valeur à Paris et dans les Hauts-de-Seine, 20 % ailleurs, soit environ deux fois l'erreur
médiane du modèle.

## Un système entièrement automatisé

- **Chaque jour** : Mise à jour des données, des estimations et de la liste des biens sous leur valeur.
- **Chaque semaine** : Réentraînement du modèle, puis publication automatique de sa mesure de qualité sur le site.
- **Communication** : Publication automatique de contenu sur les réseaux sociaux.
- **Exploitation** : Un serveur unique, une supervision (Prometheus, Grafana) et des sauvegardes vérifiées chaque jour.

## Limites

- Le modèle des annonces apprend sur des prix demandés, pas sur des prix de vente : c'est pour cela que la carte s'appuie sur les ventes réelles.
- La qualité des estimations reste inégale selon les quartiers.

## Stack

Python, XGBoost, LLM, FastAPI, nginx, React, MapLibre, PMTiles, Prometheus, Grafana.
