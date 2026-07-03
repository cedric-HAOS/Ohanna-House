# Home Assistant Green

| Élément | Valeur |
|---------|--------|
| Projet | Ohanna-House |
| Document | Home Assistant Green |
| Version | 1.0 |
| Niveau de qualité | 🟣 Référence |
| Dernière mise à jour | 03/07/2026 |

---

# 1. Introduction

Ce document décrit l'instance principale **Home Assistant Green** utilisée dans l'infrastructure **Ohanna-House**.

Elle constitue le cœur de la plateforme domotique et centralise les automatismes, les tableaux de bord, les intégrations ainsi que les services essentiels.

---

# 2. Fiche d'identité

| Élément | Valeur |
|---------|--------|
| Identifiant | HA-01 |
| Nom | Home Assistant Green |
| Fabricant | Home Assistant |
| Catégorie | Serveur domotique |
| Fonction principale | Plateforme domotique |
| Adresse IP | 192.168.1.247 |
| Interface réseau | Ethernet 1 Gb/s |
| Criticité | Très haute |
| Supervision | Auto-supervision + Home Assistant |
| Sauvegarde | Oui |
| Procédure de restauration | À rédiger |

---

# 3. Position dans l'infrastructure

| Amont | Équipement | Aval |
|--------|------------|------|
| BOX-01 → SW-01 → SW-02 → SW-03 | HA-01 | Utilisateurs, Automatismes, Tableau de bord |

---

# 4. Responsabilités

HA-01 assure les fonctions suivantes :

- exécution des automatisations ;
- hébergement des tableaux de bord ;
- gestion des intégrations ;
- supervision de l'infrastructure ;
- centralisation des équipements domotiques ;
- communication avec le broker MQTT ;
- communication avec le serveur Z-Wave JS UI.

Cette instance constitue le point central de l'infrastructure domotique.

---

# 5. Services hébergés

Les services actuellement hébergés sont :

| Service | Fonction |
|----------|----------|
| Home Assistant OS | Système principal |
| Home Assistant Core | Plateforme domotique |
| Mosquitto | Broker MQTT |
| Add-ons | Services complémentaires |

Les autres services sont documentés dans leurs documents respectifs.

---

# 6. Dépendances

HA-01 dépend notamment :

- de BOX-01 pour l'accès réseau ;
- de Mosquitto pour les échanges MQTT ;
- de RPI-01 pour la téléinformation Linky ;
- de RPI-02 pour le réseau Z-Wave ;
- des deux instances AdGuard Home pour la résolution DNS.

Une indisponibilité de HA-01 entraîne l'arrêt de la majorité des fonctions domotiques.

---

# 7. Criticité

| Élément | Valeur |
|---------|--------|
| Niveau | Très haute |
| Impact en cas de panne | Très important |
| Redondance | Aucune |

La restauration de HA-01 constitue la priorité absolue en cas de sinistre.

---

# 8. Sauvegarde

Les sauvegardes complètes de Home Assistant sont réalisées régulièrement.

Elles comprennent notamment :

- configuration Home Assistant ;
- automatisations ;
- tableaux de bord ;
- add-ons ;
- secrets ;
- intégrations.

La procédure de sauvegarde est documentée dans le dossier **procedures**.

---

# 9. Maintenance

Les opérations de maintenance comprennent :

- mise à jour de Home Assistant OS ;
- mise à jour de Home Assistant Core ;
- mise à jour des add-ons ;
- contrôle des sauvegardes ;
- vérification des journaux ;
- contrôle des intégrations.

Chaque intervention importante devra être documentée.

---

# 10. Historique fonctionnel

| Date | Version | Modification | Référence |
|------|---------|--------------|-----------|
| 2026-07-03 | v0.5.0 (Kakashi) | Création du document | Initialisation |

Les modifications importantes de la plateforme devront être consignées dans ce tableau.

---

# 11. Évolutions prévues

Les évolutions actuellement identifiées sont :

- documentation détaillée des intégrations ;
- procédure complète de restauration ;
- documentation des sauvegardes automatiques ;
- ajout éventuel de captures d'écran de configuration.

---

# 12. Documents associés

## Architecture

- Architecture-Logique.md
- Decisions-d-Architecture.md

## Services

- AdGuard.md
- WireGuard.md

## Home Assistant

- Mosquitto.md
- RPi-Linky.md
- RPi-ZWave.md

---

Le présent document décrit la configuration de référence de HA-01.

Toute modification importante devra être reportée dans cette documentation avant sa mise en production.