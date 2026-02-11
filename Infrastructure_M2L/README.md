# 🏢 Projet Infrastructure M2L – Maison des Ligues de Lorraine

## 📌 Présentation du projet

Dans le cadre de ma formation en **BTS SIO option SISR**, je réalise la conception et la mise en place d’une infrastructure réseau et serveurs pour la **Maison des Ligues de Lorraine (M2L)**.

Cette infrastructure simule un environnement d’entreprise complet permettant d’héberger plusieurs services virtualisés, avec segmentation réseau, routage, Wi-Fi sécurisé et supervision.

⚠️ L’infrastructure constitue le socle technique. Les projets (monitoring et autres) sont hébergés dessus mais ne font pas partie de son fonctionnement de base.

---

# 🌍 Architecture Réseau

## 🔢 Plan d’adressage

- Réseau principal : `172.16.3.0/24`
- Passerelle : `172.16.3.254`
- Hyperviseur 1 (PVE1) : `172.16.3.1`
- Hyperviseur 2 (PVE2) : `172.16.3.2`

DHCP :
- Service : `isc-dhcp-server`
- Distribution IP : plage 10 à 253
- DNS fournis : Google DNS

---

# 🔀 Routeur – Dell Optiplex 7010

- OS : Ubuntu Server
- Interface interne : `enp2s0`
- IP : `172.16.3.254`
- Utilisateur : `equipe3`
- Mot de passe : `claupe`

## Rôle :

- Routage réseau interne
- NAT (iptables – masquerade)
- IP forwarding activé
- DHCP interne
- Connexion au réseau école

Le routeur permet aux machines virtuelles et aux clients Wi-Fi d’accéder à Internet via le réseau de l’école.

---

# 🖥️ Serveurs Hyperviseurs – Proxmox

## 🧱 Serveur 1 – Dell PowerEdge R520 (PVE1)

- 96 Go RAM
- 4 disques
- RAID 0
- IP : `172.16.3.1`
- Mot de passe root : `louvre0`
- Interface virtuelle : `vmbr0` reliée à NIC1

### Distributions disponibles :
- Ubuntu Server
- Windows 11 25H2

---

## 🧱 Serveur 2 – Dell PowerEdge R430 (PVE2)

- 64 Go RAM
- 2 disques
- RAID 5
- IP : `172.16.3.2`
- Mot de passe root : `louvres0`

⚠️ Version Proxmox plus ancienne utilisée car la dernière version ne détectait pas le RAID 0 (compatibilité matérielle).

### Distributions disponibles :
- Ubuntu Server
- Windows 11 25H2

---

# 🌐 Infrastructure Réseau

## 🔌 Switch Cisco WS-C2960-24PC-L (PoE)

- VLAN 1 (défaut) : Fa0/1-9 + Gi0/1-2
- VLAN 2 : Fa0/10-15
- VLAN 3 : Fa0/16-24

Le switch permet :

- Segmentation réseau via VLAN
- Interconnexion des serveurs
- Alimentation du point d’accès en PoE

### 🔗 Câblage utilisé

- Câble Ethernet RJ45 Cat 5e / Cat 6
- PoE utilisé pour alimenter le point d’accès
- Câble console RS232 / USB pour configuration Cisco

Couleurs utilisées dans la maquette :
- Noir : AP
- Blanc tête verte : réseau école vers routeur
- Vert : routeur vers réseau interne
- Bleu : serveurs vers réseau interne

---

# 📡 Point d’accès Wi-Fi – Cisco AIR-CAP1702I-E-K9

- Alimenté via PoE (Power Over Ethernet)
- SSID : `equipe3`
- Mot de passe : `equipe03`
- Sécurité : WPA avec clé pré-partagée
- Chiffrement : AES
- Canal automatique (least-congested)

Configuration réalisée en CLI Cisco.

Le point d’accès permet aux clients Wi-Fi de rejoindre le réseau interne virtualisé.

---

# 🧠 Machines Virtuelles

Les hyperviseurs permettent de créer plusieurs VM :

- Ubuntu Server (services Linux)
- Windows 11 25H2 (environnement client / tests)

Les VM sont connectées au bridge `vmbr0` et intégrées au réseau interne 172.16.3.0/24.

---

# ⚙️ Fonctionnement Global

1. Les clients (filaire ou Wi-Fi) se connectent au switch.
2. Le switch segmente via VLAN.
3. Le routeur Ubuntu assure le routage + NAT.
4. Les serveurs Proxmox hébergent les machines virtuelles.
5. L’AP Wi-Fi étend le réseau interne en sans-fil.

---

# 🧠 Compétences SISR mises en œuvre

- Conception d’architecture réseau
- Virtualisation Proxmox
- Gestion RAID
- Routage Linux + NAT
- DHCP sous Linux
- VLAN Cisco
- Wi-Fi sécurisé WPA
- Gestion d’infrastructure complète
