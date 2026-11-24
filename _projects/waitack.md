---
layout: page
title: Stage chez Waitack
description: Disposer des objets dans une pièce par apprentissage par renforcement
importance: 3
category: apprentissage par renforcement
---

**En bref.** Un stage d'un mois en machine learning chez Waitack, en 2025 : apprendre à une IA à disposer des formes simples, assimilables à des
meubles, à l'intérieur d'une pièce, représentée par un polygone avec un côté courbe, sans qu'elles se chevauchent.

## Ce que j'ai fait

- **Un environnement de simulation sur mesure** : La pièce et les formes sont modélisées géométriquement. À chaque étape, l'agent déplace une forme,
  et la récompense pénalise la surface des chevauchements, avec un petit coût par étape pour l'inciter à trouver vite une disposition valide.
- **Un agent Deep Q-Network (DQN)** : Développé et entraîné pour apprendre, par essais et erreurs, à placer les formes au mieux.
- **L'analyse des résultats** : Évaluation de l'agent, visualisation des dispositions obtenues et pistes d'amélioration du modèle.

## Stack

Python, TensorFlow (Keras), Gymnasium, Shapely, NumPy, Matplotlib.
