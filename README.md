# API de Prédiction avec Flask et MLflow

Cette API Flask héberge un modèle de machine learning entraîné avec MLflow et fournit une route pour effectuer des prédictions basées sur des caractéristiques clients.

## 📌 Fonctionnalités
- Charger un modèle MLflow (LightGBM)
- Recevoir des caractéristiques clients en JSON
- Retourner une probabilité de crédit accepté/refusé

## 🚀 Déploiement sur Render
### 1️⃣ Prérequis
- Python 3.8+
- `pip install flask mlflow pandas lightgbm gunicorn`

### 2️⃣ Installation locale
```bash
# Cloner le projet
git clone https://github.com/votre-repo.git
cd votre-repo

# Installer les dépendances
pip install -r requirements.txt

# Lancer l'API
python app.py
```
L'API tournera sur `http://127.0.0.1:5000/`

### 3️⃣ Déploiement sur Render
1. Poussez votre code sur GitHub
2. Allez sur [Render](https://render.com/)
3. Créez un **nouveau service web**
4. Liez votre repo GitHub
5. Dans "Build Command", ajoutez :
   ```bash
   pip install -r requirements.txt
   ```
6. Dans "Start Command", ajoutez :
   ```bash
   gunicorn app:app --bind 0.0.0.0:$PORT
   ```
7. Déployez 🚀

## 📡 Utilisation de l'API
### 1️⃣ Tester l'API en local
#### Vérifier que l'API fonctionne :
```bash
curl http://127.0.0.1:5000/
```
#### Faire une prédiction :
```bash
curl -X POST "http://127.0.0.1:5000/predict" \
     -H "Content-Type: application/json" \
     -d '{"features": {"feature1": 0.5, "feature2": 1.2, "feature3": -0.7}}'
```

### 2️⃣ API en production
Une fois déployée sur Render, utilisez l'URL fournie :
```bash
curl -X POST "https://votre-api-render.com/predict" \
     -H "Content-Type: application/json" \
     -d '{"features": {"feature1": 0.5, "feature2": 1.2, "feature3": -0.7}}'
```

## 🛠️ Technologies utilisées
- Flask
- MLflow
- LightGBM
- Render (déploiement)

---
**Auteur** : Votre Nom | 📅 Date | 🔗 Contact


