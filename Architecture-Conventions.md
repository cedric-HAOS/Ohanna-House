# Architecture Conventions

> Ce document définit les conventions utilisées dans l'ensemble du projet Ohanna-House.

---

# 1. Modèle architectural

L'ensemble des documents Hashirama repose sur trois niveaux :

Mission
↓
Capacité
↓
Implémentation

Les décisions d'architecture portent sur les missions et les capacités.

Les implémentations sont documentées dans Naruto.

Les ADR décrivent :

- les missions ;
- les capacités.

Naruto décrit :

- les implémentations.

---

# 2. Conventions de nommage

Les équipements sont nommés selon leur fonction.
Les noms restent indépendants du constructeur, du modèle et des technologies utilisées.
Le remplacement d'un constructeur, d'un modèle ou d'une technologie ne modifie pas le nom fonctionnel de l'équipement.

Exemple :

Freebox
↓

OpenWRT

BOX-01 reste BOX-01.

---

# Préfixes

| Préfixe  | Description              |
|----------|--------------------------|
| BOX      | Routeur Internet         |
| HA       | Home Assistant           |
| INFRA    | Infrastructure réseau    |
| AP       | Point d'accès Wi-Fi      |
| SW       | Switch                   |
| LINKY    | Téléinformation          |
| ZWAVE    | Passerelle Z-Wave        |
| ZIGBEE   | Passerelle Zigbee        |
| MATTER   | Passerelle Matter        |
| VELUX    | Passerelle Velux         |
| PV       | Onduleur photovoltaïque  |
| SH       | Shelly                   |
| ESP      | ESPHome                  |
| CAM      | Caméra                   |
| NAS      | NAS                      |
| PRN      | Imprimante               |

---

# 3. Plan d'adressage

Les plages sont définies par fonction et non par technologie.

| Plage     | Fonction                   |
|-----------|----------------------------|
| .10-.19   | Services d'infrastructure  |
| .20-.29   | Serveurs domotiques        |
| .30-.39   | Infrastructure réseau      |
| .40-.49   | Passerelles domotiques     |
| .50-.99   | Équipements critiques      |
| .100-.199 | DHCP dynamique             |

---

# 4. Convention des ADR

Les ADR :

- sont indépendants des technologies ;
- décrivent des décisions d'architecture ;
- ne documentent pas les procédures ;
- restent stables dans le temps.

Les logiciels et configurations sont documentés dans Naruto.

---

# 5. Convention documentaire

Chaque document comporte, lorsque cela est pertinent :

- un objectif ;
- un contexte ;
- un périmètre ;
- un statut ;
- une date de mise à jour ;
- des références vers les documents associés.

---

# 6. Convention MQTT (future)

Tous les topics utiliseront le préfixe :

ohanna/

Exemple :

ohanna/health

ohanna/dns/sync

ohanna/dhcp/state

---

# 7. Convention Ohanna-Agent (future)

Chaque plugin devra :

- avoir une responsabilité unique ;
- publier son état MQTT ;
- répondre aux commandes standardisées ;
- produire des journaux homogènes ;
- superviser une capacité et non un logiciel.

---

# Conclusion

Les conventions définies dans ce document constituent les règles communes de conception de tous les projets de l'écosystème Ohanna-House.

Toute nouvelle architecture, documentation ou évolution devra respecter ces conventions afin de garantir la cohérence de l'ensemble.