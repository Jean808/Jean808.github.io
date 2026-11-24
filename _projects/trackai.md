---
layout: page
title: TrackAI
description: Une voiture qui apprend à piloter sur un circuit 3D par apprentissage par renforcement
importance: 4
category: apprentissage par renforcement
---

**En bref.** Un jeu de course en 3D qui tourne dans le navigateur, et une IA qui apprend seule à y piloter, par essais et erreurs, grâce à
l'apprentissage par renforcement. Projet en équipe, code public : [github.com/arthurmath/TrackAI](https://github.com/arthurmath/TrackAI).

TrackAI est la seconde version du projet. La première, [RaceAI](https://github.com/arthurmath/RaceAI), entraînait la voiture sur un circuit en 2D,
par algorithme génétique puis par Deep Q-Network (DQN).

## Le jeu

- **Rendu 3D et physique** : Un jeu web en TypeScript, avec Three.js pour la 3D et Rapier pour la physique du véhicule. Plusieurs circuits et
  plusieurs voitures.
- **Le lien avec l'IA** : À chaque instant, le jeu envoie ce que « voit » la voiture à un serveur Python par WebSocket, qui lui renvoie les commandes
  de conduite.
- **Un tableau de bord en direct** : Les courbes d'apprentissage s'affichent dans le jeu pendant l'entraînement.

## Ce que l'IA voit et fait

- **Ce qu'elle perçoit** : 14 valeurs, dont sa vitesse, cinq capteurs de distance aux bords de la piste, et la direction et la courbure de la piste
  devant elle, pour anticiper les virages.
- **Ce qu'elle décide** : Deux commandes continues, l'accélération ou le freinage, et la direction.
- **Ce qui la récompense** : Avancer le long de la piste, et vite. Elle est pénalisée si elle s'arrête, recule ou sort de la piste.

## L'algorithme

PPO (Proximal Policy Optimization), codé de zéro en PyTorch, sans bibliothèque d'apprentissage par renforcement :

- **Deux réseaux de neurones** : L'un choisit les commandes (l'acteur), l'autre estime si la situation est favorable (le critique).
- **Plusieurs voitures en parallèle** : Elles roulent en même temps et alimentent une mémoire commune, ce qui accélère l'apprentissage.

## Résultats

Après entraînement, l'agent enchaîne jusqu'à **23 tours de circuit** dans un même épisode.

## Stack

TypeScript, Vite, Three.js, Rapier, Python, PyTorch, WebSocket.
