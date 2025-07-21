---
keywords: notes de mise à jour;versions;mises à jour;futures versions;améliorations;nouvelles fonctionnalités;correctifs;mises à jour;version préliminaire;accès anticipé
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version de [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b91abbd3b7418fd4d1444d96f160c3d9017f3bf8
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 34%

---

# Notes de mise à jour de [!DNL Target] (version préliminaire)

Cet article contient des informations sur les prochaines versions d’[!DNL Adobe Target], y compris les SDK, les API et les bibliothèques JavaScript.

**Dernière mise à jour : 21 juillet 2025**

>[!NOTE]
>
>* Les dates de publication, fonctions et autres informations peuvent changer sans préavis.
>
>* Pour afficher des informations sur la version actuelle, voir [ Notes de mise à jour de Target ](release-notes.md).
>
>* Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.7.3 (vendredi 24 juillet 2025)

En raison de problèmes récents identifiés, principalement liés à des personnalisations client complexes, cette version comprend les correctifs et mises à jour suivants :

**Activités**

+++Voir les détails
* Correction d’un problème en raison duquel la méthode `buildViews` de la classe builder définissait incorrectement le `viewMaxLocalId` sur le nombre total de vues, plutôt que sur la `viewLocalId` la plus élevée attribuée. (TGT-53207)

+++

**Compositeur d’expérience d’après les formulaires**

+++Voir les détails
* Correction d’un problème dans le [!UICONTROL Form-Based Experience Composer] en raison duquel l’éditeur se bloquait après avoir cliqué sur l’icône **[!UICONTROL Manage Content]** ( ![icône Gérer le contenu](/help/main/assets/icons/Experience.svg) ) lors de la création ou de la modification d’une activité [!UICONTROL Automated Personalization] (AP). (TGT-53047)

+++

**Recommendations**

+++Voir les détails
* Correction d’un problème qui empêchait [!UICONTROL Catalog Search] de charger des résultats supplémentaires lors du défilement vers le bas de la liste, restaurant ainsi un comportement cohérent avec l’interface utilisateur héritée. (TGT-53088)
* Correction d’un problème en raison duquel la colonne [!UICONTROL Number of Products] était manquante dans la page [!UICONTROL Collections] de l’interface utilisateur de [!DNL Target] mise à jour. La colonne s’affiche désormais correctement, restaurant les fonctionnalités attendues. (TGT-53168)
* Correction d’un problème en raison duquel les règles de [!UICONTROL Collection] ne filtraient pas correctement selon les règles. (TGT-53254)
* Correction d’un problème qui bloquait la suppression d’éléments de la boîte de dialogue [!UICONTROL Criteria Details]. (TGT-53245)
* Correction d’un problème qui empêchait l’ouverture ou l’interaction avec des produits sans nom. Ce problème se produisait lors de la sélection d’environnements qui renvoyaient des résultats sans nom, empêchant l’accès aux détails du produit. (TGT-53007)
* Correction d’un problème en raison duquel la page [!UICONTROL Catalog Search] se bloquait et affichait un écran vide lors de la sélection de certains produits. (TGT-53087)

+++

**Compositeur d’expérience visuelle**

+++Voir les détails

* Correction d’un problème dans le VEC en raison duquel l’application d’une modification à une vue provoquait une duplication et déclenchait une erreur « Entrée utilisateur non valide ». (TGT-52886)
* Correction d’un problème lié à [!UICONTROL Undo] fonctionnalité des options [!UICONTROL Insert Before] et [!UICONTROL Insert After] lors de la configuration des offres d’images dans le VEC.

  Auparavant, l’annulation d’une action [!UICONTROL Insert Before] ou [!UICONTROL Insert After] sur des offres d’image entraînait un comportement incohérent ou l’échec de l’annulation correcte de la modification, en particulier dans les activités créées dans l’interface utilisateur [!DNL Target] héritée. Ce problème a été résolu afin de garantir que les actions d’annulation fonctionnent désormais de manière fiable pour ces modifications. (TGT-52809)

+++

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
