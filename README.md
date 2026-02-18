# Mission : **Construire un Écosystème Data Centré sur le Cinéma avec Python, FastAPI et Streamlit** 

**Objectif : Construire une API robuste pour centraliser et exposer les données MovieLens.**  

🔹 **Design de la base de données** :  
- Modéliser la base de données en SQL à partir des fichiers CSV.  
- Utiliser **SQLite** pour stocker les données de manière efficace.  
- Gérer les relations entre les films, les utilisateurs, les notes et les tags.  

🔹 **Développement de l’API avec FastAPI** :  
- Concevoir un **API RESTful** permettant d'interroger facilement les films et les notes des utilisateurs.  
- Intégrer **Pydantic** pour la validation des données entrantes.  
- Utiliser **SQLAlchemy** pour la gestion des requêtes à la base de données.  

🔹 **Déploiement de l’API** :  
- Prévoir une version **on-premise** avec Docker.  
- Sécuriser les endpoints et optimiser les performances.  

🔹 **Création d’un SDK en Python** :  
- Développer un **package Python** permettant aux utilisateurs d'interagir facilement avec l’API.  
- Publier ce package sur **PyPI**, afin qu’il puisse être utilisé dans d'autres projets.  

**Livrables** :  
- Une base de données centralisée et prête à l’emploi.  
- Une API FastAPI documentée et déployée.  
- Un SDK Python simple d'utilisation et bien documenté

---

## **Phase 2 : Data Analyst - Exploration et Visualisation**  

![](architecturephase.png)

**Objectif : Explorer et analyser les données en interrogeant l’API.**  

🔹 **Analyse Exploratoire des Données (EDA)** :  
- Utiliser le **SDK Python** pour requêter l’API et récupérer les données.  
- Identifier les tendances dans les notes des films.  
- Étudier les genres les plus populaires et les préférences des utilisateurs.  

🔹 **Construction d’une Data App avec Streamlit** :  
- Créer une **application interactive** qui permet de visualiser les tendances du cinéma.  
- Intégrer des **tableaux dynamiques** et des **graphiques interactifs**.  
- Offrir une **recherche avancée** des films en fonction des notes et des genres.  

**Livrables** :  
- Un notebook d'analyse exploratoire interactif.  
- Une **application web Streamlit** connectée à l’API qui présente, de manière interactive, les insights aux parties prenantes.


# Dataset MovieLens - Description des Données

Le dataset MovieLens est un ensemble de données publiques fournies par GroupLens, contenant des informations sur des films, des évaluations d'utilisateurs, ainsi que des tags attribués aux films. Il est souvent utilisé pour la recherche et l'expérimentation dans le domaine des systèmes de recommandation.



# Phase 1 : Développeur Python & Architecte API

## Introduction

![](architecture.png)


### Explication du diagramme

Une API (Application Programming Interface) est une interface qui permet à des applications ou des utilisateurs d'interagir avec un système. Ce diagramme représente comment une API fonctionne pour gérer des données et interagir avec une base de données.

#### Étape par étape :

1. **Les utilisateurs de l'API** (`API Users`)  
   - Ce sont les personnes ou applications qui utilisent l'API pour envoyer ou récupérer des données.
   - Pour interagir avec l'API, ils utilisent un **SDK** (Software Development Kit), qui est une bibliothèque (un package) Python facilitant l'envoi de requêtes.

2. **Le transfert et la validation des données** (`Pydantic`)  
   - Lorsque l'utilisateur envoie des requêtes à l'API, elles passent d'abord par **Pydantic**.  Nous parlerons davantage de Pydantic dans une autre session.
   - Pydantic vérifie que les données sont correctes (par exemple, s'il manque une valeur ou si un type est incorrect).  

3. **Le contrôleur API** (`FastAPI`)  
   - FastAPI est le cœur de l'API. Il reçoit les requêtes des utilisateurs, traite les données et décide de ce qu'il faut faire (ex. : insérer de nouvelles données, récupérer des informations, etc.).
   - Il agit comme un intermédiaire entre l'utilisateur et la base de données.

4. **Les classes de base de données** (`SQLAlchemy`)  
   - SQLAlchemy est une bibliothèque qui permet de communiquer avec la base de données de manière organisée.
   - Il traduit les requêtes Python en instructions compréhensibles par la base de données.

5. **La base de données** (`SQLite`)  
   - SQLite est la database où se trouve les données.
   - L'API envoie des requêtes pour récupérer des données de la database SQLite.

#### En résumé :
- L'utilisateur envoie des données via l'**SDK**.
- Ces données sont **validées** (`Pydantic`).
- L'API décide quoi faire (`FastAPI`).
- Si nécessaire, elle stocke ou récupère des données via **SQLAlchemy**.
- La base de données **SQLite** garde les informations de manière structurée.


## Création d'un un kit de développement logiciel (*Software development kit* ou SDK) pour l'API


### Qu'est-ce qu'un SDK et pourquoi est-il important ?

Un **Software Development Kit** (SDK) est un ensemble d'outils, de bibliothèques, de documentation et d'exemples de code qui permettent aux développeurs de facilement intégrer, étendre ou interagir avec une application, un service ou une API. Dans le contexte de notre projet, le SDK sera un package Python qui fournira une interface simple et intuitive pour interagir avec notre API MovieLens.

Les bénéfices de la création d'un SDK pour l'API sont nombreux :
- **Faciliter l'intégration** : Les utilisateurs n'ont pas besoin de comprendre les détails techniques de l'API, comme l'envoi de requêtes HTTP ou la gestion des réponses. Le SDK simplifie ces étapes.
- **Accélérer le développement** : En fournissant des fonctions prédéfinies pour effectuer des actions courantes, le SDK permet aux utilisateurs de gagner du temps.
- **Assurer la cohérence** : Un SDK bien conçu garantit que tous les utilisateurs interagiront avec l'API de manière uniforme et cohérente.
- **Support de la communauté** : En partageant un SDK via PyPI, il devient accessible à d'autres développeurs et analystes de données qui pourraient l'utiliser dans leurs projets.




