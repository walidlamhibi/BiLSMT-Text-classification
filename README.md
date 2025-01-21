
# Classification de Texte avec BiLSTM

Ce projet implémente un modèle **BiLSTM (Bidirectional Long Short-Term Memory)** pour la classification automatique de textes en quatre catégories :

- **World (Monde)**
- **Sports**
- **Business (Affaires)**
- **Sci/Tech (Science/Tech)**

## Objectif
L'objectif principal est de construire un modèle performant pour catégoriser des articles d'actualités en fonction de leur contenu textuel.

## Données
Le dataset utilisé provient de [AG News Classification](https://www.kaggle.com/datasets/amananandrai/ag-news-classification-dataset). 

### Caractéristiques des données :
- **120 000 articles pour l'entraînement.**
- **7 600 articles pour le test.**
- Chaque article contient :
  - `Title` : Le titre de l'article.
  - `Description` : Un résumé de l'article.
  - `Class Index` : La catégorie (0 : World, 1 : Sports, 2 : Business, 3 : Sci/Tech).

## Méthodologie
1. **Prétraitement des données** :
   - Combinaison des colonnes `Title` et `Description` pour enrichir le texte.
   - Nettoyage des données (suppression des caractères spéciaux, conversion en minuscules).
   - Conversion du texte en séquences numériques à l'aide d'un **Tokenizer**.
   - Normalisation des séquences avec du padding (longueur max : 300).

2. **Construction du modèle BiLSTM** :
   - **Embedding Layer** : Représentation vectorielle des mots.
   - **Bidirectional LSTM** : Capture des relations contextuelles dans les deux sens.
   - **Dense Layers** : Extraire des relations complexes.
   - **Output Layer** : Prédiction des 4 classes via Softmax.

3. **Entraînement et validation** :
   - Optimiseur : **Adam**.
   - Fonction de perte : **Categorical Crossentropy**.
   - Entraînement sur 15 époques avec un batch size de 64.

4. **Déploiement d'une interface utilisateur** :
   - Utilisation de **Streamlit** pour permettre aux utilisateurs de tester le modèle avec leurs propres textes.

## Résultats
- **Précision d'entraînement** : ~95%
- **Précision de validation/test** : ~80-85%

## Installation
1. Clonez le projet :
   ```bash
   git clone https://github.com/username/bilstm-text-classification.git
   cd bilstm-text-classification
   ```
2. Installez les dépendances :
   ```bash
   pip install -r requirements.txt
   ```
3. Lancez l'application :
   ```bash
   streamlit run app.py
   ```

## Utilisation
1. Saisissez un texte dans l'interface utilisateur Streamlit.
2. Cliquez sur le bouton pour prédire la catégorie.
3. Visualisez la classe prédite et les probabilités associées.

## Structure du Projet
```
|-- app.py                 # Script de l'application Streamlit
|-- model.h5               # Modèle BiLSTM sauvegardé
|-- tokenizer.pkl          # Tokenizer sauvegardé
|-- requirements.txt       # Liste des dépendances
|-- README.md              # Documentation du projet
```

## Améliorations possibles
- Intégrer des embeddings pré-entraînés comme **GloVe** ou **Word2Vec**.
- Étendre le projet pour inclure plus de catégories ou d'autres langues.
- Déployer l'application en ligne avec **Streamlit Cloud** ou **Heroku**.

## Auteur
**Walid** - _Casablanca, Maroc_
