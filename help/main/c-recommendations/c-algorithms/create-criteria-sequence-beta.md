---
keywords: séquence de critères;critères multiples;algorithmes;critères;critères de recommandations;séquence;nombre limite d’éléments renvoyés;contrôle au niveau de l’emplacement;emplacement
description: Découvrez comment configurer des séquences de maximum cinq critères pour exercer un plus grand contrôle sur les éléments qui apparaissent dans vos activités Recommendations.
title: Comment créer des séquences de critères dans Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: c8b0e0414603761b1c67b13d74ffa96d745c99e3
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 19%

---

# Création d’une séquence de critères

Utilisez des séquences de maximum cinq critères pour exercer un plus grand contrôle sur les éléments qui apparaissent dans vos activités [!DNL Adobe Target] [!UICONTROL Recommendations]. Vous pouvez également limiter le nombre d’éléments renvoyés (parfois appelé &quot;contrôle de niveau emplacement&quot;).

>[!NOTE]
>
>Les séquences de critères ne peuvent pas être utilisées avec les activités [!UICONTROL Recommendations] créées avant la version d’octobre 2016 de [!DNL Target Premium].

Pour créer une séquence de critères, vous devez d’abord créer les critères que vous souhaitez inclure dans la séquence. Voir [Création de critères](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md) pour plus d’informations.

En utilisant une séquence de critères, vous pouvez fournir des recommandations ciblées supplémentaires au lieu d’utiliser des recommandations de sauvegarde plus génériques lorsqu’un critère ne renvoie pas suffisamment de résultats pour remplir votre conception. En règle générale, une séquence de critères procède d’un ciblage plus spécifique, qui peut renvoyer moins de résultats, à un ciblage plus général, qui renvoie généralement plus de résultats.

Vos séquences de critères peuvent varier en fonction du type de page, comme illustré dans les exemples suivants :

| Type de page | Ordre de séquence possible |
| --- | --- |
| Page de produit | <ol><li>En fonction de l’élément actif, de la même marque</li><li>Basé sur l’article actuel, de toutes les marques</li><li>Basé sur la similarité de contenu</li><li>Basé sur les meilleurs vendeurs</li><li>Basé sur les articles les plus consultés sur le site</li></ol> |
| Page d&#39;accueil | <ol><li>Basé sur le dernier achat du visiteur </li><li>Basé sur l’article préféré du visiteur</li><li>Basé sur la catégorie préférée du visiteur</li><li>Basé sur les meilleurs vendeurs</li><li>Basé sur les articles les plus consultés sur le site</li></ol> |

## Création d’une séquence de critères

Vous créez des séquences de critères à partir de l’écran [!UICONTROL Create Criteria Sequence].

Il existe plusieurs façons d’accéder à l’écran [!UICONTROL Create Criteria Sequence]. Certaines options de l’écran varient en fonction de l’accès à ce dernier.

* Sur l’écran de la bibliothèque **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**, cliquez sur **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**. Les critères que vous créez à cet emplacement deviennent automatiquement disponibles pour toutes les activités [!UICONTROL Recommendations].
* Lorsque vous créez une activité [!UICONTROL Recommendations], dans l’écran [!UICONTROL Select Criteria], cliquez sur **[!UICONTROL Create New]** > **[!UICONTROL Create Criteria Sequence]**. Vous avez la possibilité d’enregistrer votre nouvelle séquence de critères pour l’utiliser avec d’autres activités [!UICONTROL Recommendations].
* Lorsque vous modifiez une activité [!UICONTROL Recommendations], cliquez dans la zone [!UICONTROL Recommendations Location] de votre page, puis sélectionnez **[!UICONTROL Change Criteria]**. Sur l’écran [!UICONTROL Select Criteria], cliquez sur **[!UICONTROL Create New]** > **[!UICONTROL Create Criteria Sequence]**. Vous avez la possibilité d&#39;enregistrer vos nouveaux critères pour les utiliser avec d&#39;autres activités [!UICONTROL Recommendations].

Les étapes suivantes supposent que vous accédez à l’écran [!UICONTROL Create Criteria Sequence] à l’aide de la première méthode : l’écran de bibliothèque **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** .

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Cliquez sur **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**.

1. Renseignez les informations de la section [Informations de base](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info) .

1. Dans la section **[!UICONTROL Criteria Sequence]** , cliquez sur le signe plus ( + ) pour ajouter une ou plusieurs séquences de critères.

   L’ordre de séquence définit l’ordre dans lequel une conception est remplie. Si le critère 1 ne comporte pas suffisamment de recommandations pour remplir votre conception, les créneaux restants sont remplis avec le critère 2, etc.

1. Sur l’écran [!UICONTROL Select Criteria], sélectionnez un critère, puis cliquez sur **[!UICONTROL Save]**.

   Vous pouvez utiliser la zone [!UICONTROL Search] et l’option de filtre pour trouver les critères souhaités.

1. (Facultatif) Faites glisser la bascule **[!UICONTROL Limit the number of items returned]** vers la position &quot;activée&quot;, puis spécifiez le nombre d’éléments (entre 1 et 50).

   Pour vous aider à comprendre la valeur de l’option [!UICONTROL Limit the number of items returned] (parfois appelée &quot;contrôle au niveau de l’emplacement&quot;), tenez compte des cas d’utilisation suivants :

   * **Cas d’utilisation 1** : vous souhaitez combiner différents types d’éléments dans un seul bac de recommandations. Par exemple, vous souhaitez afficher un mélange de vêtements de rechange (vestes) et de toits (chemises, T-shirts). Pour ce faire, utilisez une collection pour l’activité qui inclut tous les types de produits potentiels que vous souhaitez dans n’importe quel emplacement de votre conception. Ensuite, configurez vos premiers critères avec un filtre statique qui limite les critères pour inclure uniquement les vêtements de rechange, et configurez vos seconds critères avec un filtre statique qui limite les critères à n’inclure que les supérieurs. Enfin, ajoutez les deux critères à une séquence de critères et limitez le premier critère à 2 emplacements.

     La barre d’état Recommandations peut se présenter comme suit sur votre site :

     ![Barre de recommandations de produits phares](/help/main/c-recommendations/c-algorithms/assets/featured-products.png)

   * **Cas d’utilisation 2** : vous souhaitez combiner des éléments alternatifs et des éléments complémentaires. Configurez un critère pour utiliser un algorithme consulté/consulté et un filtre dynamique qui limite les articles recommandés à la catégorie de l’article actif. Configurez le deuxième critère pour utiliser un algorithme consulté/acheté et utilisez un filtre dynamique qui inclut uniquement les articles recommandés qui ne correspondent pas à la catégorie de l’article actif. Enfin, ajoutez les deux critères à une séquence et limitez le premier critère à 2 emplacements.

1. Continuez à ajouter des critères supplémentaires à votre séquence. Vous pouvez ajouter jusqu’à cinq critères à une séquence.

1. Activez les [options de contenu de sauvegarde](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content).

1. Cliquez sur **[!UICONTROL Create]**.

   La séquence de critères s’affiche dans la liste [!UICONTROL Criteria].

   Pour plus d’informations sur les options de logique de recommandation, consultez les [Critères](/help/main/c-recommendations/c-algorithms/algorithms.md).