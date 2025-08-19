---
keywords: séquence de critères;critères multiples;algorithmes;critères;critères de recommandations;séquence;nombre limite d’éléments renvoyés;contrôle au niveau de l’emplacement;emplacement
description: Découvrez comment définir des séquences de cinq critères maximum afin d’exercer un meilleur contrôle sur les éléments qui apparaissent dans vos activités Adobe [!DNL Target] Recommendations.
title: Comment créer des séquences de critères dans Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: 5366c86c-7685-478b-a621-9b3f24296ab7
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 24%

---

# Création d’une séquence de critères

Utilisez des séquences de cinq critères maximum pour mieux contrôler les éléments qui apparaissent dans vos activités [!UICONTROL Recommendations]. Vous pouvez également limiter le nombre d’éléments renvoyés (parfois appelé « contrôle au niveau de l’emplacement »).

>[!NOTE]
>
>Les séquences de critères ne peuvent pas être utilisées avec [!UICONTROL Recommendations] activités créées avant la version d’octobre 2016 de [!DNL Target Premium].

Pour créer une séquence de critères, vous devez d’abord créer les critères que vous souhaitez inclure dans la séquence. Voir [Créer des critères](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md) pour plus d’informations.

En utilisant une séquence de critères, vous pouvez fournir des recommandations ciblées supplémentaires au lieu d’utiliser des recommandations de sauvegarde plus génériques lorsqu’un critère ne renvoie pas suffisamment de résultats pour remplir votre conception. En règle générale, une séquence de critères passe d’un ciblage plus spécifique, qui peut renvoyer moins de résultats, à un ciblage plus général, qui renvoie généralement plus de résultats.

Les séquences de critères peuvent varier dans l’ordre en fonction du type de page, comme illustré dans les exemples suivants :

| Type de page | Ordre de séquence possible |
| --- | --- |
| Page de produit | <ol><li>Basé sur l’article actuel, de la même marque</li><li>Basé sur l’article actuel, de toutes les marques</li><li>Basé sur la similarité de contenu</li><li>Basé sur les meilleurs vendeurs</li><li>Basé sur les articles les plus consultés sur le site</li></ol> |
| Page d&#39;accueil | <ol><li>Basé sur le dernier achat du visiteur </li><li>Basé sur l’article préféré du visiteur</li><li>Basé sur la catégorie préférée du visiteur</li><li>Basé sur les meilleurs vendeurs</li><li>Basé sur les articles les plus consultés sur le site</li></ol> |

## Création d’une séquence de critères

Vous créez des séquences de critères à partir de l’écran de [!UICONTROL Create Criteria Sequence].

Il existe plusieurs façons d’accéder à l’écran [!UICONTROL Create Criteria Sequence]. Certaines options de l’écran varient en fonction de l’accès à ce dernier.

* Sur l’écran **[!UICONTROL Recommendations]** > Bibliothèque **[!UICONTROL Criteria]**, cliquez sur **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**. Les critères que vous créez à cet emplacement deviennent automatiquement disponibles pour toutes les activités [!UICONTROL Recommendations].
* Lorsque vous créez une activité [!UICONTROL Recommendations], dans l’écran Sélectionner les critères , cliquez sur **[!UICONTROL Create New]** > **[!UICONTROL Create Criteria Sequence]**. Vous aurez la possibilité d’enregistrer votre nouvelle séquence de critères pour l’utiliser avec d’autres activités [!UICONTROL Recommendations].
* Lorsque vous modifiez une activité de [!UICONTROL Recommendations], cliquez dans une zone de [!UICONTROL Recommendations Location] de votre page, puis sélectionnez **[!UICONTROL Change Criteria]**. Sur l’écran [!UICONTROL Select Criteria], cliquez sur **[!UICONTROL Create New]** > **[!UICONTROL Create Criteria Sequence]**. Vous avez la possibilité d’enregistrer les nouveaux critères afin de les utiliser avec d’autres activités [!UICONTROL Recommendations].

Les étapes suivantes supposent que vous accédez à l’écran de [!UICONTROL Create Criteria Sequence] en utilisant la première méthode : **[!UICONTROL Recommendations]** > écran de bibliothèque **[!UICONTROL Criteria]**.

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Cliquez sur **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**.

   ![Image CreateCriteriaSequence](assets/CreateCriteriaSequence.png)

1. Renseignez les informations de la section [Informations de base](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. Dans la section **[!UICONTROL Criteria Sequence]**, cliquez sur **[!UICONTROL Add Criteria]**.

   L’ordre séquentiel définit l’ordre dans lequel une conception est remplie. Si le critère 1 ne contient pas suffisamment de recommandations pour remplir votre conception, les emplacements restants seront remplis avec le critère 2, etc.

   ![Ajouter des critères](/help/main/c-recommendations/c-algorithms/assets/add-criteria.png)

1. Sur l’écran [!UICONTROL Select Criteria], sélectionnez un critère, puis cliquez sur **[!UICONTROL Add]**.

   Vous pouvez utiliser la zone de recherche et les listes déroulantes de filtres pour trouver les critères souhaités.

   ![Sélection de critères](/help/main/c-recommendations/c-algorithms/assets/select-criteria.png)

1. (Facultatif) Faites glisser le bouton **[!UICONTROL Limit the number of items returned]** sur la position « activé », puis spécifiez le nombre d’éléments (entre 1 et 50).

   ![Limiter le nombre d’éléments renvoyés par le bouton (bascule)](/help/main/c-recommendations/c-algorithms/assets/limit-number.png)

   Pour mieux comprendre la valeur de l’option [!UICONTROL Limit the number of items returned] (parfois appelée « contrôle au niveau de l’emplacement »), tenez compte des cas d’utilisation suivants :

   * **Cas d’utilisation 1** : vous souhaitez disposer de plusieurs types d’éléments dans une seule barre d’état de recommandations. Par exemple, vous souhaitez afficher un mélange de vêtements d’extérieur (vestes) et de hauts (chemises, t-shirts). Pour ce faire, utilisez une collection pour l’activité qui inclut tous les types de produits potentiels que vous souhaitez dans les emplacements de votre conception. Ensuite, configurez vos premiers critères avec un filtre statique qui limite les critères pour n’inclure que les vêtements d’extérieur, et configurez vos seconds critères avec un filtre statique qui limite les critères pour n’inclure que les dessus. Enfin, ajoutez les deux critères à une séquence de critères et limitez les premiers critères à 2 emplacements.

     La barre d’état des recommandations peut se présenter comme suit sur votre site :

     ![Bac de recommandations des produits en vedette](/help/main/c-recommendations/c-algorithms/assets/featured-products.png)

   * **Cas d’utilisation 2** : vous souhaitez combiner des éléments alternatifs et des éléments complémentaires. Configurez un critère pour utiliser un algorithme affiché/consulté et utilisez un filtre dynamique qui limite les éléments recommandés à la catégorie de l’élément actuel. Configurez le deuxième critère pour utiliser un algorithme de consultation/achat et utiliser un filtre dynamique qui inclut uniquement les éléments recommandés qui ne correspondent pas à la catégorie de l’élément actuel. Enfin, ajoutez les deux critères à une séquence et limitez les premiers critères à 2 emplacements.

1. Continuez à ajouter des critères supplémentaires à votre séquence. Vous pouvez ajouter jusqu’à cinq critères à une séquence.

1. Activez les options [Sauvegarder le contenu](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content).

1. Cliquez sur **[!UICONTROL Save]**.

   La séquence de critères apparaît dans la liste des critères.

   Pour plus d’informations sur les options logiques de recommandation, voir [Critères](/help/main/c-recommendations/c-algorithms/algorithms.md).

## Vidéo de formation : créer des critères dans Recommendations (12:33) ![Badge de tutoriel](/help/main/assets/tutorial.png)

Cette vidéo traite des sujets suivants :

* Création de critères
* Création d’une séquence de critères
* Téléchargement de critères personnalisés

>[!VIDEO](https://video.tv.adobe.com/v/29401?quality=12&captions=fre_fr)
