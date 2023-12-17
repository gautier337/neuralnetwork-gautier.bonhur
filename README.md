MyTorch - B-CNA-500
Aperçu

MyTorch est un projet dans le cadre du cours B5 - Computer Numerical Analysis (B-CNA-500). Ce projet vise à développer un réseau de neurones pour analyser des parties d'échecs. Le réseau prend en entrée un échiquier et prédit l'état de la partie : victoire, échec, pat, ou partie en cours.
Fonctionnalités

    Génération d'un nouveau réseau de neurones générique : Créer un réseau de neurones avec des poids aléatoires.
    Entraînement et prédiction : Entraîner le réseau sur un ensemble de données ou utiliser un réseau existant pour prédire l'état de parties d'échecs.
    Optimisation : Implémentation d'algorithmes pour optimiser le processus d'apprentissage, que ce soit en termes de vitesse ou de méthode.

Installation et Utilisation
Prérequis

    Tout environnement capable de gérer les scripts Python.

Execution

./my_torch

Utilisez my_torch avec les options suivantes :

./my_torch [--new IN_LAYER [HIDDEN_LAYERS...] OUT_LAYER | --load LOADFILE] [--train | --predict] [--save SAVEFILE] FILE

Structure du Projet

Le projet MyTorch est entièrement contenu dans un seul fichier script Python, my_torch.py, qui encapsule toutes les fonctionnalités du réseau de neurones pour l'analyse de parties d'échecs. Voici un aperçu des composants clés du fichier :

    Classe NeuralNetwork : Implémente le cœur du réseau de neurones, y compris les méthodes pour l'initialisation (__init__), la passe avant (forward), la rétropropagation (backward), l'enregistrement (save), et le chargement (load) du modèle.
    Fonctions Auxiliaires : Comprend des fonctions telles que relu, relu_derivative, softmax, et compute_loss pour soutenir les opérations du réseau de neurones.
    Fonctions de Traitement des Données : Inclut des fonctions comme parse_fen et convert_res_to_label pour convertir les données d'échecs au format utilisable par le réseau.
    Fonction Principale (main) : Le point d'entrée du script qui gère les arguments de la ligne de commande pour créer un nouveau réseau, charger un réseau existant, entraîner le réseau, effectuer des prédictions, et sauvegarder le modèle.
    Parseur d'Arguments : Utilise argparse pour gérer les options et arguments de ligne de commande, facilitant ainsi l'utilisation du script pour différentes opérations comme la création, l'entraînement, et la prédiction.

Documentation Technique

    Architecture du Réseau : Justification des choix architecturaux (nombre de couches, nombre de neurones par couche, fonction d'activation, etc.).
    Méthode d'Optimisation : Explications sur les techniques d'optimisation utilisées pour l'apprentissage.

Exemples d'Utilisation
Créer un Nouveau Réseau

./my_torch --new 65 4 4

Entraîner un Réseau

./my_torch --new 65 4 4 --train datasets/checkmate/10_pieces.txt --save saved_network.txt

Prédiction

./my_torch --load saved_network.txt --predict datasets/boards/10_pieces.txt
