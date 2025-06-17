---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bogues;mises à jour,mises à jour actuelles
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: d87f1fbe78512363d4fe30935cbb4f2556b4a06b
workflow-type: tm+mt
source-wordcount: '1935'
ht-degree: 19%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API [!DNL Target], les SDK, l’[!DNL Adobe Experience Platform Web SDK], at.js, ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## Mise à jour : obsolescence du bouton (bascule) de version de l’interface utilisateur [!DNL Target] (17 juin 2025) {#revised}

Depuis le 17 juin 2025, toutes les organisations IMS doivent avoir été activées pour l’interface utilisateur [!DNL Target] mise à jour, que ce soit pour des utilisateurs spécifiques ou à l’échelle de l’organisation, afin de commencer à tester la nouvelle expérience.

En raison de problèmes récents identifiés, principalement liés à des personnalisations client complexes, l’équipe [!DNL Target] a ajusté le calendrier d’abandon :

* **30 juin 2025** : l’[updated [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md) deviendra l’expérience par défaut pour toutes les organisations IMS qui ont activé le bouton (bascule) de version de l’interface utilisateur.

   * Par défaut, les clients qui consultent actuellement l’interface utilisateur héritée verront désormais l’interface utilisateur mise à jour lors de leur connexion.
   * Le bouton (bascule) de version de l’interface utilisateur reste disponible jusqu’à la fin juillet, ce qui permet aux utilisateurs et utilisatrices de revenir en arrière si nécessaire.

  >[!IMPORTANT]
  >
  > [!DNL Adobe] recommande vivement d’utiliser l’interface utilisateur de [!DNL Target] mise à jour. Revenez à l’interface utilisateur héritée uniquement si un problème de blocage se produit. Consultez [[!DNL Target] Obsolescence du bouton (bascule) de version de l’interface utilisateur (23 mai 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#toggle) dans les notes de mise à jour des versions précédentes pour obtenir des informations importantes sur le bouton (bascule).

* **du 15 au 30 juillet 2025** : le bouton (bascule) de version de l’interface utilisateur sera désactivé définitivement par phases. Les organisations IMS affectées ne pourront plus revenir à l’interface utilisateur héritée.

   * Les exceptions seront examinées au cas par cas.
   * Les délais d’abandon du bouton (bascule) ne sont accordés que brièvement (quelques jours) pendant que les problèmes de blocage sont résolus.

Contactez l’[Assistance clientèle d’Adobe](/help/main/cmp-resources-and-contact-information.md#/help/main/cmp-resources-and-contact-information.md) pour toute question ou si vous prévoyez des problèmes au cours de cette transition.

## [!DNL Target Standard/Premium] 25.6.2 (vendredi 12 juin 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Ajout d’un [nouvel article de FAQ](/help/main/c-intro/updated-ui-faq.md) pour répondre aux questions courantes sur l’interface utilisateur et le [!UICONTROL Visual Experience Composer] de [!DNL Target] mis à jour (VEC).
* Correction d’un problème en raison duquel la règle « [!UICONTROL URL - does not contain] » dans [!UICONTROL Page Delivery] ne fonctionnait pas, ce qui permettait d’afficher le contenu même lorsqu’il aurait dû être bloqué. (TGT-52754)
* Correction d’un problème en raison duquel [!UICONTROL Page Delivery] affichait incorrectement le message d’erreur : « Les URL de page en double ne sont pas autorisées. (TGT-52765)
* Correction d’un problème où les audiences des URL [!UICONTROL Page Delivery] contenant des fragments d’expérience étaient créées avec le signe # ajouté par erreur. (TGT-52786)
* Correction d’un problème en raison duquel la copie d’une activité et les paramètres de modification sur la page [!UICONTROL Goals and Settings] ne répondaient plus dans l’interface utilisateur de [!DNL Target]. (TGT-52797)
* Correction d’un problème dans le [!UICONTROL Visual Experience Composer] mis à jour (VEC) qui autorisait incorrectement la redirection d’une page supplémentaire dans une activité [!UICONTROL A/B Test] vers la même URL. (TGT-51838)
* Correction d’un problème en raison duquel les modifications apportées aux mesures sur la page [!UICONTROL Goals and Settings] n’étaient pas enregistrées lors de la modification d’une activité. (TGT-52799)
* Correction d’un problème en raison duquel l’ajout d’une nouvelle expérience alors que l’éditeur web était toujours en cours de chargement entraînait la duplication du contenu de la nouvelle expérience depuis l’expérience précédente. (TGT-51397)
* Restauration de la possibilité d’utiliser du code personnalisé en dehors de la balise `<head>`, une fonctionnalité auparavant disponible dans l’ancienne interface utilisateur de Target. (TGT-52304 et TGT-52300)
* Suppression de la validation inutile lors de la sélection de l’espace de travail par défaut lors de la création de l’activité. La validation obligatoire des propriétés ne s’applique plus à l’espace de travail par défaut, mais reste en place pour les espaces de travail non par défaut. (TGT-52449)
* Correction d’un problème dans le [!UICONTROL Visual Experience Composer] mis à jour (VEC) en raison duquel `triggerView()` appels n’étaient pas détectés. (TGT-52575)
* Correction d’un problème dans le [!UICONTROL Visual Experience Composer] mis à jour (VEC) qui empêchait les utilisateurs d’ajouter des modifications aux vues [!UICONTROL Single Page Application] (SPA). (TGT-52556)
* Correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour qui empêchait les clients d’afficher les détails de l’offre. (TGT-52607)
* Correction d’un problème en raison duquel les mises à jour apportées aux offres dans le [!UICONTROL Offers Library] n’étaient pas répercutées dans le [!UICONTROL Visual Experience Composer] mis à jour (VEC). (TGT-52637)
* Correction d’un problème qui empêchait l’affichage correct de la section Offres lors de la création d’une activité. (TGT-52773)
* Ajout d’une validation pour s’assurer que toutes les `optionLocalIds` référencées dans `optionGroups` existent dans le tableau d’options. Les références non valides sont automatiquement supprimées lors de la création de l’activité. (TGT-52687)
* Correction d’un problème où les groupes de génération de rapports et les exclusions n’étaient pas conservés après l’ajout d’une nouvelle offre. (TGT-52728)
* Correction d&#39;un problème en raison duquel les activités sans bouton [!UICONTROL Activity QA] affichaient un sélecteur d&#39;options vide. (TGT-52733)
* Correction d’un problème en raison duquel les liens d’assurance qualité ne rendaient pas correctement le contenu. (TGT-52718)
* Correction d’un problème en raison duquel le remplacement d’un élément par un fragment d’expérience ne reflétait pas correctement les modifications dans l’environnement d’assurance qualité. (TGT-52762)
* Correction d’un problème dans le [!UICONTROL Visual Experience Composer] mis à jour (VEC) qui provoquait une erreur « Entrée non valide » lorsque les utilisateurs tentaient d’ajouter des fragments d’expérience. (TGT-52701)
* Correction d’un problème en raison duquel la boîte de dialogue modale « Modifier l’audience » apparaissait vide lors de la modification du ciblage des audiences dans le [!UICONTROL Visual Experience Composer] mis à jour (VEC). (TGT-52749)
* Ajout d&#39;un message pour informer les utilisateurs qu&#39;une entité n&#39;est pas accessible dans l&#39;espace de travail sélectionné. (TGT-52767)
* Correction d’un problème en raison duquel l’interface utilisateur ne permettait pas l’affectation manuelle d’un identifiant d’environnement à un critère. Au lieu de cela, il a défini par défaut l’ID du groupe d’hôtes [!UICONTROL Product Catalog Search]. Ce correctif garantit que les modifications des critères sont désormais appliquées à tous les environnements, et pas seulement à la valeur par défaut. (TGT-52817)
* Correction d’un problème en raison duquel l’option « [!UICONTROL Download Recommendations data] » était manquante pour les activités [!UICONTROL Experience Targeting] (XT) avec des recommandations. (TGT-52730 et TGT-52756)

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

## Obsolescence du bouton (bascule) de version de l’interface utilisateur [!DNL Target] (23 mai 2025) {#toggle}

>[!IMPORTANT]
>
>L’équipe [!DNL Target] a ajusté la chronologie de l’obsolescence du bouton (bascule) de version de l’interface utilisateur. Pour plus d’informations, consultez la section [Mise à jour du basculement vers l’obsolescence de la version  [!DNL Target] UI (17 juin 2025)](#revised).

Le déploiement de la nouvelle interface utilisateur [!DNL Target] sera terminé d’ici le 27 **2025**. À ce stade, tous les clients auront accès à la dernière version de l’interface utilisateur.

À compter du **22 juin 2025**, le bouton (bascule) de version de l’interface utilisateur sera supprimé. Tous les utilisateurs passeront définitivement à la nouvelle interface, sans possibilité de revenir à la version précédente.

>[!NOTE]
>
>Les clients avec des cas spéciaux qui doivent conserver le bouton bascule après le 22 juin peuvent contacter l’assistance clientèle d’Adobe pour obtenir de l’aide.

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

* [[!DNL Target] FAQ sur la mise à jour de l’interface utilisateur](/help/main/c-intro/updated-ui-faq.md) : cette FAQ aborde les questions courantes sur la nouvelle interface utilisateur [!DNL Target] et le nouveau [!UICONTROL Visual Experience Composer] (VEC), y compris les modifications de navigation, les emplacements de fonctionnalités et l’obsolescence du bouton (bascule) de version temporaire de l’interface utilisateur. Que vous soyez spécialiste du marketing, développeur ou administrateur, cette FAQ vous aide à effectuer une transition en douceur et à tirer le meilleur parti de l’interface utilisateur mise à jour.

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
