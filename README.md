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
- 🧑‍💻**Connexion Inscription**
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
## 📜 TAGUINE Tarek
