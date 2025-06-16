# 🌐 Travaux pratiques Cisco – Gestion de commutateur et réinitialisation de routeur

## 🛠️ Contexte

Dans le cadre de mes travaux pratiques réseaux, j’ai manipulé des équipements Cisco (commutateur et routeur) afin de me familiariser avec les opérations courantes d’administration. Ces exercices ont été réalisés sur du matériel réel via des connexions console.

---

## 📦 TP 1 – Configuration d’une adresse de gestion sur un commutateur

Ce premier TP visait à configurer une **adresse IP de gestion** sur un commutateur Cisco (Catalyst 2960). Cette adresse permet un accès à distance via Telnet ou SSH. J’ai d’abord configuré les **paramètres de base** (hostname, mot de passe, interface VLAN 1), puis j’ai vérifié la **connectivité réseau** entre le PC et le switch à l’aide de commandes `ping` et `telnet`.

### ✅ Objectifs atteints
- Configuration d’une **interface VLAN** avec une IP de gestion.
- Accès à distance sécurisé via Telnet.
- Utilisation des commandes Cisco (`enable`, `config t`, `show run`, `copy run start`).
- Vérification du statut réseau via `show ip interface brief`.

---

## 🔄 TP 2 – Réinitialisation d’un routeur Cisco (mode ROMMON)

Ce TP m’a permis d’apprendre à **réinitialiser un routeur Cisco 1900** en cas d’oubli du mot de passe d’administration. En accédant au mode **ROMMON**, j’ai modifié le registre de configuration pour démarrer sans charger la configuration existante, puis réinitialisé le mot de passe, rechargé la config et sauvegardé les modifications.

### ✅ Étapes principales
- Accès au mode ROMMON via une combinaison de touches (`Ctrl + Break`).
- Modification du registre de configuration avec `confreg 0x2142`.
- Redémarrage (`reset`), reconfiguration et restauration avec `copy startup-config running-config`.
- Sauvegarde finale avec `write memory` et redémarrage (`reload`).

---

## 🧠 Compétences mobilisées

- Configuration et sécurisation d’un **commutateur Cisco**
- Utilisation des **interfaces console** pour accéder à des équipements réseau
- Réinitialisation et dépannage d’un **routeur Cisco** en mode ROMMON
- Maîtrise des **commandes IOS** de base (Cisco CLI)
- Compréhension du fonctionnement des **adresses de gestion réseau** et de l’accès distant

---

> Ces deux travaux pratiques m’ont permis de mieux comprendre la gestion physique des équipements Cisco, de consolider ma maîtrise de l’interface CLI, et d’acquérir des réflexes essentiels pour le support réseau.
