# 🧠 Classification des sentiments en arabe dialectal

> Projet de **traitement de données, NLP et Machine Learning** visant à analyser des textes en arabe dialectal et à classifier les sentiments exprimés.

---

## 📌 Présentation

Ce projet porte sur le **traitement et l'analyse de données textuelles en arabe dialectal** afin de mettre en place une approche de **classification automatique des sentiments**.

L'objectif est de transformer des données textuelles brutes en un dataset propre et exploitable, puis d'utiliser des techniques de **Natural Language Processing (NLP)** et de **Machine Learning** pour identifier automatiquement le sentiment associé à un texte.

Le projet couvre plusieurs étapes :

* exploration des données ;
* nettoyage des données ;
* préparation des textes ;
* traitement des labels ;
* transformation des données ;
* préparation pour le Machine Learning ;
* classification des sentiments ;
* évaluation des résultats.

---

# 🎯 Objectifs du projet

Les principaux objectifs sont :

* analyser un dataset contenant des textes en arabe dialectal ;
* comprendre la structure et la qualité des données ;
* nettoyer et préparer les données textuelles ;
* traiter les labels associés aux textes ;
* construire un dataset final exploitable ;
* appliquer des techniques de NLP ;
* entraîner un modèle de Machine Learning pour la classification ;
* évaluer les performances du modèle ;
* analyser les résultats obtenus.

---

# 🧠 Problématique

L'analyse automatique des sentiments permet d'identifier l'opinion exprimée dans un texte.

Dans le cas de l'arabe dialectal, cette tâche est particulièrement intéressante car les textes peuvent présenter :

* plusieurs dialectes ;
* des différences d'orthographe ;
* des caractères arabes et latins ;
* des abréviations ;
* des répétitions de caractères ;
* des emojis ;
* des expressions propres au langage courant ;
* des variations importantes entre l'arabe standard et l'arabe dialectal.

Le projet cherche donc à construire un processus permettant de **préparer ces données et de les exploiter pour la classification des sentiments**.

---

# 🏗️ Architecture complète du projet

L'architecture du projet suit un pipeline de traitement de données et de Machine Learning :

```text
                         ┌──────────────────────┐
                         │     DATASET BRUT     │
                         │                      │
                         │   data_brute.csv     │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │ Exploration des     │
                         │ données              │
                         │                      │
                         │ Pandas / NumPy       │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │ Nettoyage des        │
                         │ données              │
                         │                      │
                         │ • Texte              │
                         │ • Labels             │
                         │ • Doublons           │
                         │ • Valeurs manquantes │
                         └──────────┬───────────┘
                                    │
                                    ▼
                    ┌──────────────────────────────┐
                    │ cleaned_labels_posts.csv    │
                    │                              │
                    │    Données nettoyées         │
                    └──────────────┬───────────────┘
                                   │
                                   ▼
                         ┌──────────────────────┐
                         │ Prétraitement NLP    │
                         │                      │
                         │ • Nettoyage texte    │
                         │ • Normalisation      │
                         │ • Préparation        │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │ Préparation pour ML  │
                         │                      │
                         │ Vectorisation        │
                         │ Features             │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │    final_data.csv    │
                         │                      │
                         │   Dataset final      │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │ Machine Learning     │
                         │                      │
                         │ Classification       │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │      Évaluation      │
                         │                      │
                         │ Accuracy             │
                         │ Precision            │
                         │ Recall               │
                         │ F1-score             │
                         └──────────────────────┘
```

---

# 🔄 Pipeline de traitement

Le processus global peut être résumé comme suit :

```text
Données brutes
      │
      ▼
Exploration
      │
      ▼
Nettoyage
      │
      ▼
Prétraitement NLP
      │
      ▼
Transformation
      │
      ▼
Dataset final
      │
      ▼
Machine Learning
      │
      ▼
Classification
      │
      ▼
Évaluation
```

---

# 📊 Données

Le projet utilise plusieurs versions du dataset afin de conserver les différentes étapes de transformation.

## 1. `data_brute.csv`

Ce fichier contient les **données brutes originales**.

Il représente le point de départ du pipeline.

```text
data_brute.csv
      │
      ▼
Exploration
      │
      ▼
Nettoyage
```

---

## 2. `cleaned_labels_posts.csv`

Ce fichier contient les données après une première étape de **nettoyage et de préparation**.

Cette étape permet de travailler notamment sur :

* la qualité des données ;
* les textes ;
* les labels ;
* les valeurs manquantes ;
* les doublons ;
* les données incohérentes.

```text
data_brute.csv
      │
      ▼
Nettoyage
      │
      ▼
cleaned_labels_posts.csv
```

---

## 3. `final_data.csv`

Ce fichier représente le **dataset final préparé pour les étapes d'analyse et de classification**.

```text
cleaned_labels_posts.csv
          │
          ▼
Prétraitement
          │
          ▼
Transformation
          │
          ▼
final_data.csv
```

---

# 🧹 Prétraitement des données

Le prétraitement constitue une étape essentielle du projet.

Les données textuelles peuvent contenir différents éléments qui peuvent perturber l'apprentissage :

* ponctuation ;
* espaces inutiles ;
* caractères spéciaux ;
* chiffres ;
* URLs ;
* emojis ;
* répétitions ;
* variations d'écriture ;
* données manquantes.

Le processus de nettoyage vise à produire des données plus homogènes et adaptées aux étapes suivantes.

### Pipeline de nettoyage

```text
Texte brut
    │
    ▼
Suppression du bruit
    │
    ▼
Nettoyage
    │
    ▼
Normalisation
    │
    ▼
Texte préparé
```

---

# 🗣️ Natural Language Processing

Le projet utilise des techniques de **Natural Language Processing (NLP)** afin de transformer les textes en données exploitables par les algorithmes de Machine Learning.

Le pipeline NLP peut être représenté comme suit :

```text
                Texte arabe dialectal
                         │
                         ▼
                   Prétraitement
                         │
                         ▼
                    Nettoyage
                         │
                         ▼
                   Normalisation
                         │
                         ▼
                Représentation numérique
                         │
                         ▼
                  Modèle Machine Learning
```

---

# 🔤 Transformation du texte

Les algorithmes de Machine Learning ne peuvent pas directement exploiter une phrase sous forme de texte.

Les textes doivent donc être convertis en **représentations numériques**.

Une approche classique pour cette tâche est la **vectorisation TF-IDF**.

```text
Texte
  │
  ▼
Tokenisation
  │
  ▼
Termes
  │
  ▼
TF-IDF
  │
  ▼
Vecteur numérique
  │
  ▼
Modèle ML
```

## TF-IDF

TF-IDF permet de représenter les textes sous forme numérique en attribuant un poids aux termes selon leur importance dans les documents.

Cette représentation peut ensuite être utilisée comme entrée pour les modèles de classification.

---

# 🤖 Machine Learning

Après le traitement des textes, les données peuvent être utilisées pour entraîner un modèle de **classification supervisée**.

Le principe général est :

```text
                    Dataset final
                         │
                         ▼
                Séparation des données
                         │
                 ┌───────┴───────┐
                 │               │
                 ▼               ▼
              Training          Test
                 │               │
                 ▼               │
          Entraînement            │
                 │               │
                 ▼               │
              Modèle ────────────┘
                 │
                 ▼
             Prédictions
                 │
                 ▼
             Évaluation
```

Le projet utilise **Scikit-learn** pour les étapes de Machine Learning.

---

# 😊 Classification des sentiments

Le but final est de déterminer automatiquement le sentiment exprimé dans un texte.

Le problème peut être représenté comme :

```text
                  Texte arabe
                       │
                       ▼
                 Prétraitement
                       │
                       ▼
                  Vectorisation
                       │
                       ▼
                Modèle ML entraîné
                       │
                       ▼
                  Classification
                       │
            ┌──────────┼──────────┐
            ▼          ▼          ▼
         Positif     Neutre     Négatif
```

Les catégories exactes utilisées dépendent des labels présents dans le dataset final.

---

# 📈 Évaluation

L'évaluation permet de mesurer la qualité des prédictions du modèle.

Les principales métriques utilisées pour une classification sont :

### Accuracy

Mesure la proportion de prédictions correctes parmi toutes les prédictions.

```text
Accuracy =
Prédictions correctes
────────────────────
Prédictions totales
```

### Precision

La précision mesure la proportion des exemples prédits comme appartenant à une classe qui appartiennent réellement à cette classe.

### Recall

Le rappel mesure la capacité du modèle à identifier les exemples appartenant réellement à une classe.

### F1-score

Le F1-score combine la précision et le rappel.

```text
F1 = 2 × Precision × Recall
          ──────────────────
          Precision + Recall
```

---

# 📊 Matrice de confusion

La matrice de confusion permet d'analyser les erreurs de classification.

```text
                       Classe prédite
                  ┌────────┬────────┬────────┐
                  │ Positif│ Neutre │ Négatif│
        ┌─────────┼────────┼────────┼────────┤
        │ Positif │   ✓    │   ✗    │   ✗    │
Classe  ├─────────┼────────┼────────┼────────┤
réelle  │ Neutre  │   ✗    │   ✓    │   ✗    │
        ├─────────┼────────┼────────┼────────┤
        │ Négatif │   ✗    │   ✗    │   ✓    │
        └─────────┴────────┴────────┴────────┘
```

Elle permet notamment d'identifier les classes qui sont fréquemment confondues par le modèle.

---

# 📓 Notebook principal

## `Projet_traitement_de_données.ipynb`

Le notebook constitue le **cœur du projet**.

Il permet de suivre les différentes étapes du traitement des données et de l'analyse.

### Contenu général

```text
Projet_traitement_de_données.ipynb
│
├── Importation des bibliothèques
│
├── Chargement des données
│
├── Exploration du dataset
│
├── Nettoyage
│
├── Prétraitement
│
├── Transformation des données
│
├── Analyse
│
├── Machine Learning
│
├── Classification
│
└── Évaluation
```

---

# 📂 Structure du repository

La structure réelle du repository est organisée autour du notebook, des datasets et du rapport.

```text
Projet-traitement-de-donn-es/
│
├── 📓 Projet_traitement_de_données.ipynb
│
├── 📊 data_brute.csv
│
├── 🧹 cleaned_labels_posts.csv
│
├── 🏷️ final_data.csv
│
├── 📄 rapport du projet.docx
│
└── 📖 README.md
```

---

# 📄 Rapport du projet

## `rapport du projet.docx`

Le rapport présente la démarche complète du projet.

Il permet notamment de documenter :

* le contexte ;
* la problématique ;
* les données ;
* la méthodologie ;
* le traitement des données ;
* les techniques utilisées ;
* les résultats ;
* les conclusions.

Le rapport complète le travail réalisé dans le notebook.

---

# 🔬 Méthodologie

La méthodologie suivie est composée de plusieurs étapes.

### Étape 1 — Exploration

Analyse initiale des données afin de comprendre :

* leur structure ;
* leur volume ;
* les différentes colonnes ;
* les types de données ;
* les labels ;
* les valeurs manquantes.

### Étape 2 — Nettoyage

Suppression ou traitement des données problématiques.

### Étape 3 — Prétraitement NLP

Préparation des textes pour l'analyse automatique.

### Étape 4 — Transformation

Conversion des textes en représentations numériques.

### Étape 5 — Machine Learning

Entraînement d'un modèle de classification.

### Étape 6 — Évaluation

Analyse des performances du modèle à l'aide de plusieurs métriques.

### Étape 7 — Analyse des résultats

Interprétation des résultats et identification des éventuelles limites.

---

# 🛠️ Technologies utilisées

| Catégorie           | Technologie                 |
| ------------------- | --------------------------- |
| Langage             | Python                      |
| Data Processing     | Pandas                      |
| Calcul scientifique | NumPy                       |
| Machine Learning    | Scikit-learn                |
| Domaine             | Natural Language Processing |
| Données             | CSV                         |
| Analyse             | Jupyter Notebook            |
| Documentation       | Microsoft Word              |

---

# 🐍 Installation

## Prérequis

* Python 3.x
* Jupyter Notebook ou JupyterLab
* pip

---

## 1. Cloner le repository

```bash
git clone https://github.com/RouaBenTiba/Projet-traitement-de-donn-es.git
```

Puis :

```bash
cd Projet-traitement-de-donn-es
```

---

## 2. Créer un environnement virtuel

### Windows

```bash
python -m venv venv
```

Activer l'environnement :

```bash
venv\Scripts\activate
```

### Linux / macOS

```bash
python3 -m venv venv
```

Puis :

```bash
source venv/bin/activate
```

---

## 3. Installer les bibliothèques

```bash
pip install pandas numpy scikit-learn jupyter
```

---

# ▶️ Exécution du projet

Lancer Jupyter Notebook :

```bash
jupyter notebook
```

Puis ouvrir :

```text
Projet_traitement_de_données.ipynb
```

Exécuter ensuite les cellules du notebook dans l'ordre.

Les fichiers CSV nécessaires au traitement sont présents dans le repository.

---

# 🔄 Reproductibilité

Le projet conserve plusieurs versions des données afin de permettre de suivre le processus de transformation :

```text
data_brute.csv
      │
      ▼
cleaned_labels_posts.csv
      │
      ▼
final_data.csv
```

Cette organisation permet de distinguer :

* les données originales ;
* les données nettoyées ;
* les données finales utilisées pour l'analyse.

Le notebook contient les principales étapes permettant de reproduire le traitement.

---

# 📚 Fichiers du projet

| Fichier                              | Description                  |
| ------------------------------------ | ---------------------------- |
| `Projet_traitement_de_données.ipynb` | Notebook principal du projet |
| `data_brute.csv`                     | Dataset brut                 |
| `cleaned_labels_posts.csv`           | Dataset nettoyé              |
| `final_data.csv`                     | Dataset final                |
| `rapport du projet.docx`             | Rapport détaillé du projet   |
| `README.md`                          | Documentation du projet      |

---

# 📅 Période du projet

**Janvier 2026 – Mai 2026**

Projet consacré au traitement de données et à la classification des sentiments dans des textes en arabe dialectal.

---

# 🎓 Compétences développées

Ce projet a permis de développer des compétences dans les domaines suivants :

### Data

* Data Cleaning
* Data Processing
* Data Exploration
* Data Preparation

### NLP

* Text Preprocessing
* Text Classification
* Traitement de textes en arabe dialectal
* Feature Extraction
* Vectorisation

### Machine Learning

* Classification supervisée
* Training / Testing
* Model Evaluation
* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix

### Python

* Pandas
* NumPy
* Scikit-learn
* Jupyter Notebook



### Application

Le modèle pourrait également être transformé en une application permettant à un utilisateur d'entrer une phrase en arabe dialectal et d'obtenir automatiquement son sentiment.

```text
┌──────────────────────┐
│  Utilisateur         │
│                      │
│ "Texte arabe..."     │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│ Prétraitement NLP    │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│ Modèle ML            │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│ Sentiment prédit     │
│                      │
│ 😊 Positif           │
│ 😐 Neutre            │
│ 😞 Négatif           │
└──────────────────────┘
```

---

# 👩‍💻 Auteur

**Roua Tiba**

Software Engineering Student
**Data • NLP • Machine Learning • AI**

GitHub : **RouaBenTiba**

---

## ⭐ Projet

Ce projet constitue une mise en pratique de techniques de **Data Processing, Natural Language Processing et Machine Learning** appliquées à des données textuelles en **arabe dialectal**.
