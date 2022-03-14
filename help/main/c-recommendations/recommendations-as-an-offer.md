---
keywords: Recommendations;offre
description: Découvrez comment utiliser Adobe Recommendations en tant qu’offre dans les activités de tests A/B (y compris l’affectation automatique et le ciblage automatique) et de ciblage d’expérience (XT).
title: Comment utiliser Recommendations en tant qu’offre dans d’autres types d’activités ?
feature: Recommendations
exl-id: ec520555-b439-46a9-ab2d-f0981532bffb
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 100%

---

# ![PREMIUM](/help/main/assets/premium.png) Recommendations en tant qu’offre

Vous pouvez maintenant inclure des recommandations dans les activités de [!UICONTROL test A/B] (dont l’[!UICONTROL affectation automatique] et le [!UICONTROL ciblage automatique]) et de [!UICONTROL ciblage d’expérience].

Cette fonctionnalité offre de nouvelles fonctionnalités, telles que :

* Testez et ciblez le contenu des recommandations et des non-recommandations dans la même activité.
* Testez facilement l’emplacement des recommandations sur la page, y compris l’ordre de plusieurs recommandations.
* Dirigez automatiquement le trafic vers les recommandations les plus performantes à l’aide de l’[!UICONTROL affectation automatique].
* À l’aide du [!UICONTROL ciblage automatique], affectez de manière dynamique les visiteurs à des expériences de recommandations personnalisées en fonction de leur profil.

Pour commencer, créez une activité de [!UICONTROL test A/B] ou de [!UICONTROL ciblage d’expérience] à l’aide du [!UICONTROL compositeur d’expérience visuelle], puis utilisez l’action [!UICONTROL Insérer avant], [!UICONTROL Insérer après] ou [!UICONTROL Remplacer par] pour ajouter des recommandations à une expérience.

## Ajouter une recommandation en tant qu’offre dans une activité test A/B ou XT

1. Démarrez le workflow assisté en trois étapes à l’aide du compositeur d’expérience visuelle (VEC) pour créer une activité de [test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) ou de [ciblage d’expérience](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md) (XT).

   >[!NOTE]
   >
   >Pour les tests A/B, n’oubliez pas que vous pouvez choisir l’option [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) pour rediriger automatiquement le trafic vers les recommandations les plus performantes ou l’option [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) pour affecter les visiteurs aux expériences de recommandations personnalisées basées sur leur profil.

1. Lors de la création d‘une [expérience](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md), cliquez sur l’élément que vous souhaitez ajouter à une recommandation en tant qu‘offre, sélectionnez l‘action **[!UICONTROL Insérer avant]**, **[!UICONTROL Insérer après]** ou **[!UICONTROL Remplacer par]**, puis sélectionnez [!UICONTROL Recommandation].

   L’illustration suivante présente l’option [!UICONTROL Insérer après > Recommandation].

   ![Insérer une recommandation en tant qu’offre](/help/main/c-recommendations/assets/replace-after-recommendations.png)

1. Effectuez un choix parmi les options suivantes pour afficher les critères de recommandations populaires par type de page :

   * Page Panier
   * Page de catégorie
   * Page d’accueil
   * Page d’entrée
   * Page de produit
   * Page Résultats de recherche
   * Page de remerciement
   * Les autres

1. Sélectionnez les [critères](/help/main/c-recommendations/c-algorithms/algorithms.md) souhaités, puis cliquez sur [!UICONTROL Suivant].
1. Sélectionnez la [conception](/help/main/c-recommendations/c-design-overview/design-overview.md) souhaitée, puis cliquez sur [!UICONTROL Suivant].
1. Dans la boîte de dialogue [!UICONTROL Options], spécifiez les éléments suivants :

   * Choisissez une [collection](/help/main/c-recommendations/c-products/collections.md).
   * Configurez les options [Promotion avant et Promotion arrière](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md), en fonction des besoins.

1. Cliquez sur [!UICONTROL Enregistrer].
1. Terminez la configuration de l’activité Test A/B ou XT à l’aide du workflow assisté en trois parties.

## Modifier la configuration d’une offre de recommandations

Vous pouvez modifier la configuration d’une offre de deux manières :

* À l’aide du menu [!UICONTROL Modifier]
* À l’aide du panneau [!UICONTROL Modifications]

### Modifier une offre de recommandations à l’aide du menu Modifier

1. Sélectionnez l’offre que vous souhaitez modifier, puis cliquez sur **[!UICONTROL Modifier]**.

   ![Modifier l’offre de recommandations](/help/main/c-recommendations/assets/recs-offer-edit.png)

1. Effectuez un choix parmi les options suivantes :

   * [Modifier les critères](/help/main/c-recommendations/c-algorithms/algorithms.md)
   * [Modifier la conception](/help/main/c-recommendations/c-design-overview/design-overview.md)
   * [Modifier la collection](/help/main/c-recommendations/c-products/collections.md)
   * [Modifier la promotion](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)

1. Apportez vos modifications.

### Modifier une offre de recommandations à l’aide du panneau Modifications

1. Cliquez sur l’icône [!UICONTROL Modifications] **( `</>` )** pour afficher le panneau [Modifications](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md).
1. Passez votre curseur de souris au-dessus de l’action souhaitée, puis cliquez sur l’icône **[!UICONTROL Modifier]**.

   ![Panneau Modifications](/help/main/c-recommendations/assets/recs-offer-modifications.png)

1. Apportez vos modifications.

## Supprimer une offre de recommandations

Il existe deux façons de supprimer une offre de recommandations :

* À l’aide du menu [!UICONTROL Modifier]
* À l’aide du panneau [!UICONTROL Modifications]

### Supprimer une offre de recommandations dans le menu Édition

1. Cliquez sur l’offre à supprimer, puis sur **[!UICONTROL Mise en page > Supprimer]**.

   ![Supprimer](/help/main/c-recommendations/assets/recs-offer-remove.png)

### Supprimer une offre de recommandations à l’aide du panneau Modifications

1. Cliquez sur l’icône [!UICONTROL Modifications] **( &lt;/> )** pour afficher le panneau [Modifications](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md).
1. Passez le curseur de la souris sur l’action souhaitée, puis cliquez sur l’icône [!UICONTROL Supprimer].

   ![Icône Supprimer](/help/main/c-recommendations/assets/recs-offer-delete.png)

### Affichage de l’état de l’offre de recommandations {#status}

L’état de l’offre de recommandations (algorithme) s’affiche en bas de la page [!UICONTROL Aperçu] pour les tests A/B et les activités de ciblage d’expérience (XT) contenant des offres Recommendations :

* Résultats prêts
* Résultats non prêts
* Échec du flux

![État de l’offre de recommandations](/help/main/c-recommendations/assets/recs-offer-status.png)

## Vidéo de formation : Recommendations en tant qu’offre ![Badge d’aperçu](/help/main/assets/overview.png)

>[!VIDEO](https://video.tv.adobe.com/v/28878)
