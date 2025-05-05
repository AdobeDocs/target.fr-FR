---
keywords: Recommendations;offre
description: Découvrez comment utiliser Adobe Recommendations en tant qu’offre dans les activités de tests A/B (y compris l’affectation automatique et le ciblage automatique) et de ciblage d’expérience (XT).
title: Comment utiliser Recommendations en tant qu’offre dans d’autres types d’activités ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: 3821d868f45b85d2f6f0e204f9828544b759067b
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 47%

---

# Recommendations en tant qu’offre

Vous pouvez désormais inclure des recommandations dans les activités [!UICONTROL A/B Test] (y compris les activités [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target]) et [!UICONTROL Experience Targeting] (XT).

Cette fonctionnalité offre de nouvelles fonctionnalités, telles que :

* Testez et ciblez le contenu des recommandations et des non-recommandations dans la même activité.
* Testez facilement le placement des recommandations sur la page, y compris l’ordre de plusieurs recommandations.
* Envoyez automatiquement le trafic vers l’expérience Recommendations la plus performante à l’aide de [!UICONTROL Auto-Allocate].
* À l’aide de [!UICONTROL Auto-Target], affectez de manière dynamique les visiteurs à des expériences de recommandations personnalisées en fonction de leur profil.

Pour commencer, créez une activité de [!UICONTROL A/B Test] ou de [!UICONTROL Experience Targeting] à l’aide de l’[!UICONTROL Visual Experience Composer] et utilisez l’action de [!UICONTROL Recommend] pour ajouter des recommandations à une expérience.

## Ajouter une recommandation en tant qu’offre dans une activité test A/B ou XT

1. Démarrez le workflow assisté en trois étapes à l’aide du compositeur d’expérience visuelle (VEC) pour créer une activité de [test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) ou de [ciblage d’expérience](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md) (XT).

   >[!NOTE]
   >
   >Pour les tests A/B, n’oubliez pas que vous pouvez choisir l’option [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) pour rediriger automatiquement le trafic vers les recommandations les plus performantes ou l’option [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) pour affecter les visiteurs aux expériences de recommandations personnalisées basées sur leur profil.

1. Lors de la création d’une [expérience](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md), cliquez sur l’élément auquel vous souhaitez ajouter une recommandation en tant qu’offre, cliquez sur **[!UICONTROL Replace Content]** ( ![icône Remplacer le contenu](/help/main/assets/icons/Switch.svg) ), puis sélectionnez **[!UICONTROL Recommendation]**.

   ![Insérer une recommandation en tant qu’offre](/help/main/c-recommendations/t-create-recs-activity/assets/recs-as-offer.png)

1. Dans le rail de [!UICONTROL Recommendation] situé sur le côté droit, cliquez sur **[!UICONTROL Select a Recommendation]** pour afficher la boîte de dialogue [!UICONTROL Select Criteria].

1. Cliquez sur **[!UICONTROL Create Criteria]** ou sélectionnez un critère existant.

1. (Facultatif) Cliquez sur l’icône **[!UICONTROL Filter]** ( ![icône Filtrer](/help/main/assets/icons/Filter.svg) ) pour effectuer une sélection parmi les options suivantes afin d’afficher les critères de recommandations populaires par type de page :

   * Page Panier
   * Page de catégorie
   * Page d’accueil
   * Page de destination
   * Page de produit
   * Page Résultats de recherche
   * Page de remerciement
   * Les autres

1. Cliquez sur **[!UICONTROL Create Criteria]** ou sélectionnez un [critère](/help/main/c-recommendations/c-algorithms/algorithms.md) existant, puis cliquez sur **[!UICONTROL Next]** pour afficher la boîte de dialogue [!UICONTROL Select Design].

1. Cliquez sur **[!UICONTROL Create Design]** ou sélectionnez une [conception](/help/main/c-recommendations/c-design-overview/design-overview.md) existante, puis cliquez sur **[!UICONTROL &#x200B; Next]**.

1. Dans la boîte de dialogue [!UICONTROL Options], spécifiez ce qui suit :

   * Choisissez une [collection](/help/main/c-recommendations/c-products/collections.md).
   * Configurez les options [Promotion avant et Promotion arrière](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md), en fonction des besoins.

1. Cliquez sur **[!UICONTROL Save]**.
1. Terminez la configuration de l’activité Test A/B ou XT à l’aide du workflow assisté en trois parties.

## Modifier la configuration d’une offre de recommandations

1. Dans le rail de [!UICONTROL Recommendation], cliquez sur l’icône **[!UICONTROL Edit]** ( ![icône Modifier](/help/main/assets/icons/Edit.svg) ) en regard de [!UICONTROL Criteria Name], [!UICONTROL Design Name] ou [!UICONTROL Collection Name] pour modifier l’élément.

## Supprimer une offre de recommandations

1. Cliquez sur l’icône **[!UICONTROL Delete]** ( ![icône Supprimer](/help/main/assets/icons/Delete.svg) ) en haut du panneau [!UICONTROL Recommendation].

### Affichage du statut de l’offre de recommandations {#status}

L’état des offres de recommandations (algorithme) s’affiche au bas de la page [!UICONTROL Overview] de l’activité pour les tests A/B et les activités de ciblage d’expérience (XT) contenant des offres de recommandations :

* Résultats prêts
* Résultats non prêts
* Échec du flux
