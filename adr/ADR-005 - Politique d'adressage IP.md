# ADR-005 — Politique d'adressage IP

> **Statut :** ✅ Accepté
>
> **Date :** 2026-07-06
>
> **Décideurs :** Projet Ohanna-House
>
> **Impact :** Important

---

# Contexte

L'infrastructure Ohanna-House est appelée à évoluer au fil du temps.

De nouveaux équipements, services et passerelles viendront progressivement enrichir l'installation.

Sans règles d'adressage clairement définies, cette évolution conduit rapidement à une perte de lisibilité, à des conflits d'adresses et à une maintenance plus complexe.

Une politique d'adressage unique est donc nécessaire afin de garantir la cohérence de l'ensemble de l'infrastructure.

---

# Problème

Une attribution arbitraire des adresses IP présente plusieurs inconvénients :

- difficulté à identifier rapidement le rôle d'un équipement ;
- risque de conflits d'adresses ;
- perte de cohérence lors de l'ajout de nouveaux composants ;
- dépendance à la mémoire de l'administrateur.

L'architecture doit permettre d'identifier immédiatement la fonction d'un équipement à partir de son adresse IP.

---

# Décision

L'ensemble des équipements du réseau est organisé selon une politique d'adressage fonctionnelle.

Chaque plage d'adresses est réservée à une catégorie d'équipements ayant une responsabilité commune.

L'adressage constitue un élément de l'architecture de référence.

---

# Capacités garanties

---

## Lisibilité

L'adresse IP permet d'identifier immédiatement la catégorie fonctionnelle d'un équipement.

---

## Cohérence

Les équipements remplissant un rôle comparable appartiennent à la même plage d'adresses.

---

## Évolutivité

L'ajout d'un nouvel équipement ne remet pas en cause l'organisation existante.

Chaque catégorie dispose d'une réserve d'adresses suffisante.

---

## Prévisibilité

Les équipements critiques conservent une adresse stable dans le temps.

---

## Simplicité d'administration

La localisation d'un équipement ne dépend pas de la mémoire de l'administrateur.

---

# Organisation retenue

| Plage | Fonction |
|--------|----------|
| .1 | BOX-01 |
| .2 à .9 | Réserve infrastructure |
| .10 à .19 | Services d'infrastructure |
| .20 à .29 | Serveurs domotiques |
| .30 à .39 | Infrastructure réseau |
| .40 à .49 | Passerelles domotiques |
| .50 à .99 | Équipements critiques |
| .100 à .199 | DHCP dynamique |
| .200 à .254 | Réserve d'évolution |

---

# Principes retenus

## Organisation fonctionnelle

Les plages sont définies selon le rôle des équipements et non selon leur technologie ou leur constructeur.

---

## Réservations DHCP

Les équipements critiques utilisent des réservations DHCP.

L'utilisation d'adresses IP configurées manuellement est limitée aux cas où une réservation DHCP n'est pas possible.

---

## Convention de nommage

Chaque équipement est identifié par un nom fonctionnel indépendant de son constructeur.

Exemples :

- HA-01
- INFRA-01
- ZWAVE-01
- LINKY-01
- AP-01
- SW-01

---

## Évolutivité

Chaque plage conserve une capacité de croissance afin d'éviter toute réorganisation ultérieure.

---

# Conséquences

## Avantages

- meilleure lisibilité du réseau ;
- administration simplifiée ;
- évolutivité ;
- cohérence de l'infrastructure ;
- facilité de dépannage.

## Inconvénients

- nécessité de respecter les conventions d'adressage ;
- planification préalable lors de l'ajout de nouveaux équipements.

Ces contraintes sont considérées comme acceptables.

---

# Alternatives étudiées

## Attribution libre des adresses

Non retenue.

Elle ne garantit pas la cohérence du réseau.

---

## Adresses IP statiques configurées sur les équipements

Non retenue.

Les réservations DHCP offrent une meilleure souplesse, notamment lors d'un changement de routeur ou de plan d'adressage.

---

## Organisation par constructeur

Non retenue.

Les rôles des équipements sont privilégiés plutôt que leur technologie.

---

# Décisions dérivées

Cette décision contribue notamment à :

- Architecture-Conventions.md
- Architecture-Reference.md
- ADR-006 — Sauvegarde et restauration d'INFRA-01

---

# Références

- Architecture-Reference.md
- Architecture-Conventions.md
- ADR-001 — Autonomie locale de l'infrastructure
- ADR-003 — Services d'infrastructure (INFRA-01)

---

# Conclusion

Le plan d'adressage constitue un élément structurant de l'architecture Ohanna-House.

Il garantit une organisation cohérente, évolutive et indépendante des technologies utilisées.

L'adresse IP devient un indicateur fonctionnel du rôle d'un équipement plutôt qu'un simple identifiant réseau.