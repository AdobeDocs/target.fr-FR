---
title: Test A/B avec indicateurs de fonctionnalité
description: Découvrez comment exécuter des tests A/B à l’aide de groupes de fonctionnalités dans la section Indicateurs en configurant plusieurs variantes pour un ensemble d’indicateurs de fonctionnalités.
badge: label="Version bêta" type="Informative"
hide: true
exl-id: bb849049-229c-40ff-bbfe-7996f868bcc3
source-git-commit: 8fffd619232b2cae2f5dd0aa1e0a55183c4be698
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 1%

---

# Test A/B avec indicateurs de fonctionnalité {#a-b-testing}

Les tests A/B dans les indicateurs sont effectués à l’aide de **groupes de fonctionnalités**. En configurant plusieurs variantes dans un groupe de fonctionnalités, vous pouvez diffuser différentes versions d’une fonctionnalité à différents sous-ensembles de votre audience et comparer les résultats.

## Conditions préalables {#prerequisites}

* Vous avez accès à la console ; voir [ Connexion à la console ](../console/log-in-to-the-console.md)
* Vous appartenez à une équipe et votre application est intégrée
* Vous disposez du rôle **Propriétaire de la version de produit**
* Vous avez créé les indicateurs de fonctionnalité à tester. Voir [Créer votre premier indicateur de fonctionnalité](create-your-first-feature-flag.md)

## Étape 1 : créer un groupe de fonctionnalités avec plusieurs variantes {#create}

1. Accédez à **Tests de fonctionnalités > Groupes de fonctionnalités** et sélectionnez **Nouveau groupe de fonctionnalités**.
1. Dans **Détails de base**, fournissez un titre, une clé et une description.
1. Définissez un **déploiement en pourcentage** pour définir la proportion de votre audience qui participe au test.
1. Définissez **Variantes** sur une valeur supérieure à un (par exemple, deux variantes pour un test A/B classique). Vous pouvez définir jusqu’à 3 variantes **plus une population témoin**.
1. Voir [Définir un groupe d’attributs à déployer progressivement](set-feature-group-gradual-rollout.md) pour comprendre comment le pourcentage d’exposition est réparti entre les variantes.

>[!NOTE]
>
>L’exposition est répartie **également** entre les variantes, par exemple 50/50 pour deux variantes. Les divisions personnalisées telles que 60/40 ne sont pas prises en charge. Un indicateur de fonctionnalité unique peut être ajouté à **plusieurs variantes**. L’audience est définie **une fois par groupe de fonctionnalités**, et non par variante.

## Étape 2 : définir l’audience {#audience}

Dans l’onglet **Audience**, ajoutez des critères d’audience et sélectionnez les applications à inclure. Les groupes de fonctionnalités peuvent couvrir plusieurs applications au sein d&#39;une même équipe.

## Étape 3 : ajout de fonctionnalités par variante {#features}

Sous l’onglet **Fonctions**, chaque variante a son propre onglet. Ajoutez les indicateurs de fonctionnalité appropriés à chaque variante pour définir les différentes expériences à comparer.

>[!IMPORTANT]
>
>Un indicateur de fonctionnalité ne peut être diffusé que par une seule méthode à la fois : indicateur de fonctionnalité, groupe de fonctionnalités ou version. L’ajout d’un indicateur à un groupe de fonctionnalités supprime toute audience ou tout pourcentage de déploiement défini directement sur l’indicateur.

## Étape 4 : Enregistrer et activer {#save}

Enregistrez les paramètres du groupe de fonctionnalités. Lorsque vous êtes prêt à démarrer le test, définissez le groupe de fonctionnalités sur l&#39;état actif.

## Voir également {#see-also}

* [Créer un groupe de fonctionnalités](create-a-feature-group.md)
* [Définir un groupe de fonctionnalités à déployer progressivement](set-feature-group-gradual-rollout.md)
* [Création de rapports](reporting.md)

<!-- -->
