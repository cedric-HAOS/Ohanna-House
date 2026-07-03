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

Les documents d'exploitation décrivent un équipement ou un service particulier.

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