# 🖥️ Migration Windows 10 → Windows 11 en Environnement d’Entreprise

## 🧠 Objectif de la mission
Assurer la migration complète du parc informatique de Windows 10 vers Windows 11, malgré de nombreuses erreurs de mise à jour rencontrées sur les postes utilisateurs.  
La mission s’est déroulée sur **plus d’un mois**, avec un travail important de diagnostic, de préparation et de déploiement.

## 🏢 Contexte professionnel
L’entreprise utilise une architecture basée sur :
- Un **serveur CAS** (serveur primaire central, point d’entrée principal du parc)
- Plusieurs **serveurs secondaires** répartis en France
- Un environnement de gestion du parc via **Microsoft Endpoint Configuration Manager (MECM)**

L’ensemble permet de déployer des mises à jour, logiciels et configurations aux postes utilisateurs.

## 🔧 Problèmes rencontrés
Durant la migration, de nombreux postes Windows 10 rencontraient :
- Des **erreurs de mise à jour Windows**
- Des **échecs d’installation de Windows 11**
- L’impossibilité pour MECM de pousser correctement la mise à niveau

Ces dysfonctionnements empêchaient l’avancement global du projet.

## 🛠️ Solution mise en œuvre

### 1️⃣ Réception de la mise à jour directement depuis Microsoft  
L’équipe a reçu un **correctif officiel** fourni par Microsoft pour fiabiliser le passage à Windows 11.  
Cette mise à jour devait être intégrée dans l’infrastructure MECM.

### 2️⃣ Intégration du correctif dans MECM  
Nous avons :
- Récupéré le package de mise à jour
- Transféré celui-ci **via FTP** sur le serveur CAS
- Importé le correctif dans MECM pour qu’il puisse être distribué

### 3️⃣ Configuration du serveur CAS pour le déploiement  
Le serveur CAS effectue chaque jour des déploiements de mises à jour logicielles.  
Pour cette migration, il a fallu :
- **Indiquer manuellement** l’emplacement du correctif afin qu’il soit pris en charge
- Vérifier l’association du package avec les bons groupes de déploiement

### 4️⃣ Relance des politiques de déploiement  
Une fois la mise à jour intégrée :
- La **politique de mise à jour** du CAS a été relancée
- Le CAS a ensuite propagé le correctif vers les **serveurs secondaires**
- Enfin, les **postes utilisateurs** ont pu recevoir la mise à jour Windows 11

## ✅ Résultats & enseignements
- La migration a pu reprendre et aboutir grâce à l’intégration manuelle du correctif Microsoft.  
- Le fonctionnement en **chaîne CAS → secondaires → postes** a été validé.  
- L’utilisation de MECM et la compréhension du déploiement distribué ont été renforcées.  
- Cette intervention a permis d’améliorer la stabilité globale du processus de migration.


