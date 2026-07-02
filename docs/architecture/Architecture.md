# Architecture de l'infrastructure

| Élément | Valeur |
|---------|--------|
| Projet | Ohanna-House |
| Document | Architecture de l'infrastructure |
| Version | 0.1 "Iruka" |
| Criticité | ⭐⭐⭐⭐⭐ |
| Dernière mise à jour | 02/07/2026 |

---

# 1. Objet

Ce document décrit l'architecture générale de l'infrastructure informatique et domotique d'Ohanna-House.

Il présente les principes de conception retenus, les composants majeurs de l'infrastructure, leurs responsabilités ainsi que leurs interactions.

Il constitue le document de référence du projet.

Les détails d'implémentation, de configuration, de maintenance et de restauration sont documentés dans les chapitres spécialisés.

---

# 2. Périmètre

## Inclus

Le présent document couvre :

- l'architecture réseau ;
- l'infrastructure domotique ;
- les principaux services ;
- les interactions entre composants ;
- les principes de résilience ;
- les décisions d'architecture.

## Exclus

Le présent document ne décrit pas :

- les configurations détaillées des équipements ;
- les paramètres réseau ;
- les automatisations Home Assistant ;
- les tableaux de bord ;
- les scripts ;
- les procédures d'installation ou de restauration.

---

# 3. Principes d'architecture

L'infrastructure repose sur les principes suivants.

## Séparation des responsabilités

Chaque équipement possède une fonction principale clairement identifiée.

Cette approche simplifie la maintenance, le dépannage ainsi que les évolutions futures.

---

## Modularité

Les services sont répartis sur plusieurs équipements indépendants.

Cette organisation limite les dépendances et réduit l'impact d'une défaillance.

---

## Simplicité

L'architecture privilégie des composants standards, des protocoles ouverts et une organisation facilement compréhensible.

---

## Évolutivité

L'infrastructure est conçue afin de permettre l'intégration de nouveaux équipements sans remise en cause de son organisation générale.

---

## Documentation

Chaque composant de l'infrastructure possède son propre document technique.

Le dépôt GitHub constitue la référence documentaire unique du projet.

---

# 4. Vue d'ensemble

L'infrastructure est organisée autour de quatre couches fonctionnelles.

```text
┌──────────────────────────────────────────────┐
│ Utilisateurs                                 │
│ PC • Smartphone • Tablette                   │
└──────────────────────────────────────────────┘

┌──────────────────────────────────────────────┐
│ Services                                     │
│ Home Assistant • MQTT • DNS • Z-Wave         │
└──────────────────────────────────────────────┘

┌──────────────────────────────────────────────┐
│ Infrastructure                               │
│ Home Assistant Green • Raspberry Pi • Wi-Fi  │
└──────────────────────────────────────────────┘

┌──────────────────────────────────────────────┐
│ Réseau                                       │
│ Freebox • Switches                           │
└──────────────────────────────────────────────┘
```

Cette organisation favorise la séparation des responsabilités et facilite les évolutions de l'infrastructure.

La description détaillée des interconnexions est disponible dans **Topologie-Reseau.md**.

---

# 5. Composants principaux

## Infrastructure réseau

L'infrastructure réseau assure les communications entre les différents équipements de la maison ainsi que l'accès à Internet.

Elle comprend :

- la passerelle Internet ;
- les équipements de commutation ;
- le réseau Wi-Fi.

Documentation associée :

- Topologie-Reseau.md
- Freebox-Pop.md
- Switches.md
- Linksys-LAPAC1750.md

---

## Home Assistant Green

Le Home Assistant Green constitue l'instance principale de l'infrastructure.

Il centralise les services nécessaires au fonctionnement de la plateforme domotique.

Documentation associée :

- Home-Assistant-Green.md
- Mosquitto.md

---

## Raspberry Pi Linky

Le Raspberry Pi Linky est exclusivement dédié à l'acquisition des données de téléinformation.

Il assure leur publication vers le broker MQTT.

Documentation associée :

- RPi-Linky.md

---

## Raspberry Pi Z-Wave

Le Raspberry Pi Z-Wave est exclusivement dédié à la gestion du réseau Z-Wave.

Documentation associée :

- RPi-ZWave.md

---

## Services d'infrastructure

Les services assurent le fonctionnement de l'ensemble de la plateforme.

Ils comprennent notamment :

- Home Assistant ;
- Mosquitto ;
- AdGuard Home ;
- WireGuard.

Documentation associée :

- Mosquitto.md
- AdGuard.md
- WireGuard.md

---

# 6. Interactions entre composants

| Source | Destination | Fonction |
|---------|-------------|----------|
| Linky | Raspberry Pi Linky | Acquisition de la téléinformation |
| Raspberry Pi Linky | Mosquitto | Publication des données de consommation |
| Home Assistant Green | Raspberry Pi Z-Wave | Gestion du réseau Z-Wave |
| Clients du réseau | AdGuard Home | Résolution DNS |
| Clients distants | WireGuard | Accès sécurisé à l'infrastructure |

L'architecture logique est détaillée dans **Architecture-Logique.md**.

---

# 7. Décisions d'architecture

Les principales décisions structurantes de l'infrastructure sont documentées sous forme d'Architecture Decision Records (ADR).

| ADR | Sujet |
|------|-------|
| ADR-001 | Choix du Home Assistant Green comme instance principale |
| ADR-002 | Dédié un Raspberry Pi à la téléinformation |
| ADR-003 | Héberger le réseau Z-Wave sur un Raspberry Pi dédié |
| ADR-004 | Mettre en œuvre une redondance DNS avec AdGuard Home |
| ADR-005 | Héberger Mosquitto sur le Home Assistant Green |

Les ADR sont disponibles dans le dossier **decision-log/**.

---

# 8. Principes de résilience

L'architecture met en œuvre plusieurs mécanismes destinés à améliorer la disponibilité des services.

Les principaux principes retenus sont :

- séparation des fonctions ;
- limitation des dépendances entre composants ;
- redondance du service DNS ;
- sauvegardes régulières ;
- documentation exhaustive de l'infrastructure.

Les procédures de reprise après incident sont documentées dans le dossier **procedures/**.

---

# 9. Évolutions de l'infrastructure

L'architecture a été conçue afin de permettre les évolutions suivantes sans remise en cause de son organisation générale :

- remplacement du Raspberry Pi Z-Wave par un Home Assistant Connect ZWAVE-2 ;
- ajout d'un NAS ;
- ajout d'un onduleur (UPS) ;
- ajout de nouveaux services.

Les évolutions planifiées sont suivies dans **ROADMAP.md**.

---

# 10. Références documentaires

## Documents d'architecture

- Topologie-Reseau.md
- Architecture-Logique.md
- Inventaire-Materiel.md
- Plan-d-adressage.md
- Glossaire.md

## Infrastructure réseau

- Freebox-Pop.md
- Switches.md
- Linksys-LAPAC1750.md

## Services

- Mosquitto.md
- AdGuard.md
- WireGuard.md

## Home Assistant

- Home-Assistant-Green.md
- RPi-Linky.md
- RPi-ZWave.md

## Décisions d'architecture

- decision-log/

## Procédures

- procedures/