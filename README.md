# Projet : Chatbot basé sur un RAG

Système de RAG (Retrieval-Augmented Generation) simple qui répond aux questions des utilisateurs en s'appuyant sur un ensemble de pages Wikipedia portant sur l'IA générative.

## Créer le fichier .env

Créer le fichier `.env` à partir du fichier `.env.template` :

```
cp .env.template .env
```

Puis éditer le fichier `.env` pour y ajouter les informations nécessaires.

## Lancer l'application 

```
pip install -r requirements.txt

streamlit run app.py
```

## Construire l'image Docker

```
docker build -t rag-chatbot .
```

## Lancer le conteneur Docker

```
docker run --env-file=.env -p 8501:8501 rag-chatbot
```

Utiliser un volume persistant pour stocker les données du modèle :

```
docker run --env-file=.env -p 8501:8501 -v /vectorstore rag-chatbot
```