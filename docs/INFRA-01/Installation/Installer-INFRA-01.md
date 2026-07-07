# Installation d'INFRA-01

> Installation du serveur d'infrastructure d'Ohanna-House.

---

# Objectif

Installer le système d'exploitation constituant le socle d'INFRA-01.

À l'issue de cette procédure, le Raspberry Pi est accessible en SSH et prêt à recevoir les services d'infrastructure.

---

# Prérequis

## Matériel

- Raspberry Pi 3
- Carte microSD (16 Go minimum, classe A1 recommandée)
- Alimentation officielle Raspberry Pi
- Connexion Ethernet
- Ordinateur d'administration

## Logiciels

- Raspberry Pi Imager
- Client SSH

---

# Système retenu

| Élément | Valeur |
|----------|---------|
| Distribution | Raspberry Pi OS Lite |
| Architecture | 64 bits |
| Interface graphique | Non |
| Utilisateur | ohanna |
| Authentification | Clé SSH uniquement |
| Nom d'hôte | INFRA-01 |

---

# Préparation de la carte microSD

Lancer Raspberry Pi Imager.

Sélectionner :

```
Raspberry Pi OS Lite (64-bit)
```

Puis ouvrir les options avancées.

Configurer :

| Paramètre | Valeur |
|-----------|---------|
| Hostname | infra-01 |
| Utilisateur | ohanna |
| Authentification | Clé publique SSH |
| Activer SSH | Oui |
| Configurer le Wi-Fi | Non |
| Fuseau horaire | Europe/Paris |
| Clavier | Français |

Écrire ensuite l'image sur la carte microSD.

---

# Premier démarrage

Insérer la carte microSD.

Connecter :

- alimentation ;
- câble Ethernet.

Attendre environ deux minutes.

---

# Adresse IP

Pendant la phase d'installation, INFRA-01 obtient son adresse via le serveur DHCP existant.

Une réservation DHCP est créée sur la Freebox afin d'attribuer l'adresse définitive prévue dans le plan d'adressage.

Aucune adresse IP statique n'est configurée sur le système d'exploitation.

Cette approche est conforme à l'ADR-005 — Politique d'adressage IP.

---

# Première connexion

Depuis le poste d'administration :

```bash
ssh ohanna@infra-01.local
```

ou

```bash
ssh ohanna@<adresse_IP>
```

---

# Vérifications

Contrôler :

```bash
hostnamectl
```

Résultat attendu :

```
Static hostname: infra-01
```

Vérifier ensuite :

```bash
cat /etc/os-release
```

Puis :

```bash
uname -m
```

Résultat attendu :

```
aarch64
```

---

# Résultat attendu

À l'issue de cette procédure :

- Raspberry Pi OS Lite 64 bits est installé ;
- le Raspberry Pi est accessible en SSH ;
- le système est prêt pour la configuration de base.

Aucun service d'infrastructure n'est encore installé.

---

# Documents associés

- Configurer-INFRA-01.md
- Architecture-Reference.md
- ADR-003 — Services d'infrastructure (INFRA-01)