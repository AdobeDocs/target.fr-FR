---
keywords: criteria sequence;multiple criteria;algorithms;criteria;recommendations criteria;sequence;
description: Utilisez des séquences de cinq critères au maximum pour exercer un meilleur contrôle sur les éléments qui apparaissent dans vos activités Recommendations Adobe Target.
title: Création d’une séquence de critères
feature: criteria
uuid: 9a5ca86b-fc79-4c24-b86f-e333b0c63088
translation-type: tm+mt
source-git-commit: a0a11d91776499f7c8e62d68b64011d111bc1edc
workflow-type: tm+mt
source-wordcount: '1106'
ht-degree: 43%

---


# ![PREMIUM](/help/assets/premium.png) Création d’une séquence de critères

Utilisez des séquences de cinq critères au maximum afin d’exercer un plus grand contrôle sur les éléments qui apparaissent dans vos activités de [!UICONTROL Recommandations].

>[!NOTE]
>
>Il n’est pas possible d’utiliser des séquences de critères avec les activités [!UICONTROL Recommendations] créées avant la version d’octobre 2016 de [!DNL Target Premium].

Pour créer une séquence de critères, vous devez d’abord créer les critères que vous souhaitez inclure dans la séquence. Voir [Création de critères](/help/c-recommendations/c-algorithms/create-new-algorithm.md) pour plus d’informations.

En utilisant une séquence de critères, vous pouvez fournir des recommandations ciblées supplémentaires au lieu d’utiliser des recommandations de sauvegarde plus génériques lorsqu’un critère ne renvoie pas suffisamment de résultats pour remplir votre conception. En règle générale, une séquence de critères passe d’un ciblage plus spécifique, susceptible de renvoyer moins de résultats, à un ciblage plus général, qui renvoie généralement plus de résultats.

Vos séquences de critères peuvent varier en fonction du type de page, comme le montrent les exemples suivants :

| Type de page | Ordre de séquence possible |
| --- | --- |
| Page de produit | <ol><li>Basé sur l’article actuel, de la même marque</li><li>Basé sur l’article actuel, de toutes les marques</li><li>Basé sur la similarité de contenu</li><li>Basé sur les meilleurs vendeurs</li><li>Basé sur les articles les plus consultés sur le site</li></ol> |
| Page d&#39;accueil | <ol><li>Basé sur le dernier achat du visiteur </li><li>Basé sur l’article préféré du visiteur</li><li>Basé sur la catégorie préférée du visiteur</li><li>Basé sur les meilleurs vendeurs</li><li>Basé sur les articles les plus consultés sur le site</li></ol> |

## Accès à l’écran Créer une séquence de critères

Il existe plusieurs méthodes pour accéder à l’écran [!UICONTROL Créer une séquence de critères]. Certaines options de l’écran varient en fonction de l’accès à ce dernier.

* Dans l’écran de la bibliothèque **[!UICONTROL Recommandations]** > **[!UICONTROL Critères]**, cliquez sur **[!UICONTROL Créer des critères]** > **[!UICONTROL Créer une séquence de critères]**. Les critères que vous créez à cet emplacement deviennent automatiquement disponibles pour toutes les activités de [!UICONTROL Recommandations].
* Lorsque vous créez une activité [!UICONTROL Recommendations] , dans l’écran Sélectionner les critères, cliquez sur **[!UICONTROL Créer]** > **[!UICONTROL Créer une séquence]** de critères. Vous aurez la possibilité d’enregistrer la nouvelle séquence de critères afin de les utiliser avec d’autres activités de [!UICONTROL Recommandations].
* When you are editing a [!UICONTROL Recommendations] activity, click in a [!UICONTROL Recommendations Location] box on your page, then select **[!UICONTROL Change Criteria]**. Dans l’écran [!UICONTROL Sélectionner des critères], cliquez sur **[!UICONTROL Créer]** > **[!UICONTROL Créer une séquence de critères]**. Vous aurez la possibilité d’enregistrer les nouveaux critères afin de les utiliser avec d’autres activités de [!UICONTROL Recommandations].

Les étapes suivantes supposent que vous accédez à l’écran [!UICONTROL Créer une séquence] de critères à l’aide de la première méthode : l’écran **[!UICONTROL Recommendations]** > **[!UICONTROL Critères]** de bibliothèque.

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Critères]**.

1. Cliquez sur **[!UICONTROL Créer des critères]** > **[!UICONTROL Créer une séquence]** de critères.

   ![](assets/CreateCriteriaSequence.png)

## Renseignez la section Informations

1. Saisissez un **[!UICONTROL nom]** pour la séquence.

   Il s’agit du nom « interne » utilisé pour décrire cette séquence de critères. Les visiteurs de votre site ne verront pas ce nom.

   ![Section d’informations sur la création d’une séquence de critères](/help/c-recommendations/c-algorithms/assets/criteria-sequence-info.png)

1. Saisissez un **[!UICONTROL Titre d’affichage générique]** destiné au public qui apparaîtra sur la page si plusieurs critères de la séquence sont utilisés pour remplir la conception de [!UICONTROL Recommendations].

   Par exemple, vous souhaiterez peut-être remplacer « Les clients qui ont consulté ceci ont également consulté... » par « Recommandations personnalisées » si la conception est susceptible d’inclure des éléments en fonction de plusieurs clés de [!UICONTROL Recommandations].

1. Tapez une **[!UICONTROL Description]** succincte de la séquence de critères.

   La description doit vous aider à identifier la séquence de critères et peut inclure des informations sur son objectif.

1. Sélectionnez un **[!UICONTROL Secteur industriel vertical]**.

   Your default [industry vertical](/help/c-recommendations/c-algorithms/algorithms.md#section_936BCFCF234C49A2BEC1C38AAC2D71AF) appears automatically.

1. Sélectionnez un **[!UICONTROL Type de page]**.

   Vous pouvez sélectionner plusieurs types de page.

   Le secteur industriel vertical et les types de page sont utilisés pour classer les séquences de critères enregistrées afin que vous puissiez facilement les réutiliser pour d’autres activités de [!UICONTROL Recommandations].

## Créer une séquence {#sequence}

L’ordre de séquence définit l’ordre dans lequel une conception est remplie. Si le critère 1 ne comporte pas suffisamment de recommandations pour remplir votre conception, les créneaux restants seront remplis avec le critère 2, etc.

1. Dans la section Séquence **[!UICONTROL de]** critères, cliquez sur **[!UICONTROL Ajouter des critères]**.

   ![Critères d&#39;Ajoute](/help/c-recommendations/c-algorithms/assets/add-criteria.png)

1. On the [!UICONTROL Select Criteria] screen, select a criteria.

   Vous pouvez utiliser la zone de recherche et les listes déroulantes de filtre pour trouver les critères de votre choix.

   ![Sélection de critères](/help/c-recommendations/c-algorithms/assets/select-criteria.png)

1. Cliquez sur **[!UICONTROL Ajouter]**.

1. (Facultatif) Faites glisser la **[!UICONTROL case Limiter le nombre d’éléments renvoyés]** pour passer à la position &quot;Activé&quot;, puis indiquez le nombre d’éléments (entre 1 et 50).

   ![Limiter le nombre d&#39;éléments renvoyés à la bascule](/help/c-recommendations/c-algorithms/assets/limit-number.png)

   Pour vous aider à comprendre la valeur de l’option [!UICONTROL Limiter le nombre d’éléments renvoyés] , tenez compte des cas d’utilisation suivants :

   * **Cas d’utilisation 1**: Vous souhaitez avoir un mélange de différents types d’éléments dans un seul bac de Recommandations. Par exemple, vous souhaitez afficher un mélange de vêtements de dessus (vestes) et de dessus (chemises, T-shirts). Pour ce faire, utilisez une collection pour l’activité qui inclut tous les types de produits potentiels que vous souhaitez dans les emplacements de votre conception. Ensuite, configurez vos premiers critères avec un filtre statique limitant les critères à inclure uniquement les vêtements de dessus, et configurez vos deuxièmes critères avec un filtre statique limitant les critères à inclure uniquement les dessus. Enfin, ajoutez les deux critères à une séquence de critères et limitez le premier critère à 2 emplacements.

      La barre d’état des recommandations peut se présenter comme suit sur votre site :

      ![Bac de recommandations Produits phare](/help/c-recommendations/c-algorithms/assets/featured-products.png)

   * **Cas d’utilisation 2**: Vous voulez un mélange d&#39;éléments alternatifs et d&#39;éléments complémentaires. Configurez un critère pour utiliser un algorithme affiché/affiché et utilisez un filtre dynamique qui limite les éléments recommandés à la catégorie de l’élément actuel. Configurez le second critère pour utiliser un algorithme consulté/acheté et utilisez un filtre dynamique qui inclut uniquement les éléments recommandés qui ne correspondent pas à la catégorie de l’élément actuel. Enfin, ajoutez les deux critères à une séquence et limitez le premier critère à 2 emplacements.

1. Continuez à ajouter d’autres critères à votre séquence. Vous pouvez ajouter jusqu’à cinq critères à une séquence.

## Spécification du contenu de sauvegarde

Choisissez le contenu renvoyé lorsqu’il n’y a pas suffisamment de recommandations disponibles pour remplir le modèle de conception.

Lorsque vous créez une séquence de critères, les paramètres de recommandations de sauvegarde et de rendu de conception partiel sont ignorés en faveur des critères individuels qui composent la séquence. Pour utiliser les recommandations de sauvegarde et le rendu de conception partiel, vous devez les activer pour la séquence. Sélectionnez les bascules appropriées. Si vous choisissez d’autoriser les recommandations de sauvegarde, vous pouvez également choisir si les règles d’inclusion doivent être appliquées aux sauvegardes.

![Paramètres de sauvegarde du contenu](/help/c-recommendations/c-algorithms/assets/backup-content-settings.png)

1. (Facultatif) Faites glisser la bascule Rendu **[!UICONTROL de conception]** partiel vers la position &quot;Activé&quot;.

   Le plus grand nombre d’emplacements possible sera rempli, mais le modèle de conception peut inclure un espace vide pour les emplacements restants.

1. (Facultatif) Coupez la bascule **[!UICONTROL Sauvegarder Recommendations]** en position &quot;Activé&quot;.

   Remplissez les emplacements vides restants de la conception avec une sélection aléatoire des produits les plus consultés sur l’ensemble du site.

   Pour plus d’informations, voir [Utilisation d’une recommandation](/help/c-recommendations/c-algorithms/backup-recs.md)de sauvegarde.

1. (Conditionnel) Si vous avez sélectionné **[!UICONTROL Sauvegarder Recommendations]** à l’étape précédente, vous pouvez sélectionner **[!UICONTROL Appliquer les règles d’inclusion aux recommandations]** de sauvegarde.

   For more information see [Use dynamic and static inclusion rules](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

1. Cliquez sur **[!UICONTROL Enregistrer]**.

   La séquence de critères apparaît dans la liste des critères.

   Pour plus d’informations sur les options logiques de recommandation, voir [Critères](../../c-recommendations/c-algorithms/algorithms.md#concept_4BD01DC437F543C0A13621C93A302750).

## Vidéo de formation : Créer des critères dans Recommendations (12:33) ![Badge de didacticiel](/help/assets/tutorial.png)

Cette vidéo traite des sujets suivants :

* Création de critères
* Création d’une séquence de critères
* Téléchargement de critères personnalisés

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
