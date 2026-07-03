# Adressage IP

| Élément | Valeur |
|---------|--------|
| Projet | Ohanna-House |
| Document | Adressage IP |
| Version | 1.0 |
| Niveau de qualité | 🟣 Référence |
| Dernière mise à jour | 03/07/2026 |

---

# 1. Introduction

Ce document décrit le plan d'adressage IPv4 de l'infrastructure **Ohanna-House**.

Il recense les plages d'adresses utilisées, les réservations DHCP ainsi que les conventions retenues pour l'attribution des adresses IP.

La gestion des adresses est assurée par la Freebox Pop.

---

# 2. Caractéristiques générales

| Paramètre | Valeur |
|-----------|---------|
| Protocole | IPv4 |
| Plan d'adressage | 192.168.1.0/24 |
| Masque | 255.255.255.0 |
| Passerelle | 192.168.1.254 |
| Serveur DHCP | BOX-01 (Freebox Pop) |
| DNS | AdGuard Home (voir AdGuard.md) |
| IPv6 | Désactivé |

---

# 3. Plage DHCP

La Freebox distribue dynamiquement les adresses suivantes :

| Début | Fin |
|--------|-----|
| 192.168.1.2 | 192.168.1.54 |

Les équipements nécessitant une adresse fixe utilisent des baux DHCP statiques.

---

# 4. Réservations DHCP

| Adresse IP | Équipement |
|------------|------------|
| 192.168.1.2 | Robot piscine |
| 192.168.1.10 | Caméra laverie |
| 192.168.1.37 | Caméra salon |
| 192.168.1.40 | Shelly Plug S3 Cuisine n°1 |
| 192.168.1.53 | RPI-01 — Raspberry Pi Linky |
| 192.168.1.54 | RPI-02 — Raspberry Pi Z-Wave |
| 192.168.1.56 | Shelly Pro EM Garage n°2 |
| 192.168.1.71 | KLF200 |
| 192.168.1.73 | Panneau solaire n°1 |
| 192.168.1.78 | Shelly Pro EM Laverie |
| 192.168.1.81 | Shelly Pro 4EM Laverie |
| 192.168.1.105 | Shelly Plug S3 Salon |
| 192.168.1.111 | Caméra piscine |
| 192.168.1.115 | Shelly Plug S3 Bureau Cathy |
| 192.168.1.116 | Ventilateur chambre |
| 192.168.1.136 | Shelly Plug S3 Bureau Cédric |
| 192.168.1.139 | Caméra entrée |
| 192.168.1.174 | Shelly Plug S3 Cuisine n°2 |
| 192.168.1.202 | Aspirateur Roomba |
| 192.168.1.222 | Shelly Plug S3 Couloir |
| 192.168.1.247 | HA-01 — Home Assistant Green |

---

# 5. Principes d'attribution

Les adresses IP sont attribuées par le serveur DHCP de la Freebox.

Les équipements permanents utilisent une réservation DHCP afin de conserver une adresse constante.

Cette méthode simplifie l'administration tout en conservant une gestion centralisée des adresses.

---

# 6. Recommandations

Les futures réservations DHCP devraient respecter une organisation logique par famille d'équipements afin de faciliter la maintenance.

Exemple :

| Plage | Utilisation recommandée |
|--------|-------------------------|
| .2 → .54 | DHCP dynamique |
| .55 → .99 | Infrastructure et domotique |
| .100 → .149 | Caméras |
| .150 → .199 | Shelly |
| .200 → .229 | Robots et objets connectés |
| .230 → .254 | Réserve |

Cette organisation constitue une recommandation pour les futurs équipements et ne remet pas en cause les adresses actuellement utilisées.

---

# 7. Documents associés

## Architecture

- Architecture.md
- Topologie-Reseau.md
- Architecture-Logique.md
- Inventaire.md

## Réseau

- Freebox-Pop.md
- AdGuard.md

---

Le présent document décrit le plan d'adressage IPv4 de référence de l'infrastructure.

Toute modification des réservations DHCP devra être reportée dans cette documentation.