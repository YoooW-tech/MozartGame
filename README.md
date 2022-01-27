# PPC_Mozart_game

Projet de PPC 2021-2022
M2 STL, Sorbonne Université

Emilie SIAU
Yohann ROBERT

## Sujet
Voir le fichier `Projet.pdf`

## Exécution
Nécessite une installation de sbt
Lancer le jeu de Mozart : `sbt` puis `run X` avec X un chiffre entre 0 et 3. Il faut au moins 2 instances pour lancer la musique (un chef d'orchestre et un musicien).
Lancer cela dans jusqu'à 4 terminaux différents, avec X différent pour chaque.

## Réponses aux questions

### Schéma
Voir le fichier `Schema_Acteurs.svg`

### Cas de panne du chef d'orchestre
 - Dans le cas d'une panne du chef d'orchestre, les musiciens restants détectent la mort de celui-ci et effectuent une réelection du chef d'orchestre.
 - Le chef d'orchestre sera élu selon son identifiant (id), l'id le plus petit ayant la priorité. 
 - L'id du chef d'orchestre actuel est propagé aux musiciens. Un nouveau musicien arrivant reçoit l'id du chef d'orchestre actuel lors de son arrivée, dès qu'il reçoit un message Alive de quelqu'un d'autre.
 - Exemple : Les noeuds 0, 1 et 2 jouent ensemble, 0 était chef d'orchestre et meurt. 1 est donc nommé nouveau chef d'orchestre. => le musicien 3 arrive, il reçoit l'id du chef d'orchestre actuel (1) et reçoit donc des mesures à jouer à son tour.


