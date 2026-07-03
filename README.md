# 🏠 Ohanna-House

> Dossier d'exploitation technique de l'infrastructure informatique et domotique de la maison.

---

## Présentation

**Ohanna-House** est un dépôt GitHub privé regroupant la documentation complète de l'infrastructure informatique de la maison.

Cette documentation décrit :

- l'architecture de l'infrastructure ;
- la topologie réseau ;
- les équipements matériels ;
- les services déployés ;
- les procédures d'exploitation ;
- les procédures de sauvegarde et de restauration ;
- les décisions d'architecture.

L'objectif est de disposer d'une documentation claire, cohérente et maintenable permettant de comprendre, exploiter, maintenir et faire évoluer l'infrastructure.

---

## Version actuelle

**v0.1 "Iruka"**

Voir :

- `docs/standards/Versioning.md`
- `CHANGELOG.md`
- `ROADMAP.md`

---

## Structure du dépôt

```
Ohanna-House
│
├── docs/
├── procedures/
├── decision-log/
├── diagrams/
├── configs/
├── scripts/
├── assets/
└── backlog/
```

---

## Principes

Le projet repose sur les principes suivants :

- une information = un seul document ;
- séparation entre architecture et configuration ;
- documentation orientée exploitation ;
- évolution maîtrisée de l'infrastructure ;
- décisions d'architecture tracées par des ADR.

---

## Documentation

La documentation est organisée selon une hiérarchie :

Architecture

↓

Topologie

↓

Équipements

↓

Procédures

Chaque document possède une responsabilité unique.

---

## Licence

Le projet est actuellement hébergé dans un dépôt GitHub public afin de faciliter sa rédaction et ses revues.

À terme, le dépôt redeviendra privé une fois la version 1.0 publiée.