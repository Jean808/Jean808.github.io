---
layout: about
title: Accueil
permalink: /
subtitle: Intelligence artificielle · Apprentissage par renforcement · Vision par ordinateur · Agents IA — Paris

profile:
  align: right
  # À COMPLÉTER : dépose ta photo sous assets/img/prof_pic.jpg puis décommente la ligne suivante
  # image: prof_pic.jpg
  image_circular: true # crops the image to make it circular

selected_papers: false # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page

announcements:
  enabled: false # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

Titulaire d'un master de mathématiques, je me suis tourné vers l'intelligence artificielle et la construction de systèmes complets. Je conçois des systèmes d'IA de bout en bout, qu'il s'agisse de modèles prédictifs, d'agents qui apprennent par renforcement ou d'automatisations : de la collecte des données à la mise en production, en passant par la modélisation et une évaluation rigoureuse. Je travaille sur des données réelles, souvent incomplètes ou bruitées, avec une exigence constante : mesurer objectivement la performance des modèles.

Mes sujets : Apprentissage par renforcement, vision par ordinateur et télédétection, agents IA, modèles tabulaires sur données immobilières et cybersécurité.

Quelques projets :

- **[dpe_estate]({% link _projects/dpe_estate.md %})** _(en binôme, extension à toute la France en cours)_ : Prédire l'étiquette énergétique (DPE, de A à G) de chaque bâtiment à partir de données ouvertes : vues de rue Panoramax, photos aériennes de l'IGN, températures de surface Landsat et base des bâtiments BDNB. Inspiré d'un article scientifique (Mayer et al., 2022), le projet dépasse son score à Paris et en petite couronne (69,0 de F1 contre 64,8) et va plus loin en prédisant la lettre exacte, là où l'article se limite à « efficace » ou « inefficace ».
- **[Terralow]({% link _projects/immo_ml.md %})** _(en production sur [terralow.com](https://terralow.com), extension à toute la France en cours)_ : Repérer les biens immobiliers en vente sous leur valeur dans huit territoires. Le système est entièrement automatisé : des modèles de machine learning, entraînés sur les ventes réelles (DVF) et réentraînés chaque semaine, estiment la juste valeur de chaque bien à partir de ses caractéristiques, extraites par une IA.
- **[Stage chez Waitack]({% link _projects/waitack.md %})** _(2025, 1 mois)_ : Appliquer l'apprentissage par renforcement à un problème d'optimisation, la disposition d'objets : conception d'un environnement de simulation sur mesure, puis développement et entraînement d'un agent Deep Q-Network (DQN).
- **[TrackAI]({% link _projects/trackai.md %})** _(projet en équipe)_ : Une voiture qui apprend seule à piloter sur un circuit 3D, par apprentissage par renforcement. Le jeu tourne dans le navigateur (TypeScript, Three.js, moteur physique Rapier) et dialogue par WebSocket avec un agent PPO codé de zéro en PyTorch.
- **[Lycée Iman]({% link _projects/lycee_iman.md %})** _(en service dans l'établissement)_ : Mise en place d'automatisations et d'outils d'IA pour répondre aux besoins du [lycée](https://www.lycee-iman.com/). Côté IA et données : assistant documentaire (RAG) pour interroger les documents internes, correction de copies assistée par IA et analyse statistique des résultats du brevet. Côté automatisation : génération des emplois du temps du primaire au lycée, saisie automatique des salaires et import des élèves dans le logiciel de gestion Dolibarr, édition des fiches de paie.

**Je cherche un stage à partir de janvier 2027** (Île-de-France, télétravail possible) et je suis ouvert à des missions freelance en data et IA.

## Publications choisies

<div class="publications">
  {% bibliography --group_by none --query @*[selected=true]* %}
</div>

## Pour me contacter

- **E-mail** : jean.s82001 [at] gmail.com
- **GitHub** : [Jean808](https://github.com/Jean808)
