---
description: Dans ces notes de mise à jour, vous trouverez des informations sur les fonctions, les améliorations, les correctifs et les problèmes connus relatifs aux dernières versions ou aux versions à venir de Target.
keywords: notes de mise à jour
seo-description: Dans ces notes de mise à jour, vous trouverez des informations sur les fonctions, les améliorations, les correctifs et les problèmes connus relatifs aux dernières versions ou aux versions à venir d’Adobe Target
seo-title: Notes de mise à jour de Target (préliminaires)
solution: Target
title: Notes de mise à jour de Target (préliminaires)
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: e59b5f8fea0c0e1e79477764f6f870a50ee0bba4

---


# Notes de mise à jour de Target (préliminaires){#target-release-notes-prerelease}

Dans ces notes de mise à jour, vous trouverez des informations sur les fonctions, les améliorations, les correctifs relatifs aux dernières versions ou aux versions à venir de [!DNL Adobe Target]

**Dernière mise à jour : 21er mai 2019**

>[!NOTE]
>
>Ces notes de mise à jour contiennent des informations sur de prochaines versions. Les dates de publication, fonctions et autres informations peuvent changer. Pour afficher des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations de ces pages peuvent être identiques ou différer selon le timing des versions.

## [!DNL Target] Standard/Premium 19.5.1 (21 mai 2019) {#release-19-5-1-prerelease}

Cette version inclut les fonctionnalités, modifications et améliorations suivantes :

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].)

### Mises à jour des fonctionnalités

| Fonction/amélioration | Description |
| --- | --- |
| Compositeur d’expérience visuelle pour les applications monopages (Compositeur d&#39;expérience visuelle) | Le SPA VEC (compositeur d’expérience visuelle) a été amélioré comme suit afin que vous puissiez travailler plus vite et plus efficacement :<ul><li>Le fait de cliquer sur une action dans l&#39;application d&#39;une seule page met en évidence l&#39;élément sur le site où cette action sera appliquée. Chaque action du compositeur d&#39;expérience visuelle créée sous une vue comporte quatre icônes correspondantes : Informations, modification, déplacement et suppression. La nouvelle fonctionnalité Déplacer de cette version permet de déplacer l&#39;action vers un événement de chargement de page ou tout autre affichage existant dans le panneau Modifications. (TGT-33746)</li><li>Vous pouvez effectuer de nombreuses actions avant le chargement de la page dans VEC, ou même si la page ne parvient pas à se charger complètement (par exemple, si un code personnalisé n’est plus fonctionnel). Les actions qu’il n’est pas possible de modifier avant le chargement complet du site sont désactivées dans l’interface utilisateur de Target. (TGT-33851 et TGT-34149)</li></ul>Pour plus d’informations, reportez-vous au [Compositeur d’expérience visuelle pour application d’une seule page (SPA)](/help/c-experiences/spa-visual-experience-composer.md). |

### Améliorations, correctifs et modifications

* Les icônes de la barre d’outils s’affichent correctement après l’annulation du chargement d’une page dans le compositeur d’expérience visuelle. Si des actions spécifiques ne peuvent être effectuées qu’après le chargement complet de la page, les icônes de la barre d’outils associée sont désactivées. (TGT-33811)

## Compositeur d&#39;expérience visuelle d&#39;applications mobiles (14 mai 2019) {mobile-vec}

| Fonction/amélioration | Description |
| --- | --- |
| Compositeur d&#39;expérience visuelle d&#39;applications mobiles (VEC) | Le compositeur d&#39;expérience visuelle Mobile vous permet de créer des activités et de personnaliser le contenu sur les applications mobiles natives d&#39;une manière-elle-vous-même sans dépendances de développement continues et cycles de publication d&#39;application.<br>Pour plus d’informations, voir:<ul><li>[Compositeur d’expérience visuelle pour application mobile](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md)</li><li>[Android - Configuration de l’application mobile](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md)</li><li>[iOS - Configuration de l’application mobile](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-ios.md)</li><li>[Configuration du suivi des clics dans le VEC Mobile](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md)</li><li>[Vidéo : Compositeur d&#39;expérience visuelle d&#39;applications mobiles](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#video)</li></ul> |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir des produits à Target et à d&#39;autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour produit prioritaire Adobe :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
