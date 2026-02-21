# 🔁 TD – Mise en place d’une redondance réseau avec UCARP sous Linux

## 🧠 Objectif pédagogique du Lab
Ce TP a pour but de mettre en œuvre une solution de **haute disponibilité réseau (HA)** en utilisant l’outil **UCARP** sous Linux.  
L’objectif est d’assurer la continuité de service d’une adresse IP virtuelle même en cas de panne d’un des serveurs.

## 🎯 Objectifs pédagogiques — BTS SIO
| Bloc  | Compétence visée                                                                 |
|-------|-----------------------------------------------------------------------------------|
| B2.1  | Déployer un service réseau avec mécanisme de tolérance aux pannes                |
| B3.2  | Configurer et administrer un environnement Linux                                 |
| B3.4  | Mettre en place une solution de redondance (failover)                            |
| B4.1  | Diagnostiquer et tester la résilience d’un service réseau                        |

## 🖥️ Contexte technique
Trois machines Linux ont été utilisées :
- 🖥️ **PC1 (toi)** : rôle **MASTER UCARP**
- 🖥️ **PC2 & PC3 (collègues)** : rôle **SLAVE UCARP**

Chaque machine devait être configurée avec :
- La **même adresse IP virtuelle**
- Le **même masque de sous-réseau**
- La **même gateway**
- Le **même mot de passe UCARP**
- Le même *VHID* (Virtual Host ID)

Le fonctionnement est basé sur un protocole permettant de transférer automatiquement l’IP virtuelle d’un serveur à un autre en cas de panne.

Documentation utilisée :  
🔗 https://doc.ubuntu-fr.org/ucarp

## ⚙️ Installation & configuration
Chaque machine a reçu :
- L'installation d’UCARP (`sudo apt install ucarp`)
- La configuration d’un fichier UCARP maître/esclave
- Une IP virtuelle partagée entre les trois postes
- Un service Apache2 pour tester la bascule

Une fois UCARP configuré, chaque PC a mis en place une **page web personnalisée** pour identifier qui prenait le relais.

### 🔧 Pages Apache utilisées :
- **Toi (Master)** : *« Bienvenue chez Homer »*
- **Collègue 2** : *« Bienvenue chez les tocards »*
- **Collègue 3** : une **image de la Joconde encodée en hexadécimal**

Ces pages servaient à repérer immédiatement quel serveur possédait l'adresse IP virtuelle en cours.

## 🧪 Tests et scénarios de bascule

### 🟦 **Test 1 : Panne du MASTER**
Simulation : déconnexion réseau du PC maître (toi).

✔ Résultat :
- Les PC slaves (PC2 & PC3) reprennent automatiquement l’IP virtuelle.
- Les machines affichent les pages **des deux collègues**, mais **plus la tienne**.
- Preuve que la bascule fonctionne : l’IP virtuelle est montée sur un SLAVE.

### 🟩 **Test 2 : Panne du MASTER + d’un SLAVE**
Simulation : déconnexion de ton PC + du PC3.

✔ Résultat :
- Le seul service encore disponible est celui du **PC2**.
- L’IP virtuelle « migre » automatiquement sur lui.
- Le réseau reste fonctionnel malgré 2 machines hors service.

### 🎉 Conclusion
Ce TP a permis de vérifier :
- Le fonctionnement de la **redondance IP** avec UCARP  
- La **bascule automatique** (failover) entre MASTER ↔ SLAVE  
- La **résilience** du service Apache2 selon l’état du réseau  
- L’importance d’une configuration **strictement identique** entre les nœuds

Grâce à UCARP, l’adresse IP virtuelle reste **toujours disponible**, assurant une continuité de service même en cas d'interruption d’un ou plusieurs serveurs.

