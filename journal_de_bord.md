# Site Web
## Choix d'hébergement
- Recherche de solution d'hébergement. Choix : GitHub Pages car
	- C'est gratuit
	- Nous utilisons déjà GitHub dans l'association
	- simplicité

## Jekyll
- Utilisation du générateur de site web statique Jekyll car il est supporté par GitHub Pages
- Recherche sur l'utilisation de Jekyll
	- Utilisation de [Jekyll-Now](https://www.smashingmagazine.com/2014/08/build-blog-jekyll-github-pages/) un modèle pour utiliser Jekyll
	- Mise en ligne du site web avec un peu de personnalisation (2h)
	- Lecture du [tutoriel](https://jekyllrb.com/docs/step-by-step/01-setup/) de Jekyll et recherches complémentaires (SASS, CoffeeScript) (2h)
- Modification de Jekyll-Now pour appliquer les amélioration du tutoriel de Jekyll
	- Génération de la barre de navigation automatiquement
	- Traduction en français des différents éléments du site
	- Création d'une collections d'auteurs (2h)

## Nom de domaine
### Choix du nom de domaine
- Choix en CA du nom de domaine robotps
- Recherche sur internet de site pour acheter un nom de domaine
  - [GoDaddy](www.godaddy.com) choisi pour ses tarifs
	- [robot-ps.com](robot-ps.com)

### Mise en place
- On peut utiliser différents types de nom de domaine
	- sous-domaine www : www.robot-ps.com
	  - GitHub recommande cette solution ([raison](https://help.github.com/en/articles/about-supported-custom-domains#www-subdomains))
	- apex domaine : robot-ps.com
	  - Moins stable car si GitHub change l'adresse IP de ses serveurs, il faudra modifier la configuration du DNS.
	- "sous-domaine" un sous domaine personnalisé : "sous-domaine".robot-ps.com

- Utilisation de ce [tutoriel](http://andrewsturges.com/blog/jekyll/tutorial/2014/11/06/github-and-godaddy.html).
  - Étape 4 - l'adresse IP n'est plus à jour. Voir [ici](https://help.github.com/en/articles/setting-up-an-apex-domain#configuring-a-records-with-your-dns-provider) pour la liste des adresses IP utilisable actuellement.
- Plus d'information, voir [documentation](https://help.github.com/en/articles/using-a-custom-domain-with-github-pages) de GitHub.


## Esthétique
- Gestion d'une personne charger d'améliorer l'esthétique du site et le contenu
	- Discussion sur Slack pour différents problèmes sur le site
		- problèmes d'affichage
		- éléments récurrents qui peuvent être mis dans un seul fichier, et ainsi la maintenance est faciliter
		- utilisé le markdown dès que possible
	- je participe aussi au site sur la génération des pages.
	- besoin d'une icône pour le site
		- sondage auprès des membres de l'ARTS
		- sélection de l'image temporaire en attendant les création artistique des membres
		- utilisation d'un [site générateur d'icône](https://realfavicongenerator.net/)
		- mise en place sur le site web

# Base roulante
- La base roulante à un code fonctionnel le but est maintenant de partitionner les différentes fonction du code en plusieurs classe pour plus lisibilité, plus facile à maintenir.
- Voici les différents classes envisager :
	- Motor - pour le contrôle d'un moteur (1h)
	  - Encoder, pour connaître la position du moteur
		- PID, pour asservir le moteur en vitesse ou en position
			- S'inspirer de l'asservissement des Dynamixels et de CVRA
		- La rampe de vitesse est à l'intérieur de cette classe
	- Control - qui va contrôler les deux moteurs à tout instants, pour atteindre un point donné.
	- Trajectory - pour la génération de trajectoire
	- Odometry - pour situer le robot sur l'arène
	  - Dispose d'un coefficient correcteur pour corriger la symétrie imparfaite du robot
	- StateMachine - pour suivre les états du robot et élaborer une stratégie
	- Communication - interface avec l'ordinateur, à définir plus amplement

# Interface Arduino / PC
## Pourquoi
- Faire du debug

## Fonction
- 

# Coupe de France de Robotique
## Inscription
- Utilisation de la plateforme poolzor
  - Changement d'adresse email
- Gestion de l'envoie du paiement par chèque

## Coupe de Belgique
- Demande sur poolzor de l'inscription
- L'inscription est mise en attente car les équipes belges était prioritaire, nous nous sommes juste pré-inscrit.
- Dès fin novembre nous pouvions faire les démarches pour nous inscrire, mais n'ayant pas une liste défini des personne voulant aller a cet événement cela a été mis en attente
- Fin janvier, constitution de liste des personnes intéressé
- Calcul des frais approximatif de l'événement
- Règlements des frais par virement bancaire
  - Problème, oubli de mettre le nom de l'équipe dans le libellé du virement
	- Résolution, envoie d'un mail à l'organisation de l'événement

## Suivi de l'avancement des robots
- Programmation
- Électronique
- Mécanique

# Gestion de l'association
## Communication
- Pour assurer le bon fonctionnement de l'association moi et Augustin Bielefeld avons mis en place un Slack pour la communication et deux Trello pour suivre l'avancement des projets.
- Afin d'assurer que ces dispositifs soit utilisé je fais des rappels réguliers de consulter Trello.
- Mise en place de processus pour garder un Trello organisé

### Trello
- Mise en place de processus pour garder un Trello organisé
	- carte générale avec du détails à l'intérieur
	- liste très générale pour les contenir
	- liste "À discuter", on déplace une carte dans cette liste car il y a besoin d'en discuter
	- liste "À faire", on déplace une carte dans cette liste quand un élément au moins à besoin d'être traité
- Règles pour les cartes dans "À faire"
	- Une date limite doit être défini
	- Une ou plusieurs personnes doivent être responsable de la cartes
	- Une fois la tâche accompli, mettre à jour la carte puis la ranger
- Création d'un second tableau "Ressources ARTS". Il a été créer pour désencombré le tableau "Administration ARTS" et séparer les actions à mener des ressources pour les réaliser. Il contient :
  - Les processus de l'association
	  - Communication
		- Événement
		- Veille, se tenir informer des avancées
		- Carnet de bord
	- Les liens avec l'Administration

### Slack
- S'assurer que chaque membre de l'ARTS puissent utiliser sur Slack
	- Envoi des invitations par email
	- Rappel d'utiliser aux séances hebdomadaires
	- S'assurer que tout les membres soient sur toutes les chaînes
- Création d'une nouvelle chaîne si le sujet est conséquent
- Archiver les chaînes devenus inutiles

### Email
- Constituer avec les fiches d'inscriptions et un formulaire rempli sur un ordinateur
- Envoie hebdomadaire aux membres de l'association des activités prévu pour la séance du samedi

## Conseil d'Administration
### L'avant CA
- Souvent organiser à partir de 13h en fonction de la disponibilité des membres du bureau
- Message d'information sur Slack pour prévenir de la date du CA
- Constitution de l'ordre du jour en utilisant la liste "À discuter" de Trello

### Pendant le CA
- Discussion des points dans l'ordre du jour (liste "À discuter")
- La secrétaire prend des notes
- Attributions des tâches à effectuer à un ou plusieurs membres avec une date butoir (déplacement carte dans liste "À faire")
- Mise en place d'un nouveau système d'ordre du jour et d'actions pour les CA car la solution actuelle n'était pas efficace (24/01/2019). C'est avec Trello, que j'ai mis en place ce système
	- Une liste _Ordre du Jour_ contient les différentes cartes (sujet) à aborder en CA.
	- Une fois le CA finis. Les cartes sont rangées dans les listes adaptés ou sont mis dans Objectifs de la semaine avec une date butoir et au moins une personne responsable de la tâche.
	- Ce système peut ainsi simplifié la rédaction du compte rendu du CA.
- Réflexions sur les moyens à mettre en place pour garder un Trello lisible et rangé. (24/01/2019)
  - Si beaucoup de carte sont à propos d'un sujet commun dans une catégorie, les regroupés en une seule et mettre dans la description et utilisé des checklists pour tenir à jour l'avancement des différentes catégorie.
	- Au moins une fois par semaine, faire une relecture du tableau dans le but de supprimer les cartes obsolètes, mettre à jour si besoin, créer de nouvelles cartes puis ranger le tout.
	- Se demander si l'on peut trouver de nouvelles méthodes de rangement pour garder le Trello un espace organisé de réflexions et de suivi.
	- Vérifier que les membres applique les consignes, et si les membres n'arrive pas à les suivre, il faudrait éventuellement modifier les méthodes qui ne fonctionne pas.
- Mise en place de la convention de la C138
- Mise en place des démarches à faire toute les années
  - Convention pour l'utilisation des salles C138 et C107
	- Faire parvenir des statistiques de l'ARTS comme la répartition des membres dans les différentes filières.
- Mise en place des démarches pour la passation
	- Invitation des anciens
	- Transfert des connaissance
	  - Book de passation personnel pour chaque rôle du bureau
		- Compléter les actions qui doivent être entreprise toute l'année pour chaque rôles
- Recherche du Numéro SIRET de l'association, nécessaire pour s'inscrire à Solidatech.
  - L'association semble ne pas avoir de SIRET après recherche dans les archives de l'ARTS et sur internet.
	- Délégation de recherche poussé à la secrétaire de l'ARTS, et si il reste introuvable.
	- Démarches pour en acquérir un.
- Solidatech, est une plateforme pour aider les organisations à but non lucratif.
  - Avantages
	  - Version avec messages illimités pour Slack
