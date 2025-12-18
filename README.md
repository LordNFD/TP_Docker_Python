# TP Docker & Jenkins - Application Python

Ce projet met en place un pipeline CI/CD complet pour une application Python simple qui effectue des additions.

##  Contenu du dépôt

* **sum.py** : Le script Python principal. Il prend deux arguments et retourne la somme.
* **Dockerfile** : La configuration pour construire l'image Docker de l'application (basée sur Python Alpine).
* **test_variables.txt** : Les jeux de données utilisés pour tester l'application automatiquement.
* **Jenkinsfile** : Le script du pipeline Jenkins déclaratif.

##  Fonctionnement du Pipeline (CI/CD)

Le fichier `Jenkinsfile` automatise les étapes suivantes :

1.  **Build** : Construction de l'image Docker à partir du `Dockerfile`.
2.  **Run** : Démarrage du conteneur en arrière-plan.
3.  **Test** :
    * Lecture du fichier `test_variables.txt`.
    * Exécution du script `sum.py` à l'intérieur du conteneur pour chaque ligne de test.
    * Comparaison du résultat obtenu avec le résultat attendu.
4.  **Deploy** : Push de l'image validée sur DockerHub.

##  Prérequis techniques

* Jenkins
* Docker & Docker Pipeline Plugin
* Python 3
