# Gestion de la Scolarité - BUT Informatique (SAÉ S1.01)

Ce projet a été développé dans le cadre de la **SAÉ S1.01 : Implémentation d'un besoin client** à l'IUT de Paris - Rives de Seine (Université Paris Cité).

L'objectif est de développer une **application en langage C** pour gérer les dossiers universitaires d'une promotion d'étudiants en BUT Informatique à l'aide d'un interpréteur de commandes.

## Fonctionnalités

Le programme fonctionne comme un interpréteur qui lit les commandes depuis l'entrée standard et affiche les résultats sur la sortie standard. Il respecte les règles de scolarité officielles du diplôme (validation des modules, compensation, jurys et passage à l'année supérieure).

L'application gère :

* **Étudiants** : Inscription, démission et défaillance.
* **Notes** : Saisie des notes (0-20) pour les 6 Unités d'Enseignement (UE) de chaque semestre.
* **Relevés de notes** : Affichage du cursus académique, calcul des moyennes (RCUE) et attribution des codes de décision (ADM, AJ, ADC, etc.).
* **Jurys** : Validation automatique pour les semestres impairs et logique de délibération pour les semestres pairs (passage ou redoublement).
* **Bilans** : Génération de résumés statistiques annuels pour la promotion.

## Commandes prises en charge

Le projet interprète les 9 commandes suivantes.
*> Remarque : Les mots-clés doivent être saisis en français, comme spécifié par les exigences du projet.*

| Mot-clé de la commande | Utilisation | Description |
| --- | --- | --- |
| `INSCRIRE` | `INSCRIRE <Prenom> <Nom>` | Inscrit un nouvel étudiant (Max 100). |
| `NOTE` | `NOTE <Id> <UE> <Note>` | Enregistre une note pour une Unité d'Enseignement (UE) spécifique. |
| `CURSUS` | `CURSUS <Id>` | Affiche le relevé de notes complet et le statut d'un étudiant. |
| `DEMISSION` | `DEMISSION <Id>` | Marque un étudiant comme démissionnaire. |
| `DEFAILLANCE` | `DEFAILLANCE <Id>` | Marque un étudiant comme défaillant (en raison d'absences injustifiées). |
| `JURY` | `JURY <Semestre>` | Exécute le processus de jury pour un semestre donné (1 à 6). |
| `ETUDIANTS` | `ETUDIANTS` | Liste tous les étudiants et leur statut actuel. |
| `BILAN` | `BILAN <Annee>` | Affiche le bilan statistique pour une année spécifique (1, 2 ou 3). |
| `EXIT` | `EXIT` | Termine le programme. |

## Spécifications techniques

* **Langage** : C
* **Structure de données** : Utilisation de `struct` pour la gestion des étudiants et de la promotion afin d'optimiser l'utilisation de la mémoire.
* **Contraintes** : Prend en charge jusqu'à 100 étudiants ; Prénoms/Noms limités à 30 caractères.
* **Précision** : Les notes sont stockées en `float` mais affichées avec une décimale tronquée (sans arrondi).
