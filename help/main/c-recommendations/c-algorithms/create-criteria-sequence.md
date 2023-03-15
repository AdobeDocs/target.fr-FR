---
keywords: séquence de critères;critères multiples;algorithmes;critères;critères de recommandations;séquence;nombre limite d’éléments renvoyés;contrôle au niveau de l’emplacement;emplacement
description: Découvrez comment configurer des séquences de maximum cinq critères pour exercer un plus grand contrôle sur les éléments qui apparaissent dans votre Adobe. [!DNL Target] Activités Recommendations.
title: Comment créer des séquences de critères dans Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 5366c86c-7685-478b-a621-9b3f24296ab7
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 34%

---

# Création d’une séquence de critères

Utilisez des séquences de cinq critères au maximum afin d’exercer un plus grand contrôle sur les éléments qui apparaissent dans vos activités de [!UICONTROL Recommandations. ] Vous pouvez également limiter le nombre d’éléments renvoyés (parfois appelé &quot;contrôle au niveau de l’emplacement&quot;).

>[!NOTE]
>
>Il n’est pas possible d’utiliser des séquences de critères avec les activités [!UICONTROL Recommendations] créées avant la version d’octobre 2016 de [!DNL Target Premium].

Pour créer une séquence de critères, vous devez d’abord créer les critères que vous souhaitez inclure dans la séquence. Voir [Création de critères](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md) pour plus d’informations.

En utilisant une séquence de critères, vous pouvez fournir des recommandations ciblées supplémentaires au lieu d’utiliser des recommandations de sauvegarde plus génériques lorsqu’un critère ne renvoie pas suffisamment de résultats pour remplir votre conception. En règle générale, une séquence de critères passe d’un ciblage plus spécifique, susceptible de renvoyer moins de résultats, à un ciblage plus général, qui renvoie généralement plus de résultats.

Vos séquences de critères peuvent varier en fonction du type de page, comme illustré dans les exemples suivants :

| Type de page | Ordre de séquence possible |
| --- | --- |
| Page de produit | <ol><li>Basé sur l’article actuel, de la même marque</li><li>Basé sur l’article actuel, de toutes les marques</li><li>Basé sur la similarité de contenu</li><li>Basé sur les meilleurs vendeurs</li><li>Basé sur les articles les plus consultés sur le site</li></ol> |
| Page d&#39;accueil | <ol><li>Basé sur le dernier achat du visiteur </li><li>Basé sur l’article préféré du visiteur</li><li>Basé sur la catégorie préférée du visiteur</li><li>Basé sur les meilleurs vendeurs</li><li>Basé sur les articles les plus consultés sur le site</li></ol> |

## Création d’une séquence de critères

Vous créez des séquences de critères à partir du [!UICONTROL Création d’une séquence de critères] écran.

Il existe plusieurs méthodes pour accéder à l’écran [!UICONTROL Créer une séquence de critères]. Certaines options de l’écran varient en fonction de l’accès à ce dernier.

* Dans l’écran de la bibliothèque **[!UICONTROL Recommandations]** > **[!UICONTROL Critères]**, cliquez sur **[!UICONTROL Créer des critères]** > **[!UICONTROL Créer une séquence de critères]**. Les critères que vous créez à cet emplacement deviennent automatiquement disponibles pour toutes les activités de [!UICONTROL Recommandations].
* Lorsque vous créez une [!UICONTROL Recommendations] activité, dans l’écran Sélectionner des critères , cliquez sur **[!UICONTROL Créer]** > **[!UICONTROL Création d’une séquence de critères]**. Vous aurez la possibilité d’enregistrer la nouvelle séquence de critères afin de les utiliser avec d’autres activités de [!UICONTROL Recommandations].
* Lorsque vous modifiez une [!UICONTROL Recommendations] activité, cliquer dans une [!UICONTROL Emplacement Recommendations] sur votre page, puis sélectionnez **[!UICONTROL Modification des critères]**. Dans l’écran [!UICONTROL Sélectionner des critères], cliquez sur **[!UICONTROL Créer]** > **[!UICONTROL Créer une séquence de critères]**. Vous aurez la possibilité d’enregistrer les nouveaux critères afin de les utiliser avec d’autres activités de [!UICONTROL Recommandations].

Les étapes suivantes supposent que vous accédez au [!UICONTROL Création d’une séquence de critères] écran en utilisant la première méthode : la valeur **[!UICONTROL Recommendations]** > **[!UICONTROL Critères]** écran de la bibliothèque.

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Critères]**.

1. Cliquez sur **[!UICONTROL Création de critères]** > **[!UICONTROL Création d’une séquence de critères]**.

   ![Image CreateCritèresSequence](assets/CreateCriteriaSequence.png)

1. Renseignez les informations de la section [Informations de base](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info) .

1. Dans le **[!UICONTROL Séquence de critères]** , cliquez sur **[!UICONTROL Ajouter des critères]**.

   L’ordre de séquence définit l’ordre dans lequel une conception est remplie. Si le critère 1 ne comporte pas suffisamment de recommandations pour remplir votre conception, les créneaux restants seront remplis avec le critère 2, etc.

   ![Ajouter des critères](/help/main/c-recommendations/c-algorithms/assets/add-criteria.png)

1. Sur le [!UICONTROL Sélectionner des critères] sélectionnez un critère, puis cliquez sur **[!UICONTROL Ajouter]**.

   Vous pouvez utiliser la zone de recherche et les listes déroulantes de filtrage pour trouver les critères souhaités.

   ![Sélection de critères](/help/main/c-recommendations/c-algorithms/assets/select-criteria.png)

1. (Facultatif) Faites glisser le **[!UICONTROL Limiter le nombre d’éléments renvoyés]** basculez sur la position &quot;activé&quot;, puis spécifiez le nombre d’éléments (entre 1 et 50).

   ![Limiter le nombre d’éléments renvoyés au bouton bascule](/help/main/c-recommendations/c-algorithms/assets/limit-number.png)

   Pour vous aider à comprendre la valeur de la variable [!UICONTROL Limiter le nombre d’éléments renvoyés] (parfois appelée &quot;contrôle au niveau de l’emplacement&quot;) prenez en compte les cas d’utilisation suivants :

   * **Cas d’utilisation 1**: Vous souhaitez combiner différents types d’éléments dans un seul bac de recommandations. Par exemple, vous souhaitez afficher un mélange de vêtements de rechange (vestes) et de toits (chemises, T-shirts). Pour ce faire, utilisez une collection pour l’activité qui inclut tous les types de produits potentiels que vous souhaitez dans n’importe quel emplacement de votre conception. Ensuite, configurez vos premiers critères avec un filtre statique qui limite les critères pour inclure uniquement les vêtements de rechange, et configurez vos seconds critères avec un filtre statique qui limite les critères à n’inclure que les supérieurs. Enfin, ajoutez les deux critères à une séquence de critères et limitez le premier critère à 2 emplacements.

      La barre d’état Recommandations peut se présenter comme suit sur votre site :

      ![Bac de recommandations de produits présentés](/help/main/c-recommendations/c-algorithms/assets/featured-products.png)

   * **Cas d’utilisation 2**: Vous voulez un mélange d’éléments alternatifs et d’éléments complémentaires. Configurez un critère pour utiliser un algorithme consulté/consulté et un filtre dynamique qui limite les articles recommandés à la catégorie de l’article actif. Configurez le deuxième critère pour utiliser un algorithme consulté/acheté et utilisez un filtre dynamique qui inclut uniquement les articles recommandés qui ne correspondent pas à la catégorie de l’article actif. Enfin, ajoutez les deux critères à une séquence et limitez le premier critère à 2 emplacements.

1. Continuez à ajouter des critères supplémentaires à votre séquence. Vous pouvez ajouter jusqu’à cinq critères à une séquence.

1. Activer [Options de contenu de sauvegarde](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content).

1. Cliquez sur **[!UICONTROL Enregistrer]**.

   La séquence de critères apparaît dans la liste des critères.

   Pour plus d’informations sur les options logiques de recommandation, voir [Critères](/help/main/c-recommendations/c-algorithms/algorithms.md).

## Vidéo de formation : Créer des critères dans Recommendations (12:33) ![Badge de tutoriel](/help/main/assets/tutorial.png)

Cette vidéo traite des sujets suivants :

* Création de critères
* Création d’une séquence de critères
* Téléchargement de critères personnalisés

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
