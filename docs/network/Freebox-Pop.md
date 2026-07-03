# Freebox Pop

| Élément | Valeur |
|---------|--------|
| Projet | Ohanna-House |
| Document | Freebox Pop |
| Version | 1.0 |
| Niveau de qualité | 🟣 Référence |
| Dernière mise à jour | 03/07/2026 |

---

# 1. Introduction

Ce document décrit la configuration de la Freebox Pop utilisée comme routeur principal de l'infrastructure **Ohanna-House**.

La Freebox constitue le point d'entrée du réseau domestique et assure les services indispensables au fonctionnement de l'infrastructure.

Les éléments décrits dans ce document correspondent à l'état de référence de l'installation.

---

# 2. Fiche d'identité

| Élément | Valeur |
|---------|--------|
| Identifiant | BOX-01 |
| Nom | Freebox Pop |
| Fabricant | Free |
| Catégorie | Routeur |
| Fonction principale | Routeur Internet |
| Adresse IP LAN | 192.168.1.254 |
| Interface réseau | Ethernet 2,5 Gb/s |
| Criticité | Haute |
| Supervision | Home Assistant |
| Sauvegarde | Oui |
| Procédure de restauration | À rédiger |

---

# 3. Position dans l'infrastructure

| Amont | Équipement | Aval |
|--------|------------|------|
| Internet | BOX-01 | SW-01 |

---

# 4. Responsabilités

La Freebox assure les fonctions suivantes :

- accès Internet ;
- routage IPv4 ;
- serveur DHCP ;
- gestion des baux statiques ;
- passerelle par défaut du réseau local ;
- terminaison WireGuard (à partir de la phase dédiée).

Elle constitue le seul point d'accès entre le réseau local et Internet.

---

# 5. Configuration réseau

## Plan d'adressage

| Paramètre | Valeur |
|-----------|---------|
| Réseau | 192.168.1.0/24 |
| Masque | 255.255.255.0 |
| Passerelle | 192.168.1.254 |

---

## DHCP

| Paramètre | Valeur |
|-----------|---------|
| Activé | Oui |
| Début de plage | 192.168.1.2 |
| Fin de plage | 192.168.1.54 |

Les équipements permanents utilisent des réservations DHCP.

Le détail est décrit dans **Adressage-IP.md**.

---

## DNS

Les clients obtiennent leurs serveurs DNS via le DHCP.

La configuration détaillée est décrite dans **AdGuard.md**.

---

# 6. Connexions physiques

La Freebox est reliée au switch principal **SW-01**.

| Interface | Destination | Débit |
|------------|-------------|-------:|
| Ethernet | SW-01 | 2,5 Gb/s |

Voir également :

- Topologie-Reseau.md
- DGM-001
- DGM-002

---

# 7. Dépendances

Les équipements suivants dépendent directement de la Freebox :

- Home Assistant Green
- Raspberry Pi Linky
- Raspberry Pi Z-Wave
- Point d'accès Linksys
- Tous les équipements du réseau

Une indisponibilité de la Freebox entraîne une perte d'accès Internet et l'arrêt du serveur DHCP.

---

# 8. Criticité

| Élément | Valeur |
|---------|--------|
| Niveau | Haute |
| Impact en cas de panne | Très important |
| Redondance | Aucune |
| Tolérance à la panne | Faible |

La Freebox constitue un composant critique de l'infrastructure.

---

# 9. Sauvegarde

La configuration de la Freebox devra être sauvegardée après chaque modification importante.

Les captures d'écran de configuration seront conservées dans :

```text
docs/network/freebox/
```

Une procédure dédiée sera rédigée dans la phase **Procédures**.

---

# 10. Maintenance

Les opérations de maintenance comprennent :

- mise à jour du firmware ;
- vérification des réservations DHCP ;
- contrôle des paramètres DNS ;
- vérification des redirections de ports ;
- contrôle du fonctionnement WireGuard.

Chaque intervention devra être documentée si elle modifie la configuration de référence.

---

# 11. Historique fonctionnel

| Date | Version | Modification | Référence |
|------|---------|--------------|-----------|
| 2026-07-03 | v0.5.0 (Kakashi) | Création du document | Initialisation |

Les modifications importantes de la configuration de la Freebox devront être consignées dans ce tableau.

Les évolutions mineures (mise à jour du firmware, redémarrage, etc.) ne nécessitent pas de mise à jour de cet historique.

---

# 12. Évolutions prévues

Les évolutions actuellement identifiées sont :

- documentation complète de WireGuard ;
- documentation des redirections de ports ;
- ajout des captures d'écran de configuration ;
- rédaction de la procédure de sauvegarde ;
- rédaction de la procédure de restauration.

---

# 13. Documents associés

## Architecture

- Architecture.md
- Topologie-Reseau.md
- Adressage-IP.md
- Capacites-Reseau.md
- Decisions-d-Architecture.md

## Réseau

- Switches.md
- Linksys-LAPAC1750.md

## Services

- AdGuard.md
- WireGuard.md

---

Le présent document décrit la configuration de référence de la Freebox Pop.

Toute modification de sa configuration devra être reportée dans cette documentation avant sa mise en production.