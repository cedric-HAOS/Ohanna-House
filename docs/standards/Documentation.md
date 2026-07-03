# Standard de documentation

## Structure

Tous les documents suivent la structure suivante :

Cartouche

1. Introduction

2. ...

Documents associés

---

## Titres

Toujours des titres H1, H2, H3.

---

## Tableaux

Les tableaux sont privilégiés lorsque l'information est structurée.

---

## Diagrammes

Les diagrammes Mermaid sont référencés par leur identifiant DGM-xxx.

---

## Historique

Jamais d'historique dans les documents.

Git est la source de vérité.

---

## Qualité

🟡 Brouillon

🔵 Révision

🟢 Validé

🟣 Référence

---

# Types de documents

La documentation est organisée en deux catégories.

## Documents d'architecture

Les documents d'architecture décrivent l'organisation générale de l'infrastructure.

Ils présentent les principes de fonctionnement, les choix techniques et les interactions entre les différents composants.

Ils utilisent la structure suivante :

- Cartouche
- Introduction
- Contenu spécifique au document
- Documents associés
- Phrase de référence

Exemples :

- Architecture.md
- Topologie-Reseau.md
- Architecture-Logique.md
- Inventaire.md
- Adressage-IP.md
- Capacites-Reseau.md
- Decisions-d-Architecture.md

---

## Documents d'exploitation

Les documents d'exploitation décrivent un composant de l'infrastructure.

Ils utilisent systématiquement la structure suivante :

1. Introduction
2. Fiche d'identité
3. Responsabilités
4. Configuration
5. Connexions
6. Dépendances
7. Criticité
8. Sauvegarde
9. Maintenance
10. Historique fonctionnel
11. Évolutions prévues
12. Documents associés

Cette structure garantit une documentation homogène et facilite la recherche d'informations.

---

## Chaîne réseau

Les documents décrivant un équipement réseau doivent situer celui-ci dans la chaîne de communication.

Cette information est présentée sous la forme d'un tableau.

Exemple :

| Amont | Équipement | Aval |
|--------|------------|------|
| SW-01 | AP-01 | RPI-01 |

Cette représentation complète les diagrammes Mermaid sans les remplacer.

---

# Organisation documentaire

Les documents sont organisés selon leur responsabilité.

## Architecture

Décrit les principes généraux de l'infrastructure.

## Réseau

Décrit les équipements réseau physiques.

## Services

Décrit les services indépendants de la plateforme domotique.

## Home Assistant

Décrit la plateforme Home Assistant et ses composants propres.

## Procédures

Décrit les opérations d'installation, de maintenance et de restauration.

---

# Modèles de documents

Afin de garantir une documentation homogène, chaque catégorie de document suit un modèle de rédaction.

## Documents d'exploitation

Les documents d'exploitation décrivent un équipement ou un service particulier.

Ils utilisent systématiquement la structure suivante :

1. Introduction
2. Fiche d'identité
3. Position dans l'infrastructure
4. Responsabilités
5. Configuration
6. Dépendances
7. Criticité
8. Sauvegarde
9. Maintenance
10. Historique fonctionnel
11. Évolutions prévues
12. Documents associés

Chaque document doit rester centré sur son unique responsabilité.

Les informations relatives à l'installation, la configuration détaillée, la mise à jour ou la restauration sont décrites dans les documents du dossier `procedures/`.

---

## Documents d'architecture

Les documents d'architecture décrivent l'organisation générale de l'infrastructure.

Leur structure est adaptée au sujet traité mais comprend généralement :

- Introduction
- Description de l'architecture
- Analyse
- Documents associés

Ils décrivent les principes de conception et les interactions entre les composants, sans détailler leur configuration.

---

## Procédures

Les procédures décrivent une opération à réaliser.

Elles peuvent concerner :

- une installation ;
- une configuration ;
- une mise à jour ;
- une sauvegarde ;
- une restauration ;
- une migration.

Une procédure doit permettre de reproduire une opération de manière fiable, sans nécessiter de connaissances implicites.

## Rôles dans l'architecture

Chaque composant de l'infrastructure possède un rôle dans l'architecture.

Ce rôle décrit sa contribution au fonctionnement global de l'infrastructure.

Le rôle est distinct de la fonction principale du composant.

### Rôles de référence

| Rôle | Description |
|------|-------------|
| Orchestrateur | Coordonne les services, les automatisations et les interactions entre les composants. |
| Passerelle | Assure la communication entre deux réseaux, protocoles ou systèmes. |
| Distribution | Distribue le trafic réseau entre les différents équipements. |
| Collecte | Acquiert des données provenant d'un équipement ou d'un système externe. |
| Messagerie | Transporte les messages entre plusieurs composants. |
| Résolution DNS | Assure la résolution des noms de domaine et le filtrage DNS. |
| Accès distant | Permet l'administration sécurisée de l'infrastructure depuis l'extérieur. |
| Accès radio | Fournit une connectivité réseau sans fil aux équipements. |

De nouveaux rôles pourront être ajoutés si l'évolution de l'infrastructure le nécessite.

Le nombre de rôles doit rester limité afin de conserver une architecture simple et homogène.