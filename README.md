<div align="center">

```text
╔══════════════════════════════════════════════════════╗
║                                                      ║
║                  OHANNA-HOUSE                        ║
║                                                      ║
║        Home Infrastructure Documentation             ║
║                                                      ║
╚══════════════════════════════════════════════════════╝
```

# Ohanna-House

Documentation technique de l'infrastructure informatique et domotique de la maison.

![Version](https://img.shields.io/badge/version-v0.1%20Iruka-blue)
![Documentation](https://img.shields.io/badge/documentation-35%25-green)
![Status](https://img.shields.io/badge/status-active-orange)
![Branch](https://img.shields.io/badge/branch-main-purple)
![License](https://img.shields.io/badge/license-MIT-lightgrey)

</div>

---

## Présentation

**Ohanna-House** est le référentiel de documentation technique de l'infrastructure informatique et domotique de la maison.

Ce dépôt décrit :

- l'architecture générale ;
- les équipements matériels ;
- les services installés ;
- les procédures d'exploitation ;
- les choix techniques ;
- les évolutions de l'infrastructure.

L'objectif est de garantir qu'à tout moment, l'installation puisse être comprise, maintenue, restaurée et faire évoluer sans dépendre uniquement de la mémoire de son administrateur.

---

## Sommaire

- [Vue d'ensemble](#vue-densemble)
- [Structure du dépôt](#structure-du-dépôt)
- [Documents principaux](#documents-principaux)
- [Diagrammes](#diagrammes)
- [Feuille de route](#feuille-de-route)

---

## Vue d'ensemble

| Domaine | Description |
|--------|-------------|
| Architecture | Description complète de l'infrastructure physique et logique |
| Réseau | Freebox Pop, switchs, Wi-Fi, DNS, WireGuard |
| Domotique | Home Assistant, MQTT, Z-Wave, Linky |
| Procédures | Sauvegardes, restaurations, maintenance |
| Standards | Versioning, nommage, rédaction documentaire |

---

## Structure du dépôt

```text
Ohanna-House/
│
├── README.md
├── CHANGELOG.md
├── ROADMAP.md
├── PROJECT-STATE.md
├── LICENSE
│
├── docs/
│   ├── architecture/
│   ├── network/
│   ├── home-assistant/
│   └── standards/
│
├── procedures/
├── diagrams/
│   ├── physical/
│   ├── logical/
│   └── flows/
│
├── configs/
├── scripts/
├── assets/
└── backlog/
```

---

## Documents principaux

### Architecture

- `docs/architecture/Architecture.md`
- `docs/architecture/Topologie-Reseau.md`
- `docs/architecture/Architecture-Logique.md`
- `docs/architecture/Inventaire.md`
- `docs/architecture/Adressage-IP.md`
- `docs/architecture/Decisions-d-Architecture.md`

### Réseau

- `docs/network/Freebox-Pop.md`
- `docs/network/Switches.md`
- `docs/network/Linksys-LAPAC1750.md`
- `docs/network/AdGuard.md`
- `docs/network/WireGuard.md`

### Home Assistant

- `docs/home-assistant/Home-Assistant-Green.md`
- `docs/home-assistant/Mosquitto.md`
- `docs/home-assistant/RPi-Linky.md`
- `docs/home-assistant/RPi-ZWave.md`

---

## Diagrammes

Les diagrammes officiels sont rédigés en Mermaid et stockés dans le dossier `diagrams`.

| ID | Diagramme |
|----|-----------|
| DGM-001 | Architecture physique |
| DGM-002 | Topologie réseau |
| DGM-003 | Architecture logique |
| DGM-004 | Flux MQTT |
| DGM-005 | Flux Z-Wave |
| DGM-006 | Flux DNS / WireGuard |

---

## Feuille de route

| Phase | Nom | Statut |
|------|-----|--------|
| v0.1 | Iruka | En cours |
| v0.5 | Kakashi | Prévu |
| v1.0 | Naruto | Prévu |
| v1.1 | Yamato | Prévu |
| v1.2 | Shikamaru | Prévu |
| v1.3 | Tsunade | Prévu |
| v2.0 | Hashirama | Prévu |

---

## Licence

Ce projet est distribué sous licence MIT.
