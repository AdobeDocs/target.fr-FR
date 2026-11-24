---
keywords: séquence de critères;critères multiples;algorithmes;critères;critères de recommandations;séquence;nombre limite d’éléments renvoyés;contrôle au niveau de l’emplacement;emplacement
description: Découvrez comment définir des séquences de cinq critères maximum pour mieux contrôler les éléments qui apparaissent dans vos activités Recommendations.
title: Comment créer des séquences de critères dans Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: 5366c86c-7685-478b-a621-9b3f24296ab7
TQID: 'https://experienceleague.adobe.com/dxO5cKxesTxgzZyfcvydQUlSq4TAgFN0ztT5VIe1WKU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 9%
---
# Création d’une séquence de critères {#create-criteria-sequence}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment créer des séquences de critères pour contrôler les éléments qui apparaissent dans les activités [!DNL Adobe Target Recommendations].

>[!ENDSHADEBOX]

Les séquences de cinq critères maximum permettent de mieux contrôler les éléments qui apparaissent dans les activités [!DNL Adobe Target] **[!UICONTROL Recommendations]**. Le nombre d’éléments renvoyés peut également être limité (parfois appelé « contrôle au niveau du slot »).

Lorsqu’un critère ne renvoie pas suffisamment de résultats pour remplir la conception, une séquence de critères fournit des recommandations ciblées supplémentaires au lieu de recommandations de sauvegarde plus génériques. En règle générale, une séquence de critères passe d’un ciblage plus spécifique, qui peut renvoyer moins de résultats, à un ciblage plus général, qui renvoie généralement plus de résultats.

>[!NOTE]
>
>Les séquences de critères ne peuvent pas être utilisées avec les activités **[!UICONTROL Recommendations]** créées avant la version d’octobre 2016 de [!DNL Target Premium].

Pour créer une séquence de critères, commencez par créer les critères à inclure dans la séquence. Voir [Créer des critères](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md) pour plus d’informations.

L’ordre d’une séquence de critères peut varier en fonction du type de page, comme illustré dans les exemples suivants :

| Type de page | Ordre de séquence possible |
| --- | --- |
| Page de produit | <ol><li>Selon l’article actuel, de la même marque</li><li>Basé sur l’article actuel, de toutes les marques</li><li>Basé sur la similarité de contenu</li><li>Basé sur les meilleurs vendeurs</li><li>Basé sur les articles les plus consultés sur le site</li></ol> |
| Page d&#39;accueil | <ol><li>Basé sur le dernier achat du visiteur </li><li>Basé sur l’article préféré du visiteur</li><li>Basé sur la catégorie préférée du visiteur</li><li>Basé sur les meilleurs vendeurs</li><li>Basé sur les articles les plus consultés sur le site</li></ol> |

## Création d’une séquence de critères

Les séquences de critères sont créées à partir de l’écran **[!UICONTROL Créer une séquence de critères]**. Il existe plusieurs façons d’accéder à cet écran. Certaines options d’écran varient selon la manière dont l’écran est atteint.

* Dans l’écran de la bibliothèque **[!UICONTROL Recommandations]** > **[!UICONTROL Critères]**, cliquez sur **[!UICONTROL Créer des critères]** > **[!UICONTROL Créer une séquence de critères]**. Les critères créés ici sont automatiquement rendus disponibles pour toutes les activités **[!UICONTROL Recommendations]**.
* Lors de la création d’une activité **[!UICONTROL Recommendations]**, dans l’écran **[!UICONTROL Sélectionner les critères]**, cliquez sur **[!UICONTROL Créer]** > **[!UICONTROL Créer une séquence de critères]**. La nouvelle séquence de critères peut être enregistrée pour être utilisée avec d’autres activités **[!UICONTROL Recommendations]**.
* Lors de la modification d’une activité **[!UICONTROL Recommendations]**, cliquez dans une zone **[!UICONTROL Emplacement des recommandations]** de la page, puis sélectionnez **[!UICONTROL Modifier les critères]**. Dans l’écran **[!UICONTROL Sélectionner des critères]**, cliquez sur **[!UICONTROL Créer]** > **[!UICONTROL Créer une séquence de critères]**. Les nouveaux critères peuvent être enregistrés pour être utilisés avec d’autres activités **[!UICONTROL Recommendations]**.

Les étapes suivantes supposent que l’écran **[!UICONTROL Créer une séquence de critères]** est accessible à partir du menu **[!UICONTROL Critères]**.

1. Cliquez Sur **[!UICONTROL Recommandations]** > **[!UICONTROL Critères]**.

1. Cliquez Sur **[!UICONTROL Créer Un Critère]** > **[!UICONTROL Créer Une Séquence De Critères]**.

   ![Page de critères avec l&#39;option Créer une séquence de critères sélectionnée dans le menu Créer des critères](../assets/criteria_create_6.png)

1. Renseignez les informations de la section [Informations de base](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. Dans la section **[!UICONTROL Séquence de critères]**, cliquez sur le signe plus ( + ) pour ajouter une ou plusieurs séquences de critères.

   L’ordre séquentiel définit l’ordre dans lequel une conception est remplie. Si le critère 1 ne contient pas suffisamment de recommandations pour remplir la conception, les emplacements restants sont remplis avec le critère 2, etc.

   ![Section Séquence de critères de la boîte de dialogue Créer une séquence de critères avec cinq champs de critères et le signe plus du critère 1 sélectionné](../assets/criteria_create_7.png)

1. Sur l’écran **[!UICONTROL Sélectionner les critères]**, sélectionnez un critère, puis cliquez sur **[!UICONTROL Enregistrer]**.

   La zone **[!UICONTROL Rechercher]** et l’option de filtre peuvent être utilisées pour trouver les critères souhaités.

1. (Facultatif) Activez **[!UICONTROL Limitez le nombre d’éléments renvoyés]**, puis spécifiez le nombre d’éléments (entre 1 et 50).

   ![Section de séquence de critères avec le critère 1 Recommandé pour vous et l&#39;option Limiter le nombre d&#39;éléments renvoyés activée](../assets/criteria_create_8.png)

   Les cas d’utilisation suivants illustrent la valeur de l’option **[!UICONTROL Limiter le nombre d’éléments renvoyés]** (parfois appelée « contrôle au niveau de l’emplacement »).

   +++ Cas pratiques de limitation du nombre d’éléments renvoyés

   * **Cas d’utilisation 1** : mélange de différents types d’articles dans un seul plateau de recommandations, par exemple un mélange de vêtements d’extérieur (vestes) et de hauts (chemises, T-shirts). Pour ce faire, utilisez une collection pour l’activité qui inclut tous les types de produits pouvant apparaître dans n’importe quel emplacement de la conception. Configurez ensuite le premier critère avec un filtre statique qui comprend uniquement les vêtements d’extérieur, et le second critère avec un filtre statique qui comprend uniquement les dessus. Enfin, ajoutez les deux critères à une séquence de critères et limitez les premiers critères à 2 emplacements.

     La barre d’état des recommandations peut se présenter comme suit sur un site :

     ![Bac de recommandations de produits en vedette](assets/featured-products.png)

   * **Cas d’utilisation 2** : mélange d’éléments alternatifs et d’éléments complémentaires. Configurez un critère pour utiliser un algorithme de visionnage/visionnage et un filtre dynamique qui limite les éléments recommandés à la catégorie de l’élément actif. Configurez le deuxième critère pour utiliser un algorithme de consultation/achat et un filtre dynamique qui inclut uniquement les éléments recommandés qui ne correspondent pas à la catégorie de l’élément actuel. Enfin, ajoutez les deux critères à une séquence et limitez les premiers critères à 2 emplacements.

   +++

1. Continuez à ajouter des critères à la séquence. Vous pouvez ajouter jusqu’à cinq critères à une séquence.

1. Activez les [options de contenu de sauvegarde](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content).

1. Cliquez sur **[!UICONTROL Créer]**.

La séquence de critères s’affiche dans la liste **[!UICONTROL Critères]**.

Pour plus d’informations sur les options logiques de recommandation, consultez [Prise en main des critères](/help/main/c-recommendations/c-algorithms/algorithms.md).
