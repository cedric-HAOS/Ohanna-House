# Conventions

> Ce document définit les conventions utilisées dans l'ensemble du projet Ohanna-House.

---

# 1. Conventions de nommage

Les équipements sont nommés selon leur fonction et non selon leur constructeur.

Exemple :

AP-01

et non :

Linksys-LAPAC1750

---

# Préfixes

| Préfixe | Description |
|----------|-------------|
| BOX | Routeur Internet |
| HA | Home Assistant |
| INFRA | Infrastructure réseau |
| AP | Point d'accès Wi-Fi |
| SW | Switch |
| LINKY | Téléinformation |
| ZWAVE | Passerelle Z-Wave |
| ZIGBEE | Passerelle Zigbee |
| MATTER | Passerelle Matter |
| VELUX | Passerelle Velux |
| PV | Onduleur photovoltaïque |
| SH | Shelly |
| ESP | ESPHome |
| CAM | Caméra |
| NAS | NAS |
| PRN | Imprimante |

---

# 2. Plan d'adressage

| Plage | Fonction |
|------:|----------|
| .10-.19 | Services d'infrastructure |
| .20-.29 | Serveurs domotiques |
| .30-.39 | Infrastructure réseau |
| .40-.49 | Passerelles domotiques |
| .50-.99 | Équipements critiques |
| .100-.199 | DHCP dynamique |

---

# 3. Convention des ADR

Nom :

ADR-XXX-Titre.md

Exemple :

ADR-001-Autonomie-Locale.md

---

# 4. Convention documentaire

Chaque document comporte :

- un objectif ;
- un périmètre ;
- un statut ;
- une date de mise à jour.

---

# 5. Convention des capacités

Hashirama raisonne toujours par capacités.

Jamais par logiciels.

Exemple :

✔ Résolution DNS

❌ AdGuard

---

# 6. Convention MQTT (future)

Tous les topics utiliseront le préfixe :

ohanna/

Exemple :

ohanna/health

ohanna/adguard/run

ohanna/dhcp/state

---

# 7. Convention Ohanna-Agent (future)

Chaque plugin devra :

- avoir une responsabilité unique ;
- publier son état MQTT ;
- répondre aux commandes standardisées ;
- produire des journaux homogènes.

---

# Conclusion

Les conventions garantissent la cohérence de l'ensemble des projets Ohanna-House, Hashirama et Ohanna-Agent.