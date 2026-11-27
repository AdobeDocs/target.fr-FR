---
keywords: Recommandations;offre
description: Découvrez comment utiliser Adobe Recommandations en tant qu’offre dans les activités de tests A/B (y compris l’affectation automatique et le ciblage automatique) et de ciblage d’expérience (XT).
title: Comment utiliser Recommandations en tant qu’offre dans d’autres types d’activités ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: ec520555-b439-46a9-ab2d-f0981532bffb
TQID: 'https://experienceleague.adobe.com/ZMOb5RdY6bES331INSM7VF-w4be-5Xmjqon0YvfuNG4'
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
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 12%
---
# Recommandations en tant qu’offre {#recommendations-as-an-offer}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment ajouter, modifier et supprimer une recommandation en tant qu’offre dans les activités de [!UICONTROL Test A/B] et [!UICONTROL Ciblage d’expérience] (XT).

>[!ENDSHADEBOX]

Outre les activités [!UICONTROL Recommendations], les recommandations peuvent être incluses dans les activités [!UICONTROL Test A/B] (y compris les activités [!UICONTROL d’affectation automatique] et [!UICONTROL de ciblage automatique]) et [!UICONTROL Ciblage d’expérience] (XT). Cela permet ce qui suit :

* Testez et ciblez le contenu des recommandations et des non-recommandations dans la même activité.
* Testez le placement des recommandations sur la page, y compris l’ordre de plusieurs recommandations.
* Envoyez automatiquement le trafic vers l’expérience Recommendations la plus performante avec l’**[!UICONTROL affectation automatique]**.
* Affectez de manière dynamique les visiteurs à des expériences de recommandations personnalisées en fonction de leur profil avec le **[!UICONTROL ciblage automatique]**.

## Ajouter une recommandation en tant qu’offre {#add-recs-offer}

Une recommandation est ajoutée en tant qu’offre lors de la création d’une expérience avec le [!UICONTROL compositeur d’expérience visuelle] (VEC) dans une activité [!UICONTROL Test A/B] ou XT.

1. Démarrez le workflow guidé en trois étapes du compositeur d’expérience visuelle pour créer une activité de [test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) ou de [ciblage d’expérience](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md) (XT).

   >[!NOTE]
   >
   >Pour les tests A/B, l’option [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) envoie automatiquement le trafic vers les recommandations les plus performantes et l’option [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) affecte les visiteurs à des expériences de recommandations personnalisées en fonction de leur profil.

1. Lors de la création d’une [expérience](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md), ajoutez la recommandation en tant qu’offre de l’une des façons suivantes :

   * Cliquez sur l’élément auquel la recommandation est ajoutée, cliquez sur **[!UICONTROL Remplacer le contenu]**, puis sélectionnez **[!UICONTROL Recommandation]**.

     ![Compositeur d’expérience visuelle avec un en-tête sélectionné et l’option de recommandation mise en surbrillance dans le menu, en regard des options Offre HTML et Fragment d’expérience](/help/main/c-recommendations/t-create-recs-activity/assets/recs-as-offer.png)

   * Dans le rail **[!UICONTROL Composants]**, sélectionnez **[!UICONTROL Recommandation]** sous **[!UICONTROL Dynamique]**, survolez un élément existant de la page, puis cliquez sur **[!UICONTROL Insérer avant]** ou **[!UICONTROL Insérer après]** pour placer la recommandation avant ou après cet élément.

1. Accédez au menu **[!UICONTROL Afficher les propriétés]** et cliquez sur **[!UICONTROL Sélectionner une recommandation]**.

1. Sélectionnez les [critères](/help/main/c-recommendations/c-algorithms/algorithms.md) de votre choix, puis cliquez sur **[!UICONTROL Suivant]**.

1. Sélectionnez la [conception](/help/main/c-recommendations/c-design-overview/design-overview.md) souhaitée, puis cliquez sur **[!UICONTROL Suivant]**.

1. Dans la boîte de dialogue **[!UICONTROL Options]**, spécifiez ce qui suit :

   * Choisissez une [collection](/help/main/c-recommendations/c-products/collections.md).
   * Si nécessaire, configurez les options [Promotion avant et Promotion arrière](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md).

1. Cliquez sur **[!UICONTROL Enregistrer]**.

1. Terminez la configuration de l’activité [!UICONTROL Test A/B] ou XT avec le workflow guidé en trois étapes.

## Modification d’une offre de recommandations {#edit-recs-offer}

Les critères, la conception, la collection et les promotions d’une offre de recommandations peuvent être modifiés une fois l’offre ajoutée, à partir du volet **[!UICONTROL Recommandations]**.

1. Cliquez sur l’offre pour la modifier et parcourez les options du menu du volet de droite.

   ![Volet de recommandations contenant les noms des critères, de la conception et de la collection, ainsi que le bouton Ajouter une promotion de l&#39;offre sélectionnée](assets/create_reco_7.png)

1. Sélectionnez l’une des options suivantes :

   * [Modifier les critères](/help/main/c-recommendations/c-algorithms/algorithms.md)
   * [Modifier la conception](/help/main/c-recommendations/c-design-overview/design-overview.md)
   * [Modifier la collection](/help/main/c-recommendations/c-products/collections.md)
   * [Modifier la promotion](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)

1. Effectuez les modifications.

## Supprimer une offre de recommandations {#delete-recs-offer}

Une offre de recommandations qui n’est plus nécessaire peut être supprimée du volet **[!UICONTROL Recommandations]**.

Cliquez sur l’offre à supprimer, puis sur l’icône bin ( ![Icône bin](assets/Smock_Delete_18_N.svg) ) dans le volet **[!UICONTROL Recommandations]**.

![Volet de recommandations avec l&#39;icône bin mise en surbrillance](assets/create_reco_8.png)

## Affichage du statut d’une offre de recommandations {#status}

Le statut de l’offre de recommandations (algorithme) s’affiche au bas de la page **[!UICONTROL Aperçu]** pour les [!UICONTROL tests A/B] et les activités XT qui contiennent des offres de recommandations. Le statut est l’un des suivants :

* **[!UICONTROL Résultats Prêts]**
* **[!UICONTROL Résultats Non Prêts]**
* **[!UICONTROL Échec Du Flux]**

## Vidéo de formation : Recommandations en tant qu’offre ![Badge d’aperçu](/help/main/assets/overview.png)

>[!VIDEO](https://video.tv.adobe.com/v/28878)
