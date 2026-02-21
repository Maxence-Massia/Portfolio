# 🌐 Certification Cisco CCNA – Cisco Certified Network Associate

## 🛠️ Contexte

j’ai suivi la formation menant à la certification **CCNA (Cisco Certified Network Associate)**. Il s’agit d’une certification reconnue internationalement, qui valide les compétences fondamentales en **administration, configuration et dépannage de réseaux informatiques**.

## 📦 TP 1 – Configuration d’une adresse de gestion sur un commutateur

Ce premier TP visait à configurer une **adresse IP de gestion** sur un commutateur Cisco (Catalyst 2960). Cette adresse permet un accès à distance via Telnet ou SSH. J’ai d’abord configuré les **paramètres de base** (hostname, mot de passe, interface VLAN 1), puis j’ai vérifié la **connectivité réseau** entre le PC et le switch à l’aide de commandes `ping` et `telnet`.

### ✅ Objectifs atteints
- Configuration d’une **interface VLAN** avec une IP de gestion.
- Accès à distance sécurisé via Telnet.
- Utilisation des commandes Cisco (`enable`, `config t`, `show run`, `copy run start`).
- Vérification du statut réseau via `show ip interface brief`.

---

## 🔄 TP 2 – Réinitialisation d’un routeur Cisco (mode ROMMON)

Ce TP m’a permis d’apprendre à **réinitialiser un routeur Cisco 1900** en cas d’oubli du mot de passe d’administration. En accédant au mode **ROMMON**,

### ✅ Étapes principales
- Accès au mode ROMMON via une combinaison de touches (`Ctrl + Break`).
- Modification du registre de configuration avec `confreg 0x2142`.
- Redémarrage (`reset`), reconfiguration et restauration avec `copy startup-config running-config`.
- Sauvegarde finale avec `write memory` et redémarrage (`reload`).


## 🧩 TP 3 – Configuration initiale d’un commutateur Cisco

Ce TP consistait à effectuer la **configuration de base d’un switch Cisco** en CLI via Packet Tracer. L’objectif était de sécuriser les accès, personnaliser l’environnement, et enregistrer la configuration pour garantir sa persistance.

### ⚙️ Étapes réalisées
- Vérification de la configuration par défaut (`show running-config`)
- Attribution d’un **nom d’hôte** au commutateur (hostname)
- Sécurisation de la **console** et du **mode privilégié** par mot de passe (`enable password`, `enable secret`)
- Application de la commande `service password-encryption` pour chiffrer les mots de passe
- Création d’une **bannière MOTD** pour avertir les utilisateurs non autorisés
- Sauvegarde de la configuration dans la **mémoire NVRAM** (`copy running-config startup-config`)

Cette configuration a ensuite été appliquée à un second commutateur (S2), en répliquant les paramètres de sécurité et de personnalisation.

### ✅ Objectifs atteints
- Sécurisation complète des accès locaux au switch
- Mise en œuvre d’un **mot de passe chiffré** via `enable secret`
- Mise en place d’une **bannière de sécurité** pour l’environnement CLI
- Sauvegarde de la configuration dans la NVRAM


