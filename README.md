# Icinga2 - Mise en place d'une solution de supervision réseau

## 📋 Description du projet  
Ce projet consiste à déployer et configurer la solution de supervision réseau **Icinga2** afin de surveiller les infrastructures réseau, détecter les anomalies, prévenir les pannes et améliorer la disponibilité des services.  

Icinga2 permet de suivre en temps réel l'état des équipements (serveurs, routeurs, commutateurs, etc.), les services (bases de données, applications web, services critiques, etc.), et les métriques de performance (latence, bande passante, espace disque, etc.).

---

## 🎯 Objectifs du projet  
- Déployer et configurer **Icinga2** sur un serveur dédié.  
- Superviser les ressources réseau critiques.  
- Mettre en place des notifications automatiques en cas de détection d'anomalies.  
- Assurer la visualisation en temps réel de l'état du réseau.  
- Améliorer la réactivité face aux incidents.

---

## 🛠️ Prérequis  
Avant de démarrer, assurez-vous d’avoir :  
1. Un serveur Linux compatible (ex. Debian, Ubuntu, CentOS).  
2. Les privilèges administrateur pour installer des paquets et configurer le système.  
3. Un accès SSH au serveur.  
4. Une base de données (MySQL/MariaDB, PostgreSQL) pour stocker les données de supervision.  
5. Les paquets nécessaires : `icinga2`, `icingaweb2`, `nagios-plugins`.  

---

## 📦 Installation et configuration d'Icinga2  

### 1. **Installation d'Icinga2**
   ```bash
   sudo apt update
   sudo apt install icinga2 icingaweb2 nagios-plugins
   ```

### 2. **Configuration d'Icinga2**
   - Démarrer le service Icinga2 :  
     ```bash
     sudo systemctl start icinga2
     sudo systemctl enable icinga2
     ```
   - Configurer les hôtes et les services à superviser en modifiant les fichiers de configuration dans `/etc/icinga2/conf.d/`.

### 3. **Configuration de la base de données**
   - Installer et configurer MySQL/MariaDB ou PostgreSQL.  
   - Créer une base de données pour Icinga2.  
   - Configurer la connexion dans `/etc/icinga2/features-enabled/ido-mysql.conf`.

### 4. **Installation d'Icinga Web 2**
   - Suivre les étapes de l’assistant d’installation (`/icingaweb2/setup`).  
   - Configurer les modules nécessaires (Monitoring, IDO, etc.).

---

## 🖥️ Utilisation  
Une fois l'installation terminée :  
- Accédez à l'interface web d'Icinga2 à l'adresse suivante :  
  `http://<adresse_du_serveur>/icingaweb2`  
- Connectez-vous avec vos identifiants.  
- Ajoutez des hôtes, des services et des règles de notifications via l'interface ou les fichiers de configuration.

---

## 🔧 Fonctionnalités principales  
- Surveillance en temps réel de l’état du réseau et des services.  
- Notifications par email, SMS ou autres canaux en cas de problème.  
- Graphiques et rapports sur les performances du réseau.  
- Possibilité d’intégration avec d’autres outils (Grafana, Prometheus, etc.).

---

## 🚨 Résolution des problèmes courants  
### Erreur : "Connection refused on port 5665"  
- Vérifiez que le service Icinga2 est en cours d'exécution :  
  ```bash
  sudo systemctl status icinga2
  ```
- Assurez-vous que le pare-feu autorise le port 5665 :  
  ```bash
  sudo ufw allow 5665
  ```

### Erreur de connexion à la base de données  
- Vérifiez les identifiants de connexion dans le fichier `ido-mysql.conf`.  
- Vérifiez que le service de base de données est en cours d'exécution.

---

## 📚 Documentation complémentaire  
- [Documentation officielle Icinga2](https://icinga.com/docs/icinga2/latest/)  
- [Icinga Web 2 Documentation](https://icinga.com/docs/icingaweb2/latest/)  
- [Plugins Nagios](https://www.nagios-plugins.org/)  

---

## ✍️ Auteur  
Projet réalisé par **Fatih KILIC**, Alternant Téchnicien Système et Réseaux, dans le cadre de la mission de supervision réseau.

---

## 📄 Licence  
Ce projet est sous licence GPL.
