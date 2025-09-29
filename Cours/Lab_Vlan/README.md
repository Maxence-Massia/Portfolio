# 📘 TD – Packet Tracer : Configuring VLANs

## 🎯 Objectifs pédagogiques — BTS SIO
| Bloc  | Compétence visée                                                                 |
|-------|-----------------------------------------------------------------------------------|
| B2.1  | Mettre en place un réseau local virtuel pour segmenter le trafic                 |
| B3.1  | Configurer et administrer un switch Cisco                                        |
| B3.2  | Mettre en œuvre la QoS pour la voix sur IP                                       |
| B4.1  | Diagnostiquer un défaut de connectivité lié à une mauvaise configuration VLAN    |

## 🖥️ Contexte technique
- Chaque PC appartient à un VLAN différent (10, 20, 30).  
- Les VLAN sont créés et nommés sur les 3 commutateurs.  
- Les ports sont configurés en mode **access** et affectés aux VLAN correspondants.  
- Un VLAN **Voice (150)** est ajouté pour gérer la téléphonie IP.  

## ✅ Résultats et apprentissages
- Les PC d’un même VLAN communiquent uniquement entre eux.  
- Commande clé : `show vlan brief`.  
- Problème rencontré : perte de connectivité car VLAN non configurés sur S1.  
- Solution : configurer les interfaces **Gigabit en trunk** pour transporter plusieurs VLAN.  

# 📘 TD – Packet Tracer : Troubleshooting VLAN Implementation


## 🎯 Objectifs pédagogiques — BTS SIO
| Bloc  | Compétence visée                                                                 |
|-------|-----------------------------------------------------------------------------------|
| B2.1  | Analyser une topologie pour identifier les problèmes de configuration            |
| B2.2  | Déployer une configuration conforme à un cahier des charges                      |
| B3.1  | Configurer des VLAN et du trunking                                               |
| B4.1  | Réaliser des tests de connectivité pour valider une solution                      |

## 🖥️ Contexte technique
- VLAN natif défini : VLAN 56 (Management & Native).  
- Les VLAN 10, 20, 30 sont présents pour Faculty/Staff, Students et Guests.  
- Problèmes identifiés :  
  - Aucun VLAN sur S1.  
  - Aucune interface configurée sur S1.  
  - Pas de trunk sur S2.  

## ✅ Résultats et apprentissages
- Les VLAN ont été créés et affectés aux bons ports.  
- Le trunking a été activé pour permettre la communication inter-switch.  
- La connectivité entre les PC d’un même VLAN a été validée par ping.  


# 📘 TD – Packet Tracer : Who Hears the Broadcast?


## 🎯 Objectifs pédagogiques — BTS SIO
| Bloc  | Compétence visée                                                                 |
|-------|-----------------------------------------------------------------------------------|
| B1.1  | Comprendre la notion de domaine de diffusion et de collision                     |
| B2.1  | Identifier le périmètre de diffusion selon la configuration VLAN                 |
| B3.1  | Expérimenter avec Packet Tracer les mécanismes de broadcast et unicast           |
| B4.1  | Expliquer les impacts d’une mauvaise configuration VLAN                          |

## 🖥️ Contexte technique
- Réseau basé sur un switch Catalyst 2960 rempli (24 ports).  
- Chaque PC appartient à un VLAN (10, 20, 30).  
- Expériences réalisées avec des pings **unicast** et **broadcast**.  

## ✅ Résultats et apprentissages
- Un broadcast est reçu uniquement par les PC du **même VLAN**.  
- Communication VLAN ↔ VLAN échoue (ex. VLAN 10 → VLAN 30).  
- Unicast : seuls les ports de destination s’allument.  
- Chaque port = domaine de collision indépendant.  
- Chaque VLAN = domaine de diffusion indépendant.  
