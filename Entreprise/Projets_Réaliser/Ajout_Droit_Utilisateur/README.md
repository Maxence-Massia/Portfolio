# 📁 Ajout de droits d'accès à des dossiers réseau

## 🛠️ Contexte

Dans le cadre de mon alternance au sein du **Service Desk (SDK)**, je traite quotidiennement des tickets relatifs à l’**ajout de droits d’accès à des dossiers réseau** pour les utilisateurs. Ces demandes concernent généralement l’accès à des fichiers partagés sur les serveurs de l’organisation.

## 📌 Exemple de situation

Un **chef de département du COMSIC** (Commandement des Systèmes d’Information et de Communication) souhaite partager un dossier réseau récemment créé sur l’un des serveurs avec ses collaborateurs.

Pour cela :
- Il soumet un **ticket** de demande d’accès via DIADEM.
- Il précise les **utilisateurs concernés**, le **type de droits** à appliquer (lecture seule, modification, contrôle total), ainsi que le **chemin d’accès réseau** du dossier partagé (exemple : `\\serveur08\Comsic\PartageProjet`).

## 🔧 Traitement technique

En tant que technicien SDK :
- Je récupère les informations fournies dans le ticket.
- J’accède à la console **Active Directory (AD)** pour ajouter les utilisateurs concernés au **groupe de sécurité** lié au dossier partagé.
- Je m’assure que les **permissions NTFS et les partages réseau** sont correctement configurés sur le serveur.
- Je vérifie l’accessibilité du chemin depuis un poste utilisateur.

## ✅ Résultat

Une fois le traitement terminé, les utilisateurs ciblés peuvent accéder au dossier via l’explorateur de fichiers à l’aide du chemin réseau fourni.  
L’accès est sécurisé, centralisé et conforme aux bonnes pratiques de gestion des droits.

---

## 🧠 Compétences mobilisées

- Utilisation avancée d’**Active Directory**
- Gestion des **groupes de sécurité et des partages réseau**
- Rigueur dans la **sécurité des accès** et la documentation des interventions
- Communication claire avec les utilisateurs pour valider les droits accordés

