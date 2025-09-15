# 📸 Caméra Connectée
*Gérez votre caméra à distance via une web app sécurisée et intuitive !*

---

## 🚀 À propos
**Caméra Connectée** est une solution complète pour contrôler une caméra en temps réel via :
- une **Web App PHP** hébergée en ligne,
- une **API Flask** locale, reliée au cloud par **Cloudflare Tunnel**.  

Cette architecture garantit **sécurité**, **flexibilité** et **performance**, sans ports ouverts sur votre réseau domestique.

---

## 🌟 Fonctionnalités
- 🎥 **Streaming vidéo en direct**  
- 🕹️ **Contrôle à distance** (démarrer / arrêter)  
- 🖥️ **Interface web intuitive et accessible**  
- 🔊 **Chat vocal bidirectionnel** via RTCP (parler/écouter en temps réel)  
- 🔒 **Communications chiffrées**, zéro exposition directe du serveur local  

---

## 🏗️ Infrastructure
L’infrastructure repose sur une séparation claire entre les composants :  

- **Architecture distribuée**  
  Frontend en PHP (AlwaysData) et backend en Python (API Flask locale).  
- **Cloudflare Tunnel**  
  Connecte l’API locale au web via un tunnel sécurisé, sans ouverture de ports.  
- **Frontend hébergé**  
  Web app PHP (MVC + Twig), accessible, scalable et performante.  
- **Backend local**  
  API Flask sur Raspberry Pi ou PC, gérant la caméra, l’audio et les données.  
- **Chat vocal en temps réel**  
  Communication audio bidirectionnelle entre le navigateur et la caméra/serveur.  
  Utilisation de **RTP/RTCP** pour la transmission et le contrôle des flux audio, garantissant faible latence et synchronisation avec la vidéo.  
- **Base de données**  
  MySQL (AlwaysData) pour utilisateurs, configurations et journaux.  
- **Caméra connectée**  
  Compatible HTTP ou RTSP → adaptable à différents modèles.  

---

## 🛠️ Technologies

| Composant      | Technologies                           |
|----------------|----------------------------------------|
| Frontend       | PHP 8+, MVC, Twig, Composer, AlwaysData |
| Backend        | Python 3, Flask, pip, Cloudflare Tunnel |
| Audio/Vidéo    | RTP / RTCP (flux bidirectionnels)       |
| Base de données| MySQL                                   |
| Caméra         | HTTP, RTSP                              |

---

## 📖 Installation

### 🔑 Prérequis
- Un **compte Cloudflare** + domaine configuré  
- Un **hébergement PHP** (ex : AlwaysData)  
- Un **serveur local** (Raspberry Pi ou PC)  
- **Python 3.x, pip, PHP 8.x+, Composer**  

---

### 1️⃣ API Backend (Flask)

```bash
# Clonez le dépôt
git clone [URL_API] && cd [DOSSIER_API]

# Installez les dépendances
pip install -r requirements.txt

# Configurez Cloudflare Tunnel
cloudflared tunnel run [TUNNEL_UUID]

# Exemple : api.mondomaine.com → http://localhost:5000

# Lancez Flask
export FLASK_APP=app.py
flask run --host=0.0.0.0 --port=5000
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
