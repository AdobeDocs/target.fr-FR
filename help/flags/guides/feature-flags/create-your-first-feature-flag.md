---
title: Créer votre premier indicateur de fonctionnalité
description: Découvrez comment créer un indicateur de fonctionnalité dans les indicateurs, définir une audience et la tester avant de la déployer sur les utilisateurs.
hide: true
exl-id: ae115120-8da9-465e-a556-c17591ea7054
source-git-commit: 045bd3321fd4041fe7f723ce300a400102ed7274
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 1%

---

# Créer votre premier indicateur de fonctionnalité {#create-feature-flag}

## Conditions préalables {#prerequisites}

Avant de créer un indicateur de fonctionnalité, effectuez les opérations suivantes :

* Vous avez accès à la console Indicateurs — voir [Connexion à la console](../console/log-in-to-the-console.md)
* Votre application est intégrée : consultez la section [Intégration de votre application](../applications/onboard-your-application.md)
* Vous disposez du rôle **Développeur** ou **Propriétaire de la version de produit**

## Étape 1 : créer l’indicateur de fonctionnalité {#create}

Pour créer un indicateur de fonctionnalité, procédez comme suit dans la console :

1. Connectez-vous à la console Indicateurs et accédez à **Fonctionnalités et versions > Indicateurs de fonctionnalité**.
1. Sélectionnez votre application dans la liste déroulante **Application**.
1. Sélectionnez **Nouvelle fonctionnalité**.
1. Renseignez les champs du formulaire :

   | Champ | Description |
   | --- | --- |
   | **Nom** | Libellé d&#39;affichage de l&#39;indicateur de fonctionnalité. Non utilisé dans le code. |
   | **Clé** * | Identifiant utilisé dans votre code pour évaluer l’indicateur . Impossible de modifier après la création. |
   | **Description** | Description facultative à des fins de documentation. |
   | **Métadonnées** | Facultatif. Jusqu’à 1 024 caractères. Utilisez ce champ pour toutes les métadonnées supplémentaires à associer à l’indicateur. |
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

>[!NOTE]
>
>Le rôle **Développeur** est en sandbox. Les développeurs ne peuvent s’exposer à une fonctionnalité qu’en ajoutant leur propre ID utilisateur sous **Audience > Profil > ID utilisateur**. Pour exposer une fonctionnalité à des utilisateurs externes, vous devez disposer du rôle **Propriétaire de la version du produit**.

## Étape 3 : calculer la taille de l’audience {#audience-size}

Après avoir ajouté des critères d’audience, sélectionnez **Calculer** dans la barre inférieure pour obtenir une estimation du nombre d’utilisateurs qui remplissent les critères de la fonctionnalité. Cela permet de valider le ciblage avant la mise en ligne.

## Étape 4 : Planifier (facultatif) {#schedule}

Vous pouvez planifier l&#39;activation d&#39;un indicateur de fonctionnalité à une date et une heure futures à l&#39;aide de l&#39;option **Planifier** dans les paramètres d&#39;indicateur de fonctionnalité.

## FAQ : Je ne peux pas ajouter d’indicateur de fonctionnalité en tant que développeur {#faq}

Le rôle **Développeur** est en sandbox. Les développeurs peuvent tester les fonctionnalités de manière privée en ajoutant leur identifiant utilisateur à l’audience. Ils ne peuvent pas exposer de fonctionnalités à des utilisateurs externes. Utilisez le rôle **Propriétaire de la version du produit** pour publier des fonctionnalités pour des utilisateurs externes. Contactez votre administrateur pour mettre à jour votre rôle.

## Voir également {#see-also}

* [Définir une fonctionnalité à déployer progressivement](set-feature-gradual-rollout.md)
* [Créer un groupe de fonctionnalités](create-a-feature-group.md)

<!-- -->
