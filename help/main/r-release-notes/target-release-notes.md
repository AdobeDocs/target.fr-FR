---
keywords: notes de mise à jour;versions;mises à jour;futures versions;améliorations;nouvelles fonctionnalités;correctifs;mises à jour;version préliminaire;accès anticipé
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version dʼ [!DNL Target], notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version de [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: be371f3631d79c65c632a23776ab08de21b031eb
workflow-type: tm+mt
source-wordcount: '2610'
ht-degree: 7%

---

# Notes de mise à jour de [!DNL Target] (version préliminaire)

Cet article contient des informations sur les prochaines versions d’[!DNL Adobe Target], y compris les SDK, les API et les bibliothèques JavaScript.

**Dernière mise à jour : 27 août 2025**

>[!NOTE]
>
>* Les dates de publication, fonctions et autres informations peuvent changer sans préavis. Les informations de cet article sont mises à jour fréquemment, en particulier avant les versions .
>
>* Pour afficher des informations sur la version actuelle, voir [ Notes de mise à jour de Target ](release-notes.md).
>
>* Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.8.4 (28 août 2025)

Cette version comprend les mises à jour et correctifs suivants :

**[!UICONTROL Activities]**

+++Afficher les détails
* **Correction d’un problème en raison duquel les activités planifiées affichaient incorrectement un statut « [!UICONTROL Live] » dans l’interface utilisateur mise à jour au cours du processus de création d’activités** : les activités avec des dates d’activation ultérieures affichent désormais correctement un statut « [!UICONTROL Scheduled] ». (TGT-53187)
* **Les activités planifiées affichaient incorrectement un statut [!UICONTROL Live] jusqu’à l’actualisation de la page** : les clients ont signalé que lors de la planification d’une activité pour une activation à une date et une heure futures, le statut s’affichait initialement comme [!UICONTROL Live] au lieu de [!UICONTROL Scheduled]. Cela entraînait une confusion malgré le message de confirmation indiquant le comportement correct de la planification. Le statut de l’activité reflète désormais précisément les [!UICONTROL Scheduled] immédiatement après l’enregistrement, sans nécessiter d’actualisation de page. (TGT-52937)
* **Les modifications apportées aux expériences dupliquées ont involontairement affecté l’expérience originale** : les clients et clientes ont signalé que lors de la duplication d’une expérience dans une activité et de l’affectation d’une nouvelle audience, toute modification apportée à l’expérience dupliquée, telle que la conception ou les critères, était également répercutée dans l’expérience originale. Cela empêchait la création de variations indépendantes et affectait les workflows de production. Les expériences dupliquées peuvent désormais être modifiées indépendamment sans affecter la version d’origine. (TGT-53361)
* **Correction d’un problème qui empêchait les clients et clientes d’enregistrer une activité en raison d’une erreur `InvalidProperty.Json`** : auparavant, les clients et clientes rencontraient une erreur « Entrée utilisateur non valide » lorsqu’ils tentaient d’enregistrer une activité sans apporter de modifications. L’erreur est due à un nom de propriété « content » non reconnu dans la payload JSON. Ce problème a été résolu, et les activités peuvent désormais être enregistrées dans l’interface utilisateur mise à jour, même si aucune modification n’est apportée. (TGT-53513)

+++

**Analytics for Target (A4T)**

+++Afficher les détails
* **Impossible de saisir les noms des suites de rapports lors de la création d’activités A4T** : les clients n’ont pas pu saisir du texte dans la liste déroulante [!UICONTROL Report Suite] lors de la sélection de [!UICONTROL Analytics] comme source de création de rapports dans l’interface utilisateur mise à jour.  Ce problème rendait difficile la localisation de suites de rapports spécifiques, en particulier pour les organisations disposant de listes volumineuses. La liste déroulante prend désormais en charge la saisie et la recherche par nom, ce qui améliore l’efficacité du processus de création d’activités. (TGT-53345)

+++

**[!UICONTROL Audiences]**

+++Afficher les détails
* **Les audiences « Période » expirées bloquaient l’enregistrement de l’activité même après la suppression** : auparavant, les clients ne pouvaient pas enregistrer une activité si elle avait précédemment inclus une audience « Période » expirée, même après la suppression de cette audience. Ce problème était dû à une validation persistante sur l’audience d’activité seule, qui a continué à déclencher des erreurs. Les activités peuvent désormais être enregistrées comme prévu une fois les audiences expirées supprimées. (TGT-53517)
* **Des pages supplémentaires et plusieurs audiences ont disparu après l’enregistrement d’une activité** : auparavant, les clients et clientes qui créaient une activité [!UICONTROL A/B Test] dans le processus de création d’activité perdaient des pages supplémentaires configurées et plusieurs audiences après l’enregistrement. Ce comportement était inattendu et a provoqué une confusion lors de la configuration. Ces configurations persistent désormais correctement après l’enregistrement de l’activité. (TGT-52357)

+++

**Offres de décision**

+++Afficher les détails
* **Impossible de modifier les offres de décision ou de sélectionner des éléments de page spécifiques dans le VEC mis à jour** : les clients et clientes ont rencontré plusieurs problèmes dans l’interface utilisateur mise à jour qui ont bloqué leur capacité à mettre à jour les activités existantes ou à en créer de nouvelles :

   * Les offres de décision s’affichaient incorrectement en tant qu’offres HTML, empêchant les modifications.
   * Des éléments de page spécifiques n’ont pas pu être sélectionnés dans le VEC.
   * Les modifications apportées lors de la modification n’ont pas été enregistrées.
   * Certaines URL régionales n’ont pas pu se charger correctement dans le VEC, ce qui nécessite des ajustements manuels des cookies.

  Les clients peuvent désormais modifier les offres de décision, sélectionner les éléments de page avec précision et enregistrer les modifications comme prévu. Les pages régionales se chargent également correctement dans le VEC. (TGT-53425)

* **Les sélecteurs de décision d’offre n’ont pas pu être modifiés et changés de manière inattendue après l’enregistrement** : les clients ont signalé que lors de l’application de décisions d’offre dans l’interface utilisateur mise à jour, le sélecteur ne pouvait pas être modifié à partir de sa valeur par défaut. Les tentatives de modification du sélecteur (par exemple, en `#tf-cq-hr or body`) ont été ignorées et, après avoir enregistré l’activité, le sélecteur a été remplacé par une valeur générique telle que `#cdq_element_0`. Ce problème entraînait la disparition de l’offre du compositeur d’expérience visuelle (VEC) et bloquait d’autres modifications. Les clients peuvent désormais modifier les sélecteurs de décision d’offre comme prévu et les sélecteurs enregistrés persistent correctement sans modifications inattendues. (TGT-53433)
* **Les décisions d’offre ont disparu des activités après l’enregistrement** : les clients ont signalé que les décisions d’offre appliquées aux éléments de page dans l’interface utilisateur mise à jour n’étaient plus visibles après l’enregistrement de l’activité. Dans certains cas, le sélecteur a été modifié de manière inattendue et le rendu de l’offre a échoué dans le compositeur d’expérience visuelle lors de la modification. Les décisions d’offres persistent désormais correctement après l’enregistrement et les sélecteurs restent stables, ce qui garantit que les offres sont visibles et modifiables comme prévu. (TGT-53434)

+++

**Fragments d’expérience**

+++Afficher les détails
* **Les clients ont reçu une erreur lors de l’insertion de [!UICONTROL Experience Fragments] à l’aide de [!UICONTROL Insert Before] ou[!UICONTROL Insert After]** : les clients ont rencontré une erreur lors de leur tentative d’insertion de [!UICONTROL Experience Fragments] dans une activité à l’aide des options [!UICONTROL Insert Before] ou [!UICONTROL Insert After] de l’interface utilisateur mise à jour. Le message d’erreur affiché était :

  « Le contenu de l’offre doit contenir exactement un élément HTML. »

  Ce problème était spécifique à l’interface utilisateur mise à jour et ne se produisait pas dans la version précédente. Elle a maintenant été résolue et les clients peuvent insérer des [!UICONTROL Experience Fragments] sans rencontrer cette erreur. (TGT-53432)

* **Message d’erreur lors de l’ajout d’un [!UICONTROL Experience Fragment] à une activité** : précédemment, les clients et les clientes qui tentaient d’insérer un [!UICONTROL Experience Fragment] à l’aide de l’option [!UICONTROL Insert Before] ou [!UICONTROL Insert After] rencontraient l’erreur : « Le contenu de l’offre doit contenir exactement un élément HTML. » Cette erreur s’est produite malgré la validité du fragment et son acceptation dans l’interface utilisateur héritée, qui incluait un bouton bascule pour prendre en charge cette configuration. Le problème a été résolu dans le compositeur d’expérience visuelle mis à jour. (TGT-53442)

+++

**Localisation**

+++Afficher les détails
* **Les messages toast de l’étape [!UICONTROL Goals & Settings] n’étaient pas localisés** : auparavant, les clients rencontraient un message toast non localisé lors de la saisie de caractères non pris en charge, tels que des émoticônes, dans le champ [!UICONTROL Objective] pendant le processus de création d’activité. Les messages Toast sont désormais correctement localisés dans toutes les langues prises en charge, ce qui garantit une expérience cohérente et accessible aux clients du monde entier. (TGT-52251)
* **Une chaîne de la boîte de dialogue [!UICONTROL Create Audience] n’a pas été localisée** : auparavant, le message « Choisir au moins une date de début ou de fin pour « ne se répète pas » s’affichait non localisé dans la boîte de dialogue modale [!UICONTROL Create Audience] lors de la configuration des attributs de période. La chaîne est désormais correctement localisée dans toutes les langues prises en charge, ce qui garantit une expérience cohérente pour les clients globaux dans le workflow [!UICONTROL Audiences]. (TGT-52253)
* **L’info-bulle de la boîte de dialogue [!UICONTROL Create Audience] n’était pas localisée** : auparavant, lorsque les clients pointaient sur l’info-bulle d’erreur après avoir saisi des caractères non pris en charge, tels que des émoticônes, dans le champ nom de l’audience, l’info-bulle s’affichait non localisée. L’info-bulle affiche désormais un message correctement localisé dans toutes les langues prises en charge, ce qui garantit une expérience cohérente et accessible dans le workflow de [!UICONTROL Audiences]. (TGT-52254)

+++

**[!DNL Recommendations]**

+++Afficher les détails
* **Impossible de désactiver les [!UICONTROL Front Promotion] dans les activités dynamiques** : correction d’un problème en raison duquel les clients et clientes ne pouvaient pas désactiver les [!UICONTROL Front Promotion] dans les activités dynamiques à l’aide de l’interface utilisateur mise à jour. Les modifications apportées à la section de promotion au cours du processus de création d’activités persistent désormais comme prévu, garantissant ainsi une configuration précise des activités en direct dans [!UICONTROL Product Catalog Search]. (TGT-53231)
* **La modification de la recommandation d’une expérience dupliquée a eu un impact sur l’expérience d’origine** : les clients ont signalé que lors de la duplication d’une expérience dans une activité et de la modification de la conception de recommandation ou des critères dans le doublon, ces modifications ont été involontairement appliquées à l’expérience d’origine.  Ce problème empêchait la création de variations indépendantes et perturbait le comportement attendu dans le processus de création d’activités mis à jour. Les expériences dupliquées peuvent désormais être modifiées indépendamment sans affecter la version d’origine. (TGT-53369)
* **Impossible d’afficher la liste de produits lors de la modification d’une collection ou d’une exclusion dans l’onglet [!UICONTROL Recommendations]** Auparavant, la liste de produits filtrée par les règles appliquées n’était pas visible dans la boîte de dialogue modale de modification, ce qui rendait difficile pour les clients de confirmer quels produits étaient inclus ou exclus. La liste des produits s’affiche désormais correctement et est mise à jour en temps réel à mesure que les règles sont modifiées, ce qui améliore la visibilité et la convivialité dans l’interface utilisateur de [!DNL Recommendations] mise à jour. (TGT-53481)
* **Mise à jour de la disposition de la boîte de dialogue [!UICONTROL View Details] dans l’onglet [!UICONTROL Recommendations]** : auparavant, la boîte de dialogue [!UICONTROL View Details] n’avait pas de structure claire, ce qui rendait difficile pour les clients l’accès aux informations spécifiques à l’article et liées au stock. La mise en page a été mise à jour afin d’inclure deux onglets : un onglet affiche les détails de l’élément sélectionné et le second affiche l’inventaire filtré par les règles actuelles de la collection ou de l’exclusion. Cette amélioration améliore la clarté et la convivialité de l’interface utilisateur de [!DNL Recommendations] mise à jour. (TGT-53503)
* **Les clients ne pouvaient pas rechercher de suites de rapports dans la liste déroulante [!UICONTROL Goals & Settings]** : auparavant, la liste déroulante des suites de rapports de la section [!UICONTROL Goals & Settings] du processus de création d’activités ne prenait pas en charge la saisie de texte pour la recherche, ce qui rendait difficile, pour les clients disposant d’un grand nombre de suites de rapports, la recherche de la bonne. Cette fonctionnalité, disponible dans l’interface utilisateur héritée, a été restaurée. Les clients peuvent désormais saisir du texte pour rechercher et sélectionner des suites de rapports plus efficacement. (TGT-53514)
* **Les clients ne peuvent pas télécharger le fichier CSV de critères personnalisés dans l’interface utilisateur de [!DNL Recommendations]** : auparavant, le fait de cliquer sur le lien de téléchargement pour les fichiers CSV de critères personnalisés dans l’onglet [!UICONTROL Recommendations] renvoyait une erreur 404 et ne parvenait pas à s’ouvrir dans un nouvel onglet. Le lien de téléchargement s’ouvre désormais dans un nouvel onglet et diffuse correctement le fichier CSV, ce qui améliore l’accessibilité et la convivialité pour les clients qui gèrent des critères personnalisés. (TGT-51966)
* **L’activation d’une promotion [!UICONTROL Recommendations] sans données d’entrée déclenchait un message d’erreur générique**  : auparavant, les clients qui activaient une promotion front ou back dans une activité Recommendations sans spécifier les champs requis rencontraient une vague « erreur d’entrée non valide » avec le code `error.restapi.missingFields`. Le système fournit désormais un message d’erreur clair et exploitable qui indique quels champs sont manquants, ce qui améliore la convivialité et réduit la confusion pendant le processus de création d’activité. (TGT-52616)
* **Les miniatures et images de produit ne se chargeaient pas de manière cohérente dans[!UICONTROL Catalog Search]** : les clients ont signalé que les miniatures de produit et les images en taille réelle dans [!UICONTROL Catalog Search] étaient manquantes ou endommagées par intermittence, en particulier après avoir parcouru la colonne ou modifié sa visibilité. Le chargement des miniatures et des images est désormais fiable, quels que soient les paramètres de colonne ou le comportement de navigation, ce qui améliore l’expérience globale dans le workflow de [!UICONTROL Recommendations]. (TGT-52778)
* **Impossible de créer des [!UICONTROL Designs] et des [!UICONTROL Criteria] dans l’environnement [!UICONTROL Stage]** : les clients et clientes ont rencontré une erreur « Entrée utilisateur non valide » lors de la tentative de création de [!UICONTROL Designs] ou de [!UICONTROL Criteria] dans l’onglet [!UICONTROL Recommendations] de l’environnement [!UICONTROL Stage]. Les clients peuvent désormais créer des [!UICONTROL Designs] et des [!UICONTROL Criteria] sans erreur dans l’environnement [!UICONTROL Stage]. (TGT-53205)
* **[!UICONTROL Promotions]n’ont pas été supprimés des activités [!UICONTROL Recommendations] après l’enregistrement** : les clients ont signalé que les promotions ajoutées à [!DNL Recommendation] activités continuaient à apparaître même après avoir été supprimées et enregistrées. Ce problème affectait les environnements d’évaluation et de production et persistait lors de plusieurs tentatives d’enregistrement. Les promotions reflètent désormais correctement les modifications apportées lors de la modification des activités dans le processus de création d’activités mis à jour. (TGT-53490)

+++

**[!UICONTROL Reports]**

+++Afficher les détails
* **[!UICONTROL Automated Segments]a affiché une audience null dans les rapports d’activité** : les clients ont observé que lors de l’affichage de [!UICONTROL Automated Segments] dans la section [!UICONTROL Reports] d’une activité, le champ d’audience s’affichait comme nul, même si des données de segment valides étaient attendues. Ce problème affectait la visibilité du ciblage des audiences et la précision des rapports. [!UICONTROL Automated Segments] désormais afficher correctement les informations d’audience associées dans les rapports d’activité. (TGT-52793)
* **Échec du téléchargement des rapports d’activité au format CSV** : les clients et clientes qui tentaient d’exporter les rapports d’activité à partir de l’onglet [!UICONTROL Reports] ont rencontré un échec lors de la sélection de l’option de téléchargement CSV. Ce problème affectait à la fois les rapports standard et les exportations de détails de commande. Les rapports sont désormais correctement téléchargés au format CSV. (TGT-53464)

+++

**Applications monopages (SPA)**

+++Afficher les détails
* **Le passage entre les modes [!UICONTROL Browse] et [!UICONTROL Design] réinitialise les états des applications monopages (SPA) dans l’éditeur web** : les clients ont signalé que le passage entre les modes [!UICONTROL Browse] et [!UICONTROL Design] dans le compositeur d’expérience visuelle entraînait le rechargement de l’éditeur web, la réinitialisation de l’état de la SPA et l’interruption du processus de création d’activité. L’éditeur conserve désormais l’état de navigation de la SPA lors du changement de mode, ce qui garantit une expérience de modification plus fluide et plus cohérente. (TGT-53074)

+++

**[!UICONTROL Visual Experience Composer (VEC)]**

+++Afficher les détails
* **Le changement de nom d’un emplacement dans une activité [!UICONTROL Automated Personalization] (AP) ou [!UICONTROL Multivariate Test] (MVT) n’a pas persisté après avoir accédé à l’étape [!UICONTROL Targeting] et être revenu.** clients peuvent désormais modifier et enregistrer les noms des emplacements. Les modifications restent visibles tout au long du processus de création d’activités. (TGT-52367)
* **L’interface utilisateur du compositeur d’expérience visuelle hérité s’affichait sur les clients dans l’environnement [!UICONTROL Stage]** : correction d’un problème lors de l’accès à certains clients dans l’environnement [!UICONTROL Stage] qui s’affichaient incorrectement dans l’interface utilisateur héritée au lieu du compositeur d’expérience visuelle mis à jour. Ce problème était reproductible sur plusieurs chemins de connexion et affectait la section [!UICONTROL Activities]. L’interface utilisateur mise à jour s’affiche désormais correctement pour les deux clients dans l’environnement [!UICONTROL Stage]. (TGT-52261)
* **La sélection d’une couleur d’arrière-plan entraînait le blocage de la page dans le VEC mis à jour** :
Correction d’un problème en raison duquel la sélection d’une couleur d’arrière-plan dans le panneau d’[!UICONTROL Style] du VEC mis à jour entraînait le blocage de la page et son virement. Les erreurs de console ont indiqué une échec de lecture des propriétés à partir d’un élément non défini, spécifiquement lié à `querySelector`. Les clients peuvent désormais sélectionner en toute sécurité des couleurs de fond sans déclencher de blocage. (TGT-53561)
* **Les activités n’ont pas pu être enregistrées en raison d’une erreur d’entrée utilisateur non valide** : correction d’une erreur lors de la tentative d’enregistrement d’activités existantes dans le VEC mis à jour. L’erreur s’est affichée uniquement lors des modifications, et non lors de la création de nouvelles activités avec la même propriété. Le message d’erreur incluait :

  `Invalid Json. Unrecognized property name 'content'. Location: line - 1, column - 432.`

  Les activités qui utilisent la propriété concernée peuvent désormais être enregistrées après modification. (TGT-53507)

* **Les images transparentes n’incluaient plus le paramètre « fmt=png-alpha » dans le VEC mis à jour** : les clients ont signalé que lors du remplacement des images dans l’interface utilisateur mise à jour, les arrière-plans transparents n’étaient plus conservés. Les URL d’image générées par le VEC mis à jour ont omis le paramètre `fmt=png-alpha`, qui assurait auparavant la transparence dans l’ancienne interface utilisateur. L’interface utilisateur mise à jour ajoute désormais correctement le paramètre `fmt=png-alpha` pour les images transparentes, ce qui restaure le comportement de rendu attendu. (TGT-52615)
* **Les clients ne pouvaient pas accéder à la section de ciblage dans les activités AP sans ajouter deux emplacements** : les clients créant des activités [!UICONTROL Automated Personalization] (AP) dans l’interface utilisateur mise à jour ne pouvaient pas accéder à la section de ciblage, sauf si deux emplacements ont été ajoutés. Ce comportement différait de celui de l’interface utilisateur précédente, où un seul emplacement suffisait. Le problème a bloqué la création et l’enregistrement d’activités pour les clients qui préféraient utiliser un seul emplacement. Les clients peuvent maintenant passer au ciblage et enregistrer les activités AP avec un seul emplacement, restaurant ainsi les fonctionnalités attendues. (TGT-53426)
* **Offres HTML dupliquées dans l’espace de travail lors du changement d’expérience** : précédemment, les clients insérant des offres HTML dans du contenu dupliqué expérimenté dans l’espace de travail après avoir basculé entre les expériences. Ce problème empêchait également le défilement de l’espace de travail, ce qui affectait la convivialité. HTML Offres ne se duplique plus et l’espace de travail reste défilable lors du changement d’expérience dans le VEC mis à jour. (TGT-53487)
* **La mise à jour manuelle d’un sélecteur CSS a provoqué l’apparition d’un écran vide dans le VEC** : les clients et clientes ont signalé que lors de la modification d’une offre dans le VEC, la mise à jour manuelle du sélecteur CSS a déclenché un écran vide, même si le sélecteur était valide et présent sur la page. L’écran du compositeur d’expérience visuelle reste désormais stable lorsque les sélecteurs sont mis à jour manuellement pendant le processus de création d’activité. (TGT-53553)
* **Problème de troncature dans le champ Date de début lors de la sélection de la « date et l’heure spécifiées » dans[!UICONTROL Goals & Settings]** : les clients ont rencontré un problème de troncature dans le champ [!DNL Start date] lors de la sélection de l’option date et heure spécifiées dans la section durée de la page [!UICONTROL Goals & Settings] lors de la création de l’activité. La date et l’heure complètes s’affichent désormais correctement dans les paramètres régionaux pris en charge. (TGT-47843)
* **L’icône de filtre a disparu lors de la réduction du navigateur dans le rail de [!UICONTROL Manage Content]** : les clients et clientes ont signalé que l’icône de filtre dans le rail de [!UICONTROL Manage Content] du flux de création d’activité de [!UICONTROL Automated Personalization] a disparu lorsque la fenêtre du navigateur a été redimensionnée ou réduite. L’icône de filtre reste désormais visible et accessible quelle que soit la taille du navigateur, ce qui améliore la convivialité entre les résolutions d’écran. (TGT-51449)

+++

**[!UICONTROL Workspaces]**

+++Afficher les détails
* **Les clients limités à un seul espace de travail pouvaient afficher les activités d’autres espaces de travail** : les clients dont l’accès était limité à un espace de travail spécifique pouvaient toujours sélectionner des [!UICONTROL All Workspaces] dans l’interface utilisateur mise à jour et afficher les activités d’autres espaces de travail. Ce comportement entraînait un risque de modifications involontaires des activités en direct qui n’étaient pas de leur ressort. Les restrictions de Workspace sont désormais correctement appliquées et les clients ne peuvent afficher les activités que dans l’espace de travail qui leur est affecté. (TGT-53101)
* **Les clients pouvaient afficher les activités du [!UICONTROL Default Workspace] sans accès** : les clients pouvaient afficher les activités du [!UICONTROL Default Workspace] sans y avoir accès. Les autorisations Workspace sont désormais correctement appliquées dans l’interface utilisateur mise à jour, ce qui garantit que les clients voient uniquement les activités associées à l’espace de travail qui leur est affecté. (TGT-53297)

+++

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
