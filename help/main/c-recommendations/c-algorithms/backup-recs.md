---
keywords: recommandation, sauvegarde, sauvegarde
description: Découvrez comment utiliser les recommandations de sauvegarde dans Adobe [!DNL Target Recommendations].
title: Utilisation d’une recommandation de sauvegarde
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: 070aa8ef-5691-4106-b5cf-45eb9f6f334c
TQID: 'https://experienceleague.adobe.com/TziWJoAuEdCqa7uMTpX0O0InnlnjtbPXP-0wzQ-FCM0'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 18%
---
# Utilisation d’une recommandation de sauvegarde {#backup-recommendations}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment les recommandations de sauvegarde remplissent les emplacements restants d’une conception dans [!DNL Adobe Target Recommendations].

>[!ENDSHADEBOX]

Lorsqu&#39;une recommandation ne comporte pas suffisamment d&#39;éléments recommandés pour remplir la conception, la fonction de recommandation de sauvegarde dans [!DNL Adobe Target] affiche les résultats de l&#39;algorithme de sauvegarde au lieu du contenu par défaut. Sans recommandation de sauvegarde, le système affiche le contenu par défaut à l’utilisateur.

>[!NOTE]
>
>Pour plus d’informations, y compris une matrice qui explique les résultats de l’utilisation des options **[!UICONTROL Rendu de conception partiel]** et **[!UICONTROL Afficher le contenu de sauvegarde]** ensemble ou séparément, consultez la section [Contenu de sauvegarde de l’article Créer des critères](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content).

La fonction de recommandation de sauvegarde utilise toujours les éléments les plus consultés sur le site pour remplir les emplacements restants une fois les données de l’algorithme utilisées. Par exemple, une conception est configurée pour afficher cinq éléments recommandés, mais l’algorithme dispose de suffisamment de données pour remplir seulement deux des cinq emplacements. La fonction de recommandation de sauvegarde remplit ensuite les trois autres emplacements avec les éléments les plus consultés.

Les recommandations de sauvegarde sont choisies de manière aléatoire à partir des 500 produits les plus consultés sur l’ensemble du site. La période des données pour les recommandations de sauvegarde est d’une semaine.

Les 500 résultats les plus consultés sont classés par ordre séquentiel, puis répartis par lots de 20. Les compartiments sont diffusés dans l’ordre, mais les résultats à l’intérieur de chaque compartiment sont randomisés et renvoyés à la page. Ainsi, les utilisateurs qui actualisent la page se voient présenter de nouveaux résultats randomisés. Si le jeu de résultats de l’union de la collection et des règles de filtrage est inférieur à 20, les éléments sont sélectionnés de manière aléatoire à partir de la collection.

Ce processus de compartimentation implique que les recommandations de sauvegarde sont indiquées dans l’ordre suivant :

1. Les 20 éléments les plus consultés, randomisés.
1. Les 20 éléments suivants les plus consultés, randomisés.
1. Les 20 éléments les plus consultés suivants, randomisés, etc.

Sans regroupement, le 499e article le plus consulté pourrait être affiché, suivi du 200e article le plus consulté, suivi du 380e article le plus consulté, et ainsi de suite. Le regroupement garantit que les éléments les plus consultés sont recommandés en premier.

Si des éléments sont regroupés dans des collections, les recommandations de sauvegarde générées pour chaque critère utilisent également la collection, de sorte que seuls les éléments de la collection sont inclus dans la recommandation de sauvegarde. Tout article exclu par des règles d’exclusion globales n’est pas diffusé comme recommandation de sauvegarde. Les doublons sont supprimés des lots de recommandations.

Les recommandations de sauvegarde sont activées par défaut et remplissent les emplacements supplémentaires dans une conception avec une sélection aléatoire des éléments les plus populaires sur le site.

L’utilisation des recommandations de sauvegarde fait généralement partie des discussions avec l’équipe d’implémentation lors de la configuration initiale. Pour modifier le paramètre de recommandation de sauvegarde après l’implémentation, contactez le gestionnaire de compte.

Lorsque le **[!UICONTROL Rendu de conception partiel]** (voir [Contenu de sauvegarde](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)) n’est pas activé et que la conception ne peut pas être remplie, les recommandations de sauvegarde (lorsqu’elles sont activées) ou le contenu par défaut s’affichent à la place.
