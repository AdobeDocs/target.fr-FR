---
description: Les équipes de produits de la technologie contemporaine adoptent des principes de livraison continue pour les lancements de produits. Target aide les développeurs et les équipes de produits à déployer rapidement et efficacement de nouvelles fonctionnalités de produit.
keywords: déploiement;déploiement;livraison continue;lancement du produit;déploiement progressif
seo-description: Les équipes de produits de la technologie contemporaine adoptent des principes de livraison continue pour les lancements de produits. Adobe Target aide les développeurs et les équipes de produits à déployer rapidement et efficacement de nouvelles fonctionnalités de produit dans le cadre d’un déploiement échelonné.
seo-title: Les équipes de produits de la technologie contemporaine adoptent des principes de livraison continue pour les lancements de produits. Adobe Target aide les développeurs et les équipes de produits à déployer rapidement et efficacement de nouvelles fonctionnalités de produit.
solution: Target
title: Marquage des fonctionnalités
topic: Standard
translation-type: tm+mt
source-git-commit: 08debab3ec3d2f6e6bfd3c42476dc1a021185ab7

---


# Marquage des fonctionnalités

Les équipes de produits de la technologie contemporaine adoptent des principes de livraison continue pour les lancements de produits. Adobe Target aide les développeurs et les équipes de produits à déployer rapidement et efficacement de nouvelles fonctionnalités de produit dans le cadre d’un déploiement échelonné.

Les liens suivants fournissent des informations sur les concepts clés que vous devez comprendre pour permettre une diffusion continue :

* [Activités de test A/B](/help/c-activities/t-test-ab/test-ab.md)
* [offres JSON](/help/c-experiences/c-manage-content/create-json-offer.md)
* [Améliorations du public](/help/c-target/c-audiences/creating-a-profile-attribute-comparison-audience.md)

## Livraison continue

1. Par défaut, désactivez la fonctionnalité lors de la publication.

   Utilisez une variable côté serveur ou in-app pour contrôler cela.

1. Créez une offre JSON Target qui active cette variable.

1. Créez une activité de test A/B dans le compositeur d’expérience [visuelle](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) avec deux expériences et utilisez l’offre JSON créée à l’étape précédente dans une seule expérience.

   OU

   Créez une activité de test A/B dans le compositeur [d’expérience d’après les](/help/c-experiences/form-experience-composer.md) formulaires avec une seule expérience et utilisez l’offre JSON créée à l’étape précédente.

   >[!NOTE]
   >
   >The Form-based Experience Composer allows you to create an A/B Test activity with a single experience. You cannot create the activity with a single experience using the VEC.

1. Specify your desired traffic allocation for the activity.

   If you want to start by rolling this feature out to 5% of your visitors, specify 5 in the Targeting step of the three-part guided workflow and send 100% of the qualifying visitors to the experience with the JSON offer (Experience A).

   The following illustration shows the VEC with two experiences.

   ![Traffic allocation for feature flagging in the VEC](/help/c-implementing-target/c-api-and-sdk-overview/assets/feature-flagging.png)

   The following illustration shows the Form-based Experience Composer with a single experience.

   ![Traffic allocation for feature flagging in the Form-based Experience Composer](/help/c-implementing-target/c-api-and-sdk-overview/assets/feature-flagging-form.png)

1. You can increase the traffic allocation to this activity by gradually increasing the 5% either through the Target UI or using the API until you reach 100% traffic allocation.

   >[!NOTE]
   >
   >An A/B Test activity is sticky for a visitor through the session. If you decrease the traffic allocation, visitors who started seeing this feature continue to view it until their sessions are reset.

## Fonctions de test A/B

If you are using A/B/..N Test features, use the approach discussed above with the following improvements:

* Each feature variant should be represented using an appropriate JSON offer that makes a Target experience.
* You can manage traffic allocation for this test in the manner described above.

## Déploiements paramétrés

La méthode décrite ci-dessus vous aide à gérer un déploiement contrôlé.

Vous pouvez déployer une fonctionnalité pour vos participants bêta uniquement, puis la déployer ultérieurement pour tous les autres clients. Pour ce faire, il est facile de tirer parti des paramètres [d’emplacement](/help/c-target/c-audiences/c-target-rules/custom-parameters.md) cible (mbox) ou des paramètres [de](/help/c-target/c-audiences/c-target-rules/visitor-profile.md)profil. Ces paramètres peuvent être utilisés conjointement avec l’affectation progressive du trafic.

## Côté serveur ou côté client

Les déploiements de fonctionnalités et les tests peuvent être diffusés via les API [de](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md) Target (et les SDK côté serveur), ainsi que les SDK côté client (JS, Mobile SDK). Selon l’architecture de votre site Web, de votre application mobile ou de votre kiosque, vous pouvez tirer parti des différentes options d’intégration de Target.
