---
title: Créer votre premier indicateur de fonctionnalité
description: Découvrez comment créer un indicateur de fonctionnalité dans les indicateurs, définir une audience et la tester avant de la déployer sur les utilisateurs.
badge: label="Version bêta" type="Informative"
hide: true
exl-id: ae115120-8da9-465e-a556-c17591ea7054
source-git-commit: 8fffd619232b2cae2f5dd0aa1e0a55183c4be698
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 2%

---

# Créer votre premier indicateur de fonctionnalité {#create-feature-flag}

## Conditions préalables {#prerequisites}

Avant de créer un indicateur de fonctionnalité, effectuez les opérations suivantes :

* Vous avez accès à la console Indicateurs — voir [Connexion à la console](../console/log-in-to-the-console.md)
* Votre application est intégrée : consultez la section [Intégration de votre application](../applications/onboard-your-application.md)
* Vous disposez du rôle **Propriétaire de la version de produit**

## Étape 1 : créer l’indicateur de fonctionnalité {#create}

Pour créer un indicateur de fonctionnalité, procédez comme suit dans la console :

1. Connectez-vous à la **console Flags**, accédez au panneau de gauche, puis sélectionnez **Indicateurs de fonctionnalité**.
1. Sélectionnez votre application dans la liste déroulante **Application**.
1. Sélectionnez **Nouveaux indicateurs de fonctionnalité**.
1. Renseignez les champs du formulaire :

   | Champ | Description |
   | --- | --- |
   | **Nom** | Libellé d&#39;affichage de l&#39;indicateur de fonctionnalité. Non utilisé dans le code. |
   | **Clé** * | Identifiant utilisé dans votre code pour évaluer l’indicateur . Impossible de modifier après la création. |
   | **Description** | Description facultative à des fins de documentation. |
   | **Métadonnées** | Facultatif. Jusqu’à 1 024 caractères. Utilisez ce champ pour toutes les métadonnées supplémentaires à associer à l’indicateur. |
   | **Balises** | Balises facultatives à des fins de documentation. |
   | **Identité** * | Identité en fonction de laquelle l’indicateur est évalué (par exemple, ECID). Il s’agit de l’identité transmise dans la requête de fonctionnalité. |
   | **Pourcentage de déploiement** | Pourcentage de l’audience définie qui bénéficie de cette fonctionnalité. La valeur par défaut est 100 %. Voir [Définir une fonctionnalité à déployer progressivement](set-feature-gradual-rollout.md). |

   Les champs marqués d’un * sont obligatoires.

>[!IMPORTANT]
>
>L’identifiant **Key** est utilisé dans votre code et ne peut pas être modifié après sa création. Les clés **ne peuvent pas contenir d’espaces** et sont **sensibles à la casse**. Le **Name** est un libellé affiché uniquement et n&#39;est pas utilisé dans le code ; les deux sont indépendants (le Name n&#39;est pas converti en Key). La saisie d’un espace dans le champ Clé génère l’erreur : _« Valeur non valide pour la clé de la fonction »_

1. Vous pouvez éventuellement ajouter un critère d’audience (voir Étape 2).
1. Enregistrez les paramètres des indicateurs de fonctionnalité.

## Étape 2 : ajouter un critère d’audience {#audience}

Les critères d’audience contrôlent quels utilisateurs voient la fonctionnalité. Vous pouvez cibler les utilisateurs avec des **attributs de contexte** — valeurs que votre site web ou application envoie dans la demande de fonctionnalité (par exemple, `locale` ou `platform`). Les combiner avec **AND**, **OR** et **NOT**. Voir [Utilisation du contexte dans les règles d’audience](../audience/using-context-in-audience-rules.md).

Pour ajouter des critères d’audience, accédez à l’onglet **Audience** lors de la création ou de la modification d’un indicateur de fonctionnalité.

## Voir également {#see-also}

* [Définir une fonctionnalité à déployer progressivement](set-feature-gradual-rollout.md)
* [Créer un groupe de fonctionnalités](create-a-feature-group.md)

<!-- -->
