---
title: Utilisation du contexte dans les règles d’audience
description: Découvrez comment utiliser les attributs contextuels dans les règles d’audience pour les indicateurs de fonctionnalités et les groupes de fonctionnalités dans les indicateurs.
hide: true
exl-id: 0367f475-9209-4d53-86b4-a739a73a23a7
source-git-commit: eeba7af62ab101e687852ce993a001832ce4a83b
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 1%

---

# Utilisation du contexte dans les règles d’audience {#context-in-audience-rules}

Les attributs contextuels sont des valeurs fournies par l’application cliente au moment de l’exécution. Ils vous permettent de cibler les utilisateurs en fonction d’informations dynamiques au niveau de la session, telles que la langue active de l’utilisateur, le type d’appareil ou l’état de l’application.

Les attributs de contexte sont pertinents pour les clients web et mobiles.

## Fonctionnement des attributs de contexte {#how-context-attributes-work}

Votre application transmet des attributs de contexte aux indicateurs lors de l&#39;évaluation d&#39;un indicateur de fonctionnalité. Vous définissez des règles dans la console pour vérifier ces valeurs, et la plateforme les utilise au moment de l’évaluation pour déterminer si l’utilisateur est admissible.

## Ajout d’un attribut de contexte {#adding-context-attribute}

Pour ajouter un attribut de contexte à une règle d’audience :

1. Ouvrez l&#39;indicateur de fonctionnalité ou le groupe de fonctionnalités dans la console.
2. Accédez à l’onglet **Audience**.
3. Sous **Contexte**, ajoutez une nouvelle condition.
4. Sélectionnez l’attribut de contexte, l’opérateur et la valeur.

Si l’attribut de contexte dont vous avez besoin n’apparaît pas dans la liste, vous pouvez en créer un, voir [ Création de vos attributs de contexte ](creating-your-context-attributes.md).

## Voir également {#see-also}

* [Audience dans les indicateurs de fonctionnalité et les groupes de fonctionnalités](audience-in-feature-flags-and-feature-groups.md)

<!-- -->
