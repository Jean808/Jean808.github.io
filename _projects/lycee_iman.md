---
layout: page
title: Lycée Iman
description: "Automatisations et outils d'IA pour un établissement scolaire : correction assistée, emplois du temps, gestion"
importance: 5
category: missions
---

**En bref.** Des automatisations et des outils d'IA conçus pour répondre aux besoins du [Lycée Iman](https://www.lycee-iman.com/), du primaire au
lycée, et en service dans l'établissement.

## IA et données

- **Un assistant documentaire (RAG)** : Un système qui permet d'interroger en langage naturel les documents internes de l'établissement. L'IA
  retrouve les passages utiles, puis rédige sa réponse à partir d'eux.
- **Correction de copies assistée par IA** : En service dans l'établissement.
- **Analyse des résultats du brevet** : Moyennes, médianes, taux de réussite, mentions et corrélations entre matières, livrées dans un fichier Excel
  prêt à l'emploi pour l'équipe pédagogique.

## Emplois du temps

- **À partir d'une semaine type** : Le script produit les emplois du temps du mois entier, par classe, par enseignant et par groupe d'élèves.
- **Trois formats** : Des tableaux, des calendriers à importer dans Google Agenda ou Outlook, et des grilles en PDF à afficher.
- **Tous les niveaux** : Du primaire au lycée, avec les enseignements de spécialité et les matières en arabe. Un validateur repère les conflits et
  les doublons.

## Gestion de l'établissement

- **Saisie automatique des salaires** : Un robot remplit le logiciel de gestion de l'établissement (Dolibarr) à partir d'un fichier, avec un mode
  test qui simule sans rien enregistrer.
- **Import des élèves** : Les listes de chaque classe sont fusionnées et nettoyées, sans doublons, pour être importées dans Dolibarr.
- **Fiches de paie et factures** : Édition des fiches de paie en PDF, avec un contrôle, et classement automatique des factures.

## Stack

Python, LLM et RAG, pandas, NumPy, matplotlib, ReportLab, Selenium, Dolibarr.
