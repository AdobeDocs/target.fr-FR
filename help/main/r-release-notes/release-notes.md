---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bugs;mises à jour;mises à jour actuelles
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 6ecc59588b51da505b8f567a7e87ccef0f375477
workflow-type: tm+mt
source-wordcount: '1959'
ht-degree: 15%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Découvrez les dernières fonctionnalités, améliorations et correctifs d’[!DNL Adobe Target]. Ces notes de mise à jour couvrent également les mises à jour des API [!DNL Target], des SDK, de la [!DNL Adobe Experience Platform Web SDK], d’at.js et d’autres composants de plateforme, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## Mises à jour sensibles à l’heure que vous devez connaître {#time-sensitive}

[!BADGE Important]{type=Informative}

Pour les mises à jour urgentes relatives à [!DNL Adobe Target] et à votre implémentation, [!DNL Adobe]fournit des notes de mise à jour détaillées et une documentation via [!UICONTROL Experience League]. Voici quelques points forts importants liés à votre implémentation :

### Obsolescence du bouton (bascule) de version de l’interface utilisateur [!DNL Target]

+++Voir les détails
L’équipe [!DNL Target] propose une fonctionnalité temporaire qui vous permet de basculer entre l’interface utilisateur de [!DNL Target] mise à jour et la version héritée à l’aide d’un bouton bascule. Cette option n’est disponible que pendant la phase finale du déploiement de l’interface utilisateur.

![Basculement de la version de l’interface utilisateur de Target](/help/main/r-release-notes/assets/toggle.png)

Une fois le déploiement terminé, le bouton (bascule) est supprimé et tous les utilisateurs passent définitivement à l’interface utilisateur mise à jour. [!DNL Adobe] recommande de planifier l’avenir, car cette fonctionnalité sera bientôt supprimée.

#### Chronologie de l’obsolescence

En raison de problèmes récents identifiés, principalement liés à des personnalisations client complexes, l’équipe [!DNL Target] a ajusté le calendrier d’abandon :

* **17 juin 2025** : toutes les organisations IMS ont été activées pour l’interface utilisateur [!DNL Target] mise à jour, pour des utilisateurs spécifiques ou à l’échelle de l’organisation, afin de commencer à tester la nouvelle expérience.

* **30 juin 2025** : l’[updated [!DNL Target] UI](/help/main/c-intro/understand-the-target-ui.md) est devenue l’expérience par défaut pour toutes les organisations IMS qui ont activé le bouton (bascule) de version de l’interface utilisateur.

   * Les clients qui consultent actuellement l’interface utilisateur héritée, par défaut, voient désormais l’interface utilisateur mise à jour lors de la connexion.
   * Le bouton (bascule) de version de l’interface utilisateur reste disponible jusqu’à la fin juillet, ce qui permet aux utilisateurs et utilisatrices de revenir en arrière si nécessaire.

  >[!IMPORTANT]
  >
  > [!DNL Adobe] recommande vivement d’utiliser l’interface utilisateur de [!DNL Target] mise à jour. Revenez à l’interface utilisateur héritée uniquement si un problème de blocage se produit, en raison des [limitations du comportement du bouton (bascule)](#limitations).

* **du 15 au 30 juillet 2025** : le bouton (bascule) de version de l’interface utilisateur sera désactivé définitivement par phases. Les organisations IMS affectées ne peuvent plus revenir à l’interface utilisateur héritée.

   * Les exceptions sont examinées au cas par cas.
   * Les délais d’abandon du bouton (bascule) ne sont accordés que brièvement (quelques jours) pendant que les problèmes de blocage sont résolus.

Contactez l’[Assistance clientèle d’Adobe](/help/main/cmp-resources-and-contact-information.md#/help/main/cmp-resources-and-contact-information.md) si vous avez des inquiétudes ou si vous prévoyez des problèmes au cours de cette transition.

#### Limites du comportement du bouton (bascule) de l’interface utilisateur {#limitations}

Les informations suivantes décrivent les limites que vous devez connaître lorsque vous choisissez d’utiliser le bouton (bascule) de version :

* **Visibilité des nouvelles activités** : les activités créées dans l’interface utilisateur mise à jour ne seront pas visibles si vous revenez à l’interface utilisateur héritée.
* **Modification d’activités existantes** : les modifications apportées à des activités existantes (créées à l’origine dans l’interface utilisateur héritée) lors de l’utilisation de l’interface utilisateur mise à jour sont publiées sur votre site web. Toutefois, ces mises à jour ne sont pas visibles dans l’interface utilisateur héritée si vous revenez en arrière ; seules les dernières mises à jour effectuées à partir de l’interface utilisateur héritée y apparaissent.
* **Cohérence des détails de l’activité** : les modifications les plus récentes, quelle que soit l’interface utilisateur que vous utilisez, sont répercutées sur votre site web actif. Cependant, l’interface utilisateur héritée n’affiche que les dernières modifications apportées à partir de cette version. Cette situation peut prêter à confusion si les activités modifiées dans l’interface utilisateur mise à jour ont un aspect différent de celui de l’interface utilisateur héritée.

#### Plus de ressources pour en savoir plus sur l’interface utilisateur mise à jour

* [[!DNL Target] FAQ sur la mise à jour de l’interface utilisateur](/help/main/c-intro/updated-ui-faq.md) : cette FAQ aborde les questions courantes sur la nouvelle interface utilisateur [!DNL Target] et le nouveau [!UICONTROL Visual Experience Composer] (VEC), y compris les modifications de navigation, les emplacements de fonctionnalités et l’obsolescence du bouton (bascule) de version temporaire de l’interface utilisateur. Que vous soyez spécialiste du marketing, développeur ou administrateur, cette FAQ vous aide à effectuer une transition en douceur et à tirer le meilleur parti de l’interface utilisateur mise à jour.
* [[!DNL Target Standard/Premium] Notes de mise à jour de la version 25.2.1 (17 février 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2) : fournit un résumé des principales modifications apportées à l’interface utilisateur des [!DNL Target] pour [!UICONTROL Activities], [!UICONTROL Recommendations] et le [!UICONTROL Visual Experience Composer] (VEC).
* Notes de mise à jour de la version [[!DNL Target Standard/Premium] 25.1.1 (9 janvier 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1) : fournit un résumé des principales modifications apportées à l’interface utilisateur des [!DNL Target] pour le [!UICONTROL Offers Library].
* [Présentation de l [!DNL Target] interface utilisateur ](/help/main/c-intro/understand-the-target-ui.md) : fournit un bref aperçu pour vous familiariser avec les [!DNL Target] et fournit des liens vers des informations plus détaillées et des instructions détaillées.
* [[!UICONTROL Visual Experience Composer] modifications ](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md) : la version [!DNL Adobe Target Standard/Premium] 25.2.1 (17 février 2015) introduit un [!UICONTROL Visual Experience Composer] mis à jour (VEC). Cet article explique les différences entre les versions héritées et mises à jour du compositeur d’expérience visuelle.
* [[!UICONTROL Visual Experience Composer] options ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md) : cet article explique l’interface utilisateur du compositeur d’expérience visuelle mise à jour et ses options.

+++

## [!DNL Target Standard/Premium] 25.8.1 (7 août 2025)

Cette version comprend les améliorations et correctifs suivants :

**Activités**

+++Voir les détails
* Correction de plusieurs problèmes liés à l’interface utilisateur mise à jour, notamment des erreurs lors de la suppression de types de page en raison de l’espacement des valeurs d’entrée, d’une copie d’activité non fiable entre les espaces de travail et d’un dysfonctionnement des règles de diffusion de page dans les environnements d’assurance qualité. (TGT-52703)
* Correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour en raison duquel les utilisateurs dotés du rôle [!UICONTROL Editor] pouvaient accéder aux activités en direct et tenter de les modifier, ce qui devait être limité. Les écrans de liste et d’aperçu des activités n’affichaient pas correctement les options de modification des activités en direct, ce qui entraînait des modifications involontaires potentielles. (TGT-53055)
* Correction d’un problème dans l’interface utilisateur de [!UICONTROL Advanced Search] en raison duquel la sélection des opérateurs « valeur présente » ou « valeur absente » invitait les utilisateurs à saisir un opérande, qui n’était pas obligatoire pour ces conditions. (TGT-51961)
* Correction d’un problème dans l’interface utilisateur mise à jour en raison duquel les tentatives de copie des activités de l’espace de travail d’évaluation vers l’espace de travail de production échouaient systématiquement, même dans les environnements sandbox. Les clients ont rencontré divers messages d’erreur, notamment « Audience anonyme déjà utilisée par l’activité » et « Identifiant d’audience non valide », même s’ils utilisaient des configurations valides et disposaient des autorisations d’espace de travail appropriées. (TGT-52394)

+++

**Fragments d’expérience (XF)**

+++Voir les détails
* Correction d’un problème en raison duquel le rendu du contenu du fragment d’expérience (XF) échouait dans l’aperçu du [!UICONTROL Visual Experience Composer] (VEC), malgré le fonctionnement correct dans la diffusion de contenu. (TGT-53318)

+++

**Localisation**

+++Voir les détails
* Correction d’un problème de localisation en raison duquel le bouton « Ajouter une promotion » de la section « Promotions » apparaissait non localisé dans plusieurs environnements linguistiques dans le client d’assurance qualité. (TGT-53263)

+++

**Offres**

+++Voir les détails
* Correction d’un problème en raison duquel la modification d’une offre HTML existante via le Compositeur d’expérience visuelle (VEC) entraînait la suppression de toutes les modifications de la diffusion de contenu. Les modifications apparaissent grisées dans l’onglet de modification et ne sont pas répercutées dans les aperçus de l’assurance qualité, bien qu’elles aient été correctement appliquées dans l’interface utilisateur héritée. (TGT-52863)
* Correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour en raison duquel les modifications d’offre HTML effectuées dans le [!UICONTROL Visual Experience Composer] (VEC) ne persistaient pas après avoir repassé de l’onglet [!UICONTROL Targeting] à [!UICONTROL Experiences]. (TGT-52874)
* Correction d’un problème dans l’interface utilisateur [!DNL Target] mise à jour en raison duquel l’insertion d’une offre HTML avant et d’une autre après le même sélecteur provoquait une génération d’emplacement incorrecte. Lorsque les clients sont revenus de l’onglet [!UICONTROL Targeting] à l’onglet [!UICONTROL Experience] , un seul sélecteur a été conservé, ce qui a entraîné la perte des modifications et l’interruption de la diffusion de contenu. Ce comportement était différent de celui de l’interface utilisateur héritée, qui conservait correctement les deux modifications avec des identifiants d’emplacement distincts. (TGT-52891)
* Correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour, en raison duquel le fait de cliquer sur une offre ajoutée dans le rail de [!UICONTROL Modifications] entraînait l’affichage et la disparition intermittents du panneau de [!UICONTROL Configuration] de droite, ce qui rendait difficile l’interaction avec les paramètres de l’offre. (TGT-53288)
* Correction d’un problème où les offres d’HTML ajoutées à des variations spécifiques à l’audience dans une activité n’étaient pas systématiquement enregistrées ou affichées dans la section de modification. Après avoir basculé entre les audiences lors de la modification, les offres précédemment appliquées disparaissaient parfois ou ne s’affichaient pas, ce qui perturbait la validation et retardait la préparation de l’activité. (TGT-53440)
* Correction d’un problème en raison duquel la copie d’une activité qui incluait des offres entraînait la création d’offres en double dans la nouvelle activité. Ce comportement entraînait un encombrement et une confusion inutiles, en particulier lors du déplacement d’activités entre les espaces de travail. Le correctif garantit que [!DNL Target] offres sont désormais correctement copiées dans l’espace de travail de destination sans duplication, ce qui permet de rationaliser la gestion des activités et d’améliorer l’efficacité des workflows. (TGT-53454)

+++

**Applications monopages (SPA)**

+++Voir les détails
* Correction d’un problème dans le VEC mis à jour qui empêchait les clients et clientes d’appliquer des modifications aux vues [!UICONTROL Single Page Application] (SPA). Bien que les activités créées dans l’ancienne interface utilisateur prenaient en charge le ciblage spécifique des vues, la nouvelle interface utilisateur n’a pas réussi à détecter ou à autoriser les modifications de ces vues, et les commandes de changement de vue sont apparues désactivées. (TGT-52556)

+++

**Compositeur d’expérience visuelle**

+++Voir les détails
* Correction d’un problème en raison duquel les modifications apportées aux expériences dans le [!UICONTROL Visual Experience Composer] n’étaient pas visibles ou s’affichaient de manière incohérente dans l’interface utilisateur. (TGT-TGT-53381)
* Correction d’un problème dans le VEC mis à jour en raison duquel la section [!UICONTROL Manage Content] n’affichait pas de texte secondaire pour les miniatures d’expérience. Ce problème rendait difficile l’identification des documents pour les utilisateurs et les utilisatrices, en particulier lorsque les noms de fichier étaient longs ou tronqués. (TGT-52291)
* Correction d’une erreur en raison de laquelle les clients rencontraient des erreurs de validation incorrectes lors de la configuration des règles [!UICONTROL page delivery] dans les activités du compositeur d’expérience visuelle. En particulier, les opérateurs tels que « est égal à n’importe lequel » et « n’est égal à aucun de » déclenchent une « entrée non valide pour le type d’opérateur » lors de la saisie de valeurs de texte, même si le texte doit être pris en charge. (TGT-52629)
* Correction de plusieurs problèmes qui provoquaient un comportement incohérent dans le panneau [!UICONTROL Modifications] de l’interface utilisateur mise à jour lors de la sélection des offres à l’aide du bouton « Sélectionner une offre ». Au lieu de remplacer l’offre existante, l’interface utilisateur a ajouté un doublon et a tenté d’interagir avec l’une ou l’autre des offres, ce qui a entraîné des erreurs de console, telles que `selectorNotFound`. De plus, certaines offres n’affichent pas le bouton « Sélectionner une offre », affichant uniquement les propriétés modifiables. (TGT-53321)
* Correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour en raison duquel les modifications de code HTML effectuées lors de la configuration de l’activité ne persistaient pas sur les pages de variation, même si elles étaient correctement enregistrées pour les populations témoins. Malgré plusieurs tentatives et la recréation de tests sans regroupements de pages, les pages de variation ne conservaient jamais les modifications, ce qui affectait la diffusion du contenu et la validation de l’assurance qualité. (TGT-53436)
* Correction d’un problème dans le VEC mis à jour en raison duquel l’opérateur « égal à n’importe lequel » dans les règles de diffusion de page n’acceptait pas les valeurs d’entrée. Lors de la configuration des paramètres client dans toutes les mbox, la sélection de cet opérateur entraînait une erreur « Entrée non valide », empêchant la création de la règle. (TGT-52623)

+++

**Workspaces**

+++Voir les détails
* Amélioration du workflow lors de la copie d’activités entre les espaces de travail. Les activités de copie entre les espaces de travail entraînaient précédemment des erreurs de synchronisation en raison d’audiences manquantes et de propriétés non attribuées. Cette mise à jour introduit un workflow plus intelligent et plus intuitif qui garantit que les activités copiées sont correctement configurées et prêtes à être publiées. (TGT-47094)
* Correction d’un problème en raison duquel les clients ne pouvaient pas copier d’activités entre les espaces de travail en raison d’un échec de la mutation `copyActivityBatchOperations`. Les tentatives de duplication d’activités ont entraîné une erreur de serveur (500) et une payload de réponse nulle. (TGT-52405)
* Correction d’un problème en raison duquel les activités ne se synchronisaient pas lorsque les offres référencées dans la configuration n’étaient pas accessibles dans l’espace de travail sélectionné. Cela provoquait des erreurs de publication et laissait les activités dans un état d’échec. (TGT-52535)
* Correction de plusieurs problèmes lors de la copie d’activités entre des espaces de travail dans l’interface utilisateur [!DNL Target] mise à jour. Les clients rencontrent des erreurs liées à l’accès à l’audience, en particulier avec les activités en direct, et une validation de privilèges incorrecte, même lorsque l’utilisateur disposait de rôles « [!UICONTROL Approver] » dans les espaces de travail source et de destination. (TGT-53002)
* Correction d’un problème dans l’interface utilisateur mise à jour en raison duquel la copie d’activités dans le même espace de travail dupliquait inutilement les offres et audiences associées. (TGT-53457)
* Correction d’un problème en raison duquel les audiences ad hoc (anonymes) n’étaient pas correctement copiées entre les espaces de travail non par défaut ou entre les espaces de travail non par défaut et les espaces de travail par défaut. Alors que les mises à jour précédentes assuraient une duplication appropriée pour les scénarios par défaut et d’espace de travail identique, cette amélioration se concentrait sur la conservation des configurations d’audience combinées qui s’étendent sur plusieurs espaces de travail. Le correctif garantit un comportement d’audience cohérent et un ciblage précis sur toutes les transitions d’espace de travail. (TGT-53268)

+++

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
