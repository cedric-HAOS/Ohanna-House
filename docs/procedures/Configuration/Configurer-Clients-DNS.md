# Configurer les clients DNS

| Élément | Valeur |
|---------|--------|
| Projet | Ohana-House |
| Procédure | Configurer les clients DNS |
| Version | 1.0 |
| Niveau de qualité | 🟣 Référence |
| Dernière mise à jour | 04/07/2026 |

> ℹ️ **Information**
>
> Cette procédure décrit la configuration des équipements utilisant le serveur **AdGuard Home** de l'infrastructure Ohana-House.
>
> Elle ne couvre pas la configuration du serveur AdGuard Home, décrite dans **Configurer-AdGuard.md**.

---

# 1. Objectif

Configurer les équipements de l'infrastructure afin qu'ils utilisent **AdGuard Home** comme serveur DNS principal.

---

# 2. Contexte

Utiliser cette procédure :

- après la configuration d'AdGuard Home ;
- après l'ajout d'un nouvel équipement ;
- après une reconstruction d'un équipement ;
- après une modification de l'adressage DNS.

---

# 3. Prérequis

Les éléments suivants sont nécessaires :

- Configurer-AdGuard.md terminé.
- Réseau local opérationnel.
- AdGuard Home accessible.

---

# 4. Niveau de risque

| Élément | Valeur |
|---------|--------|
| Risque | Faible |

---

# 5. Impact

| Élément | Valeur |
|---------|--------|
| Interruption de service | Oui |
| Impact utilisateur | Faible |
| Fenêtre de maintenance recommandée | Oui |

---

# 6. Procédure

## Étape 1

Configurer la **Freebox Pop** afin qu'elle distribue l'adresse du serveur AdGuard Home comme serveur DNS via DHCP.

---

## Étape 2

Vérifier que **HA-01** utilise AdGuard Home pour la résolution DNS.

---

## Étape 3

Vérifier que **RPI-Linky** utilise AdGuard Home.

---

## Étape 4

Vérifier que **RPI-ZWave** utilise AdGuard Home.

---

## Étape 5

Renouveler le bail DHCP des équipements si nécessaire afin qu'ils récupèrent la nouvelle configuration DNS.

---

## Étape 6

Contrôler le bon fonctionnement de la résolution DNS sur les différents équipements.

---

# 7. Configuration appliquée

| Élément | Valeur |
|----------|--------|
| Serveur DNS principal | AdGuard Home |
| Distribution DHCP | Freebox Pop |
| Clients DNS | HA-01, RPI-Linky, RPI-ZWave et équipements du réseau |

---

# 8. Vérifications

Vérifier les points suivants :

- [ ] La Freebox distribue le serveur DNS attendu.
- [ ] HA-01 résout correctement les noms de domaine.
- [ ] RPI-Linky résout correctement les noms de domaine.
- [ ] RPI-ZWave résout correctement les noms de domaine.
- [ ] Les requêtes DNS apparaissent dans les journaux d'AdGuard Home.
- [ ] Le filtrage DNS est opérationnel.

---

# 9. Retour arrière

En cas d'échec :

- vérifier la configuration DHCP de la Freebox ;
- vérifier l'adresse IP du serveur AdGuard Home ;
- renouveler les baux DHCP des équipements ;
- contrôler les journaux AdGuard Home ;
- reprendre la procédure depuis le début.

---

# 10. Documents associés

## Documents d'exploitation

- AdGuard.md
- Freebox-Pop.md
- Home-Assistant-Green.md
- RPi-Linky.md
- RPi-ZWave.md

## Procédures

- Configurer-AdGuard.md
- Configurer-RPi-Linky.md
- Configurer-RPi-ZWave.md
- Restaurer-Freebox.md