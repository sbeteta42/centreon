# 🖥️ Script d'Installation Autonome Centreon
Un script Bash automatisé pour installer et configurer Centreon sur Debian 12 avec MariaDB local.

# 📋 Prérequis

- **OS:** Debian 12 (Bookworm)
- **RAM:** Minimum 1 GB recommandé
- **Espace disque:** Au moins 20 GB libres
- **Accès:** Privilèges sudo ou root
- **Réseau:** Connexion Internet active

# 🚀 Installation Rapide

wget https://raw.githubusercontent.com/[votre-username]/centreon-auto-install/main/install_centreon.sh

# Rendre exécutable
chmod +x install_centreon.sh

# Lancer l'installation
sudo ./install_centreon.sh

# ⚙️ Fonctionnalités

✅ Installation complète de Centreon 24.10
✅ Configuration MariaDB avec sécurisation
✅ Activation automatique des services
✅ Configuration SNMP pour auto-supervision
✅ Installation des plugins de supervision
✅ Configuration réseau optimisée

# 🔧 Configuration Post-Installation

**Interface Web:** Accédez à http://[IP-SERVEUR]/centreon
Utilisateur: admin
Mot de passe: AdminPassword123!

Base de données:
Utilisateur root: root
Mot de passe: MotDePasseSecurise123!

# 📖 Guide d'Utilisation
1. Assistant Web
Suivez l'assistant d'installation web avec les paramètres pré-configurés du script.
2. Export de Configuration
Après ajout d'hôtes, exportez toujours la configuration :

Configuration > Collecteurs > Collecteurs
Sélectionner "Central" → "Exporter la configuration"

3. Supervision SNMP
Le serveur est pré-configuré pour s'auto-superviser :

Communauté SNMP: public
Port: 161/UDP

🛠️ Personnalisation
Modifiez les variables en début de script :
bashHOSTNAME="central"                          # Nom du serveur
DB_ROOT_PASSWORD="VotreMotDePasse"         # Mot de passe MariaDB
CENTREON_ADMIN_USER="admin"                # Utilisateur admin
CENTREON_ADMIN_PASSWORD="VotrePassword"    # Mot de passe admin
🔍 Vérification
Vérifiez que tous les services sont actifs :
bashsudo systemctl status apache2 mariadb centreon cbd centengine
🚨 Sécurité
⚠️ Important: Ce script désactive temporairement le pare-feu. Réactivez-le après installation :
bashsudo systemctl enable ufw && sudo systemctl start ufw
sudo ufw allow 80/tcp    # Interface web Centreon
sudo ufw allow 161/udp   # SNMP
📚 Documentation

Documentation officielle Centreon
Guide SNMP Linux

🤝 Contribution
Les contributions sont les bienvenues ! N'hésitez pas à :

Signaler des bugs
Proposer des améliorations
Soumettre des pull requests

📄 Licence
Ce projet est sous licence MIT. Voir le fichier LICENSE pour plus de détails.
