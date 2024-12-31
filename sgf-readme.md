# Simulateur de Gestion de Fichiers (SGF)

Ce simulateur permet de gérer une mémoire secondaire simulée avec différentes stratégies d'organisation des fichiers.

## Fonctionnalités

- Initialisation d'une mémoire secondaire avec un nombre de blocs et une taille de bloc personnalisables
- Création de fichiers avec deux types d'organisation :
  - Organisation contiguë
  - Organisation chaînée
- Visualisation de l'état de la mémoire
- Affichage des métadonnées des fichiers

## Compilation et Exécution

Pour compiler le programme :
```bash
gcc -o sgf main.c sgf.c -Wall
```

Pour exécuter le programme :
```bash
./sgf
```

## Utilisation du Simulateur

### 1. Initialisation de la Mémoire

Au premier lancement, vous devez initialiser la mémoire :
- Sélectionnez l'option 1 dans le menu
- Entrez le nombre total de blocs et la taille de chaque bloc
  - Exemple : `10 5` créera une mémoire de 10 blocs pouvant contenir chacun 5 enregistrements

### 2. Création d'un Fichier

Pour créer un nouveau fichier :
- Sélectionnez l'option 2
- Entrez le nom du fichier (maximum 50 caractères)
- Spécifiez le nombre d'enregistrements souhaités
- Choisissez le type d'organisation :
  - 0 : Organisation contiguë (les blocs sont alloués de manière adjacente)
  - 1 : Organisation chaînée (les blocs peuvent être dispersés)

### 3. Visualisation de la Mémoire

Pour voir l'état de la mémoire (option 3) :
- Les blocs occupés sont marqués en rouge [X]
- Les blocs libres sont marqués en vert [ ]
- Les détails des blocs utilisés sont affichés en dessous

### 4. Consultation des Métadonnées

L'option 4 affiche un tableau des métadonnées contenant :
- Nom du fichier
- Nombre de blocs
- Nombre d'enregistrements
- Premier bloc
- Organisation globale (Contiguë/Chaînée)
- Organisation interne (Triée/Non triée)

## Limites du Système

- Nombre maximum de fichiers : 100
- Taille maximale du nom de fichier : 50 caractères
- Taille maximale des données par enregistrement : 100 caractères

## Notes Importantes

- Assurez-vous d'initialiser la mémoire (option 1) avant toute autre opération
- La création d'un fichier échouera si l'espace disponible est insuffisant
- Dans le cas d'une organisation contiguë, les blocs nécessaires doivent être disponibles de manière adjacente
- Pour une organisation chaînée, les blocs peuvent être dispersés dans la mémoire

## Structure des Données

Le simulateur utilise les structures suivantes :
- `Record` : Structure d'un enregistrement
- `Block` : Structure d'un bloc de la mémoire
- `Metadata` : Informations sur un fichier
- `SecondaryMemory` : Structure principale de la mémoire simulée
