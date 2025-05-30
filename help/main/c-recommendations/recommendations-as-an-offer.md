---
keywords: Recommendations;offre
description: Découvrez comment utiliser Adobe Recommendations en tant qu’offre dans les activités de tests A/B (y compris l’affectation automatique et le ciblage automatique) et de ciblage d’expérience (XT).
title: Comment utiliser Recommendations en tant qu’offre dans d’autres types d’activités ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: ec520555-b439-46a9-ab2d-f0981532bffb
source-git-commit: f848c79cb95009b5810a1707d04e548a57220e12
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 60%

---

# Recommendations en tant qu’offre

Vous pouvez désormais inclure des recommandations dans les activités [!UICONTROL A/B Test] (y compris les activités [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target]) et [!UICONTROL Experience Targeting] (XT).

Cette fonctionnalité offre de nouvelles fonctionnalités, telles que :

* Testez et ciblez le contenu des recommandations et des non-recommandations dans la même activité.
* Testez facilement l’emplacement des recommandations sur la page, y compris l’ordre de plusieurs recommandations.
* Envoyez automatiquement le trafic vers l’expérience Recommendations la plus performante à l’aide de [!UICONTROL Auto-Allocate].
* À l’aide de [!UICONTROL Auto-Target], affectez de manière dynamique les visiteurs à des expériences de recommandations personnalisées en fonction de leur profil.

Pour commencer, créez une activité de [!UICONTROL A/B Test] ou de [!UICONTROL Experience Targeting] à l’aide de l’[!UICONTROL Visual Experience Composer] et utilisez l’action de [!UICONTROL Insert Before], de [!UICONTROL Insert After] ou de [!UICONTROL Replace With] pour ajouter des recommandations à une expérience.

## Ajouter une recommandation en tant qu’offre dans une activité test A/B ou XT

1. Démarrez le workflow assisté en trois étapes à l’aide du compositeur d’expérience visuelle (VEC) pour créer une activité de [test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) ou de [ciblage d’expérience](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md) (XT).

   >[!NOTE]
   >
   >Pour les tests A/B, n’oubliez pas que vous pouvez choisir l’option [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) pour rediriger automatiquement le trafic vers les recommandations les plus performantes ou l’option [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) pour affecter les visiteurs aux expériences de recommandations personnalisées basées sur leur profil.

1. Lors de la création d’une [expérience](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md), cliquez sur l’élément auquel vous souhaitez ajouter une recommandation en tant qu’offre, cliquez sur **[!UICONTROL Replace Content]**, puis sélectionnez **[!UICONTROL Recommendation]**.

   ![Insérer une recommandation en tant qu’offre](/help/main/c-recommendations/t-create-recs-activity/assets/recs-as-offer.png)

1. Effectuez un choix parmi les options suivantes pour afficher les critères de recommandations populaires par type de page :

   * Page Panier
   * Page de catégorie
   * Page d’accueil
   * Page de destination
   * Page de produit
   * Page Résultats de recherche
   * Page de remerciement
   * Les autres

1. Sélectionnez le [critère](/help/main/c-recommendations/c-algorithms/algorithms.md) souhaité, puis cliquez sur [!UICONTROL Next].
1. Sélectionnez la [conception](/help/main/c-recommendations/c-design-overview/design-overview.md) souhaitée, puis cliquez sur [!UICONTROL Next].
1. Dans la boîte de dialogue [!UICONTROL Options], spécifiez ce qui suit :

   * Choisissez une [collection](/help/main/c-recommendations/c-products/collections.md).
   * Configurez les options [Promotion avant et Promotion arrière](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md), en fonction des besoins.

1. Cliquez sur [!UICONTROL Save].
1. Terminez la configuration de l’activité Test A/B ou XT à l’aide du workflow assisté en trois parties.

## Modifier la configuration d’une offre de recommandations

Vous pouvez modifier la configuration d’une offre de deux manières :

* Utilisation du menu [!UICONTROL Edit]
* Utilisation du panneau [!UICONTROL Modifications]

### Modifier une offre de recommandations à l’aide du menu Modifier

1. Cliquez sur l’offre à modifier, puis sur **[!UICONTROL Edit]**.

   ![Modifier l’offre de recommandations](/help/main/c-recommendations/assets/recs-offer-edit.png)

1. Effectuez un choix parmi les options suivantes :

   * [Modifier les critères](/help/main/c-recommendations/c-algorithms/algorithms.md)
   * [Modifier la conception](/help/main/c-recommendations/c-design-overview/design-overview.md)
   * [Modifier la collection](/help/main/c-recommendations/c-products/collections.md)
   * [Modifier la promotion](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)

1. Apportez vos modifications.

### Modifier une offre de recommandations à l’aide du panneau Modifications

1. Cliquez sur l’icône [!UICONTROL Modifications] **( `</>` )** pour afficher le volet [Modifications](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md).
1. Pointez sur l’action souhaitée, puis cliquez sur l’icône **[!UICONTROL Edit]** .

   ![Panneau Modifications](/help/main/c-recommendations/assets/recs-offer-modifications.png)

1. Apportez vos modifications.

## Supprimer une offre de recommandations

Il existe deux façons de supprimer une offre de recommandations :

* Utilisation du menu [!UICONTROL Edit]
* Utilisation du panneau [!UICONTROL Modifications]

### Supprimer une offre de recommandations dans le menu Édition

1. Cliquez sur l’offre à supprimer, puis sur **[!UICONTROL Layout > Remove]**.

   ![Supprimer](/help/main/c-recommendations/assets/recs-offer-remove.png)

### Supprimer une offre de recommandations à l’aide du panneau Modifications

1. Cliquez sur l’icône [!UICONTROL Modifications] **( &lt;/> )** pour afficher le volet [Modifications](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md).
1. Pointez sur l’action souhaitée, puis cliquez sur l’icône [!UICONTROL Delete] .

   ![Icône Supprimer](/help/main/c-recommendations/assets/recs-offer-delete.png)

### Affichage du statut de l’offre de recommandations {#status}

L’état (algorithme) de l’offre de recommandations s’affiche au bas de la page [!UICONTROL Overview] pour les tests A/B et les activités de ciblage d’expérience (XT) contenant des offres Recommendations :

* Résultats prêts
* Résultats non prêts
* Échec du flux

![État de l’offre de recommandations](/help/main/c-recommendations/assets/recs-offer-status.png)

## Vidéo de formation : Recommendations en tant qu’offre ![Badge d’aperçu](/help/main/assets/overview.png)

>[!VIDEO](https://video.tv.adobe.com/v/28878)
