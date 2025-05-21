# 📸 Caméra Connectée

**Gérez votre caméra à distance via une web app sécurisée et intuitive !**

## 🚀 À propos

**Caméra Connectée** est une solution pour contrôler une caméra via une web app PHP et une API Flask, avec une infrastructure moderne et sécurisée grâce à Cloudflare Tunnel.

---

## 🌟 Fonctionnalités

- 🎥 Streaming vidéo en direct.
- 🕹️ Contrôle à distance (démarrer/arrêter).
- 🖥️ Interface web intuitive.
- 🔒 Communications chiffrées, zéro port ouvert.

---

## 🏗️ Infrastructure 🔥

L'infrastructure est le cœur de ce projet, conçue pour allier **sécurité**, **flexibilité** et **performance** :

- **Architecture distribuée** : Séparation nette entre le **frontend** (PHP sur AlwaysData) et le **backend** (API Flask hébergée localement, ex. Raspberry Pi), garantissant modularité et résilience.
- **Cloudflare Tunnel** : Connecte l’API locale au web via un tunnel sécurisé, sans ouvrir de ports sur votre réseau. Les requêtes passent par le réseau Cloudflare, avec chiffrement de bout en bout et protection DDoS.
- **Frontend hébergé** : Web app PHP sur AlwaysData, optimisée pour l’accessibilité et la scalabilité, avec un pattern MVC et Twig pour une UI fluide.
- **Backend local** : API Flask sur un serveur local (Raspberry Pi, PC), gérant la caméra et les données avec une empreinte légère.
- **Base de données** : MySQL sur AlwaysData, stockant utilisateurs, configs et journaux, avec accès sécurisé depuis le frontend et le backend.
- **Caméra connectée** : Intégration flexible via HTTP, RTSP ou MQTT, adaptable à divers modèles de caméras.

Cette infra garantit une **sécurité maximale** (zéro exposition directe du serveur local) et une **expérience utilisateur fluide**, même sur des réseaux domestiques.

---

## 🛠️ Technologies

| **Composant** | **Technologies**                     |
|---------------|--------------------------------------|
| Frontend      | PHP, MVC, Twig, Composer, AlwaysData |
| Backend       | Python, Flask, pip, Cloudflare Tunnel|
| Base de données | MySQL                              |
| Caméra        | RTSP/HTTP/MQTT                     |

---

## 📖 Installation

### Prérequis
- Compte Cloudflare + domaine.
- Serveur PHP (AlwaysData).
- Serveur local (Raspberry Pi/PC).
- Python 3.x, pip, PHP 7.x+, Composer.
- (Optionnel) Broker MQTT.

### 1. API Backend
1. Clonez : `git clone [URL_API] && cd [DOSSIER_API]`
2. Dépendances : `pip install -r requirements.txt`
3. Cloudflare Tunnel :
   - Installez `cloudflared` ([doc](https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/)).
   - Lancez : `cloudflared tunnel run [TUNNEL_UUID]`
   - Configurez `api.mondomaine.com` → `http://localhost:5000`.
4. Lancez Flask : 
   ```bash
   export FLASK_APP=app.py
   flask run --host=0.0.0.0 --port=5000

   ### 2. Web App
1. Transférez dépôt PHP sur AlwaysData (FTP/git).
2. Configurez `public/` comme racine.
3. Dépendances : `composer install`
4. URL API : `define('API_BASE_URL', 'https://api.mondomaine.com');` dans `config/app.php`.
5. Configurez variables MySQL (doc AlwaysData).

### 3. Base de données
1. Créez base MySQL sur AlwaysData.
2. Appliquez schémas SQL (phpMyAdmin/script).
3. Mettez à jour identifiants MySQL.

### 4. Caméra
1. Configurez caméra pour envoyer données à l’API (Cloudflare URL/MQTT).
2. Implémentez logique (RTSP/MQTT) dans Flask.

---

## 🚀 Utilisation
1. Accédez à la web app (AlwaysData).
2. Connectez-vous/créez compte.
3. Contrôlez caméra et visualisez flux.

---

## 🤝 Contribuer
1. Forkez dépôt.
2. Branche : `git checkout -b feature/ma-fonction`.
3. Commit : `git commit -m 'Ajout fonctionnalité'`.
4. Push : `git push origin feature/ma-fonction`.
5. Pull Request.

---

## 📜 TAGUINE Tarek
