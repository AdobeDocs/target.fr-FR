---
title: Création des attributs de contexte
description: Découvrez comment créer et organiser des attributs et des groupes de contexte dans les indicateurs afin de les utiliser dans les critères d’audience.
badge: label="Version bêta" type="Informative"
hide: true
source-git-commit: 8fffd619232b2cae2f5dd0aa1e0a55183c4be698
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 5%

---

# Création des attributs de contexte {#creating-your-context-attributes}

Les attributs contextuels sont des champs de données personnalisés qui décrivent le contexte de l’utilisateur, de la session ou de l’application (par exemple, le niveau d’abonnement, la version de l’application ou la région). Utilisez des attributs contextuels pour définir des critères d’audience pour les indicateurs de fonctionnalité.

Les groupes de contextes organisent les attributs de contexte associés dans une hiérarchie logique. Utilisez des groupes de contexte pour faciliter la recherche et la gestion des attributs lors de la configuration des fonctionnalités.

| Terme | Description | Utilisé dans |
| --- | --- | --- |
| **Attribut Context** | Champ nommé avec un type de données et des valeurs prédéfinies facultatives. | Critères d’audience, configuration des fonctionnalités |
| **Groupe de contexte** | Une catégorie qui organise les attributs contextuels associés. | Sélection du contexte lors de la création d’une fonctionnalité |
| **libellé de l’interface utilisateur** | Nom d’affichage affiché dans l’interface utilisateur. | Critères d’audience et pages d’administration |
| **ID** | Identifiant technique unique. | Requêtes d’application |
| **Valeurs prédéfinies** | Liste facultative des valeurs autorisées avec des libellés d’affichage. | Listes déroulantes et créateurs de règles d’audience |

## Conditions préalables {#prerequisites}

Avant de gérer les attributs de contexte et les groupes de contexte, effectuez les opérations suivantes :

* Vous avez accès à la console **Flags** dans le sandbox approprié.
* Vous disposez du rôle **Admin** requis pour créer et gérer des attributs de contexte et des groupes de contexte.

## Accéder aux attributs de contexte {#navigate}

1. Connectez-vous à la **console Flags**.
1. Dans le volet de navigation de gauche, sous **Tableaux de bord**, sélectionnez **Attributs de contexte**.

Vous êtes maintenant sur la page **Attributs de contexte**. Utilisez cette page pour créer des groupes de contexte et des attributs de contexte.

## Créer un groupe de contexte {#create-group}

Chaque attribut de contexte doit appartenir à un groupe.

1. Dans le volet de navigation de gauche, sous **Tableaux de bord**, sélectionnez **Attributs de contexte**.
1. Dans l’onglet **Mes attributs de contexte**, sélectionnez **Ajouter un groupe**.
1. Renseignez les champs obligatoires.
1. Sélectionnez **Créer**.

### Regrouper les champs {#group-fields}

| Champ | Description |
| --- | --- |
| **Nom du groupe** | Saisissez un nom unique pour le groupe. |
| **Créer un sous-groupe de** | Sélectionnez un groupe parent pour organiser la hiérarchie. Vous pouvez également créer un groupe lors de la création d’un attribut. |

## Création d’un attribut de contexte {#create-attribute}

1. Dans l’onglet **Mes attributs de contexte**, sélectionnez **Nouvel attribut de contexte**.
1. Renseignez les champs obligatoires.
1. Sélectionnez **Envoyer**.

### Champs d’attribut {#attribute-fields}

| Champ | Description |
| --- | --- |
| **Libellé de l’interface utilisateur** | Saisissez le nom d’affichage utilisé dans les critères d’audience. |
| **ID** | Saisissez un identifiant technique unique utilisé dans les demandes d’application. |
| **Groupe de contexte** | Sélectionnez un groupe ou créez un groupe sur la ligne. |
| **Type de données** | Sélectionnez le type correspondant aux données envoyées par votre application. |

| Type de données | Exemple |
| --- | --- |
| CHAÎNE | `gold` |
| NOMBRE ENTIER | `42` |
| BOOLÉEN | `true` |
| DÉCIMAL | `9.99` |
| DATE | `2026-07-17` |
| VERSION | `1.2.0` |

### Valeurs prédéfinies (facultatif) {#predefined-values}

Utilisez des valeurs prédéfinies pour limiter un attribut à un ensemble fixe de valeurs. Sélectionnez **Ajouter des valeurs prédéfinies**.

| Champ | Description |
| --- | --- |
| **Libellé de l’interface utilisateur** | Saisissez le nom d’affichage. |
| **Valeur** | Saisissez la valeur technique envoyée par l’application. |

Sélectionnez **Enregistrer** pour appliquer vos modifications.

## Résolution des problèmes {#troubleshooting}

| Problème | Résolution |
| --- | --- |
| **Créer** est désactivé | Renseignez les champs **Nom du groupe** et **Créer un sous-groupe de**. |
| Impossible d’envoyer un attribut | Complétez **ID** et **Groupe contextuel**. |
| Groupe non visible dans la liste déroulante | Actualisez la page ou créez le groupe intégré à partir du formulaire d’attribut. |
| Valeurs prédéfinies non enregistrées | Sélectionnez **Enregistrer** dans la boîte de dialogue modale avant d’envoyer l’attribut. |

## Voir également {#see-also}

* [Création et utilisation d’ensembles de règles](creating-and-using-rule-sets.md)
* [Utilisation du contexte dans les règles d’audience](using-context-in-audience-rules.md)
* [Audience dans les indicateurs de fonctionnalité et les groupes de fonctionnalités](audience-in-feature-flags-and-feature-groups.md)

<!-- -->
