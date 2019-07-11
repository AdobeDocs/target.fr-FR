---
description: Ces notes de mise à jour fournissent des informations sur les fonctionnalités, les améliorations et les correctifs pour les [! ! Versions DNL Adobe Target].
keywords: notes de mise à jour
seo-description: Ces notes de mise à jour fournissent des informations sur les fonctionnalités, les améliorations et les correctifs pour les [! ! Versions DNL Adobe Target].
seo-title: Notes de mise à jour d'Adobe Target (bêta)
solution: Target
title: Notes de mise à jour de Target (préliminaires)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 414783c4072a574d278166bedc8243047135265b

---


# Notes de mise à jour de Target (préliminaires){#target-release-notes-prerelease}

Dans ces notes de mise à jour, vous trouverez des informations sur les fonctions, les améliorations, les correctifs relatifs aux dernières versions ou aux versions à venir de [!DNL Adobe Target]

**Dernière mise à jour : 10 juillet 2019**

>[!NOTE]
>
>Ces notes de mise à jour contiennent des informations sur de prochaines versions. Les dates de publication, les fonctionnalités et d&#39;autres informations peuvent être modifiées sans préavis. Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques ou différer selon le timing des versions.
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Target Standard/Premium 19.7.1 (23 juillet 2019) {#tgt-19-7-1}

Cette version comprend les nouvelles fonctionnalités et améliorations suivantes :

| Fonctionnalité / Amélioration | Description |
| --- | --- |
| Compositeur d’expérience visuelle (VEC) | When you click an image then click [!UICONTROL Replace With], two new options display:<ul><li>**HTML**: Vous pouvez remplacer une image par HTML pour vous donner le contrôle total de l&#39;élément sans avoir à sélectionner l&#39;élément parent pour accéder à l&#39;option HTML.</li><li>**Fragment d&#39;expérience**: Vous pouvez remplacer une image par un fragment [d&#39;expérience Adobe Experience Manager (AEM)](/help/c-experiences/c-manage-content/aem-experience-fragments.md) pour insérer rapidement des éléments créés dans AEM dans les activités Target.</li></ul>(TGT-34097) |
| Compositeur d’expérience visuelle pour application mobile | Un nouveau panneau Modifications s&#39;affiche dans le compositeur d&#39;expérience visuelle Mobile, qui affiche les éléments que vous avez configurés pour le suivi des clics. (TGT-31741) |
| ![Badgerecommendations](/help/assets/premium.png)<br>dans les activités de test A/B et de ciblage d&#39;expérience (XT) | L&#39;état d&#39;offre de recommandations (algorithme) s&#39;affiche sur la page Aperçu pour les tests A/B et les activités de ciblage d&#39;expérience contenant des offres Recommendations. Les états incluent : Résultats prêts, Résultats non prêts et Échec du flux. (TGT-33649) |
| Prise en charge de suivi interdomaines pour at. js 2.0 + via la bibliothèque Experience Cloud ID (ECID) | Auparavant, le suivi inter-domaines n&#39;était pas pris en charge dans at. js 2.*x*. Avec cette version, les utilisateurs qui utilisent at. js 2.0 ou version ultérieure peuvent désormais utiliser le suivi inter-domaines via la bibliothèque ECID. La bibliothèque ECID doit être installée sur la page conjointement avec at. js 2.0 ou version ultérieure pour que le suivi inter-domaines fonctionne. It is highly recommended to use [Experience Cloud ID library 4.3.0+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html). |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
