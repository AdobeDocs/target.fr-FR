---
keywords: recommandation, sauvegarde, sauvegarde
description: Découvrez comment utiliser les recommandations de sauvegarde dans  [!DNL Target Recommendations].
title: Comment utiliser une recommandation de sauvegarde dans  [!DNL Target Recommendations] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: 070aa8ef-5691-4106-b5cf-45eb9f6f334c
TQID: https://experienceleague.adobe.com/TziWJoAuEdCqa7uMTpX0O0InnlnjtbPXP-0wzQ-FCM0
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 533
ht-degree: 68%

---

# Utilisation d’une recommandation de sauvegarde

Si vous utilisez la fonction de recommandation de sauvegarde dans [!DNL Adobe Target], toute recommandation qui ne comporte pas suffisamment d’éléments recommandés n’affiche pas le contenu par défaut. Recommandations affiche, à la place, les résultats de l’algorithme de sauvegarde.

Si vous n’utilisez pas de recommandation de sauvegarde ou si une recommandation ne comporte pas suffisamment d’articles pour remplir l’écran, le système présente le contenu par défaut à l’utilisateur.

>[!NOTE]
>
>Vous trouverez des informations supplémentaires dans la section [Contenu) de la rubrique Création de critères](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content) y compris une matrice qui explique les résultats que vous observerez lors de l’utilisation conjointe ou séparée des options [!UICONTROL Rendu de conception partiel] et [!UICONTROL Afficher les recommandations de sauvegarde].

La fonction de recommandation de sauvegarde utilise toujours les éléments les plus consultés sur le site pour remplir les emplacements restants une fois les données de l’algorithme utilisées. Par exemple, votre modèle est configuré de manière à afficher cinq articles recommandés et vous utilisez l’algorithme *Affinités d’achats*. Toutefois, si vous ne disposez que de données pour remplir deux des cinq créneaux, la fonction de recommandation de sauvegarde remplira les trois autres par les articles les plus consultés.

Les recommandations de sauvegarde sont choisies de manière aléatoire à partir des 500 produits les plus consultés sur l’ensemble du site. La période des données pour les recommandations de sauvegarde est d’une semaine.

Les 500 résultats les plus consultés sont classés par ordre séquentiel, puis répartis par lots de 20. Ces lots sont servis dans l’ordre, mais les résultats qu’ils contiennent sont randomisés et renvoyés vers la page. Si les utilisateurs actualisent la page, ils visualisent des résultats nouveaux et randomisés. Si le jeu de résultats de l’union de la collection et des règles de filtrage est inférieur à 20, il effectue une sélection aléatoire dans la collection.

Ce processus de compartimentation implique que les recommandations de sauvegarde sont indiquées dans l’ordre suivant :

1. Afficher les 20 éléments les plus consultés, randomisés, puis
1. Afficher les 20 éléments suivants les plus consultés, randomisés, puis
1. Afficher les 20 éléments suivants les plus consultés, randomisés,
1. et ainsi de suite.

Sans ce regroupement des recommandations de sauvegarde, il aurait été possible d’afficher le 499e élément le plus consulté, suivi du 200e, puis du 380e, etc. Le processus de regroupement par lots garantit que les éléments les plus consultés sont recommandés en priorité.

>[!NOTE]
>
>Si vous regroupez vos articles dans des catalogues, les recommandations de sauvegarde générées pour chaque algorithme de la recommandation utilisent également le catalogue. Par conséquent, seuls les articles du catalogue sont inclus dans la recommandation de sauvegarde.

Tout article exclu par des règles d’exclusion globales n’est pas diffusé comme recommandation de sauvegarde.

Les recommandations de sauvegarde sont activées par défaut et remplissent les créneaux supplémentaires d’un modèle sur la base d’une sélection aléatoire des articles les plus populaires du site.

Les doublons sont supprimés des lots de recommandations.

L’utilisation des recommandations de sauvegarde fait généralement partie de la discussion avec l’équipe de mise en œuvre lors de la configuration initiale. Si vous souhaitez modifier la recommandation de sauvegarde après la mise en œuvre, contactez votre gestionnaire de compte.

Si l’option Activer le rendu de conception partiel (voir [Paramètres de contenu](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)) n’est pas activée et que le modèle ne s’affiche pas, la recommandation de sauvegarde ou le contenu par défaut s’affiche à la place.
