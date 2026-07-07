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

Architecture, documentation et exploitation de l'infrastructure informatique et domotique d'Ohanna-House.

![Version](https://img.shields.io/badge/version-v2.0%20Hashirama-blue)
![Documentation](https://img.shields.io/badge/documentation-45%25-green)
![Status](https://img.shields.io/badge/status-architecture--phase-orange)
![Branch](https://img.shields.io/badge/branch-hashirama-purple)
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

Depuis la version **Hashirama**, le projet ne documente plus uniquement l'infrastructure.

Il définit également son architecture de référence, ses principes de conception ainsi que les décisions d'architecture (ADR) qui guideront toutes les évolutions futures.

---

## Sommaire

- [Vue d'ensemble](#vue-densemble)
- [Architecture de référence](#architecture-de-référence)
- [Structure du dépôt](#structure-du-dépôt)
- [Documents principaux](#documents-principaux)
- [Diagrammes](#diagrammes)
- [Feuille de route](#feuille-de-route)

---

## Vue d'ensemble

| Domaine | Description |
|--------|-------------|
| Architecture | Architecture de référence, missions, capacités et décisions |
| Réseau | Freebox Pop, switchs, Wi-Fi, DNS, DHCP, NTP, WireGuard |
| Domotique | Home Assistant, MQTT, Z-Wave, Linky, Shelly, ESPHome |
| Procédures | Installation, configuration, sauvegarde, maintenance, restauration |
| Standards | Conventions, nommage, adressage, ADR |

---

## Architecture de référence

La phase **Hashirama** introduit une architecture de référence décrivant :

- les capacités attendues de la maison ;
- les responsabilités de chaque machine ;
- les conventions d'architecture ;
- les principes de résilience ;
- les décisions d'architecture (ADR).

Cette architecture constitue désormais la référence pour toutes les futures évolutions d'Ohanna-House.

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
├── HASHIRAMA.md
├── Architecture-Reference.md
├── Architecture-Conventions.md
│
├── adr/
│
├── docs/
│   ├── architecture/
│   ├── network/
│   ├── services/
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

## Cycle de vie documentaire

Chaque composant de l'infrastructure est documenté selon son cycle de vie.

```text
Composant
        │
        ▼
Document d'exploitation
        │
        ▼
Installation
        │
        ▼
Configuration
        │
        ▼
Maintenance
        │
        ▼
Sauvegarde
        │
        ▼
Restauration
        │
        ▼
Migration
```

Cette organisation garantit que chaque opération est documentée de manière indépendante, tout en conservant une documentation cohérente et facilement maintenable.

---

## Documents principaux

### Architecture

- `docs/architecture/Architecture.md`
- `docs/architecture/Topologie-Reseau.md`
- `docs/architecture/Architecture-Logique.md`
- `docs/architecture/Inventaire.md`
- `docs/architecture/Adressage-IP.md`
- `docs/architecture/Capacites-Reseau.md`
- `docs/architecture/Decisions-d-Architecture.md`

### Réseau

- `docs/network/Freebox-Pop.md`
- `docs/network/Switches.md`
- `docs/network/Linksys-LAPAC1750.md`

### Services

- `docs/services/AdGuard.md`
- `docs/services/WireGuard.md`
- `docs/services/Mosquitto.md`

### Home Assistant

- `docs/home-assistant/Home-Assistant-Green.md`

### Hashirama

- `HASHIRAMA.md`
- `Architecture-Reference.md`
- `Architecture-Conventions.md`
- `adr/`

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

| Version | Nom          | Statut              |
| ------- | ------------ | ------------------- |
| v1.0    | Naruto       | ✅ Stable            |
| v2.0    | Hashirama    | ✅ Stable    |
| v3.0    | Ohanna-Agent | ⚪ Vision            |

---

## Documents de pilotage

Les documents suivants sont placés à la racine du dépôt afin de faciliter l'exploitation de l'infrastructure :

| Document | Rôle |
|-----------|------|
| START-HERE.md | Point d'entrée de la documentation |
| README.md | Présentation du projet |
| PROJECT-STATE.md | État actuel du projet |
| ROADMAP.md | Évolutions prévues |
| CHANGELOG.md | Historique des évolutions |
| Guide-de-Reconstruction.md | Reconstruction complète de l'infrastructure |
| Chemin-Critique-de-Reconstruction.md | Checklist de reconstruction |
| Validation-Finale.md | Validation de l'infrastructure |
| HASHIRAMA.md | Vision de la phase Hashirama |
| Architecture-Reference.md | Architecture de référence |
| Architecture-Conventions.md | Conventions d'architecture |
| adr/ | Décisions d'architecture |

---

## Licence

Ce projet est distribué sous licence MIT .
