---
keywords: notes de mise à jour;versions;mises à jour;futures versions;améliorations;nouvelles fonctionnalités;correctifs;mises à jour;version préliminaire;accès anticipé
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version dʼ [!DNL Target], notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version de [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 95d8bd994ffdb1d256b7eb0aea1a2462b40ce530
workflow-type: tm+mt
source-wordcount: '2221'
ht-degree: 7%

---

# Notes de mise à jour de [!DNL Target] (version préliminaire)

Cet article contient des informations sur les prochaines versions d’[!DNL Adobe Target], y compris les SDK, les API et les bibliothèques JavaScript.

**Dernière mise à jour : 21 août 2025**

>[!NOTE]
>
>* Les dates de publication, fonctions et autres informations peuvent changer sans préavis. Les informations de cet article sont mises à jour fréquemment, en particulier avant les versions .
>
>* Pour afficher des informations sur la version actuelle, voir [ Notes de mise à jour de Target ](release-notes.md).
>
>* Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.8.3 (21 août 2025)

Cette version comprend les mises à jour et correctifs suivants :

**[!UICONTROL Activities]**

+++Afficher les détails
* **Correction d’un problème où l’enregistrement des activités déclenchait une erreur d’entrée utilisateur non valide en raison de données de propriété incorrectes** : les clients et clientes rencontraient une erreur critique lors de la tentative d’enregistrement des activités existantes. Le message d’erreur indiquait une entrée utilisateur non valide, faisant spécifiquement référence à un contenu de nom de propriété non reconnu dans la payload JSON. Notamment, les nouvelles activités utilisant la même propriété ont été enregistrées avec succès, ce qui suggère que le problème a été isolé des données d’activité héritées. Le processus de création d’activités gère désormais correctement les configurations de propriété héritées, ce qui évite les erreurs d’entrée non valides et garantit un comportement d’enregistrement cohérent entre les activités nouvelles et existantes. (TGT-53507)
* **Correction d’un problème qui empêchait les clients d’enregistrer une activité en raison d’une erreur InvalidProperty.Json** : les clients rencontraient une erreur lorsqu’ils tentaient d’enregistrer une activité dans l’interface utilisateur mise à jour, même sans apporter de modifications. Le message d’erreur indique une structure JSON non valide : « JSON non valide. Nom de propriété « content » non reconnu. Emplacement : ligne - 1, colonne - 432. » Ce problème était dû à une propriété non reconnue dans la payload de requête et a été résolu. Les clients peuvent enregistrer les activités sans rencontrer cette erreur. (TGT-53513)
* **Correction d’un problème en raison duquel les activités planifiées affichaient incorrectement un statut [!UICONTROL Live] jusqu’à l’actualisation de la page** : les clients et clientes ont observé que lors de la planification d’une activité pour une activation à une date et une heure futures, le statut s’affichait immédiatement comme [!UICONTROL Live] au lieu de [!UICONTROL Scheduled]. Cela a semé la confusion, même si le message de confirmation indiquait correctement que l’activité était planifiée. Actualiser la page a corrigé l’affichage du statut. Ce problème a été résolu et les activités planifiées affichent correctement le statut Planifié sans qu’une actualisation soit nécessaire. (TGT-52937)

+++

**[!UICONTROL Analytics for Target](A4T)**

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
* **Correction d’un chargement incohérent des images dans[!UICONTROL Catalog Search]** : correction d’un problème en raison duquel les miniatures et les images dans [!UICONTROL  Catalog Search] ne se chargeaient pas de manière cohérente dans le processus de création d’activités. Les images ne s’affichaient pas, sauf si la colonne « URL de la miniature » était visible et que certaines images de produit étaient partiellement chargées ou pas du tout après des actions de navigation ou de recherche. Le comportement de chargement des images est stabilisé et les miniatures s’affichent désormais de manière fiable, quelle que soit la visibilité des colonnes ou les actions de navigation. (TGT-52778)
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

**[!UICONTROL Visual Experience Composer](VEC)**

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

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
