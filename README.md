# Documentation de l'Application Web

## Introduction

Bienvenue dans la documentation de **Aleo**. Cette application web est conçue pour extraire des annonces de véhicules, de biens immobiliers et d'emplois. Elle utilise une combinaison de technologies, dont Selenium pour l'extraction web, Flask pour le backend, React pour le frontend et MongoDB pour la base de données.

Cette documentation vous guidera à chaque étape, de la configuration de l'environnement de développement à la compréhension des fonctionnalités de l'application. Que vous soyez un utilisateur, un développeur ou un administrateur, ce guide vous couvre.

## Table des Matières

1. [Mise en Route](#1-mise-en-route)
    - [Installation](#11-installation)
    - [Configuration](#12-configuration)
2. [Guide de l'Utilisateur](#2-guide-de-lutilisateur)
    - [Page d'Accueil](#21-page-daccueil)
    - [Page de Recherche](#22-page-de-recherche)
3. [Documentation de l'API](#3-documentation-de-lapi)
    - [Obtenir Toutes les Annonces](#31-obtenir-toutes-les-annonces)
    - [Rechercher des Annonces](#32-rechercher-des-annonces)
    - [Extraction de Données](#33-extraction-de-donnees)
    - [Supprimer une Annonce par ID](#34-supprimer-une-annonce-par-id)
4. [Section d'Administration](#4-section-dadministration)
    - [Extraire de Nouvelles Annonces](#41-extraire-de-nouvelles-annonces)
    - [Supprimer des Annonces](#42-supprimer-des-annonces)
    - [Compter le Nombre d'Annonces](#43-compter-le-nombre-dannonces)
    - [Supprimer des Annonces Supprimables](#44-supprimer-des-annonces-supprimables)
    - [Vérifier le Nombre d'Annonces Supprimables](#45-verifier-le-nombre-dannonces-supprimables)
5. [Dépannage et Foire aux Questions](#5-depannage-et-foire-aux-questions)
    - [Problèmes Courants](#51-problemes-courants)
    - [FAQ](#52-faq)
6. [Légal et Licence](#6-legal-et-licence)
7. [Coordonnées](#7-coordonnees)

Bien sûr ! Voici la section complète de la "Mise en Route" pour l'intégration de React, Flask et MongoDB, écrit en format Markdown (`.md`) en français :

## 1. Mise en Route

### 1.1 Installation et Configuration

Pour commencer avec **Aleo**, suivez ces étapes pour configurer l'environnement de développement et mettre en place les technologies clés : React, Flask et MongoDB.

#### Partie Frontend avec React

1. Clonez le dépôt depuis [URL du Dépôt GitHub].
2. Ouvrez un terminal dans le répertoire du frontend de l'application.
3. Installez les dépendances du frontend en exécutant la commande suivante :

   ```bash
   cd frontend
   npm install
   ```

#### Partie Backend avec Flask

1. Ouvrez un terminal dans le répertoire racine de l'application.
2. Installez les dépendances du backend en exécutant la commande suivante :

   ```bash
   cd BackEnd
   pip install -r requirements.txt
   ```

#### Configuration

Avant de lancer l'application, assurez-vous de configurer les éléments suivants :

##### Configuration de MongoDB

- Dans le fichier `config.py`, configurez les détails de connexion à votre base de données MongoDB.

##### Configuration de Flask

- Dans le fichier `config.py`, configurez les paramètres de Flask, tels que les clés secrètes et autres options.

### 1.2 Démarrage de l'Application

Une fois que les dépendances sont installées et la configuration est en place, suivez ces étapes pour démarrer l'application :

1. Dans un terminal, lancez le backend Flask :

   ```bash
   python app.py
   ```

2. Dans un autre terminal, lancez le serveur de développement React pour le frontend :

   ```bash
   npm start
   ```

L'application sera accessible dans votre navigateur à l'adresse [http://localhost:3000]. Vous pouvez ainsi explorer les fonctionnalités et l'interface de l'application.


## 2. Guide de l'Utilisateur

Bienvenue dans le Guide de l'Utilisateur de **Aleo**. Cette section vous guidera à travers les fonctionnalités de l'application et vous montrera comment interagir avec ses différentes parties.

### 2.1 Page d'Accueil

La page d'accueil de l'application est votre point de départ. Elle offre une introduction à l'application ainsi qu'une barre de recherche pour vous aider à trouver rapidement les annonces qui vous intéressent.

![Page d'Accueil](/images/page_accueil.png)

- Utilisez la barre de recherche pour entrer des mots-clés pertinents pour les annonces que vous recherchez.
- Sélectionnez une catégorie dans le menu déroulant pour affiner votre recherche.
- Appliquez des filtres supplémentaires tels que le prix minimum et maximum, le type d'annonce et la localisation.
- Cliquez sur "Rechercher" pour afficher les résultats correspondants.

### 2.2 Page de Recherche

La page de recherche affiche les résultats de votre recherche en fonction des critères que vous avez spécifiés sur la page d'accueil. Vous verrez une liste d'annonces qui correspondent à vos critères de recherche.

![Page de Recherche](/images/page_recherche.png)

- Parcourez les annonces affichées sur la page. Cliquez sur une annonce pour afficher plus de détails.
- Utilisez les filtres de recherche sur le côté pour affiner davantage vos résultats.
- Si vous souhaitez revenir à la page d'accueil, cliquez sur "Accueil" dans la barre de navigation.

### 2.3 Section d'Administration

Si vous êtes un administrateur de l'application, vous avez accès à la section d'administration pour effectuer des tâches spécifiques.

#### 2.3.1 Extraire de Nouvelles Annonces

- Cliquez sur "Extraire Nouvelles Annonces" pour lancer le processus d'extraction de nouvelles annonces à partir des sources externes.

#### 2.3.2 Supprimer des Annonces

- Cliquez sur "Supprimer Annonce" à côté d'une annonce pour la supprimer de la base de données.

#### 2.3.3 Compter le Nombre d'Annonces

- Vous pouvez afficher le nombre total d'annonces dans la base de données en cliquant sur "Compter Annonces".

#### 2.3.4 Supprimer des Annonces Supprimables

- Cliquez sur "Supprimer Annonces Supprimables" pour lancer le processus de suppression des annonces qui ne sont plus nécessaires.

#### 2.3.5 Vérifier le Nombre d'Annonces Supprimables

- Utilisez "Vérifier Annonces Supprimables" pour obtenir des informations sur le nombre d'annonces supprimables dans la base de données.

## 3. Documentation de l'API


### 3.1 Obtenir Toutes les Annonces

**Endpoint** : `/api/posts`

Cet endpoint vous permet d'obtenir toutes les annonces disponibles dans la base de données.

- **Méthode HTTP** : GET
- **Paramètres** : Aucun
- **Réponse** : Un tableau d'objets représentant les annonces, avec les détails suivants pour chaque annonce :
  - Titre
  - Description
  - Prix
  - Type
  - Localisation
  - ...

### 3.2 Rechercher des Annonces

**Endpoint** : `/api/search/<category>/<q>`

Cet endpoint vous permet de rechercher des annonces en fonction de critères spécifiques.

- **Méthode HTTP** : GET
- **Paramètres** :
  - `category` : Catégorie de l'annonce (ex. véhicules, propriétés, emplois)
  - `q` : Termes de recherche
  - Autres paramètres optionnels pour filtrer la recherche : `minPrice`, `maxPrice`, `type`, `localisation`
- **Réponse** : Un tableau d'objets représentant les annonces correspondant aux critères de recherche.

### 3.3 Extraction de Données

**Endpoint** : `/api/admin/scrape`

Cet endpoint permet aux administrateurs de lancer le processus d'extraction de nouvelles annonces à partir des sources externes.

- **Méthode HTTP** : GET
- **Paramètres** : Aucun
- **Réponse** : Un message confirmant le lancement du processus d'extraction.

### 3.4 Supprimer une Annonce par ID

**Endpoint** : `/api/admin/delete/<id>`

Cet endpoint permet aux administrateurs de supprimer une annonce en spécifiant son ID.

- **Méthode HTTP** : GET
- **Paramètres** :
  - `id` : ID de l'annonce à supprimer
- **Réponse** : Un message indiquant si l'annonce a été supprimée avec succès.


## 4. Section d'Administration
### 4.1 Extraire de Nouvelles Annonces

**Endpoint** : `/api/admin/scrape`

Cet endpoint permet aux administrateurs de lancer le processus d'extraction de nouvelles annonces à partir des sources externes.

- **Méthode HTTP** : GET
- **Paramètres** : Aucun
- **Réponse** : Un message confirmant le lancement du processus d'extraction.

### 4.2 Supprimer des Annonces

**Endpoint** : `/api/admin/delete/<id>`

Cet endpoint permet aux administrateurs de supprimer une annonce en spécifiant son ID.

- **Méthode HTTP** : GET
- **Paramètres** :
  - `id` : ID de l'annonce à supprimer
- **Réponse** : Un message indiquant si l'annonce a été supprimée avec succès.

### 4.3 Compter le Nombre d'Annonces

**Endpoint** : `/api/admin/posts/count`

Cet endpoint permet aux administrateurs d'obtenir le nombre total d'annonces dans la base de données.

- **Méthode HTTP** : GET
- **Paramètres** : Aucun
- **Réponse** : Le nombre total d'annonces dans la base de données.

### 4.4 Supprimer des Annonces Supprimables

**Endpoint** : `/api/admin/posts/remove`

Cet endpoint permet aux administrateurs de supprimer les annonces qui ne sont plus nécessaires.

- **Méthode HTTP** : GET
- **Paramètres** : Aucun
- **Réponse** : Un message confirmant la suppression des annonces.

### 4.5 Vérifier le Nombre d'Annonces Supprimables

**Endpoint** : `/api/admin/posts/404`

Cet endpoint permet aux administrateurs de vérifier et de compter le nombre d'annonces supprimables dans la base de données.

- **Méthode HTTP** : GET
- **Paramètres** : Aucun
- **Réponse** : Un message avec le nombre d'annonces supprimables.


## 5. Dépannage et FAQ

### 5.1 Problèmes Courants

Voici quelques problèmes courants que vous pourriez rencontrer lors de l'utilisation de l'application et leurs solutions possibles :

#### Problème 1 : L'application ne se lance pas correctement.

- Assurez-vous que vous avez correctement installé toutes les dépendances du frontend et du backend.
- Vérifiez la configuration de Flask et MongoDB pour vous assurer que les paramètres sont corrects.

#### Problème 2 : Les résultats de recherche ne s'affichent pas.

- Vérifiez les paramètres de recherche que vous avez saisis et assurez-vous qu'ils correspondent aux annonces disponibles dans la base de données.
- Assurez-vous que le processus d'extraction de nouvelles annonces a été correctement exécuté.

#### Problème 3 : Les annonces supprimables ne sont pas supprimées.

- Assurez-vous que vous avez correctement exécuté l'endpoint pour supprimer les annonces supprimables.
- Vérifiez que le processus de suppression a été exécuté avec succès.

### 5.2 FAQ

#### Question 1 : Comment puis-je effectuer une recherche spécifique ?

- Sur la page d'accueil, saisissez des mots-clés pertinents dans la barre de recherche et sélectionnez une catégorie.
- Vous pouvez également utiliser les filtres pour affiner davantage votre recherche.

#### Question 2 : Puis-je supprimer une annonce que j'ai ajoutée ?

- Actuellement, l'application ne prend pas en charge la suppression d'annonces ajoutées par les utilisateurs. Seuls les administrateurs peuvent supprimer des annonces.

#### Question 3 : Comment puis-je devenir un administrateur ?

- Les administrateurs sont définis dans la base de données. Veuillez contacter l'équipe de support pour demander un accès administrateur.

#### Question 4 : Comment puis-je signaler un bug ou demander de l'aide ?

- Vous pouvez nous contacter à abdelwahed.akhechane@gmail.com pour signaler tout bug ou demander de l'aide.


## 6. Légal et Licence

### 6.1 Droits d'Auteur

**Aleo** est la propriété de [Nom de Votre Entreprise ou Organisation] et est protégé par les lois sur le droit d'auteur. Tous les droits sont réservés.

### 6.2 Licence

L'application **Aleo** est distribuée sous la licence [Type de Licence]. Cette licence régit l'utilisation, la distribution et la modification de l'application. Assurez-vous de lire et de comprendre les termes de la licence avant d'utiliser l'application.

### 6.3 Utilisation Responsable

L'utilisation de **Aleo** doit être conforme aux lois et réglementations locales et internationales. Les utilisateurs sont tenus de respecter les droits des autres utilisateurs et de ne pas utiliser l'application à des fins illégales, frauduleuses ou nuisibles.

### 6.4 Contact Juridique

Pour toute question juridique ou relative aux droits d'auteur, veuillez nous contacter à [Adresse Email de Contact Juridique].

