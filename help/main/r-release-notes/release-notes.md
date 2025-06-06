---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bogues;mises à jour,mises à jour actuelles
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 5f41bcebce4e103fada006f53cd3ccd297769d0d
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 28%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API [!DNL Target], les SDK, l’[!DNL Adobe Experience Platform Web SDK], at.js, ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## [!DNL Target Standard/Premium] 25.6.1 (samedi 6 juin 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’un problème en raison duquel les liens d’assurance qualité ne fournissaient pas l’expérience appropriée pour l’activité associée. (TGT-52163 et TGT-52790)
* Correction d’un problème en raison duquel les liens d’assurance qualité ne comportaient pas l’identifiant d’audience associé. (TGT-52722)
* Correction d’un problème pour s’assurer que les expériences ne sont diffusées que lorsque les conditions de l’URL de diffusion de page configurées sont précisément remplies. (TGT-52696)
* Correction d’un problème qui empêchait les clients de créer un modèle de conception [!DNL Recommendations]. La tentative de création d’un modèle a déclenché l’erreur : « Au moins 1 variable d’entité doit être utilisée dans le script. » (TGT-52395)
* Correction d’un problème qui empêchait l’enregistrement des conceptions [!DNL Recommendations] à l’aide de tableaux Velocity. Le message d’erreur « Il doit y avoir au moins 1 variable d’entité utilisée dans le script » a été déclenché de manière incorrecte. (TGT-52734)
* Correction d’un problème en raison duquel les modifications n’étaient pas accessibles dans le [!UICONTROL Visual Experience Composer] (VEC) lorsque le chargement de la page échouait pour les pages web internes. (TGT-52488 ET TGT-52470)
* Correction d’un problème en raison duquel le panneau [!UICONTROL Modifications] n’était pas visible sur les plus petites tailles d’écran dans le VEC. (TGT-52470)
* Correction d’un problème dans le VEC mis à jour en raison duquel le retour du mode [!UICONTROL Browse] au mode [!UICONTROL Design] provoquait une erreur de console et empêchait toute autre interaction. (TGT-52532)
* Correction d’un problème dans le VEC en raison duquel cliquer sur certains éléments développait involontairement leur taille. (TGT-52497)
* Correction d’un problème en raison duquel certains éléments de page ne se chargeaient pas ou n’étaient pas reconnus dans le VEC, ce qui empêchait des interactions telles que la sélection de boutons ou de bannières et perturbait le suivi précis des événements dans les activités. (TGT-52663)
* Correction d’un problème qui empêchait les clients de supprimer des offres dans les activités [!UICONTROL Automated Personalization] (AP). (TGT-52690)
* Correction d’un problème qui provoquait un comportement incohérent de qualification des activités dans les activités multi-pages. (TGT-52694)
* Correction d’un problème en raison duquel la page [!UICONTROL Overview] de l’activité affichait une URL non valide pour la [!UICONTROL Activity Location]. (TGT-52695)
* Correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour qui entraînait l’affichage de doublons pour les emplacements d’activités. (TGT-52693)
* Correction d’un problème qui déclenchait une erreur `getAudiencesV3`, empêchant les clients de modifier ou de copier des activités. (TGT-52709)
* Correction d’un problème qui provoquait une erreur de payload non valide lors de l’ajout d’offres [!UICONTROL Experience Fragments] ou HTML à une activité. (TGT-52779 et TGT-52773)
* Correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour en raison duquel E[!UICONTROL xperience Fragments] ne s’affichait pas correctement en raison d’une erreur d’entrée non valide. (TGT-52701)
* Correction d’un problème qui empêchait les clients et clientes de modifier les activités dans le [!UICONTROL Form-based Experience Composer] en raison d’une erreur utilisateur non valide. (TGT-52470)
* Correction d’un problème de localisation en langue coréenne en raison duquel les traductions précédentes utilisaient des caractères en dehors du plan multilingue de base. La traduction mise à jour utilise des caractères appropriés qui transmettent précisément la signification prévue. (TGT-52508 et TGT-52509)
* Correction d’un problème de localisation en coréen en raison duquel la traduction de la « date » était incohérente lors de la sélection des dates de début et de fin d’une activité. (TGT-52510)

## Obsolescence du bouton (bascule) de la version de l’interface utilisateur Target (23 mai 2025) {#toggle}

Le déploiement de la nouvelle interface utilisateur [!DNL Target] sera terminé d’ici le 27 **2025**. À ce stade, tous les clients auront accès à la dernière version de l’interface utilisateur.

À compter du **22 juin 2025**, le bouton (bascule) de version de l’interface utilisateur sera supprimé. Tous les utilisateurs passeront définitivement à la nouvelle interface, sans possibilité de revenir à la version précédente.

### Informations importantes sur le bouton (bascule) de version de l’interface utilisateur

Nous proposons une fonctionnalité temporaire qui vous permet de basculer entre l’interface utilisateur [!DNL Target] mise à jour et la version héritée à l’aide d’un bouton bascule. Cette option n’est disponible que pendant la phase finale du déploiement de l’interface utilisateur.

![Basculement de la version de l’interface utilisateur de Target](/help/main/r-release-notes/assets/toggle.png)

Une fois le déploiement terminé, le bouton (bascule) sera supprimé et tous les utilisateurs passeront définitivement à l’interface utilisateur mise à jour le **22 juin 2025**. Adobe recommande de planifier l’opération, car cette fonctionnalité sera bientôt supprimée.

### Limites du comportement du bouton (bascule) de l’interface utilisateur

* **Visibilité des nouvelles activités** : les activités créées dans l’interface utilisateur mise à jour ne seront pas visibles si vous revenez à l’interface utilisateur héritée.
* **Modification d’activités existantes** : les modifications apportées à des activités existantes (créées à l’origine dans l’interface utilisateur héritée) lors de l’utilisation de l’interface utilisateur mise à jour seront publiées sur votre site web. Toutefois, si vous revenez en arrière, ces mises à jour ne seront pas visibles dans l’interface utilisateur héritée. Seules les dernières mises à jour effectuées à partir de l’interface utilisateur héritée y apparaîtront.
* **Cohérence des détails de l’activité** : les modifications les plus récentes, quelle que soit l’interface utilisateur que vous utilisez, seront répercutées sur votre site web actif. Cependant, l’interface utilisateur héritée n’affiche que les dernières modifications apportées à partir de cette version. Cela peut prêter à confusion si les activités modifiées dans l’interface utilisateur mise à jour ont un aspect différent de celui de l’interface utilisateur héritée.

### Informations supplémentaires sur l’interface utilisateur mise à jour

* [[!DNL Target Standard/Premium] Notes de mise à jour de la version 25.2.1 (17 février 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2) : fournit un résumé des principales modifications apportées à l’interface utilisateur des [!DNL Target] pour [!UICONTROL Activities], [!UICONTROL Recommendations] et le [!UICONTROL Visual Experience Composer] (VEC).

* Notes de mise à jour de la version [[!DNL Target Standard/Premium] 25.1.1 (9 janvier 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1) : fournit un résumé des principales modifications apportées à l’interface utilisateur des [!DNL Target] pour le [!UICONTROL Offers Library].

* [Présentation de l [!DNL Target] interface utilisateur ](/help/main/c-intro/understand-the-target-ui.md) : fournit un bref aperçu pour vous familiariser avec les [!DNL Target] et fournit des liens vers des informations plus détaillées et des instructions détaillées.

* [[!UICONTROL Visual Experience Composer] modifications ](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md) : la version [!DNL Adobe Target Standard/Premium] 25.2.1 (17 février 2015) introduit un [!UICONTROL Visual Experience Composer] mis à jour (VEC). Cet article explique les différences entre les versions héritées et mises à jour du compositeur d’expérience visuelle.

* [[!UICONTROL Visual Experience Composer] options ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md) : cet article explique l’interface utilisateur du compositeur d’expérience visuelle mise à jour et ses options.

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| [Modifications de la documentation](/help/main/r-release-notes/doc-change.md) | Obtenez des informations détaillées sur les mises à jour apportées à ce guide qui ne sont pas incluses dans les notes de mise à jour. |
| [Notes de mise à jour pour les versions antérieures](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium. |
| [Notes De Mise À Jour De Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr){target=_blank} | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud. |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| [Mise à jour prioritaire des produits Adobe](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Recevez des notifications anticipées sur les améliorations à venir de [!DNL Target] et d’autres solutions [!DNL Adobe Experience Cloud]. |
| [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Informations sur les versions de Target du mois en cours, y compris des informations sur la version préliminaire. |
