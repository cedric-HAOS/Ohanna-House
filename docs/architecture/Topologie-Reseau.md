# Topologie du réseau

| Élément | Valeur |
|---------|--------|
| Projet | Ohanna-House |
| Document | Topologie du réseau |
| Version | 0.1 "Iruka" |
| Criticité | ⭐⭐⭐⭐⭐ |
| Dernière mise à jour | 02/07/2026 |

---

# 1. Objet

Ce document décrit la topologie physique du réseau de l'infrastructure Ohanna-House.

Il présente les équipements constituant le réseau local, leurs interconnexions ainsi que les technologies utilisées pour assurer les communications.

Les paramètres de configuration des équipements sont documentés dans leurs chapitres respectifs.

---

# 2. Topologie physique

La figure ci-dessous présente l'organisation physique des équipements constituant l'infrastructure.

```text
                                        Internet
                                            │
                                          Fibre
                                            │
                                    ┌─────────────────┐
                                    │ BOX-01          │
                                    └────────┬────────┘
                                             │
                                       Ethernet 2.5 Gb
                                             │
                                    ┌────────▼────────┐
                                    │ SW-01           │
                                    └──────┬─────┬────┘
                                           │     │
                             Ethernet 1 Gb │     │ Ethernet 10 Gb
                                           │     │
                                           │     ▼
                              ┌────────────▼──┐  ┌─────────────────┐
                              │ AP-01         │  │ SW-02           │
                              └──────┬────────┘  └────────┬────────┘
                                     │                    │
                                   Wi-Fi             Ethernet 1 Gb
                                     │                    │
                          ┌──────────▼───────┐   ┌────────▼────────┐
                          │ RPI-01           │   │ SW-03           │
                          └──────────────────┘   └──────┬─────┬────┘
                                                        │     │
                                            Ethernet 1 Gb│     │Ethernet 1 Gb
                                                        │     │
                                           ┌────────────▼┐ ┌──▼────────────┐
                                           │ HA-01       │ │ RPI-02        │
                                           └─────────────┘ └───────────────┘
```

**Figure 1 — Topologie physique de l'infrastructure**

### Légende

| Symbole | Signification |
|----------|---------------|
| ───── | Liaison Ethernet |
| Wi-Fi | Liaison sans fil |
| Fibre | Accès Internet |

---

# 3. Inventaire des équipements

| Identifiant | Fonction | Documentation |
|-------------|----------|---------------|
| BOX-01 | Passerelle Internet | Freebox-Pop.md |
| SW-01 | Switch principal | Switches.md |
| SW-02 | Switch de distribution | Switches.md |
| SW-03 | Switch dédié à l'infrastructure domotique | Switches.md |
| AP-01 | Point d'accès Wi-Fi | Linksys-LAPAC1750.md |
| HA-01 | Instance principale Home Assistant | Home-Assistant-Green.md |
| RPI-01 | Acquisition de la téléinformation | RPi-Linky.md |
| RPI-02 | Gestion du réseau Z-Wave | RPi-ZWave.md |

---

# 4. Liaisons

| Origine | Destination | Support | Capacité de liaison |
|----------|-------------|---------|--------------------:|
| BOX-01 | SW-01 | Ethernet | 2,5 Gb |
| SW-01 | SW-02 | Ethernet | 10 Gb |
| SW-02 | SW-03 | Ethernet | 1 Gb |
| SW-01 | AP-01 | Ethernet | 1 Gb |
| AP-01 | RPI-01 | Wi-Fi | Variable |
| SW-03 | HA-01 | Ethernet | 1 Gb |
| SW-03 | RPI-02 | Ethernet | 1 Gb |

---

# 5. Chemins principaux

Les principaux flux de communication empruntent les chemins suivants.

| Communication | Chemin |
|---------------|--------|
| Internet → Home Assistant | BOX-01 → SW-01 → SW-02 → SW-03 → HA-01 |
| Linky → Home Assistant | RPI-01 → AP-01 → SW-01 → SW-02 → SW-03 → HA-01 |
| Home Assistant → Réseau Z-Wave | HA-01 → SW-03 → RPI-02 |

---

# 6. Technologies utilisées

| Technologie | Usage |
|-------------|-------|
| Fibre | Accès Internet |
| Ethernet | Communications filaires |
| Wi-Fi | Connexion du Raspberry Pi Linky |

---

# 7. Dépendances

| Équipement | Dépend de |
|------------|-----------|
| SW-01 | BOX-01 |
| SW-02 | SW-01 |
| SW-03 | SW-02 |
| AP-01 | SW-01 |
| HA-01 | SW-03 |
| RPI-01 | AP-01 |
| RPI-02 | SW-03 |

---

# 8. Documents associés

## Architecture

- Architecture.md
- Architecture-Logique.md
- Inventaire-Materiel.md
- Plan-d-adressage.md
- Glossaire.md

## Réseau

- Freebox-Pop.md
- Switches.md
- Linksys-LAPAC1750.md

## Home Assistant

- Home-Assistant-Green.md
- RPi-Linky.md
- RPi-ZWave.md