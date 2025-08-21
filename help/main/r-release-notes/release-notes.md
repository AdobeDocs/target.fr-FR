---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bugs;mises à jour;mises à jour actuelles
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: b178785b1936cff2b55c85e41fc44f230243f849
workflow-type: tm+mt
source-wordcount: '5850'
ht-degree: 6%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Découvrez les dernières fonctionnalités, améliorations et correctifs d’[!DNL Adobe Target]. Ces notes de mise à jour couvrent également les mises à jour des API [!DNL Target], des SDK, de la [!DNL Adobe Experience Platform Web SDK], d’at.js et d’autres composants de plateforme, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## Mises à jour sensibles à l’heure que vous devez connaître {#time-sensitive}

[!BADGE Important]{type=Informative}

Pour les mises à jour urgentes relatives à [!DNL Adobe Target] et à votre implémentation, [!DNL Adobe]fournit des notes de mise à jour détaillées et une documentation via [!UICONTROL Experience League]. Voici quelques points forts importants liés à votre implémentation :

### Obsolescence du bouton (bascule) de version de l’interface utilisateur [!DNL Target]

+++Afficher les détails
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

## [!DNL Target Standard/Premium] 25.8.3 (21 août 2025)

Cette version comprend les mises à jour et correctifs suivants :

**[!UICONTROL Activities]**

+++Afficher les détails
* **Correction d’un problème où l’enregistrement des activités déclenchait une erreur d’entrée utilisateur non valide en raison de données de propriété incorrectes** : les clients et clientes rencontraient une erreur critique lors de la tentative d’enregistrement des activités existantes. Le message d’erreur indiquait une entrée utilisateur non valide, faisant spécifiquement référence à un contenu de nom de propriété non reconnu dans la payload JSON. Notamment, les nouvelles activités utilisant la même propriété ont été enregistrées avec succès, ce qui suggère que le problème a été isolé des données d’activité héritées. Le processus de création d’activités gère désormais correctement les configurations de propriété héritées, ce qui évite les erreurs d’entrée non valides et garantit un comportement d’enregistrement cohérent entre les activités nouvelles et existantes. (TGT-53507)
* **Correction d’un problème qui empêchait les clients d’enregistrer une activité en raison d’une erreur InvalidProperty.Json** : les clients rencontraient une erreur lorsqu’ils tentaient d’enregistrer une activité dans l’interface utilisateur mise à jour, même sans apporter de modifications. Le message d’erreur indique une structure JSON non valide : « JSON non valide. Nom de propriété « content » non reconnu. Emplacement : ligne - 1, colonne - 432. » Ce problème était dû à une propriété non reconnue dans la payload de requête et a été résolu. Les clients peuvent enregistrer les activités sans rencontrer cette erreur. (TGT-53513)
* **Correction d’un problème en raison duquel les activités planifiées affichaient incorrectement un statut [!UICONTROL Live] jusqu’à l’actualisation de la page** : les clients et clientes ont observé que lors de la planification d’une activité pour une activation à une date et une heure futures, le statut s’affichait immédiatement comme [!UICONTROL Live] au lieu de [!UICONTROL Scheduled]. Cela a semé la confusion, même si le message de confirmation indiquait correctement que l’activité était planifiée. Actualiser la page a corrigé l’affichage du statut. Ce problème a été résolu et les activités planifiées affichent correctement le statut Planifié sans qu’une actualisation soit nécessaire. (TGT-52937)

+++

**[!UICONTROL Analytics for Target] (A4T)**

+++Afficher les détails
* **Correction d’un problème en raison duquel les clients ne pouvaient pas saisir les noms des suites de rapports pendant le processus de création d’activités** : les clients qui utilisaient [!DNL Adobe Analytics] comme source de création de rapports pendant le processus de création d’activités ne pouvaient pas saisir de noms dans la liste déroulante [!UICONTROL Report Suite] pour rechercher des suites de rapports spécifiques. Cela affectait les workflows pour les organisations ayant un grand nombre de suites de rapports, où le défilement manuel retardait considérablement la configuration. La liste déroulante n’était pas triée par ordre alphabétique et ne répondait pas de manière cohérente aux entrées saisies, ce qui rendait difficile la localisation de suites de rapports telles que « Office + Store - Web - Prod ». Ce problème a été résolu et les clients peuvent désormais effectuer une recherche efficace en saisissant les noms des suites de rapports. (TGT-53345)

+++

**[!UICONTROL Audiences]**

+++Afficher les détails
* **Correction d’un problème en raison duquel les audiences « Time Frame » expirées bloquaient l’enregistrement de l’activité même après la suppression** : les clients ne pouvaient pas enregistrer les activités dans l’interface utilisateur mise à jour en raison d’une erreur liée aux audiences « Time Frame » expirées. Même après la suppression de l’audience affectée, le message d’erreur persistait : « L’activité contient une audience avec une période non valide ». Ce problème se produisait car le système continuait à valider l’audience d’activité seule, même lorsqu’elle n’était plus utilisée. Le comportement était encore compliqué par des écarts de fuseau horaire. La logique de validation a été corrigée et les clients peuvent désormais enregistrer les activités sans rencontrer cette erreur. (TGT-53517)

+++

**[!UICONTROL Experience Fragment]s**

+++Afficher les détails
* **Correction d’un problème qui empêchait les clients et clientes d’insérer des fragments d’expérience à l’aide de [!UICONTROL Insert Before] ou [!UICONTROL Insert After] dans l’interface utilisateur** les clients et clientes rencontraient une erreur lors de la tentative d’insertion de [!UICONTROL Experience Fragments] dans une activité à l’aide des options « Insérer avant » ou « Insérer après » dans l’interface utilisateur mise à jour. Le message d’erreur affiché était le suivant : « Le contenu de l’offre doit contenir exactement un élément HTML ». Ce problème était spécifique à l’interface utilisateur mise à jour et ne se produisait pas dans la version précédente. Ce problème a été résolu et les clients peuvent insérer des [!UICONTROL Experience Fragments] sans rencontrer cette erreur. (TGT-53442)

+++

**[!UICONTROL Offer decisions]**

+++Afficher les détails
* **Correction d’un problème qui empêchait les clients de modifier les offres de décision et de sélectionner des éléments de page spécifiques dans l’interface utilisateur mise à jour** : dans le processus de création d’activité mis à jour, les clients ne pouvaient pas modifier les offres de décision existantes ni sélectionner des éléments de page spécifiques dans le compositeur d’expérience visuelle (VEC). Les offres de décision s’affichaient incorrectement en tant qu’offres HTML et les modifications apportées lors de la modification n’ont pas été enregistrées. En outre, certaines URL régionales, telles que le site du Japon, n’ont pas pu se charger correctement dans le VEC, ce qui a bloqué la création et les mises à jour d’activités. Les offres de décision s’affichent désormais correctement, les éléments de page peuvent être sélectionnés comme prévu et les URL régionales se chargent correctement dans le VEC, ce qui restaure l’ensemble des fonctionnalités de modification. (TGT-53425)
* **Correction d’un problème en raison duquel les sélecteurs de [!UICONTROL Offer Decision] ne pouvaient pas être modifiés et changés de manière inattendue après l’enregistrement** : dans le processus de création d’activité mis à jour, les clients ne pouvaient pas modifier le sélecteur de [!UICONTROL Offer Decision] comme prévu. Les tentatives de modification du sélecteur ont échoué, et le sélecteur est revenu à une valeur incorrecte après l’enregistrement. Ce comportement a entraîné la disparition de l’offre de décision du Compositeur d’expérience visuelle (VEC), bloquant d’autres modifications. Les modifications apportées au sélecteur sont désormais correctement conservées et les offres de décision restent visibles et modifiables dans le VEC après l’enregistrement.(TGT-53433)
* **Correction d’un problème en raison duquel les [!UICONTROL Offer Decisions] disparaissaient de l’activité après l’enregistrement** : les [!UICONTROL Offer Decisions] ajoutées pendant le processus de création d’activité n’étaient pas conservées après l’enregistrement et la réouverture de l’activité. Ce problème se produisait lors de la modification de contenu dynamique et de l’insertion de [!UICONTROL Offer Decisions] avec des sélecteurs et des propriétés spécifiques. Les [!UICONTROL Offer Decisions] persistent désormais correctement après l’enregistrement et les sélecteurs restent intacts, ce qui garantit un comportement cohérent de ciblage et de modification. (TGT-53434)

+++

**[!DNL Recommendations]**

+++Afficher les détails
* **Correction d’un problème dans [!DNL Recommendations]’interface utilisateur en raison duquel le téléchargement d’un CSV de critères personnalisés renvoyait une erreur 404** : correction d’un problème en raison duquel les clients et clientes ne pouvaient pas télécharger le CSV de critères personnalisés dans le processus de création d’activités. Le lien de téléchargement fonctionne désormais correctement, ce qui permet aux clients d’exporter des critères personnalisés comme prévu. (TGT-51966)
* **Correction d’un chargement incohérent des images dans[!UICONTROL Catalog Search]** : correction d’un problème en raison duquel les miniatures et les images dans [!UICONTROL &#x200B; Catalog Search] ne se chargeaient pas de manière cohérente dans le processus de création d’activités. Les images ne s’affichaient pas, sauf si la colonne « URL de la miniature » était visible et que certaines images de produit étaient partiellement chargées ou pas du tout après des actions de navigation ou de recherche. Le comportement de chargement des images est stabilisé et les miniatures s’affichent désormais de manière fiable, quelle que soit la visibilité des colonnes ou les actions de navigation. (TGT-52778)
* **Correction d’un problème en raison duquel la modification d’une recommandation dans une expérience dupliquée avait un impact sur l’expérience d’origine** : les clients ont signalé que la modification d’une recommandation dans une expérience dupliquée modifiait involontairement l’expérience d’origine. Plus précisément, après avoir dupliqué l’expérience B dans le processus de création d’activité et modifié sa conception ou ses critères, les mêmes modifications ont été répercutées dans l’expérience B d’origine, bien qu’il s’agisse d’entités distinctes. Les expériences dupliquées conservent désormais des configurations distinctes, ce qui garantit que les modifications apportées à une expérience n’affectent pas l’expérience d’origine. (TGT-53369)
* **Correction d’un problème en raison duquel les modifications apportées à une expérience dupliquée affectaient involontairement l’expérience originale dans une activité** : les clients et clientes signalaient que lors de la duplication d’une expérience au sein d’une activité et de l’affectation d’une nouvelle audience, toute modification apportée à la conception ou aux critères de l’expérience dupliquée était également répercutée dans l’expérience originale. Ce problème se produisait même si aucune modification n’était apportée directement à la version d’origine, ce qui affectait la possibilité de créer des variations indépendantes au sein de la même activité. Le processus de création d’activités isole désormais correctement les expériences dupliquées, en veillant à ce que les modifications apportées à une expérience n’affectent pas l’expérience originale. (TGT-53361)
* **Correction d’un problème en raison duquel le [!UICONTROL Recommendation Catalog] échouait par intermittence à afficher les données complètes d’attributs de produit** : dans l’interface utilisateur de [!DNL Recommendations] mise à jour, les clients rencontraient un problème en raison duquel certains attributs de produit, tels que le message, n’étaient pas affichés de manière cohérente dans les résultats du [!UICONTROL Catalog Search], même si les données existaient dans le flux. Pour résoudre ce problème, les clients devaient reconfigurer manuellement la visibilité de la colonne pour récupérer les valeurs manquantes. [!UICONTROL Catalog Search] affiche désormais de manière fiable tous les attributs configurés, ce qui élimine la nécessité de réinitialiser manuellement les colonnes. (TGT-52769)
* **Correction d’un problème en raison duquel une [!UICONTROL Front Promotion] ne pouvait pas être désactivée dans une activité active** : les tentatives de désactivation d’une [!UICONTROL Front Promotion] dans une activité active n’étaient pas enregistrées. Après avoir sélectionné [!UICONTROL Change Promotion] et désactivé cette option, la promotion est restée active lors de la modification de l’activité, empêchant la mise à jour des configurations de recommandation. Les paramètres de promotion s’enregistrent désormais correctement, ce qui permet aux clients de désactiver ou de modifier les promotions dans les activités dynamiques comme prévu. (TGT-53231)
* **Correction d’un problème en raison duquel l’activation d’un [!DNL Recommendations] [!UICONTROL Promotion] sans données déclenchait un message d’erreur flou** : l’activation d’un [!UICONTROL Front] ou d’un [!UICONTROL Back Promotion] dans une activité [!DNL Recommendations] sans spécifier les valeurs requises générait un message d’erreur « Entrée non valide » générique. Le problème sous-jacent était l’absence d’un champ de configuration , mais le message d’erreur n’indiquait pas clairement la cause, ce qui rendait le dépannage difficile. Le processus de création d’activités génère désormais un message d’erreur clair et exploitable lorsque des champs obligatoires, tels que des `collectionId` ou des règles, sont manquants, ce qui permet aux clients d’identifier et de résoudre rapidement les problèmes de configuration. (TGT-52616)
* **Correction d’un problème qui empêchait l’affichage de la liste de [!UICONTROL Product] dans la boîte de dialogue modale [!UICONTROL Edit] de l’onglet [!UICONTROL Recommendations]** : les clients ne pouvaient pas afficher la liste de produits filtrée lors de la modification d’un [!UICONTROL collection] ou d’un [!UICONTROL exclusion] dans l’onglet [!UICONTROL Recommendations] . La liste devait être mise à jour en temps réel en fonction des règles appliquées, mais elle n’apparaissait pas comme prévu. Ce problème a été résolu, et la liste des produits s’affiche désormais correctement et se met à jour dynamiquement à mesure que les règles sont modifiées. (TGT-53481)
* **Correction d’un problème lié à la disposition de la boîte de dialogue Afficher les détails dans l’interface utilisateur mise à jour** : la disposition de la boîte de dialogue modale Afficher les détails dans l’interface utilisateur mise à jour a été modifiée pour améliorer la clarté et la convivialité. La boîte de dialogue comprend désormais deux onglets :
   * Onglet [!UICONTROL Details] : affiche toutes les informations pertinentes pour l’élément sélectionné.
   * Onglet [!UICONTROL Inventory] : affiche tous les produits filtrés par les règles de collecte et d’exclusion actuelles.

  Cette amélioration permet aux clients de parcourir et de comprendre plus facilement les données spécifiques à un article et le contexte de l’inventaire dans le processus de création d’activités. (TGT-53503)

   * **Correction d’un problème en raison duquel les promotions supprimées dans les activités de recommandation réapparaissaient après l’enregistrement** : les clients signalaient que lorsque des promotions [!UICONTROL front] ou [!UICONTROL back] étaient supprimées de [!DNL Recommendations] activités et que l’activité était enregistrée, les promotions continuaient à apparaître lors de la réouverture. Ce problème se produisait dans les environnements d’évaluation et de production et affectait le processus de création d’activité mis à jour. Le problème a été résolu. Les promotions supprimées d’une activité persistent désormais correctement après l’enregistrement. (TGT-53490)

+++

**Rapports**

+++Afficher les détails
* **Correction d’un problème où le rapport [!UICONTROL Automated Segments] affichait des valeurs d’audience nulles** : les clients et clientes signalaient que les [!UICONTROL Automated Segments] dans les rapports d’activité affichaient une valeur nulle pour les données d’audience, empêchant une analyse précise des performances du segment. Ce problème se produisait lors de l’accès à la section [!UICONTROL Reports] et de la sélection de [!UICONTROL Automated Segments], même si des données d’audience valides étaient attendues. [!UICONTROL Automated Segments] affiche désormais correctement les valeurs d’audience, garantissant ainsi des rapports et des informations de segmentation fiables. (TGT-52793)

+++

**Applications monopages (SPA)**

+++Afficher les détails
* **Correction d’un problème en raison duquel le passage entre les modes [!UICONTROL Browse] et [!UICONTROL Design] réinitialisait l’état de la SPA dans l’interface utilisateur mise à jour** : les clients ont signalé que le passage entre les modes [!UICONTROL Browse] et [!UICONTROL Design] dans l’interface utilisateur mise à jour entraînait le rechargement de l’éditeur web, la réinitialisation de l’état des SPA. Ce problème interrompait les workflows et obligeait les clients à saisir à nouveau les informations. Le problème a été résolu. L’état de la SPA est désormais préservé lors du basculement entre les modes, ce qui garantit une expérience plus fluide et plus cohérente lors de la création de l’activité. (TGT-53074)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Afficher les détails
* **Correction d’un problème dans le processus de création d’activités qui bloquait la progression vers l’étape [!UICONTROL Targeting] dans les activités AP**: correction d’un problème dans le processus de création d’activités en raison duquel les clients ne pouvaient pas passer à l’étape [!UICONTROL Targeting] dans les activités [!UICONTROL Automated Personalization] (AP) à moins que deux emplacements ne soient ajoutés. Ce comportement différait de l’expérience précédente, où un seul emplacement avec plusieurs offres était suffisant. Cette exigence a été corrigée, ce qui permet aux clients de continuer à utiliser des configurations à emplacement unique dans le cadre de leurs workflows AP. (TGT-53426)
* **Correction d’un problème en raison duquel le nouveau processus de création d’activités ne définissait pas le paramètre fmt=png-alpha pour les images transparentes** : dans l’interface utilisateur mise à jour, les images insérées pendant le processus de création d’activités n’incluaient plus le paramètre `fmt=png-alpha` par défaut, ce qui entraînait une perte de transparence. Ce comportement était différent de celui de l’interface utilisateur précédente, qui ajoutait automatiquement le paramètre aux URL des images, préservant ainsi les arrière-plans transparents. Le processus de création d’activités applique désormais correctement le paramètre `fmt=png-alpha` aux URL d’images lorsque la transparence est requise, garantissant ainsi un rendu cohérent des ressources transparentes. (TGT-52615)
* **Correction d’un problème qui empêchait les clients de rechercher des suites de rapports dans l’interface utilisateur mise à jour** : dans l’interface utilisateur mise à jour, la liste déroulante [!UICONTROL Report Suites] de la section [!UICONTROL Goals & Settings] ne permettait pas aux clients de saisir et de rechercher des suites de rapports, ce qui rendait difficile la localisation de suites de rapports spécifiques, en particulier pour les clients avec un grand nombre d’entrées. Contrairement à l’interface utilisateur précédente, la liste n’était pas triée et ne comportait pas de filtrage basé sur les entrées. Ce problème a été résolu. Les clients peuvent désormais saisir du texte pour rechercher et filtrer des suites de rapports, restaurant ainsi la fonctionnalité disponible dans l’interface utilisateur héritée. (TGT-53514)

+++

**[!UICONTROL Workspaces]**

+++Afficher les détails
* **Correction d’un problème en raison duquel un client limité à un seul espace de travail pouvait afficher les activités d’autres espaces de travail** : les clients dont l’accès était limité à un espace de travail pouvaient de manière inattendue afficher les activités de tous les espaces de travail lors de la sélection de [!UICONTROL All Workspaces] dans le processus de création d’activités. Cette visibilité entraînait un risque de modifications involontaires des activités en direct dans d’autres espaces de travail, ce qui pouvait avoir un impact sur les performances du site web. Les contrôles d’accès de Workspace ont été renforcés pour s’assurer que les clients peuvent afficher et interagir uniquement avec les activités dans l’espace de travail qui leur est affecté. (TGT-53101)
* **Correction d’un problème en raison duquel un client pouvait afficher des activités à partir de l’[!UICONTROL Default Workspace] sans y avoir accès :** un client avec un accès limité à l’espace de travail d’évaluation pouvait afficher des activités à partir de l’[!UICONTROL Default Workspace] via le processus de création d’activités. Ce comportement s’est produit malgré une configuration de serveur principal et des droits d’accès corrects. Les contrôles d’accès de Workspace ont été renforcés pour s’assurer que les clients peuvent afficher les activités uniquement dans l’espace de travail qui leur est affecté.(TGT-53297)

+++

## [!DNL Target Standard/Premium] 25.8.2 (14 août 2025)

Cette version comprend les correctifs et mises à jour suivants :

**[!UICONTROL Activities]**

+++Afficher les détails
* **Correction d’un problème de chargement d’activité dans l’interface utilisateur de [!DNL Target] mise à jour**: correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour où certaines activités ne se chargeaient pas lors de la tentative de modification. Ce problème entraînait le départ des clients dans un écran de chargement indéfini. Ce problème affectait plusieurs activités et il était signalé de manière incohérente parmi les clients. Grâce à ce correctif, les activités affectées se chargent désormais correctement, ce qui permet une modification transparente et réduit l’interruption des workflows d’activité. (TGT-53209)
* **Correction d’une erreur d’enregistrement dans le processus de création d’activités en raison de la validation du `optionLocalId`** : correction d’un problème dans le processus de création d’activités qui empêchait les clients d’enregistrer les modifications en raison d’une erreur de validation du serveur principal : `OptionLocalIdReferentialIntegrity.ABActivity - Invalid optionLocalIds:` ce problème se produisait lors de la modification d’éléments spécifiques dans une activité, ce qui entraînait l’échec de l’opération d’enregistrement. Le correctif garantit que les références `optionLocalId` sont désormais correctement validées, ce qui permet aux clients d’enregistrer les activités sans rencontrer cette erreur. (TGT-53293)
* **Correction du blocage dans le processus de création d’activités en raison de références d’option non valides lors du changement de page** : correction d’un problème dans le processus de création d’activités en raison duquel l’interface utilisateur se bloquait après avoir changé de page trois fois lors de la modification. Le crash a été déclenché par des références d&#39;option non valides, entraînant des erreurs de console telles que « Option avec localId &#39;7&#39; introuvable. » Grâce à cette mise à jour, les clients peuvent désormais basculer entre les pages et appliquer des modifications sans rencontrer de défaillances ou d’interruptions du système. (TGT-53295)
* **Correction d’une erreur d’enregistrement dans le processus de création d’activités due à une entrée utilisateur non valide lors de la modification d’expériences** : correction d’un problème dans le processus de création d’activités en raison duquel les clients et clientes ne pouvaient pas enregistrer les modifications apportées à une activité en raison d’une erreur d’entrée utilisateur non valide. L’erreur s’est produite lors de la modification d’expériences dans l’interface utilisateur mise à jour, empêchant la validation des mises à jour. L’activité peut désormais être enregistrée avec succès, ce qui permet aux clients de la modifier et de la publier sans interruption. (TGT-53267)
* **Correction d’un problème de chargement dans le processus de création d’activités qui bloquait la modification dans l’interface utilisateur mise à jour** : correction d’un problème dans le processus de création d’activités en raison duquel les clients ne pouvaient pas modifier les activités dans l’interface utilisateur mise à jour en raison d’un écran de chargement continu. Les clients peuvent désormais ouvrir et modifier des activités sans rencontrer d’échecs de chargement. (TGT-53415)
* **Correction d’un problème d’exigence d’expérience dans le processus de création d’activités pour les activités AP dans l’interface utilisateur mise à jour** : correction d’un problème dans le processus de création d’activités où les activités [!UICONTROL Automated Personalization] (AP) nécessitaient deux emplacements au lieu de deux expériences dans l’interface utilisateur mise à jour. Ce comportement bloque les cas d’utilisation où les clients configurent un emplacement unique avec plusieurs offres, qui était auparavant pris en charge. L’exigence a été corrigée pour correspondre à la fonctionnalité d’origine, ce qui permet aux clients de poursuivre les activités AP à l’aide de deux expériences, quel que soit le nombre d’emplacements. (TGT-53429)
* **Correction du comportement des champs d’élément suivis en mode Cliquer sur le suivi pour empêcher l’enregistrement d’une entrée et améliorer la clarté** : correction d’un problème dans le processus de création d’activités où le champ [!UICONTROL Tracked Element] en mode [!DNL Click Track] était modifiable, mais ne conservait pas le nom saisi, ce qui entraînait une confusion pour les clients. Le champ est maintenant désactivé pour empêcher toute entrée non enregistrée et le nom des éléments sélectionnés a été clarifié pour améliorer la configuration des objectifs et la précision du suivi.** (TGT-53458)
* **Correction d’un problème dans le processus de création d’activités qui bloquait l’attribution de noms aux composants suivis en mode [!UICONTROL Click Track]** : correction d’un problème dans le processus de création d’activités en raison duquel les clients et clientes ne pouvaient pas nommer les composants suivis en mode [!UICONTROL Click Track]. Après avoir saisi un nom, le champ semblait modifiable, mais ne conservait pas l’entrée. Par défaut, les libellés génériques tels que « MON OBJECTIF DE PRINCIPAL 0 » étaient utilisés en mode d’édition. Le champ Élément suivi est maintenant désactivé et le comportement de dénomination a été clarifié afin d’améliorer la configuration des objectifs et la précision du suivi. (TGT-51396)

+++

**Fragments d’expérience (XF)**

+++Afficher les détails
* **Correction d’un problème dans le processus de création d’activités qui autorisait la modification involontaire par HTML des fragments exportés par AEM** : correction d’un problème dans le processus de création d’activités qui permettait aux clients de modifier l’HTML des [!DNL Experience Fragments] (XF) exportés depuis [!DNL Adobe Experience Manager] (AEM) dans [!DNL Target]. Ce comportement n’était pas prévu, car les fichiers XF doivent rester verrouillés pour modification une fois publiés à partir d’AEM. Le correctif garantit que l’option « Modifier HTML » n’est plus disponible pour les fragments exportés par AEM, préservant ainsi l’intégrité du contenu et la gouvernance attendue. (TGT-53286)
* **Correction d’un problème d’aperçu intermittent du contenu XF dans le processus de création d’activités dans l’interface utilisateur mise à jour** : correction d’un problème dans le processus de création d’activités où le rendu du contenu XF échouait par intermittence en mode d’aperçu dans l’interface utilisateur mise à jour. Bien que le contenu ait été correctement diffusé, l’aperçu ne s’affichait pas de manière cohérente, ce qui rendait difficile la validation de la configuration de l’offre pour les clients. Les aperçus XF se chargent désormais de manière fiable, améliorant la confiance et l’efficacité lors de la configuration des activités. (TGT-53318)

+++

**Mode assurance qualité**

+++Afficher les détails
* **Correction d’un problème dans le processus de création d’activités en raison duquel les espaces de début dans les URL provoquaient des liens d’assurance qualité rompus** : correction d’un problème dans le processus de création d’activités en raison duquel les espaces de début dans l’URL de l’activité n’étaient pas correctement supprimés lors de l’enregistrement. Cela entraînait des liens d’assurance qualité non valides et un formatage incorrect dans le serveur principal. Après la mise à jour, les URL sont désormais enregistrées proprement, ce qui empêche les liens rompus et améliore la fiabilité des workflows d’assurance qualité pour les clients et les clientes. (TGT-53427)

+++

**[!UICONTROL Recommendations]**

+++Afficher les détails
* **Correction d’un problème dans l’interface utilisateur de recherche de catalogue en raison duquel la recherche avancée ne pouvait pas fournir de suggestions** : correction d’un problème dans la nouvelle interface utilisateur de [!UICONTROL Catalog Search] en raison duquel la fonction de [!UICONTROL Advanced Search] ne pouvait pas fournir de suggestions. Les utilisateurs devaient saisir des valeurs exactes avec une orthographe précise, ce qui rendait la recherche difficile et susceptible de contenir des erreurs. Grâce à ce correctif, le [!UICONTROL Advanced Search] offre désormais des suggestions pertinentes au fur et à mesure que les utilisateurs saisissent, améliorant ainsi la convivialité et réduisant le frottement lors de la localisation des produits. (TGT-52008)
* **Résolution de plusieurs problèmes d’interface utilisateur et de filtrage pour améliorer la réactivité et l’interaction des entités** : résolution de plusieurs problèmes, notamment la faible réactivité des détails des critères sur les appareils à petit écran, l’absence de résultats lors de la sélection de « Tous les groupes d’hôtes » dans le filtre Environnement et l’impossibilité d’interagir avec des entités sans nom. Ces correctifs améliorent la convivialité sur toutes les tailles d’écran, assurent un filtrage précis et permettent une interaction complète avec toutes les entités de produit, améliorant ainsi l’expérience globale pour les utilisateurs. (TGT-52992)
* **Correction d’ID de produit manquants dans la vue détaillée Recommendations lors de la création de l’activité** : correction d’un problème dans le processus de création d’activité [!DNL Recommendations] en raison duquel les ID de produit étaient manquants dans l’écran des détails du produit, ce qui rendait difficile pour les clients de copier ou de référencer les ID de produit pendant les workflows. Les identifiants de produit apparaissent désormais clairement dans la vue détaillée, ce qui améliore la visibilité et permet une gestion plus efficace des produits pour les clients. (TGT-51964)
* **Correction d’un problème dans le processus de création d’activités en raison duquel les messages de produit ne s’affichaient pas dans la vue de recommandations**: correction d’un problème dans le processus de création d’activités en raison duquel la colonne [!UICONTROL Message] de la vue de [!DNL Recommendations] n’affichait pas les données de produit, même si des messages étaient présents. Les clients devaient supprimer et ajouter à nouveau manuellement la colonne pour afficher temporairement le contenu, qui disparaissait souvent à nouveau lors du défilement ou de la recherche. Cette mise à jour restaure une visibilité cohérente des messages de produit, améliorant la navigation dans le catalogue et les workflows de révision. (TGT-52777)
* **Correction d’un problème dans le processus de création d’activités, en raison duquel la sélection de « Tous les groupes d’hôtes » n’avait renvoyé aucun résultat dans la vue de recommandations** : correction d’un problème dans le processus de création d’activités, en raison duquel la sélection de l’environnement « Tous les groupes d’hôtes » dans la vue de [!DNL Recommendations] n’avait renvoyé aucun résultat. Les clients peuvent désormais afficher comme prévu les données de produit sur tous les groupes d’hôtes, ce qui améliore la visibilité et la précision du filtrage lors de la configuration des activités. (TGT-53006)
* **Correction d’un problème dans le processus de création d’activités en raison duquel le bouton de promotion front ne persistait pas après l’enregistrement** : correction d’un problème dans le processus de création d’activités en raison duquel la désactivation du bouton de promotion front dans les paramètres d’activité ne persistait pas après l’enregistrement. Les clients qui tentaient de supprimer la promotion principale ont trouvé que le bouton (bascule) était réactivé lors de leur visite de l’activité, empêchant une personnalisation correcte. Cette mise à jour permet d’enregistrer les modifications de manière fiable, ce qui donne aux clients un contrôle total sur les paramètres de promotion. (TGT-53215)
* **Correction d’un tri incohérent par colonne [!UICONTROL Last Updated] :** correction d’un problème dans le processus de création d’activités en raison duquel le tri du catalogue par colonne [!UICONTROL Last updated] générait des résultats incohérents. Les clients ne pouvaient pas organiser de manière fiable les données de produit en fonction des horodatages de mise à jour, ce qui rendait la révision et la gestion du catalogue plus difficiles. Le tri fonctionne désormais comme prévu, ce qui améliore la précision et la convivialité dans l’interface utilisateur mise à jour. (TGT-53116)

+++

**Compositeur d’expérience visuelle**

+++Afficher les détails
* **Correction des problèmes de chargement des activités et de bouton de [!UICONTROL Cancel] dans le processus de création d’activités** : correction d’un problème dans le processus de création d’activités où le chargement de certaines activités échouait, empêchant les clients d’accéder aux modifications. En outre, le bouton [!UICONTROL Cancel] ne répondait pas, ce qui empêchait les clients d’arrêter le processus de chargement ou de quitter la vue de modification. Ce correctif garantit que les activités se chargent désormais de manière fiable et que le bouton [!UICONTROL Cancel] fonctionne comme prévu, améliorant ainsi la stabilité globale et l’expérience utilisateur du compositeur d’expérience visuelle. (VEC)(TGT-53218)
* **Correction d’un problème de changement d’expérience dans l’interface utilisateur du VEC mise à jour qui bloquait la modification et désactivait [!UICONTROL Cancel] bouton** : correction d’un problème dans l’interface utilisateur du VEC mise à jour où les modifications ne se chargeaient pas lors du changement d’expérience dans une activité de ciblage d’expérience (XT). Les clients ne pouvaient pas modifier les expériences au-delà de celle qu’ils avaient saisie initialement et le bouton [!UICONTROL Cancel] était manquant ou ne répondait pas. Ce correctif garantit que les modifications se chargent désormais correctement sur toutes les expériences et que le bouton [!UICONTROL Cancel] fonctionne de manière fiable, même sans l’extension d’assistance, améliorant les workflows de modification et réduisant la frustration. (TGT-53256)
* **Correction d’un problème d’écran blanc lors du changement entre plusieurs expériences dans le processus de création d’activités** : correction d’un problème en raison duquel le changement entre plusieurs expériences provoquait un écran blanc. Correction également d’un problème dans le processus de création d’activités en raison duquel les clients et clientes rencontraient un écran blanc lorsqu’ils tentaient de modifier plusieurs expériences au sein d’une activité. Ce problème se produisait après l’application des modifications à deux expériences, puis la sélection d’une troisième expérience, ce qui empêchait d’autres modifications. La mise à jour assure des transitions fluides entre les expériences, ce qui permet aux clients d’apporter des modifications sans interruption. (TGT-53266)
* **Correction d’un problème dans le VEC en raison duquel les modifications de code personnalisé n’étaient pas enregistrées de manière fiable dans les sessions de modification** : correction d’un problème en raison duquel les modifications de code personnalisé effectuées dans le compositeur d’expérience visuelle (VEC) n’étaient pas enregistrées de manière fiable en une seule tentative. Les clients ont signalé que des modifications, telles que des mises à jour de style ou des modifications d’HTML, manquaient par intermittence sur le site web et dans les URL d’assurance qualité, même après avoir utilisé les boutons [!UICONTROL Edit Content] et [!UICONTROL Save] final. Cette régression a été résolue, en veillant à ce que toutes les modifications du code personnalisé persistent comme prévu entre les sessions de modification.** (TGT-53418)
* **Correction d’un `triggerViews` manquant dans l’interface utilisateur mise à jour lors de la création de l’activité** : correction d’un problème dans le processus de création d’activités où les `triggerViews` n’apparaissaient pas dans l’interface utilisateur mise à jour, même si elles étaient correctement implémentées sur la page. Cela affectait plusieurs clients et rendait difficile la validation des déclencheurs basés sur les vues lors de la configuration de l’activité. Les `TriggerViews` s’affichent désormais comme prévu, ce qui permet aux clients de terminer et de tester leurs configurations de manière fiable. (TGT-53239)
* **Correction d’un problème de chargement des vues dans le processus de création d’activités pour des pages web spécifiques dans l’interface utilisateur mise à jour** : correction d’un problème dans le processus de création d’activités en raison duquel les vues ne se chargeaient pas dans l’interface utilisateur mise à jour pour des pages web spécifiques, bien qu’elles aient été correctement implémentées et visibles dans les appels de diffusion ou d’interaction. Cela affectait plusieurs clients et clientes et rendait difficile la validation du ciblage basé sur les vues. Les vues sont désormais renseignées de manière cohérente sur les pages prises en charge, ce qui améliore la fiabilité lors de la configuration des activités. (TGT-53246)
* **Correction d’un problème de chargement des vues intermittentes dans le processus de création d’activités dans l’interface utilisateur mise à jour** : correction d’un problème dans le processus de création d’activités où les vues ne s’affichaient pas par intermittence dans l’interface utilisateur mise à jour lors de la modification des activités. Bien que le nom d’affichage correct était présent dans la payload du réseau, il n’était pas reconnu de manière cohérente dans l’interface, ce qui affectait la capacité des clients à configurer la personnalisation basée sur les vues. Les vues apparaissent désormais de manière fiable, ce qui facilite la configuration et les workflows de validation. (TGT-53223)
* **Correction d’un problème dans le processus de création d’activités, en raison duquel les noms des actions suivies n’étaient pas enregistrés dans l’interface utilisateur mise à jour** : correction d’un problème dans le processus de création d’activités, en raison duquel les mesures des actions suivies ne pouvaient pas être enregistrées dans l’interface utilisateur mise à jour. Après avoir nommé un élément suivi et enregistré l’activité, le nom est réinitialisé à un libellé par défaut lors de la réouverture, ce qui entraîne une confusion et perturbe la configuration des objectifs. Les actions suivies conservent désormais leurs noms attribués, ce qui permet aux clients de définir et de gérer avec précision les mesures de conversion. (TGT-53453)

+++

## [!DNL Target Standard/Premium] 25.8.1 (7 août 2025)

Cette version comprend les améliorations et correctifs suivants :

**Activités**

+++Afficher les détails
* Correction de plusieurs problèmes liés à l’interface utilisateur mise à jour, notamment des erreurs lors de la suppression de types de page en raison de l’espacement des valeurs d’entrée, d’une copie d’activité non fiable entre les espaces de travail et d’un dysfonctionnement des règles de diffusion de page dans les environnements d’assurance qualité. (TGT-52703)
* Correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour en raison duquel les utilisateurs dotés du rôle [!UICONTROL Editor] pouvaient accéder aux activités en direct et tenter de les modifier, ce qui devait être limité. Les écrans de liste et d’aperçu des activités n’affichaient pas correctement les options de modification des activités en direct, ce qui entraînait des modifications involontaires potentielles. (TGT-53055)
* Correction d’un problème dans l’interface utilisateur de [!UICONTROL Advanced Search] en raison duquel la sélection des opérateurs « valeur présente » ou « valeur absente » invitait les utilisateurs à saisir un opérande, qui n’était pas obligatoire pour ces conditions. (TGT-51961)
* Correction d’un problème dans l’interface utilisateur mise à jour en raison duquel les tentatives de copie des activités de l’espace de travail d’évaluation vers l’espace de travail de production échouaient systématiquement, même dans les environnements sandbox. Les clients ont rencontré divers messages d’erreur, notamment « Audience anonyme déjà utilisée par l’activité » et « Identifiant d’audience non valide », même s’ils utilisaient des configurations valides et disposaient des autorisations d’espace de travail appropriées. (TGT-52394)

+++

**Fragments d’expérience (XF)**

+++Afficher les détails
* Correction d’un problème en raison duquel le rendu du contenu du fragment d’expérience (XF) échouait dans l’aperçu du [!UICONTROL Visual Experience Composer] (VEC), malgré le fonctionnement correct dans la diffusion de contenu. (TGT-53318)

+++

**Localisation**

+++Afficher les détails
* Correction d’un problème de localisation en raison duquel le bouton « Ajouter une promotion » de la section « Promotions » apparaissait non localisé dans plusieurs environnements linguistiques dans le client d’assurance qualité. (TGT-53263)

+++

**Offres**

+++Afficher les détails
* Correction d’un problème en raison duquel la modification d’une offre HTML existante via le Compositeur d’expérience visuelle (VEC) entraînait la suppression de toutes les modifications de la diffusion de contenu. Les modifications apparaissent grisées dans l’onglet de modification et ne sont pas répercutées dans les aperçus de l’assurance qualité, bien qu’elles aient été correctement appliquées dans l’interface utilisateur héritée. (TGT-52863)
* Correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour en raison duquel les modifications d’offre HTML effectuées dans le [!UICONTROL Visual Experience Composer] (VEC) ne persistaient pas après avoir repassé de l’onglet [!UICONTROL Targeting] à [!UICONTROL Experiences]. (TGT-52874)
* Correction d’un problème dans l’interface utilisateur [!DNL Target] mise à jour en raison duquel l’insertion d’une offre HTML avant et d’une autre après le même sélecteur provoquait une génération d’emplacement incorrecte. Lorsque les clients sont revenus de l’onglet [!UICONTROL Targeting] à l’onglet [!UICONTROL Experience] , un seul sélecteur a été conservé, ce qui a entraîné la perte des modifications et l’interruption de la diffusion de contenu. Ce comportement était différent de celui de l’interface utilisateur héritée, qui conservait correctement les deux modifications avec des identifiants d’emplacement distincts. (TGT-52891)
* Correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour, en raison duquel le fait de cliquer sur une offre ajoutée dans le rail de [!UICONTROL Modifications] entraînait l’affichage et la disparition intermittents du panneau de [!UICONTROL Configuration] de droite, ce qui rendait difficile l’interaction avec les paramètres de l’offre. (TGT-53288)
* Correction d’un problème où les offres d’HTML ajoutées à des variations spécifiques à l’audience dans une activité n’étaient pas systématiquement enregistrées ou affichées dans la section de modification. Après avoir basculé entre les audiences lors de la modification, les offres précédemment appliquées disparaissaient parfois ou ne s’affichaient pas, ce qui perturbait la validation et retardait la préparation de l’activité. (TGT-53440)
* Correction d’un problème en raison duquel la copie d’une activité qui incluait des offres entraînait la création d’offres en double dans la nouvelle activité. Ce comportement entraînait un encombrement et une confusion inutiles, en particulier lors du déplacement d’activités entre les espaces de travail. Le correctif garantit que [!DNL Target] offres sont désormais correctement copiées dans l’espace de travail de destination sans duplication, ce qui permet de rationaliser la gestion des activités et d’améliorer l’efficacité des workflows. (TGT-53454)

+++

**Applications monopages (SPA)**

+++Afficher les détails
* Correction d’un problème dans le VEC mis à jour qui empêchait les clients et clientes d’appliquer des modifications aux vues [!UICONTROL Single Page Application] (SPA). Bien que les activités créées dans l’ancienne interface utilisateur prenaient en charge le ciblage spécifique des vues, la nouvelle interface utilisateur n’a pas réussi à détecter ou à autoriser les modifications de ces vues, et les commandes de changement de vue sont apparues désactivées. (TGT-52556)

+++

**Compositeur d’expérience visuelle**

+++Afficher les détails
* Correction d’un problème en raison duquel les modifications apportées aux expériences dans le [!UICONTROL Visual Experience Composer] n’étaient pas visibles ou s’affichaient de manière incohérente dans l’interface utilisateur. (TGT-TGT-53381)
* Correction d’un problème dans le VEC mis à jour en raison duquel la section [!UICONTROL Manage Content] n’affichait pas de texte secondaire pour les miniatures d’expérience. Ce problème rendait difficile l’identification des documents pour les utilisateurs et les utilisatrices, en particulier lorsque les noms de fichier étaient longs ou tronqués. (TGT-52291)
* Correction d’une erreur en raison de laquelle les clients rencontraient des erreurs de validation incorrectes lors de la configuration des règles [!UICONTROL page delivery] dans les activités du compositeur d’expérience visuelle. En particulier, les opérateurs tels que « est égal à n’importe lequel » et « n’est égal à aucun de » déclenchent une « entrée non valide pour le type d’opérateur » lors de la saisie de valeurs de texte, même si le texte doit être pris en charge. (TGT-52629)
* Correction de plusieurs problèmes qui provoquaient un comportement incohérent dans le panneau [!UICONTROL Modifications] de l’interface utilisateur mise à jour lors de la sélection des offres à l’aide du bouton « Sélectionner une offre ». Au lieu de remplacer l’offre existante, l’interface utilisateur a ajouté un doublon et a tenté d’interagir avec l’une ou l’autre des offres, ce qui a entraîné des erreurs de console, telles que `selectorNotFound`. De plus, certaines offres n’affichent pas le bouton « Sélectionner une offre », affichant uniquement les propriétés modifiables. (TGT-53321)
* Correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour en raison duquel les modifications de code HTML effectuées lors de la configuration de l’activité ne persistaient pas sur les pages de variation, même si elles étaient correctement enregistrées pour les populations témoins. Malgré plusieurs tentatives et la recréation de tests sans regroupements de pages, les pages de variation ne conservaient jamais les modifications, ce qui affectait la diffusion du contenu et la validation de l’assurance qualité. (TGT-53436)
* Correction d’un problème dans le VEC mis à jour en raison duquel l’opérateur « égal à n’importe lequel » dans les règles de diffusion de page n’acceptait pas les valeurs d’entrée. Lors de la configuration des paramètres client dans toutes les mbox, la sélection de cet opérateur entraînait une erreur « Entrée non valide », empêchant la création de la règle. (TGT-52623)

+++

**Workspaces**

+++Afficher les détails
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
