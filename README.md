# Auto Clicker

## Description
Auto Clicker est une application Windows qui permet d'automatiser les clics de souris à des positions spécifiques de l'écran. Développée par Ryan Harrison en 2011, cette application permet aux utilisateurs de configurer des séquences de clics qui peuvent être répétées automatiquement.

## Fonctionnalités

### Positionnement du curseur
- Surveillance en temps réel de la position actuelle du curseur
- Affichage des coordonnées X et Y du curseur
- Copie rapide de la position actuelle via le bouton "Copy to Add Position" (F1)

### Configuration des clics
- Ajout de positions de clic à une file d'attente (F2)
- Configuration du type de clic (gauche ou droit) pour chaque position
- Réglage du temps d'attente (en millisecondes) entre chaque clic
- Liste détaillée des positions programmées avec leurs paramètres
- Suppression individuelle ou en masse des positions configurées

### Exécution
- Configuration du nombre de répétitions de la séquence de clics
- Démarrage de la séquence de clics (F3)
- Arrêt d'urgence de la séquence en cours (F4)
- Exécution de la séquence dans un thread séparé pour maintenir l'interface utilisateur réactive

### Interface utilisateur
- Interface simple et intuitive
- Raccourcis clavier pour les fonctions principales
- Menu contextuel pour la gestion des positions de clic

## Architecture technique

### Structure du projet
- Implémentation en C# avec Windows Forms
- Utilisation de l'API Windows (user32.dll) pour simuler les clics de souris
- Multi-threading pour éviter le blocage de l'interface utilisateur

### Classes principales
- `MainForm` : Interface utilisateur principale et gestion des événements
- `ClickThreadHelper` : Classe interne qui gère l'exécution des clics dans un thread séparé

### Méthodes clés
- `ClickLeftMouseButtonSendInput()` et `ClickRightMouseButtonSendInput()` : Simulation des clics de souris
- `SetCursorPosition()` : Positionnement du curseur à des coordonnées spécifiques
- `Run()` : Exécution de la séquence de clics programmée

## Utilisation

1. Lancer l'application Auto Clicker
2. Observer les coordonnées du curseur en temps réel dans la section "Current Cursor Position"
3. Placer le curseur à l'endroit désiré et appuyer sur F1 pour copier sa position
4. Configurer le type de clic (gauche ou droit) et le temps d'attente
5. Cliquer sur "Add Position" (F2) pour ajouter cette position à la liste
6. Répéter les étapes 3-5 pour créer une séquence complète
7. Définir le nombre de répétitions souhaité
8. Cliquer sur "Start Clicking" (F3) pour exécuter la séquence
9. Si nécessaire, cliquer sur "Stop Clicking" (F4) pour arrêter l'exécution

## Précautions d'usage
- Utilisez cette application avec précaution, car elle peut interagir avec d'autres programmes
- Ayez toujours le bouton "Stop Clicking" à portée de main pour arrêter l'exécution
- L'application ne vérifie pas la validité des actions à effectuer sur les positions ciblées

## Aspects techniques notables
- Utilisation des fonctions `SendInput` et `mouse_event` de l'API Windows
- Implémentation de structures spécifiques (INPUT, MOUSEINPUT) pour interagir avec l'API système
- Gestion des exceptions pour assurer la stabilité de l'application
- Validation des entrées utilisateur pour éviter les erreurs
- Thread dédié pour l'exécution des clics afin de maintenir l'interface utilisateur réactive

## Exigences système
- Système d'exploitation : Windows
- Framework : .NET Framework
