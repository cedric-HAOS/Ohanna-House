# Architecture Reference

> Document de référence de l'architecture cible d'Ohanna-House.
>
> Ce document décrit l'architecture fonctionnelle de l'infrastructure.
> Il constitue la référence de conception du projet Hashirama.
>
> Les Architecture Decision Records (ADR) détaillent les décisions ayant conduit à cette architecture.

---

# Statut

| Élément | Valeur |
|---------|--------|
| Projet | Ohanna-House |
| Phase | Hashirama |
| Version | 2.0 |
| Statut | 🟢 Validé |

---

# 1. Vision

L'objectif d'Ohanna-House est de construire une infrastructure :

- autonome ;
- documentée ;
- résiliente ;
- simple à maintenir ;
- évolutive.

L'infrastructure doit continuer à assurer les fonctions essentielles même en cas de perte d'Internet ou de la Freebox.

---

# 2. Principes d'architecture

## Principe 1

Les décisions sont prises en fonction des capacités offertes à la maison, et non des logiciels utilisés.

## Principe 2

Chaque machine possède une responsabilité principale clairement identifiée.

## Principe 3

L'autonomie locale est prioritaire sur les services Cloud.

## Principe 4

Les services critiques privilégient les liaisons Ethernet.

## Principe 5

Une panne ne doit provoquer qu'une dégradation progressive des capacités.

## Principe 6

Les points de défaillance uniques sont acceptés uniquement lorsqu'ils sont documentés, sauvegardés et rapidement restaurables.

---

# 3. Capacités

## Niveau 1 — Infrastructure

- DHCP
- DNS
- NTP
- Home Assistant

## Niveau 2 — Services domotiques

- MQTT
- Téléinformation
- Z-Wave
- Shelly
- ESPHome
- Velux

## Niveau 3 — Services externes

- Internet
- VPN
- Notifications
- Cloud
- Mises à jour

---

# 4. Architecture cible

                     Internet
                         │
                     BOX-01
               Modem • Routeur • NAT
                         │
─────────────────────────┼─────────────────────────
                         │
                  Infrastructure LAN
                         │
       ┌─────────┬──────────┬──────────┬──────────┐
       │         │          │          │
    HA-01    INFRA-01   ZWAVE-01   LINKY-01

---

# 5. Responsabilités

## BOX-01

Mission :

Assurer la connectivité Internet.

---

## HA-01

Mission :

Piloter la maison.

Services :

- Home Assistant
- Mosquitto

---

## INFRA-01

Mission :

Garantir les services fondamentaux de l'infrastructure.

Services :

- DHCP
- NTP
- Synchronisation AdGuard
- Supervision
- Scripts d'administration
- (Ohanna-Agent à terme)

---

## ZWAVE-01

Mission :

Passerelle domotique principale.

Services :

- Z-Wave JS UI
- AdGuard (DNS principal)

---

## LINKY-01

Mission :

Acquérir les données énergétiques.

Services :

- Téléinformation
- AdGuard (DNS secondaire)

---

# 6. Flux principaux

Pilotage des équipements

HA-01

↓

MQTT / Z-Wave

↓

Équipements

---

Téléinformation

LINKY-01

↓

MQTT

↓

HA-01

---

Résolution DNS

Clients

↓

ZWAVE-01

↓

LINKY-01 (secours)

---

DHCP

Clients

↓

INFRA-01

---

Temps

INFRA-01

↓

Tous les équipements

---

# 7. Plan d'adressage

| Plage | Usage |
|------:|-------|
| .1 | BOX-01 |
| .2-.9 | Réserve infrastructure |
| .10-.19 | Services d'infrastructure |
| .20-.29 | Serveurs domotiques |
| .30-.39 | Infrastructure réseau |
| .40-.49 | Passerelles domotiques |
| .50-.99 | Équipements critiques |
| .100-.199 | DHCP dynamique |
| .200-.254 | Réserve |

---

# 8. Paramètres réseau

Passerelle :

BOX-01

DNS principal :

ZWAVE-01

DNS secondaire :

LINKY-01

DHCP :

INFRA-01

NTP :

INFRA-01

---

# 9. Dégradation maîtrisée

La perte d'un composant ne doit entraîner que la perte de la capacité assurée par celui-ci.

L'objectif est de maintenir le fonctionnement local de la maison aussi longtemps que possible.

---

# 10. Documents associés

HASHIRAMA.md

Conventions.md

ADR

Naruto

---

# Conclusion

Une architecture n'est pas définie par les logiciels qu'elle utilise.

Elle est définie par les capacités qu'elle garantit.