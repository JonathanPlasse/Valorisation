# Développement
## Tests unitaires
- Pytest
- Travis

## IDE
- Atom
- Platformio

## Langages
- C/C++
- Python

## Bibliothèques
- Matplotlib
- Numpy/Scipy
- Yaml
- PyQt5
- ROS

# Projets
## BinSerial
### Rôle
Transférer des données entre une Arduino et un ordinateur.

### Principe
Les données sont stocker transmise en binaire via UART. Elles sont sous la forme de structures (exemple: {int8, uint32, float})

À l'initialisation, l'ordinateur attend 2 secondes le temps d'être sûr que l'Arduino a eu le temps de démarrer.

### Développement
#### Bibliothèques
- Python
  - pyserial
  - collection.struct
  - time
  - argparse
- C++
  - stdint.h
  - Serial from Arduino.h

#### Fonctions implanter
- read
  - format de la structure
  - retourne la structure reçu
- write
  - format de la structure
  - structure à envoyer

## MotorCaracteristics
### Rôle
Utilitaire permettant de calculer les caractéristiques d'un moteur à courant continu.

### Principe
Calcul des caractéristiques (gain et temps de réponse) à partir de la réponse indicielle du moteur.

Approximation : le moteur répond comme un système du premier ordre.

Multiples mesures de la réponse indicielle ensuite moyennées pour avoir une courbe plus précise.

Une régression non linéaire permet de calculer le gain et le temps de réponse du moteur.

### Développement
#### Bibliothèques
- Python
  - binserial (cf. ci dessus)
  - scipy.optimize
  - numpy
  - yaml
  - PyQt5
  - matplotlib
- C++
  - stdint.h
  - Encoder.h
  - motor.hpp

#### Implantation
- Réglage des paramètres de l'utilitaire
  - Port de la liaison série (UART)
  - Baud rate de la liaison série
  - Amplitude de l'échelon
  - Temps d'échantillonnage de la réponse
  - Nombre de d'échantillon par mesure de réponse
  - Nombre de réponse indicielle
  - Temps d'attente entre chaque mesure de réponse
- Mesure des réponses indicielles du moteur
- Envoie en parallèle de la mesure à l'ordinateur
- Calcul des caractéristiques du moteur
- Affichage du résultat
  - Mesure de la réponse
  - Réponse du modèle déduit

#### Problèmes éventuels
- Mauvais résultat de régression
  - Modifier les valeurs estimer du modèle. Cela facilite la convergence.

## Tests unitaires
### Rôle
Tester le bon fonctionnement de fonctions individuelles.

### Utilité
- Réflexion sur l'implémentation de la fonction
  - arguments
  - retour
- Pendant le développement de la fonction, vérifier si la fonction a bien été implantée.
- Pendant la maintenance, vérifier si l'on n'a pas casser le fonctionnement de la fonction.

### Utilisation
- pytest est un module python qui permet d'utiliser l'assert de python pour faire les tests unitaires.
- Travis CI est un service sur GitHub qui vérifie à chaque commit que les tests (fait avec pytest) soient validés.

## EasyRst
### Rôle
Utilitaire calculant automatiquement les réglages d'un correcteur RST pour asservir un moteur en position.

### Principe
Implantation d'une méthode générale du calcul de RST.

Les coefficient R, S, T sont calculer en fonction de
- zéros et pôles du systèmes à compenser ou non (B+, B-, A+, A-)
- retard (d)
- modèle du système souhaité (Am)
- filtrage de la mesure (A0)
- ordre des perturbations à rejeter (p)
- ordre de consigne à suivre (r)

Dans notre cas
- les zéros et les pôles sont calculé à partir du gain et du temps de réponse du moteur
- le moteur réagi sans retard (d = 1)
- le moteur doit réagir comme un système du second ordre avec un double pôle réglable
- éventuelle passe bas réglable
- perturbation constante à rejeter (p = 1)
- ordre de consigne à déterminer (r = ?)

### Développement
#### Bibliothèques
- numpy
- control
- PyQt5
- matplotlib
- pytest

#### Tests unitaires
Pour développer la méthode générale de résolution, une résolution d'équation diophantienne à été implanter


## Base roulante
  - Asservissement
    - Calcul caractéristiques moteur
    - PID
    - RST
  - Odométrie
  - Génération de trajectoire
  - Détection d'obstacle

## Site internet
- Github Pages
- Jekyll
- Rédaction
- Nom de domaine
- Esthétique

# Administratif

## Projet Ingénieur
- Établir cahier des charges
- Suivi de l'avancement
- Conseiller

## Association
- Gestion
  - Trello
    - Hiérarchisation
    - Processus
  - Slack
  - Github
  - Journal de bord
- Réunion
  - Projecteur
  - Points du jour
  - Actions à mener
- Coupe de France de Robotique
  - Inscription
  - Déplacement
  - Hébergement
  - Gestion du développement du robot

# Compétences
- Soft skill
  - Gestion d'équipe
  - Planification
  - Communication
