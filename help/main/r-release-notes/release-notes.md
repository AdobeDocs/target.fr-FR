---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bugs;mises à jour;mises à jour actuelles
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: f0536e466d59fc4e3cccd61c25b7fe7f48f03954
workflow-type: tm+mt
source-wordcount: '4858'
ht-degree: 7%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Découvrez les dernières fonctionnalités, améliorations et correctifs d’[!DNL Adobe Target]. Ces notes de mise à jour couvrent également les mises à jour des API [!DNL Target], des SDK, de la [!DNL Adobe Experience Platform Web SDK], d’at.js et d’autres composants de plateforme, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## Mises à jour sensibles à l’heure que vous devez connaître {#time-sensitive}

[!BADGE Important]{type=Informative}

Pour les mises à jour urgentes relatives à [!DNL Adobe Target] et à votre implémentation, [!DNL Adobe] fournit des notes de mise à jour détaillées et une documentation via [!UICONTROL Experience League]. Voici quelques points forts importants liés à votre implémentation :

### Obsolescence du bouton (bascule) de version de l’interface utilisateur [!DNL Target]

Pour plus d’informations, voir [[!DNL Target] FAQ sur la mise à jour de l’interface utilisateur](/help/main/c-intro/updated-ui-faq.md).

## [!DNL Target Standard/Premium] 25.9.3 (30 septembre 2025)

Cette version comprend les améliorations et correctifs suivants.

+++[!UICONTROL Audiences]

* **Les règles d’exclusion d’audience étaient incorrectement affichées comme inclusion dans l’interface utilisateur de [!DNL Target].** audiences configurées avec des règles d’exclusion s’affichaient comme incluses lors de la modification du ciblage dans une activité. Bien que la logique d’exclusion ait été correctement appliquée lors de l’exécution, l’interface utilisateur n’a pas reflété la règle avec précision, omettant le libellé « exclusion ». L’interface utilisateur de [!DNL Target] affiche désormais correctement les règles d’exclusion dans les workflows de configuration et de ciblage des audiences, ce qui garantit la clarté et la cohérence de la configuration des campagnes. (TGT-53808)
* **La section [!UICONTROL Targeting] n’indiquait pas qu’une règle d’audience était définie sur exclure.** audiences configurées avec la logique d’exclusion s’affichaient incorrectement en tant qu’inclusion dans la section [!UICONTROL Targeting] de l’interface utilisateur de création d’activité. Bien que le serveur principal ait correctement appliqué la règle d’exclusion, l’interface utilisateur n’a pas pu la représenter visuellement, omettant le libellé « Exclure » et provoquant une confusion lors de la configuration de la campagne. La section [!UICONTROL Targeting] affiche désormais clairement les règles d’exclusion, assurant ainsi la cohérence entre la configuration des audiences et la visualisation de ciblage. (TGT-53809)

+++

+++Localisation

* **Correction d’une incohérence terminologique dans la traduction chinoise simplifiée de « Vue détaillée complète ».**
Auparavant, le terme « Détails » était incorrectement traduit par « 详情 » dans le paramètre régional Chinois simplifié (zh_CN), enfreignant les directives terminologiques établies. Ce paramètre a été corrigé en « 详细信息 » pour assurer la cohérence avec la base terminologique. (TGT-53741)

+++

+++[!UICONTROL Recommendations]

* **Les zones de recommandation étaient difficiles à localiser et à sélectionner dans le compositeur d’expérience visuelle.** Après l’ajout d’une offre de recommandations dans le (VEC), le fait de cliquer sur la modification dans le panneau de gauche ne mettait pas en surbrillance ni n’affichait la zone de recommandation correspondante sur la page. Cela rendait difficile la localisation et la modification de l’offre, en particulier lorsqu’elle était masquée sous les sélecteurs ou mise en forme de manière minimale. Cliquer sur une modification de recommandation met désormais correctement en surbrillance l’élément associé et le fait défiler, ce qui améliore la convivialité et l’efficacité de la modification dans le processus de création d’activité mis à jour. (TGT-52571)
* **Les sélecteurs de recommandation ont été réécrits de manière incorrecte après l’enregistrement d’une activité.** Lors de l’ajout d’une recommandation à un élément dans le VEC, le sélecteur était initialement correct, mais après l’enregistrement et la réouverture de l’activité, il est devenu un sélecteur générique. Les tentatives de restauration manuelle du sélecteur d’origine ont provoqué des erreurs de validation. Les sélecteurs de recommandations persistent désormais avec précision après l’enregistrement, assurant ainsi un ciblage fiable et la modifiabilité dans le processus de création d’activité mis à jour. (TGT-53709)
* **Impossible de modifier le contenu des critères lors de la modification d’une activité existante.** Lors de la modification d’une activité, la section [!UICONTROL Criteria] contenu s’affichait désactivée, les boutons étaient grisés et ne répondaient pas. Ce problème a été résolu en s’assurant que les configurations [!UICONTROL Criteria] sont entièrement modifiables lors des mises à jour des activités. Les clients peuvent désormais modifier [!UICONTROL Criteria] contenu sans avoir à changer de sélection ni à utiliser des solutions de contournement, ce qui améliore la flexibilité et la convivialité du processus de création d’activités mis à jour. (TGT-53812)
* **Les critères n’ont pas pu être modifiés dans une activité.** Les options [!UICONTROL Edit Criteria] et [!UICONTROL Remove Criteria] étaient désactivées lors de l’accès aux critères depuis une activité. Toutefois, les mêmes critères peuvent être modifiés avec succès via l’onglet [!UICONTROL Recommendations] . Les critères sont désormais entièrement modifiables à partir du workflow de modification d’activité et de l’onglet [!UICONTROL Recommendations] , ce qui garantit une expérience de modification cohérente et efficace. (TGT-53814)

+++

+++[!UICONTROL Reports]

* **La génération d’offres ad hoc dans les activités A[!UICONTROL utomated Personalization] entraînait des incohérences dans les rapports.** L’utilisation de la fonctionnalité Générer des offres ad hoc dans les activités [!UICONTROL Automated Personalization] (AP) entraînait des rapports inexacts. Plus précisément, les identifiants d’offre ont été réutilisés entre les emplacements, ce qui a entraîné l’attribution incorrecte ou le remplacement des données de rapport. Les offres ad hoc sont désormais générées avec des identifiants distincts par emplacement, ce qui garantit un suivi et un reporting précis sur toutes les expériences configurées. (TGT-53757)
* **Échec du chargement des rapports d’activité en raison d’une erreur JavaScript.** clients ont rencontré un message « Un problème est survenu » lors de l’accès à l’onglet [!UICONTROL Reports] pour certaines activités. L&#39;erreur est due à une exception JavaScript : impossible de lire les propriétés de l&#39;objet undefined (lecture de &#39;indexOf&#39;), déclenchées lors de l&#39;appel `getAnalyticsReportSummary` de GraphQL. Les rapports se chargent désormais correctement et la gestion des erreurs a été améliorée afin d’éviter des échecs similaires dans le workflow de création d’activité mis à jour. (TGT-53797)
* **Rapports bloqués après interaction avec la barre de défilement.** Le fait de cliquer sur la barre de défilement dans l’onglet [!UICONTROL Reports] a provoqué le blocage de la page, accompagné d’une erreur JavaScript :
  Les rapports `SyntaxError: Failed to execute 'querySelector' on 'Element': '[data-key="a-currentcopy"hiretalent""]' is not a valid selector.` se chargent et défilent désormais correctement sans déclencher d’erreurs ou de blocages. (TGT-53828)
* **Les rapports n’affichaient pas la mesure principale.** La mesure principale, configurée en tant que mesure de conversion à l’aide d’une mbox, était absente des rapports d’activité. La recherche par nom de mesure ou de mbox n’a donné aucun résultat, ce qui empêche de voir les données de performances clés. Les mesures de Principal s’affichent désormais correctement dans l’onglet [!UICONTROL Reports], ce qui permet d’assurer un suivi et une analyse précis des performances de la campagne. (TGT-53773)
* **L’onglet [!UICONTROL Reports] de l’interface utilisateur mise à jour s’est bloqué lors de l’interaction avec la barre de défilement horizontale.** La vue [!UICONTROL Reports] s’est bloquée par intermittence avec une erreur « Un problème est survenu » lors de l’utilisation de la barre de défilement horizontale pour accéder aux mesures non visibles. La barre de défilement fonctionne désormais de manière fiable, ce qui permet aux clients d’afficher et d’analyser toutes les mesures sans avoir à recourir à des solutions telles que le zoom arrière ou l’utilisation de la touche Maj-Scroll. (TGT-53824)

+++

+++[!UICONTROL Visual Experience Composer] (VEC)

* **Le fait de cliquer sur les chemins de navigation dans le VEC n’affichait pas systématiquement le menu de modification.**
Lors de la sélection d’éléments HTML via les chemins de navigation dans le (VEC), le menu d’édition ne s’affiche ou disparaît rapidement par intermittence, ce qui rend la sélection d’éléments peu fiable. Le menu d’édition s’affiche désormais de manière cohérente lorsque vous naviguez à travers les chemins de navigation, ce qui améliore le workflow de sélection d’éléments dans le processus de création d’activité mis à jour. (TGT-52873)
* **Le menu contextuel n’a pas pu apparaître par intermittence dans le compositeur d’expérience visuelle.** Le menu contextuel de l’interface utilisateur du compositeur d’expérience visuelle mise à jour n’apparaissait pas de manière cohérente lorsque vous cliquiez sur des éléments, ce qui rendait difficile l’accès aux options de modification. Le menu contextuel s’affiche désormais de manière fiable lors de la sélection d’un élément, ce qui améliore le workflow de modification et la convivialité globale dans le processus de création d’activité mis à jour. (TGT-53015)
* **Le menu contextuel n’a pas pu s’afficher pour certains éléments dans le compositeur d’expérience visuelle.** Le menu contextuel ne s’affichait pas lors de la sélection d’éléments spécifiques dans le compositeur d’expérience visuelle mis à jour, ce qui rendait difficile l’application des modifications. Le menu contextuel s’affiche désormais de manière cohérente pour tous les éléments pris en charge, ce qui améliore la fiabilité et la convivialité de l’expérience de modification dans le workflow de création d’activité mis à jour. (TGT-53248)
* **Le menu contextuel disparaissait lors du premier clic lors de l’utilisation de chemins de navigation dans le VEC.** La sélection d’un élément parent via les chemins de navigation dans le compositeur d’expérience visuelle a fait apparaître brièvement le menu contextuel, puis l’a fait disparaître, ce qui a rendu difficile l’accès aux options de modification. Le menu contextuel reste désormais visible et fonctionnel lors de la navigation dans les éléments à travers les chemins de navigation, ce qui améliore la fiabilité du workflow de sélection d’éléments dans le processus de création d’activités mis à jour. (TGT-53424)
* **Le menu contextuel ne s’affichait pas pour les éléments de niveau supérieur dans le compositeur d’expérience visuelle.** La sélection d’éléments de niveau supérieur, tels que des balises `<div>` ou `<main>`, via les chemins de navigation dans le compositeur d’expérience visuelle, n’a pas déclenché le menu contextuel, empêchant ainsi d’autres actions de modification. Le menu contextuel s’affiche désormais de manière cohérente pour tous les éléments pris en charge, y compris les conteneurs de niveau supérieur, ce qui améliore la flexibilité et la convivialité du workflow de création d’activité. (TGT-53770)
* **Les éléments d’une page spécifique n’étaient pas modifiables dans le compositeur d’expérience visuelle.** Certains éléments de la page n’ont pas pu être sélectionnés ou modifiés dans le VEC mis à jour. Ce problème était isolé à cette page et n’affectait pas d’autres pages du même compte. Tous les éléments de la page peuvent désormais être sélectionnés et modifiés comme prévu, ce qui restaure toutes les fonctionnalités du workflow de création d’activité. (TGT-53353)
* **Amélioration du workflow lors de l’affichage d’éléments enfants lors de la sélection d’éléments dans le VEC.** Pour améliorer la convivialité et la précision lors de la création de l’activité, le compositeur d’expérience visuelle affiche désormais les éléments enfants lors du survol ou de la sélection d’un élément HTML parent. Cette amélioration permet aux clients de mieux comprendre la structure de la page et d’apporter des modifications plus précises, ce qui simplifie le workflow de modification dans l’interface utilisateur mise à jour. (TGT-53416)
* **Les éléments des activités existantes n’ont pas pu être modifiés à l’aide de la barre de modification.** Lors de la modification d’activités créées précédemment, la barre de modification ne s’activait pas pour certains éléments de la page, empêchant ainsi les mises à jour. Ce problème a principalement été observé dans les activités modifiées et était difficile à reproduire dans les activités nouvellement créées. La barre de modification s’affiche désormais de manière cohérente et permet de modifier tous les éléments pris en charge, ce qui améliore la fiabilité et la convivialité du workflow de création d’activité mis à jour. (TGT-53013)

+++

+++[!UICONTROL Workspaces]

* **Le clonage d’une activité vers un autre espace de travail a déclenché une erreur « Entrée utilisateur non valide ».** Tentative de clonage d’une activité d’un espace de travail à un autre a entraîné une erreur : « InvalidProperty.Json - Unknown property name &#39;content&#39; ». Ce problème était dû à une gestion incorrecte des métadonnées d’activité pendant le processus de clonage. Les activités peuvent désormais être clonées dans les espaces de travail sans déclencher d’erreurs de validation, ce qui garantit des workflows de déploiement d’activité plus fluides. (TGT-53731 et TGT-53736)

+++

## [!DNL Target Standard/Premium] 25.9.2 (22 septembre 2025)

Cette version comprend les améliorations et correctifs suivants :

**[!UICONTROL Audiences]**

+++Afficher les détails
* **Correction d’un problème en raison duquel les activités ne pouvaient pas être copiées en raison d’identifiants d’audience non valides.** Les clients et clientes qui tentent de copier des activités dans le processus de création d’activités mis à jour ont rencontré une erreur due à des ID d’audience non valides (par exemple, -1752722444307). Ce problème de validation du serveur principal a empêché la duplication des activités dans le même espace de travail. Ce problème a été résolu, et les activités peuvent désormais être copiées sans erreurs liées aux audiences. (TGT-53717)
* **Correction d’un problème en raison duquel des erreurs d’entrée utilisateur non valides s’affichaient pour les audiences d’activité uniquement dans les activités [!UICONTROL Automated Personalization] la fenêtre modale [!UICONTROL Manage Content].** clients ont rencontré des erreurs d’entrée utilisateur non valides lors de la configuration des audiences d’activité uniquement dans la boîte de dialogue modale [!UICONTROL &#x200B; Manage Content] pour les activités AP. Ce problème se produisait malgré l’utilisation réussie des audiences précédentes. Les configurations d’audience combinées s’enregistrent désormais correctement sans déclencher d’erreurs de validation. (TGT-53749)

+++

**Documentation**

+++Afficher les détails
* **Déplacement des pages de documentation de Web SDK spécifiques à Target vers le référentiel Adobe Target.** Dans le cadre de la restructuration de la documentation de Web SDK, le contenu spécifique à [!DNL Target] a été migré de la documentation générale de Web SDK vers le [!DNL Adobe Target] [guide de développement](https://experienceleague.adobe.com/fr/docs/target-dev/developer/a4t/overview-a4t?lang=en){target=_blank}. Cette modification améliore la visibilité du contenu et garantit que l’équipe produit appropriée maintient les conseils spécifiques à la solution. (TGT-53374)

+++

**[!UICONTROL Offer Decisions]**

+++Afficher les détails
* L’option **Décision d’offre est désormais systématiquement visible lors de la création de l’activité initiale.** Correction d’un problème dans l’interface utilisateur mise à jour où l’option [!UICONTROL Offer Decision] ne s’affichait pas lors du flux de création pour la première fois des activités A/B, en particulier lors d’un accès en mode incognito sur des clients pour lesquels les décisions d’offre étaient activées. L’option ne s’affichait qu’après avoir accédé à l’étape [!UICONTROL Targeting] et être revenu à [!UICONTROL Experiences]. Ce correctif garantit que l’option [!UICONTROL Offer Decision] est immédiatement disponible lors de la configuration initiale, ce qui améliore la convivialité et réduit la confusion. (TGT-51888)

+++

**[!UICONTROL Offers]**

+++Afficher les détails
* **Correction d’un problème en raison duquel les offres de redirection n’incluaient pas de `redirectOptions` dans la payload lors de la `includeContent=true`.** clients récupérant des offres de redirection avec `includeContent=true `n’avaient pas le champ `redirectOptions` dans la payload de réponse. Cette incohérence affectait les workflows, tels que la copie d’offres et la création d’activités. Les offres de redirection incluent désormais correctement les `redirectOptions` lorsque du contenu est demandé. (TGT-53737)

+++

**[!DNL Recommendations]**

+++Afficher les détails
* **Suivi des clics restauré pour [!UICONTROL Recommendations] activités créées dans l’interface utilisateur mise à jour.** Correction d’un problème en raison duquel les activités [!UICONTROL Recommendations] créées dans l’interface utilisateur mise à jour n’enregistraient pas le suivi des clics, ce qui entraînait l’absence de conversions signalées. Les activités intégrées à l’interface utilisateur héritée ont correctement suivi les clics et signalé les conversions comme prévu. Ce correctif garantit que les activités Recommendations créées dans l’interface utilisateur mise à jour incluent désormais les attributs de suivi corrects, ce qui restaure les rapports de conversion et l’alignement sur les mesures A4T. (TGT-53287)
* **Suivi des clics restauré pour les activités Recommendations.** Correction d’un problème en raison duquel les activités [!UICONTROL Recommendations] créées dans l’interface utilisateur mise à jour n’enregistraient pas le suivi des clics, ce qui entraînait l’absence de conversions signalées. L’interface utilisateur héritée a correctement appliqué un identifiant de suivi (`at-track-click`) au contenu [!UICONTROL Recommendations], tandis que l’interface utilisateur mise à jour a inséré par erreur un espace réservé (`__recsClickTrackIdPlaceholder__`), empêchant le suivi du serveur principal. Ce correctif garantit que [!DNL Recommendations] contenu inclut désormais l’identifiant de suivi correct, restaurant les rapports de conversion et l’alignement sur les mesures A4T. (TGT-53496)
* **Le blocage de l’éditeur de collections a été résolu dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur du [!UICONTROL Visual Experience Composer] mis à jour (VEC) en raison duquel l’ouverture d’une collection à partir du panneau de l’éditeur entraînait le blocage de la page avec une erreur TypeError : impossible de lire les propriétés de l’objet non défini (lecture de « customLocale »). Cette erreur s’est produite sur plusieurs types d’activité, y compris les tests [!UICONTROL Recommendations] et A/B. (TGT-53703)
* **Option permettant de supprimer la collection sélectionnée restaurée dans le compositeur d’expérience visuelle.** Correction d’un problème dans le VEC en raison duquel les utilisateurs ne pouvaient remplacer qu’une collection sélectionnée dans une activité [!UICONTROL Recommendations], mais ne pouvaient pas la supprimer entièrement. Cette limitation a bloqué les cas d’utilisation nécessitant une suppression nette de la collection sans substitution. Ce correctif introduit une option claire pour supprimer la collection sélectionnée, ce qui permet une plus grande flexibilité dans la configuration de l’activité et l’alignement avec le comportement hérité de l’interface utilisateur. (TGT-53652)
* **Les collections de critères personnalisés s’affichent désormais correctement dans l’interface utilisateur de [!UICONTROL Recommendations].** Correction d’un problème dans l’interface de Recommendations en raison duquel les collections créées à l’aide de critères personnalisés n’affichaient pas les résultats du produit. Bien que les collections standard basées sur les attributs aient fonctionné comme prévu, celles qui utilisent des filtres personnalisés ont renvoyé « Aucun résultat trouvé » malgré des correspondances de catalogue valides. Ce correctif garantit que les collections qui utilisent des attributs personnalisés s’affichent désormais correctement dans l’onglet [!UICONTROL Product] , restaurant ainsi l’intégralité des fonctionnalités des workflows de recommandations personnalisées. (TGT-53653)
* **Correction d’un problème en raison duquel les collections n’affichaient pas les produits lors de la première ouverture de la page [!UICONTROL Products].** clients accédant aux collections dans la section [!UICONTROL Recommendations] ont affiché des résultats de produit vides lors de la première ouverture de la page [!UICONTROL Products]. Ce problème était dû à une erreur de serveur principal dans la requête GraphQL, qui n’a pas réussi à charger les données de produit pour les collections avec des critères personnalisés. Le problème a été résolu et les produits s’affichent désormais correctement sans nécessiter de changement d’environnement. (TGT-53694)
* **Correction d’un problème en raison duquel les collections ne pouvaient pas être supprimées dans les activités de [!UICONTROL Recommendations] basées sur des formulaires.** Les clients qui ont créé des activités [!UICONTROL Recommendations] à l’aide de l’[!UICONTROL Form-Based Experience Composer] n’ont pas pu désélectionner une collection précédemment sélectionnée. L’interface utilisateur exigeait qu’une collection soit sélectionnée avant d’enregistrer, ce qui empêche les utilisateurs de revenir à « Toutes les collections ». Ce comportement a été mis à jour pour correspondre à la fonctionnalité du VEC, ce qui permet aux clients d’enregistrer sans sélectionner de collection et de définir par défaut « Toutes les collections » comme prévu. (TGT-53708)
* **Correction d’un problème en raison duquel les promotions ne pouvaient pas être définies par attribut en raison de valeurs de règle de collecte ou de filtrage manquantes.** Les clients qui configurent des promotions par attribut dans le processus de création d’activité ont rencontré une erreur indiquant qu’il manquait un ID de collection ou des valeurs de règle de filtrage pour une promotion. Ce problème de validation a bloqué la progression même lorsque la configuration semblait terminée. Les promotions peuvent désormais être enregistrées correctement lorsqu’elles sont configurées par attribut . (TGT-53750)
* **Correction d’un problème en raison duquel les activités ne pouvaient pas être enregistrées en raison de noms d’expérience en double.** clients ont rencontré une erreur d’entrée utilisateur non valide lors de l’enregistrement d’activités qui incluaient des combinaisons spécifiques de critères et de conceptions. L’erreur a été déclenchée par des noms d’expérience en double, même si la configuration semblait valide. Les activités avec des configurations distinctes peuvent désormais être enregistrées sans conflits de noms. (TGT-53805)
* **Correction d’un problème en raison duquel la validation n’était pas valide pour les promotions configurées par attribut.** clients ont rencontré des erreurs de validation persistantes lors de la configuration des promotions par attribut dans le processus de création d’activités, même lorsque tous les champs obligatoires étaient correctement renseignés. Ce problème était dû à une logique de validation incorrecte dans le workflow [!UICONTROL Recommendations]. Les promotions basées sur les attributs sont désormais validées et enregistrées comme prévu. (TGT-53811)
* **Correction d’un problème en raison duquel l’application d’une promotion à une activité Live [!UICONTROL Recommendations] déclenchait une erreur.** clients ont rencontré l’erreur « Il manque un ID de collection ou des valeurs de règle de filtrage dans une promotion » lors de la tentative d’application d’une promotion front-end à une activité Live [!UICONTROL Recommendations], même après avoir fourni des détails de configuration valides. Les promotions peuvent désormais être appliquées avec succès aux activités actives sans déclencher d’erreurs de validation, ce qui garantit une expérience plus fluide dans l’interface utilisateur de création d’activité mise à jour. (TGT-53738)
* **Correction d’un problème en raison duquel les produits n’étaient pas visibles dans les collections dans l’interface utilisateur de [!UICONTROL Recommendations].** clients d’un seul client ont signalé que le chargement des listes de produits a échoué lors de l’affichage de certaines collections dans la section [!UICONTROL Recommendations] de la nouvelle interface utilisateur. Le problème a été temporairement résolu en changeant d’environnement, mais cette solution de contournement a entraîné une mauvaise expérience utilisateur. Les entités de produit se chargent désormais de manière cohérente sans basculement d’environnement. (TGT-53783)
* **Correction d’un problème où les critères et les conceptions ne s’affichaient pas sur une ligne dans l’interface utilisateur de création d’activités.** Auparavant, les critères et les conceptions du processus de création d’activités étaient affichés dans un format compressé, ce qui rendait difficile l’affichage et la gestion des éléments individuels pour les clients. Chaque critère et conception apparaît désormais sur sa propre ligne, ce qui améliore la lisibilité et la convivialité dans l’interface utilisateur mise à jour. (TGT-53818)

+++

**Rapports**

+++Afficher les détails
* **[!UICONTROL Total Revenue]mesure est désormais incluse dans les exportations au format CSV des rapports d’activité.** Correction d’un problème dans l’interface utilisateur de [!UICONTROL Overview] mise à jour où le chiffre d’affaires total s’affichait correctement dans la vue du rapport d’activité, mais était absent de l’exportation au format CSV, avec une valeur de 0 $. Cette incohérence empêchait les utilisateurs de se fier aux données exportées pour l’analyse et la création de rapports hors ligne. (TGT-53325)
* **[!UICONTROL Total Sales]mesure est désormais incluse dans les exportations au format CSV des rapports d’activité.** Correction d’un problème dans l’interface utilisateur mise à jour où la mesure [!UICONTROL Total Sales] apparaissait correctement dans la vue du rapport d’activité, mais était absente de l’exportation au format CSV. Cette incohérence empêchait les utilisateurs d’accéder à des données de performances complètes dans les rapports téléchargés. Ce correctif garantit que les valeurs [!UICONTROL Total Sales] sont désormais incluses avec précision dans les exportations CSV, ce qui restaure la cohérence entre les rapports in-app et les analyses hors ligne. (TGT-53330)
* **Amélioration de la messagerie d’erreur pour les [!UICONTROL Graph View] lorsque les mesures ne sont pas activées.** Correction d’un problème dans le VEC en raison duquel le [!UICONTROL Graph View] affichait un message générique « Un problème est survenu » lorsqu’une mesure demandée n’était pas activée dans la suite de rapports [!DNL Analytics] associée. Ce problème a été déclenché par une erreur `not_enabled_metric` dans la réponse GraphQL du serveur principal. Ce correctif remplace l’erreur vague par un message plus informatif qui aide les utilisateurs et utilisatrices à identifier les problèmes de configuration dans [!DNL Analytics], ce qui réduit la confusion et les remontées inutiles de l’assistance. (TGT-53577)
* **Correction d’un problème en raison duquel la durée du rapport dépassait la limite prise en charge de 90 jours.** clients et clientes utilisant le filtre « [!UICONTROL Last X Days] » dans la section [!UICONTROL Reports] ont pu sélectionner des durées supérieures à 90 jours, ce qui peut entraîner des problèmes de performances et des données incomplètes. Le filtre a été mis à jour pour appliquer une plage maximale de 90 jours, ce qui garantit la cohérence et la fiabilité des rapports. (TGT-53795)
* **Correction d’un problème où les rapports CSV de performances étaient générés à l’aide de l’environnement par défaut au lieu de l’environnement sélectionné.** Auparavant, lorsque les clients modifiaient l’environnement dans les paramètres du rapport et généraient un rapport de performances, le fichier CSV obtenu contenait des données de l’environnement par défaut plutôt que de l’environnement sélectionné.  L’interface utilisateur transmet désormais correctement le paramètre `environmentId`, en s’assurant que le rapport reflète l’environnement choisi. En outre, la gestion des erreurs a été améliorée. Si des erreurs GraphQL se produisent lors de la génération du fichier CSV, l’interface utilisateur affiche désormais un message d’erreur clair au lieu de produire un fichier CSV vide. (TGT-53064)
* **Correction d’un problème en raison duquel les rapports Analytics for Target (A4T) n’affichaient pas les données dans [!UICONTROL Graph View].** clients qui utilisent [!DNL Target] avec l’intégration A4T ont rencontré une erreur « Un problème s’est produit » lors du passage à la vue Graphique dans l’onglet Rapports des activités de test A/B. Bien que le [!UICONTROL Table View] ait été correctement chargé, [!UICONTROL Graph View] n’a pas réussi à générer les tendances des mesures sur la période sélectionnée. [!UICONTROL Graph View] affiche désormais les données de performances attendues pour toutes les mesures prises en charge, ce qui améliore la visibilité et la précision des rapports dans l’interface utilisateur mise à jour. (TGT-53573)

+++

**Compositeur d’expérience visuelle**

+++Afficher les détails
* **Les métadonnées d’élément sont désormais visibles au survol dans le menu de chemin de navigation.** Amélioration du menu de navigation dans le VEC pour afficher des détails d’élément supplémentaires tels que l’identifiant, la classe et le nom lorsque vous passez la souris sur un élément. Cette amélioration permet aux utilisateurs et utilisatrices d’identifier et de différencier plus facilement les éléments lors de la configuration des activités. (TGT-53409)
* Le pointage du chemin de navigation **met désormais en surbrillance l’élément correspondant dans le VEC.** Amélioration de la [!UICONTROL Visual Experience Composer] pour mettre en surbrillance l’élément correspondant dans l’éditeur lorsque vous passez la souris sur des éléments du menu de chemin de navigation. Le type d’élément est également affiché, par exemple conteneur, texte en gras ou bouton. Ce comportement s’applique aux éléments frères et exclut les types non pris en charge tels que SVG, en fonction de la liste de validation. (TGT-53411)
* **Alerte Modifications non enregistrées restaurée dans les workflows de modification du compositeur d’expérience visuelle.** Correction d’un problème dans le VEC en raison duquel les utilisateurs n’étaient plus avertis des modifications non enregistrées des modifications du code personnalisé. Contrairement à l’interface utilisateur héritée, la nouvelle expérience ne comportait pas d’invites lors de la fermeture de l’éditeur de personnalisation, ce qui entraînait une perte accidentelle de la progression. Ce correctif restaure les alertes pour tous les types de modification, y compris le code personnalisé, et garantit que les utilisateurs sont avertis avant de quitter sans enregistrer. (TGT-53435).
* **Les modifications du code personnalisé persistent désormais pendant l’actualisation de la page dans le VEC.** Correction d’un problème dans le VEC en raison duquel les modifications du code personnalisé étaient perdues lors des actualisations du site web. Ce problème se produisait sur les pages comportant plusieurs rechargements, ce qui entraînait la réinitialisation et l’annulation des modifications non enregistrées par l’éditeur. Le correctif garantit que les modifications de code personnalisé restent intactes même si la page se recharge lors de la modification, évitant ainsi toute perte accidentelle de la progression. (TTGT-53501)
* **Problème de connexion résolu pour l’accès au site dans le compositeur d’expérience visuelle.** Correction d’un problème en raison duquel les utilisateurs ne pouvaient pas se connecter à leur site lors de l’accès à celui-ci via le VEC. Le flux de connexion a redirigé à plusieurs reprises les utilisateurs vers la page de connexion, empêchant la configuration et la prévisualisation de l’activité. Ce correctif garantit que le compositeur d’expérience visuelle n’interfère plus avec le comportement de connexion et restaure l’accès attendu pour les utilisateurs authentifiés. (TGT-53524)
* **Problème de duplication des cookies résolu dans l’extension d’assistance du VEC.** Correction d’un problème en raison duquel l’extension [!UICONTROL Adobe Experience Cloud Visual Editing Helper] dupliquait le cookie `at_qa_mode` lors de l’assurance qualité via les liens de prévisualisation. Lors du changement manuel d’index d’aperçu, plusieurs cookies ont été créés avec des valeurs en conflit entre les domaines, empêchant les testeurs de changer de variantes de manière fiable. Ce comportement a été observé même en dehors de l’interface utilisateur de Target et a affecté les comptes internes et clients. Ce correctif garantit une gestion cohérente des cookies en empêchant les entrées en double et en alignant la portée du domaine, ce qui permet un changement de variante transparent sans nécessiter de nettoyage manuel des cookies. (TGT-53579)
* **Correction d’un problème en raison duquel le clic sur les éléments d’une certaine page d’accueil provoquait des fuites de mémoire.** Les clients et clientes qui créent des activités sur cette page d’accueil ont rencontré des fuites de mémoire lors de leur interaction avec les éléments de page. Le problème était lié à des avertissements excessifs de la console et à l&#39;augmentation de l&#39;utilisation de la mémoire dans les sous-trames, en particulier en ce qui concerne les attributs srcset incorrects. L’utilisation de la mémoire reste désormais stable lors de l’interaction. (TGT-53761)
* **Correction d’un problème en raison duquel le VEC se bloquait et affichait un écran vide lors du chargement de certaines activités.** clients d’un client spécifique ont signalé que l’éditeur n’a pas réussi à charger des activités spécifiques. Le compositeur d’expérience visuelle est resté bloqué sur « Application des modifications initiales » avant de se bloquer et d’afficher un écran vide. Le compositeur d’expérience visuelle charge désormais les activités affectées sans erreur dans le processus de création d’activités mis à jour. (TGT-52932)
* **Correction d’un problème en raison duquel le rail [!UICONTROL Manage Content] dans [!UICONTROL Automated Personalization] activités affichait des libellés d’emplacement incohérents.** clients et clientes ont signalé que les numéros d’emplacement du rail [!UICONTROL Manage Content] ne correspondaient pas dans les onglets [!UICONTROL Experiences] et [!UICONTROL Offers]. (par exemple, Emplacement 2 et Emplacement 4 dans Expériences, et Emplacement 1 et Emplacement 2 dans Offre) même si seulement deux emplacements ont été configurés. Les libellés d’emplacement sont désormais cohérents et mappés avec précision aux modifications, ce qui améliore la clarté et la convivialité du processus de création d’activités. (TGT-52934)
* **Correction d’un problème en raison duquel les modifications du VEC étaient perdues après l’enregistrement.** clients et clientes ont signalé qu’après avoir enregistré une modification dans le VEC, la page s’actualisait et revenait à la version précédente de la modification. Ce problème entraînait la perte des mises à jour les plus récentes, sauf si l’activité entière était enregistrée immédiatement. Les modifications persistent désormais correctement après l’enregistrement et l’éditeur n’annule plus les modifications de manière inattendue, ce qui garantit une expérience fiable dans le workflow de création d’activité. (TGT-53500)
* **Amélioration de la sélection d’éléments dans le VEC en affichant le type d’élément lors du survol et de la sélection.** Pour améliorer la convivialité lors de la création de l’activité, le compositeur d’expérience visuelle agrémente désormais les éléments HTML avec leur type lorsqu’ils sont survolés ou sélectionnés. Cette amélioration permet aux clients d’identifier et de sélectionner plus facilement les éléments corrects. Les éléments sélectionnés sont mis en surbrillance avec une couleur distincte et les éléments survolés sont entourés en bleu. Le type d’élément s’affiche également, fournissant un contexte plus clair lors de la modification. (TGT-53502)

+++

## Mises à jour des flux de données (19 septembre 2025)

L’identifiant du flux de données et la combinaison de sandbox doivent être uniques pour les connexions de destination [!DNL Adobe Target].

Mise à jour de la logique de validation pour [!DNL Target] connexions de destination afin d’imposer que la combinaison de l’identifiant du flux de données et du nom du sandbox doit être unique au sein d’une organisation IMS. Cela signifie :

* La même paire identifiant de flux de données + nom de sandbox ne peut pas être réutilisée sur plusieurs connexions de destination [!DNL Target].
* Un même identifiant de flux de données peut être utilisé pour différentes connexions uniquement si elles sont configurées dans différents sandbox.
* Cette règle s’applique à toutes les sélections de flux de données, y compris lorsque l’option « Aucun » est sélectionnée.

Cette mise à jour garantit une configuration cohérente et empêche les conflits entre les environnements multi-sandbox. Pour plus d’informations, voir [Connexion Adobe Target](https://experienceleague.adobe.com/fr/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection){target=_blank} dans le guide *Destinations Experience Platform*.

## [!DNL Target Standard/Premium] 25.9.1 (5 septembre 2025)

Cette version comprend les mises à jour et correctifs suivants :

**[!UICONTROL Experience Fragments]**

+++Afficher les détails
* **Amélioration de l’attribution des utilisateurs pour les offres [!UICONTROL AEM Experience Fragment].** Correction d’un problème dans le VEC en raison duquel le champ « [!UICONTROL Last updated] » pour les offres de [!UICONTROL AEM Experience Fragment] (XF) affichait incorrectement un ID de code au lieu du nom d’utilisateur. Cette incohérence s’est produite lors de la sélection des offres dans l’interface utilisateur mise à jour, créant une incohérence avec les offres de l’interface utilisateur et d’HTML héritées, qui affichaient correctement le nom du dernier éditeur. Ce correctif garantit une attribution utilisateur cohérente entre les types d’offres, ce qui améliore la transparence et l’alignement sur le comportement attendu. (TGT-52880 et TGT-52898)

+++

**Offer Decisioning**

+++Afficher les détails
* **L’erreur de décision d’offre a été résolue pour les offres ODE.** Correction d’un problème où les offres du moteur de décision d’offre (ODE) injectées par [!DNL Target] renvoyaient une erreur 400 en raison de métadonnées de format manquantes. Le message d’erreur indiquait que le type MIME était nul, ce qui empêchait le traitement réussi des décisions d’offre. Ce correctif garantit la gestion appropriée des métadonnées de l’offre, la restauration de la fonctionnalité pour la diffusion de contenu personnalisé et la possibilité d’exécuter sans interruption les campagnes marketing. (TGT-53635)
* **Le problème de rendu des offres ODS a été résolu.** Correction d’un problème en raison duquel les offres [!DNL Offer Decision Service] (ODS) créées via [!DNL Adobe Journey Optimizer] (AJO) n’étaient pas rendues lorsque les activités étaient créées à l’aide du VEC dans l’interface utilisateur mise à jour. La même configuration fonctionnait correctement dans l’interface utilisateur héritée, ce qui entraînait une confusion et bloquait l’exécution de la campagne. Ce correctif garantit la cohérence de la diffusion des offres dans les deux versions de l’interface utilisateur et restaure le comportement attendu pour la personnalisation pilotée par AJO.

+++

**Rapports**

+++Afficher les détails
* **Option de téléchargement restaurée dans la section Rapports de l’interface utilisateur de présentation des rapports mise à jour.** Correction d’un problème dans la nouvelle interface utilisateur de l’aperçu en raison duquel le bouton [!UICONTROL Download] était absent de la section Rapports, ce qui empêchait les utilisateurs d’exporter les scores d’importance des attributs. Cette mise à jour restaure l’intégralité des fonctionnalités d’exportation, permettant un accès rationalisé aux données téléchargeables pour l’analyse et le reporting. (TGT-53222)
* **[!UICONTROL Download full CSV report]bouton restauré dans la vue [!UICONTROL Important attributes].** Correction d’un problème dans l’interface utilisateur de création d’activités mise à jour où le bouton [!UICONTROL Download full CSV report] était absent de la section [!UICONTROL Important Attributes] de la vue Rapports. Ce correctif restaure l’accès aux informations téléchargeables, garantissant ainsi des fonctionnalités cohérentes dans les interfaces utilisateur mises à jour et héritées. (TGT-53238)
* **Résolution des problèmes d’interface utilisateur affectant les rapports [!UICONTROL Auto Target] dans l’interface utilisateur de présentation mise à jour.** Correction de plusieurs problèmes d’interface utilisateur dans l’interface de présentation mise à jour qui affectaient les rapports d’activité [!UICONTROL Auto Target]. Ces correctifs incluent :

   * Mesures d’effet élévateur et de confiance manquantes dans les rapports de synthèse
   * Indicateur de couleur incorrect pour la case à cocher « modèles créés »
   * Rapport graphique non fonctionnel malgré la variance des données dans [!DNL Analytics]
   * Lien de téléchargement manquant pour les rapports [!UICONTROL Automated Segments] et [!UICONTROL Important Attributes]
   * Affichage du rapport de [!UICONTROL Automated Segments] endommagé

  Ces correctifs restaurent le comportement de création de rapports attendu et améliorent la visibilité sur les performances [!UICONTROL Auto Target] dans l’interface utilisateur mise à jour. (TGT-53484)

+++

**[!UICONTROL Visual Experience Composer]**

+++Afficher les détails
* **Validation du formulaire corrigée pour les conditions de présence des paramètres dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur mise à jour où la sélection de « [!UICONTROL Custom mbox parameter value is present] » ou « [!UICONTROL Parameter is present] » nécessitait incorrectement que les clients saisissent une valeur. Ce comportement était en conflit avec la logique prévue, qui vérifie simplement l’existence d’un paramètre quelle que soit sa valeur. Le correctif aligne la validation du formulaire sur le comportement attendu, ce qui permet une configuration plus fluide des activités et une adoption complète de l’interface utilisateur mise à jour. (TGT-53638)
* **Correction de la logique de formulaire pour les règles de présence de paramètres dans la diffusion de page. »** Correction d’un problème dans l’interface utilisateur mise à jour où la sélection de règles de diffusion de page telles que « [!UICONTROL Parameter is present] », « [!UICONTROL Parameter is not present] », « [!UICONTROL Parameter value is present] » ou « [!UICONTROL Parameter value is not present] » obligeait incorrectement les utilisateurs à saisir une valeur de paramètre supplémentaire. Ce comportement était incompatible avec l’interface utilisateur héritée et contredisait la logique prévue de détection de la présence de paramètres sans spécifier de valeur. Ce correctif restaure le comportement attendu de configuration des règles, rationalisant la configuration des activités et améliorant la convivialité. (TGT-53640)
* **Amélioration de la logique de validation pour le créateur de règles à plusieurs pages dans l’interface utilisateur mise à jour.** a résolu plusieurs problèmes de validation dans le créateur de règles multi-pages dans l’interface utilisateur mise à jour. Ces correctifs incluent :

   * Empêcher la création de règles lorsque le paramètre mbox est vide
   * Affichage des messages d’erreur appropriés pour les états de règle non valides
   * Correction de la logique de validation pour les opérateurs unaires et basés sur des paramètres qui ne nécessitent pas de valeurs d’opérande
   * Activation des règles de fragment de hachage avec des opérateurs unaires en restaurant la fonctionnalité d’enregistrement

  Ces mises à jour garantissent une configuration des règles précise et améliorent la convivialité sur plusieurs scénarios de diffusion de pages complexes. (TGT-53722)
* **Problème de changement de nom de l’emplacement résolu dans les activités A/B et MVT.** Correction d’un bug dans l’interface utilisateur mise à jour en raison duquel le changement de nom d’un emplacement dans une activité [!UICONTROL A/B Test] ou [!UICONTROL Multivariate Test] (MVT) ne persistait pas après la navigation entre la liste d’emplacements, le ciblage et le retour. Cette mise à jour garantit que les modifications du nom de l’emplacement sont enregistrées et répercutées de manière cohérente tout au long du workflow d’activité. (TGT-52367)
* **Persistance du nom de l’emplacement corrigée pour les activités MVT et AP dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur mise à jour en raison duquel les noms d’emplacement modifiés dans les activités [!UICONTROL Multivariate Test] (MVT) et [!UICONTROL Automated Personalization] (AP) n’étaient pas enregistrés correctement. Après avoir renommé un emplacement, la navigation entre les onglets, tels que [!UICONTROL Targeting] et [!UICONTROL Experiences], a fait revenir les noms à leur état précédent. Ce correctif garantit la cohérence des noms d’emplacement entre les onglets et améliore la fiabilité lors de la configuration des activités. (TGT-52927)
* **Correction de l’étiquetage de l’emplacement dans le panneau Gérer les expériences pour les activités MVT.** Résolution d’un problème dans l’interface utilisateur mise à jour où le panneau [!UICONTROL Manage Experiences] dans les activités [!UICONTROL Multivariate Test] (MVT) affichait une numérotation d’emplacement incohérente. Ce correctif garantit que les libellés d’emplacement sont séquentiels et correctement alignés sur les modifications définies par l’utilisateur, ce qui améliore la clarté et la convivialité lors de la configuration de l’expérience. (TGT-52929)

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
