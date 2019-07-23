---
description: Notes de mise à jour qui fournissent des informations sur les fonctionnalités, les améliorations et les correctifs pour les [! ! Versions DNL Adobe Target].
keywords: notes de mise à jour
seo-description: Notes de mise à jour qui fournissent des informations sur les fonctionnalités, les améliorations et les correctifs pour les [! ! Versions DNL Adobe Target].
seo-title: Notes de mise à jour d'Adobe Target (bêta)
solution: Target
title: Notes de mise à jour de Target (préliminaires)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 71419ee6053eeb86ab6595cfba2f05d8506e05b3

---


# Notes de mise à jour de Target (préliminaires){#target-release-notes-prerelease}

Dans ces notes de mise à jour, vous trouverez des informations sur les fonctions, les améliorations, les correctifs relatifs aux dernières versions ou aux versions à venir de [!DNL Adobe Target]

**Dernière mise à jour : 24 juillet 2019**

>[!NOTE]
>
>Ces notes de mise à jour contiennent des informations sur de prochaines versions. Les dates de publication, les fonctionnalités et d'autres informations peuvent être modifiées sans préavis. Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques ou différer selon le timing des versions.
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Target Standard/Premium 19.7.1 (24 juillet 2019) {#tgt-19-7-1}

Cette version comprend les nouvelles fonctionnalités et améliorations suivantes :

| Fonctionnalité / Amélioration | Description |
| --- | --- |
| Compositeur d’expérience visuelle pour application mobile | Un nouveau panneau Modifications s'affiche dans le compositeur d'expérience visuelle Mobile, qui affiche les éléments que vous avez configurés pour le suivi des clics. (TGT-31741)<br> See [Set up click tracking in the Mobile App](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md). |
| ![Badgerecommendations](/help/assets/premium.png)<br>dans les activités de test A/B et de ciblage d'expérience (XT) | L'état d'offre de recommandations (algorithme) s'affiche sur la page Aperçu pour les tests A/B et les activités de ciblage d'expérience contenant des offres Recommendations. Les états incluent : Résultats prêts, Résultats non prêts et Échec du flux. (TGT-33649)<br>See [Recommendations as an offer](/help/c-recommendations/recommendations-as-an-offer.md#status). |
| Prise en charge de suivi interdomaines pour at. js 2.0 + via la bibliothèque Experience Cloud ID (ECID) | Auparavant, le suivi inter-domaines n'était pas pris en charge dans at. js 2.*x*. Avec cette version, les utilisateurs qui utilisent at. js 2.0 ou version ultérieure peuvent désormais utiliser le suivi inter-domaines via la bibliothèque ECID. La bibliothèque ECID doit être installée sur la page conjointement avec at. js 2.0 ou version ultérieure pour que le suivi inter-domaines fonctionne. [La bibliothèque Experience Cloud ID 4.3.0 +](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) doit être utilisée.<br>Voir [Prise en charge du suivi inter-domaines dans at. js 2. x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md#cross-domain). |
| Prise en charge de Target pour ITP 2.1 et ITP 2.2 d'Apple via la bibliothèque d'Experience Cloud ID (ECID) 4.3 | Aujourd'hui, les clients Target peuvent réduire les ITP 2.1 et ITP 2.2 Apple en exploitant le programme de certification CNAME d'Adobe.<br>Avec cette version, Target introduit une intégration transparente avec la bibliothèque ECID 4.3, qui utilise un cookie côté serveur pour atténuer ITP 2.1 et ITP 2.2. Il est vivement recommandé aux clients Target de déployer [la bibliothèque ECID 4.3 +](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) conjointement avec la bibliothèque JavaScript de Target pour atténuer les futures versions ITP. La bibliothèque ECID continue à déployer les améliorations qui offrent une solution fiable aux stratégies de cookies qui évoluent constamment par les navigateurs.<br>Voir [Apple Intelligent Tracking Prevention (ITP) 2. x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md). |

**Améliorations, correctifs et modifications**

* Correction d'un problème qui empêchait l'effacement des valeurs d'exclusion dans les activités de recommandations lors de l'ajout de valeurs en double. (TGT-34996)
* Vous pouvez désormais supprimer une conception dans une activité de recommandations de la page Ciblage (étape 2 du workflow assisté en trois parties). Notez que pour supprimer une conception, plusieurs conceptions doivent être sélectionnées. (TGT-35118)
* Correction d'un problème qui empêchait le chargement correct des cartes de critères personnalisés pour certains clients dans l'interface utilisateur de Target ou pour être modifiables. (TGT-35170)

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
