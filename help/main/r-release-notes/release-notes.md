---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bugs;mises à jour;mises à jour actuelles
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 265108dbb0a459e1b111fda01a35042170f05562
workflow-type: tm+mt
source-wordcount: '4383'
ht-degree: 11%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Découvrez les dernières fonctionnalités, améliorations et correctifs d’[!DNL Adobe Target]. Ces notes de mise à jour couvrent également les mises à jour des API [!DNL Target], des SDK, de la [!DNL Adobe Experience Platform Web SDK], d’at.js et d’autres composants de plateforme, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## Mises à jour sensibles à l’heure que vous devez connaître {#time-sensitive}

[!BADGE Important]{type=Informative}

Pour les mises à jour urgentes relatives à [!DNL Adobe Target] et à votre implémentation, [!DNL Adobe]fournit des notes de mise à jour détaillées et une documentation via [!UICONTROL Experience League]. Voici quelques points forts importants relatifs à votre implémentation :

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

## [!DNL Target Standard/Premium] 25.7.3 (vendredi 24 juillet 2025)

En raison de problèmes récents identifiés, principalement liés à des personnalisations client complexes, cette version comprend les correctifs et mises à jour suivants :

**Activités**

+++Voir les détails
* Correction d’un problème en raison duquel la méthode `buildViews` de la classe builder définissait incorrectement le `viewMaxLocalId` sur le nombre total de vues, plutôt que sur la `viewLocalId` la plus élevée attribuée. (TGT-53207)
* Correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour en raison duquel les offres supprimées dans les activités [!UICONTROL Automated Personalization] (AP) s’affichaient sous la forme `Deleted option with ID: X` au lieu de leurs noms d’origine (par exemple, `Offer Name [Deleted]` comme indiqué dans l’interface utilisateur héritée). Ce correctif restaure l’étiquetage significatif pour les offres supprimées, améliorant ainsi la clarté et rendant les rapports plus précis et plus conviviaux. (TGT-52921)
* Correction d’un problème en raison duquel certaines activités migrées du serveur frontal [!DNL Target] vers [!DNL Target] Central présentaient des configurations de mesures incohérentes en raison d’un bug de synchronisation précédemment corrigé. Plus précisément, les activités qui utilisaient à l’origine une mesure de conversion et qui ont ensuite été mises à jour vers une mesure basée sur les analyses conservaient des valeurs obsolètes dans les champs `primaryMetricType` et `successCriteria`. (TGT-52643)
* Correction d’un problème où l’intégralité du contenu d’une page d’aperçu de l’assurance qualité devenait modifiable en raison de l’inclusion involontaire de l’attribut `contentEditable` dans les modifications d’HTML. Cela permettait aux utilisateurs de cliquer et de modifier n’importe quel texte de la page, ce qui pouvait entraîner des problèmes de mise en page et une confusion lors de l’assurance qualité. (TGT-53247)
* Correction d’un problème en raison duquel le déplacement d’une modification de [!DNL Page Load] vers un [!UICONTROL View] entraînait la duplication de la modification, le maintien dans [!UICONTROL Page Load] tout en apparaissant également dans le [!UICONTROL View]. En outre, la suppression de la modification du [!UICONTROL View] la supprimerait également incorrectement de [!UICONTROL Page Load]. (TGT-53270)

+++

**API**

+++Voir les détails
* Correction d’un problème dans la couche de persistance du serveur principal en raison duquel les options supprimées étaient correctement stockées, mais non accessibles via les points d’entrée de l’API existants. Par conséquent, les applications frontales ne pouvaient pas récupérer de noms significatifs pour les options supprimées, ce qui affectait les vues de rapports historiques. Ce correctif garantit que les données des options supprimées conservées peuvent désormais être correctement affichées dans l’interface utilisateur. (TGT-52973)
* Mise en œuvre d’un nouveau point d’entrée de migration pour prendre en charge le transfert des options d’activité supprimées des activités basées sur JCR vers [!DNL Target] Central. Cette fonctionnalité permet un suivi et des rapports cohérents entre les systèmes. Cette fonctionnalité garantit que les options supprimées sont préservées et synchronisées sur le serveur frontal et le serveur principal [!DNL Target], ce qui améliore les rapports historiques et l’intégrité des données. (TGT-53217)
* Ajout d’un nouveau point d’entrée d’API qui permet aux utilisateurs de restaurer des options d’activité supprimées précédemment d’une base de données secondaire. Cette fonctionnalité tire parti de l’infrastructure existante fournie par les classes `RemovedCampaignElements` et `RemovedOptionInfo`, assurant ainsi une réintégration transparente des options supprimées dans les activités actives. (TGT-52903)
* Correction d’un problème en raison duquel les activités [!DNL Recommendations] contenant des noms de mesures de plus de 25 caractères ne pouvaient pas être ouvertes ni modifiées en raison des limitations de l’API. Ce correctif garantit la compatibilité avec les noms de mesures dépassant la limite de caractères et restaure un accès complet aux activités affectées. (TGT-52839)

+++

**Compositeur d’expérience d’après les formulaires**

+++Voir les détails
* Correction d’un problème dans le [!UICONTROL Form-Based Experience Composer] en raison duquel l’éditeur se bloquait après avoir cliqué sur l’icône **[!UICONTROL Manage Content]** ( ![icône Gérer le contenu](/help/main/assets/icons/Experience.svg) ) lors de la création ou de la modification d’une activité [!UICONTROL Automated Personalization] (AP). (TGT-53047)

+++

**Recommendations**

+++Voir les détails
* Correction d’un problème qui empêchait [!UICONTROL Catalog Search] de charger des résultats supplémentaires lors du défilement vers le bas de la liste, restaurant ainsi un comportement cohérent avec l’interface utilisateur héritée. (TGT-53088)
* Correction d’un problème qui bloquait la suppression d’éléments de la boîte de dialogue [!UICONTROL Criteria Details]. (TGT-53245)
* Correction d’un problème qui empêchait l’ouverture ou l’interaction avec des produits sans nom. Ce problème se produisait lors de la sélection d’environnements qui renvoyaient des résultats sans nom, empêchant l’accès aux détails du produit. (TGT-53007)
* Correction d’un problème en raison duquel la page [!UICONTROL Catalog Search] se bloquait et affichait un écran vide lors de la sélection de certains produits. (TGT-53087)
* Correction d’un problème en raison duquel les utilisateurs ne pouvaient pas modifier l’activité de [!DNL Recommendation] site_cart_z1 dans l’interface utilisateur de [!DNL Target]. La tentative d’ouverture de l’activité a déclenché une erreur sur la page [!UICONTROL Overview], bloquant l’accès à l’éditeur. (TGT-53221)

+++

**Création de rapports**

+++Voir les détails
* Correction d’un problème en raison duquel le champ sandbox de la base de données des activités n’était pas effacé lors du changement de la source de création de rapports de [!DNL Customer Journey Analytics] ou [!DNL Analytics] à [!DNL Target]. Auparavant, l’interface utilisateur envoyait correctement la sandbox : null, mais le serveur principal ignorait cette valeur, laissant en place des données de sandbox obsolètes. Le serveur principal efface désormais correctement le champ sandbox lorsque la valeur null est reçue. (TGT-52798)
* Nouvelle implémentation de la couche de persistance des options supprimées dans le serveur principal de Target pour prendre en charge la création de rapports historiques précis dans les activités [!UICONTROL Automated Personalization] (AP). Auparavant, lorsqu’une option était supprimée, son nom était perdu, ce qui rendait difficile l’interprétation des données de performances antérieures.

  **Améliorations clés** :

   * Les options supprimées sont désormais suivies à l’aide des infrastructures `RemovedCampaignElements` et `RemovedOptionInfo` existantes.
   * Lorsqu’une option est supprimée d’une activité AP, ses métadonnées (par exemple, l’identifiant et le nom) sont conservées.
   * L’interface utilisateur de création de rapports peut désormais afficher le nom de l’option d’origine (par exemple, `Option Name [Deleted]`) avec les mesures historiques, ce qui améliore la clarté et la convivialité.

  Cette mise à jour garantit la cohérence et la pertinence des rapports, même après la suppression d’options d’une activité. (TGT-52986)

+++

**Compositeur d’expérience visuelle**

+++Voir les détails

* Correction d’un problème dans le VEC en raison duquel l’application d’une modification à une vue provoquait une duplication et déclenchait une erreur « Entrée utilisateur non valide ». (TGT-52886)
* Correction d’un problème lié à [!UICONTROL Undo] fonctionnalité des options [!UICONTROL Insert Before] et [!UICONTROL Insert After] lors de la configuration des offres d’images dans le VEC.

  Auparavant, l’annulation d’une action [!UICONTROL Insert Before] ou [!UICONTROL Insert After] sur des offres d’image entraînait un comportement incohérent ou l’échec de l’annulation correcte de la modification, en particulier dans les activités créées dans l’interface utilisateur [!DNL Target] héritée. Ce problème a été résolu afin de garantir que les actions d’annulation fonctionnent désormais de manière fiable pour ces modifications. (TGT-52809)

* Correction d’un problème en raison duquel l’attribut `contentEditable` était involontairement défini sur true et conservé dans le contenu HTML enregistré. Cette mise à jour garantit une sortie HTML plus épurée et attendue, sans comportement de modification involontaire. (TGT-52319)
* Pour éviter la perte permanente d’options supprimées et garantir un comportement cohérent entre les services, la fonctionnalité de suppression réversible a été mise en œuvre pour les options de l’interface utilisateur et les microservices associés.

  **Modifications clés** :

   * Les options ne sont plus supprimées définitivement. Au lieu de cela, ils sont marqués d’un nouvel indicateur deleted : true dans l’objet XML des paramètres.
   * Cet indicateur est utilisé uniquement par l’interface utilisateur [!DNL Target] mise à jour pour exclure les options supprimées du rendu et empêcher leur envoi aux services Edge.
   * Les options supprimées restent une partie de la payload de l’activité lors des modifications, ce qui permet d’assurer la traçabilité tout en évitant la diffusion d’options inexistantes aux clients.

  Cette mise à jour améliore l’intégrité des données et s’aligne sur les bonnes pratiques de gestion des suppressions dans les systèmes distribués. (TGT-52726)

+++

**Workspaces**

+++Voir les détails
* Correction d’un problème lors de la copie d’une activité d’un espace de travail non par défaut vers un espace de travail par défaut ou entre des espaces de travail non par défaut. Les offres sont désormais dupliquées avec un suivi et un nommage améliorés afin d’éviter les conflits.

  **Améliorations clés** :
   * Les offres sont recréées dans l’espace de travail de destination avec des identifiants et des métadonnées mis à jour.
   * Les offres copiées sont renommées au format : « Copie du nom de l’offre » plus un nombre aléatoire ou un horodatage pour garantir l’unicité.
   * Le système met à jour les états des offres et des activités pour refléter les nouveaux identifiants.
   * Cette fonctionnalité empêche les erreurs dues à plusieurs noms de « Copie d’offre » identiques lors d’actions de copie répétées.
   * Les offres peuvent ne pas apparaître immédiatement dans la liste des offres de l’espace de travail de destination, mais sont traitées et affichées de manière appropriée.

  Cette mise à jour améliore la fiabilité et la traçabilité lors de la gestion des offres sur plusieurs espaces de travail. (TGT-53080)

+++

## [!DNL Target Standard/Premium] 25.7.2 (samedi 18 juillet 2025)

En raison de problèmes récents identifiés, principalement liés à des personnalisations client complexes, cette version comprend les correctifs et mises à jour suivants :

**Activités**

+++Voir les détails
* Ajout d’un avertissement de confirmation supplémentaire lors de l’annulation des modifications d’activité avec des modifications non enregistrées : « Voulez-vous vraiment enregistrer cette activité ? Si vous n’enregistrez pas, toutes vos modifications seront perdues. » Ce message permet d’éviter les pertes de données accidentelles. (TGT-52865)
* Restauration de la fonctionnalité héritée du curseur [!UICONTROL Priority] dans [!UICONTROL Goals & Settings], ce qui permet aux clients de saisir directement une valeur numérique, comme pris en charge dans l’interface utilisateur héritée. (TGT-53185 et TGT-53219)

+++

**Audiences**

+++Voir les détails
* Correction d’un problème qui empêchait l’enregistrement ou la modification des activités contenant des audiences personnalisées. Les clients ont rencontré le message d’erreur « Nous ne pouvons pas traiter votre demande. Contactez [!DNL Adobe Client Care] si le problème persiste. » lorsque vous tentez d’enregistrer les modifications apportées à certaines activités , ou même de les enregistrer sans modification. (TGT-53189)

+++

**[!UICONTROL Analytics for Target](A4T)**

+++Voir les détails
* Correction d’un problème en raison duquel les clients affichaient les rapports d’activités spécifiques sur la page [!UICONTROL Goals & Settings] ; le lien [!UICONTROL View in Analytics] pointait incorrectement vers l’environnement d’assurance qualité plutôt que vers l’environnement de production. (TGT-53163)

+++

**[!UICONTROL Experiences]et[!UICONTROL Offers]**

+++Voir les détails
* Correction d’un problème où l’appel de `triggerView` via du code personnalisé provoquait une boucle infinie. (TGT-52885)
* Correction d’un problème qui entraînait des incohérences entre les `LocalIds` définis pour les activités et ceux `LocalIds` dans les définitions des expériences. (TGT-52669)
* Correction d’un problème en raison duquel les noms des mesures étaient manquants sur la page de [!UICONTROL Overview] des activités, affichant uniquement « Offre » au lieu du nom de mesure correct. (TGT-53054)

+++

**Compositeur d’expérience d’après les formulaires**

+++Voir les détails
* Correction d’un problème dans le [!UICONTROL Form-Based Experience Composer] qui empêchait l’enregistrement des activités et déclenchait le message d’erreur : « Impossible de lire les propriétés de l’objet non défini (lecture d’un « mappage ») ». (TGT-53145)

+++

**Recommendations**

+++Voir les détails
* Correction d’un problème en raison duquel cliquer sur un produit dans [!UICONTROL Catalog Search] affichait l’erreur « Échec de la récupération des détails du produit » et ouvrait une boîte de dialogue modale sans option de fermeture. (TGT-53082)
* Correction d’un problème en raison duquel les [recommandations en tant qu’offres](/help/main/c-recommendations/recommendations-as-an-offer.md) dans les activités [!UICONTROL A/B Test] n’étaient pas correctement mises à jour lors de la modification des collections ou des promotions. (TGT-52884)
* Correction d’un problème dans l’environnement de production en raison duquel le fait de cliquer sur une entité dans l’interface utilisateur mise à jour affichait l’erreur : « Échec de la récupération des détails du produit. Contactez [!DNL Adobe Client Care] si ce problème persiste. » (TGT-53071)

+++

**Rapports**

+++Voir les détails
* Correction d’un problème en raison duquel l’enregistrement des détails de commande dans un fichier CSV générait un fichier vide. (TGT-52225)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++Voir les détails
* Correction d’un problème sur la page [!UICONTROL Goals & Settings] en raison duquel les sélecteurs utilisés dans plusieurs expériences n’étaient pas systématiquement mis en surbrillance comme sélectionnés. (TGT-53062)
* Correction d’un problème qui empêchait la modification des activités et déclenchait le message d’erreur : « Impossible de lire les propriétés de l’objet non défini (lecture d’un « mappage ») ». (TGT-53161)

+++

**Workspaces**

+++Voir les détails
* Amélioration de la gestion des offres ad hoc lors du changement d’espace de travail.
   * Lorsque vous passez de l’espace de travail par défaut à un espace de travail non par défaut (ou entre des espaces de travail non par défaut), les offres ad hoc sont désormais correctement copiées. Lors de l’initialisation, le contexte de l’espace de travail est mis à jour et un nouvel identifiant est attribué à l’offre afin d’en assurer l’unicité.
   * Aucune modification ne se produit lorsque vous restez dans le même espace de travail. (TGT-53079)
* Correction d’un problème qui empêchait les clients de [copier des activités entre différents espaces de travail](/help/main/c-activities/edit-activity.md#section_45A92E1DD3934523B07E71EF90C4F8B6). (TGT-52753 et TGT-47094)
* Correction d’un problème lors de la modification des propriétés entre les espaces de travail.
   * Lorsque vous passez de l’espace de travail par défaut à un espace de travail autre que celui par défaut, si la propriété actuelle existe dans l’espace de travail de destination, la propriété est conservée.
   * Si la liste [!UICONTROL Properties] affiche un avertissement (susceptible d’indiquer que certaines propriétés peuvent ne pas être compatibles) et que le client clique sur [!UICONTROL Add] ou [!UICONTROL Remove] puis sur [!UICONTROL Save], toutes les propriétés qui ne se trouvent pas dans l’espace de travail de destination sont supprimées. Si le client clique sur [!UICONTROL Cancel], toutes les propriétés restent, même si elles n’existent pas dans l’espace de travail de destination. (TGT-47094)
   * Si vous restez dans le même espace de travail ou passez d’un espace de travail non par défaut à l’espace par défaut ou à un autre espace de travail, tout reste tel quel. (TGT-53078)
* Mise à jour de la logique de validation des entités pour respecter le contexte d’espace de travail original de l’activité. Les entités telles que les [!UICONTROL Experience Fragments] (XF) sont désormais validées en fonction de l’espace de travail dans lequel l’activité a été créée à l’origine. Par exemple, si un fichier XF existe dans l’espace de travail par défaut et que l’activité est copiée de l’espace de travail X vers l’espace de travail Y, la validation est toujours effectuée tant que le fichier XF est valide dans l’espace de travail d’origine (par défaut). (TGT-53196)
* Amélioration de la prise en charge de la copie d’audiences ad hoc lors de la duplication des activités.
   * Les audiences ad hoc, y compris les mesures, les rapports, les pages et les types d’activités uniquement, sont désormais automatiquement copiées dans les scénarios suivants :
      * Lors de la copie d’une activité de l’espace de travail par défaut vers un espace de travail non par défaut.
      * Lors de la copie d’une activité dans le même espace de travail. (TGT-53197)

+++

## [!DNL Target Standard/Premium] 25.7.1 (samedi 11 juillet 2025)

En raison de problèmes récents identifiés, principalement liés à des personnalisations client complexes, cette version comprend les correctifs et mises à jour suivants :

**Activités**

+++Voir les détails
* Correction d’un problème en raison duquel l’URL [!UICONTROL Activity QA] incluait un paramètre de requête inutile : `at_preview_evaluate_as_true_audience_ids`. (TGT-52907)
* Correction d’un problème en raison duquel les URL de prévisualisation incluaient incorrectement des audiences supplémentaires au-delà de celle explicitement saisie par l’utilisateur. Ce comportement a été corrigé afin de garantir que seule l’audience spécifiée est appliquée lors de la génération d’un lien d’assurance qualité ou de prévisualisation. (TGT-52912)
* Correction d’un problème qui empêchait les utilisateurs de créer des activités [!UICONTROL Auto-Target] (AT) si [!UICONTROL Auto-Allocate] (AA) était sélectionné en premier lors de la configuration de l’affectation du trafic. Ce problème entraînait une erreur de validation du serveur principal et empêchait l’enregistrement de l’activité. (TGT-53096)

+++

**Audiences**

+++Voir les détails
* Correction d’un problème en raison duquel les utilisateurs dotés du rôle [!UICONTROL Approver] ne pouvaient pas ajouter ou enregistrer les améliorations d’audience d’activité uniquement. Toute tentative de ce type a provoqué une erreur 403 Interdit, indiquant que le privilège « [editor] » était requis, même si l’utilisateur disposait des autorisations suffisantes pour approuver et gérer les activités. (TGT-52984)
* Correction d’un problème en raison duquel une audience spécifique à une activité était supprimée à l’aide de l’option [!UICONTROL Remove Audience Refinement], l’audience n’apparaissait plus dans la liste des audiences pour être resélectionnée au sein de la même activité. Ce comportement empêchait les utilisateurs d’ajouter à nouveau la même audience, sauf si elle était recréée à partir de zéro. (TGT-52979)
* Correction d’un problème en raison duquel les améliorations d’audience d’activité unique disparaissaient de l’interface utilisateur immédiatement après avoir été supprimées d’un emplacement, avant même que l’activité ne soit enregistrée. Ce comportement est en contradiction avec la fonctionnalité attendue et le guide d’info-bulle, qui indique : « Toutes les audiences inutilisées de cette bibliothèque seront supprimées une fois l’activité enregistrée ». (TGT-52982)
* Correction d’un problème lors de la tentative d’affectation d’une audience autre que [!UICONTROL All Visitors] à une activité. Lors de l’enregistrement, le message d’erreur suivant s’affichait : « Nous ne pouvons pas terminer votre demande. Contactez [!UICONTROL Adobe Client Care] si le problème persiste. » (TGT-53008)
* Correction d’un problème qui empêchait l’enregistrement d’une activité après la création et l’affectation d’une nouvelle audience dans l’éditeur d’activités. Le message d’erreur affiché était le suivant : « Nous ne pouvons pas traiter votre demande. Contactez [!UICONTROL Adobe Client Care] si le problème persiste. » (TGT-52977)

+++

**[!UICONTROL Analytics for Target](A4T)**

+++Voir les détails
* Correction d’un problème en raison duquel la copie d’une activité existante et la modification de la source de création de rapports en [!DNL Adobe Analytics] (A4T) entraînaient une erreur « Entrée utilisateur non valide ». L’erreur a été déclenchée lorsque certaines actions de mesures incompatibles avec les rapports [!DNL Analytics], telles que `restart_same_experience`, `restart_random_experience` et `restart_new_experience`, ont été conservées dans l’activité d’origine. (TGT-52900)
* Correction d’un problème qui empêchait les clients de créer ou d’enregistrer une activité lors de la sélection de [!DNL Adobe Analytics] (A4T) comme source de création de rapports à l’étape [!UICONTROL Goals & Settings]. Le problème s’est produit spécifiquement lors de la sélection d’une mesure [!UICONTROL Custom Event] (par exemple, « Événement personnalisé 16 »), ce qui a entraîné l’erreur suivante : « Entrée utilisateur non valide ». (TGT-52910)
* Correction d’un problème en raison duquel le fait de cliquer sur le lien « [!UICONTROL View in Analytics] » redirigeait les utilisateurs vers la page d’accueil plutôt que vers le tableau de bord [!DNL Analytics] prévu. (TGT-53092 et TGT-53093)
  <!-- * Fixed an issue when cloning an existing activity and changing the reporting source from [!DNL Target] to [!DNL Adobe Analytics], users encounter a "400 - Invalid User Input" error, preventing the activity from being saved. (TGT-52875)-->
* Correction d’un problème lors de l’affichage d’une activité [!DNL Recommendations] dans l’interface utilisateur de [!UICONTROL Overview] mise à jour. Le chargement de la section [!UICONTROL Goals & Settings] échouait lorsque [!DNL Adobe Analytics] (A4T) était sélectionné comme source de création de rapports. Le message d’erreur suivant s’affichait : « Un problème est survenu. Nous ne pouvons pas traiter votre demande. Si le problème persiste, contactez l’assistance clientèle Adobe. » (TGT-52999)

+++

**[!UICONTROL Experiences]et[!UICONTROL Offers]**

+++Voir les détails
<!-- * Fixed an issue where using the [!UICONTROL Manage Content] feature in [!UICONTROL Automated Personalization] (AP) activities caused the page to crash and remain blank. This issue occurred after clicking [!UICONTROL Done] in the content manager, particularly in activities created or edited in the updated UI. (TGT-53047)-->
* Correction d’un problème en raison duquel la fonction [!UICONTROL Manage Content] ne validait pas correctement l’état d’un emplacement après la suppression de toutes les options de contenu. Ce problème peut entraîner un comportement incohérent ou des erreurs lors de la tentative d’enregistrement ou de poursuite de la configuration de l’activité. (TGT-52801)
* Correction d’un problème en raison duquel les utilisateurs rencontraient une erreur « Entrée non valide » lors de l’ajout d’une nouvelle page et de la suppression d’éléments spécifiques dans différentes expériences. L’erreur est déclenchée par la génération de `LocalIds` en double lors de la manipulation des éléments, en particulier lors du passage d’une expérience à l’autre et de la modification des structures de page partagées. (TGT-52720)
* Correction d’un problème en raison duquel l’utilisation de la fonction [!UICONTROL Generate Adhoc Offer] entraînait l’affichage d’emplacements non définis dans le panneau [!UICONTROL Manage Content]. (TGT-53076 et TGT-53070)
* Clarification du comportement vis-à-vis du client selon lequel les modifications apportées à l’aide d’une offre HTML peuvent sembler manquantes lors de la navigation de la [!UICONTROL Targeting] étape à [!UICONTROL Experiences]. Pour ce client ou cette cliente, le site web affecté a généré dynamiquement plusieurs sélecteurs DOM qui ont changé à chaque chargement de page. Par conséquent, le sélecteur utilisé à l’origine pour la modification est introuvable lorsque l’éditeur est rouvert, ce qui fait que la modification semble manquante ou non valide. Ce scénario fonctionne comme prévu. Pour que les modifications soient conservées visuellement dans l’éditeur, il est recommandé aux clients d’utiliser des sélecteurs stables et cohérents, qui ne changent pas lors des rechargements de page. (TGT-52874)
* Correction d’un problème où la tentative de suppression ou de désactivation d’une offre qui faisait partie d’une expérience exclue déclenchait une erreur « Entrée utilisateur non valide ». Ce problème se produisait même si l’offre n’était pas activement utilisée dans les expériences incluses. (TGT-52917)

+++

**Compositeur d’expérience d’après les formulaires**

+++Voir les détails
* Correction d’un problème dans les activités basées sur des formulaires où la duplication d’une expérience et la modification du code personnalisé dans l’une des expériences dupliquées appliquaient involontairement ces modifications à toutes les expériences dupliquées. Chaque expérience conserve désormais son propre code personnalisé indépendamment après duplication. (TGT-51600)

+++

**Localisation**

+++Voir les détails
* Mise à jour des chaînes de localisation dans la nouvelle interface utilisateur pour le français (fr_FR), l’allemand (de_DE), l’italien (it_IT), le coréen (ko_KO) et le chinois simplifié (zh_CN).

+++

**[!DNL Recommendations]**

+++Voir les détails
* Ajout d’un nouveau flux de [!DNL Recommendations] [statut](/help/main/c-recommendations/c-products/feeds.md#status) : [!UICONTROL Partial Import Failed]. (KB-2215)
* Correction d’un problème affectant le workflow de création d’activité lors de l’ajout de [!DNL Recommendations] avec [!UICONTROL promotions]. Lorsque les utilisateurs sélectionnaient « [!UICONTROL Promote by Attribute] » et ajoutaient une règle de filtrage (par exemple, [!UICONTROL Parameter Matching]), le type de règle et les valeurs d’opérande sélectionnés n’étaient pas conservés après l’enregistrement et la modification de l’activité. Lors de la réouverture, le type de règle de filtrage change de manière inattendue et les valeurs d’opérande sont manquantes. (TGT-53059)
* Correction d’un problème dans l’interface utilisateur de [!DNL Recommendations] en raison duquel toute promotion créée avec une seule règle était incorrectement interprétée et affichée comme un type de promotion « Liste d’éléments », quelle que soit la logique de la règle. (TGT-53063)
* Correction d’un problème lors de l’utilisation de l’interface utilisateur [!UICONTROL Overview] mise à jour, le bouton « [!UICONTROL Download Recommendations Data] » était manquant pour les activités [!UICONTROL Experience Targeting] (XT) qui incluent [!DNL Recommendations]. (TGT-52730 et TGT-52756)
* Auparavant, l’interface utilisateur de Recommendations affichait uniquement le nombre d’entités importées à partir d’un flux. Cependant, le format du message principal inclut à la fois le nombre d’entités importées et le nombre total d’entités au format : `# of entities imported / # of total entities`. En raison de cette incohérence, les utilisateurs ne voyaient que la première valeur (nombre importé) dans l’interface utilisateur, ce qui entraînait une confusion. L’interface utilisateur affiche désormais les deux nombres. (TGT-53073)
* Correction d’un problème en raison duquel les clients ne pouvaient pas enregistrer de règle de filtrage lors de la configuration d’une promotion « [!UICONTROL Promote by attribute] » dans une activité A/B basée sur des formulaires avec des recommandations. Après avoir enregistré et rouvert l’activité, la règle de filtrage était manquante et l’activité n’a pas pu être enregistrée correctement. (TGT-53057)

+++

**Rapports**

+++Voir les détails
* Correction d’un problème en raison duquel la sélection de « [!UICONTROL Export order details to CSV] » dans la page [!UICONTROL Reports] entraînait le téléchargement d’un fichier vide. Ce problème se produisait même lorsque des données de commande valides étaient présentes dans l’activité. (TGT-52225)
* Correction d’un problème lors de la tentative d’enregistrement d’une activité après la création et l’affectation d’une nouvelle audience de rapport. Le message d’erreur renvoyé était le suivant : « Accès refusé. Pour effectuer cette opération, tous les privilèges suivants sont requis : [éditeur]. » Ce problème se produisait malgré l’accès de l’utilisateur au niveau de l’approbateur. (TGT-53103)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++Voir les détails
* Correction d’un problème où l’application d’une modification à une vue entraînait la duplication de la vue et le renvoi d’une erreur « Entrée utilisateur non valide » par l’activité. Ce correctif garantit que les modifications d’affichage sont appliquées correctement sans déclencher de duplication ou d’erreurs de validation. (TGT-52886)
* Correction d’un problème en raison duquel les modifications du code personnalisé s’affichaient incorrectement pour une expérience incorrecte. Plus précisément, les modifications destinées à une expérience ont été présentées dans une expérience différente, ce qui a entraîné une confusion et une mauvaise configuration potentielle des activités en direct. (TGT-52776)
* Correction d’un problème qui empêchait la modification ou l’enregistrement des modifications de code personnalisé dans la nouvelle interface utilisateur du VEC. Plus précisément :

   * Après modification d’un bloc de code personnalisé et enregistrement, les modifications n’étaient pas répercutées dans l’interface utilisateur ou dans l’aperçu de l’assurance qualité.
   * Dans certains cas, les modifications ne pouvaient pas être supprimées à moins que l’activité ne soit fermée et rouverte.
   * Pour pallier ce problème, les utilisateurs devaient copier le code, supprimer la modification et le recréer manuellement avec le contenu mis à jour. (TGT-53072)

* Correction d’un problème en raison duquel la modification et l’enregistrement du code personnalisé provoquaient une perte de réponse du panneau [!UICONTROL Modifications]. (TGT-53075)
* Correction d’un problème en raison duquel les modifications apportées au code personnalisé dans les variantes d’expériences étaient involontairement répercutées dans l’expérience [!UICONTROL Control]. Cela a provoqué des changements inattendus dans le comportement de la diffusion. L’expérience [!UICONTROL Control] reste désormais isolée des modifications de code personnalisé apportées à d’autres expériences. (TGT-52413)
* Correction d’un problème où les modifications apportées à une expérience (par exemple, l’expérience B) étaient involontairement dupliquées vers une autre expérience (expérience A) si l’utilisateur cliquait sur la deuxième expérience avant que l’éditeur ne soit complètement chargé. Ce comportement peut également entraîner la perte des modifications si l’expérience sélectionnée initialement n’a pas été modifiée. (TGT-52597)
* Correction d’un problème en raison duquel les modifications apportées à l’étape [!UICONTROL Modifications] de la création d’activités n’étaient pas enregistrées de manière cohérente. Dans certains cas, une fois toutes les étapes terminées et que vous avez cliqué sur [!UICONTROL Save], le script personnalisé ajouté à la section [!UICONTROL Modifications] n’est pas reflété sur le site actif, bien qu’aucune erreur visible n’ait été rencontrée pendant le processus d’enregistrement. (TGT-52661)
* Correction d’un problème en raison duquel les modifications du code personnalisé n’étaient pas enregistrées correctement et étaient involontairement mises en miroir sur plusieurs expériences au sein de la même activité. En outre, les utilisateurs rencontraient des problèmes d’accès lors de l’ouverture ou de l’actualisation de certaines activités, ce qui entraînait des écrans vierges. Ces problèmes ont été résolus afin d’assurer une modification d’activité stable et une isolation d’expérience précise. (TGT-52594)
* Correction d’un problème en raison duquel les utilisateurs ne pouvaient pas accéder à une autre URL en [!UICONTROL Browse Mode]. Cela empêchait les testeurs et les éditeurs de valider ou de prévisualiser d’autres pages dans la même session d’activité. (TGT-53052)
* Correction d’un problème où plusieurs instances [!UICONTROL Visual Experience Composer] (VEC) s’ouvraient simultanément lors de la création de l’activité. Ce problème se produisait lorsque les utilisateurs désactivaient le [!UICONTROL Enhanced Experience Composer] (EEC) et supprimaient la barre oblique de fin de l’URL du site web à l’étape [!UICONTROL Page Delivery]. (TGT-52782)
* Correction d’un problème en raison duquel la liste déroulante des mesures de [!UICONTROL Revenue] de l’étape de [!UICONTROL Goals & Settings] était incorrectement définie par défaut sur [!UICONTROL Revenue per Visit] (RPVISIT), même après la sélection d’une autre mesure par l’utilisateur.  Le problème s’est produit lors de la réduction et du développement du panneau de configuration des mesures, entraînant la réinitialisation de la valeur sélectionnée précédemment. (TGT-52811 et TGT-52878)
* Correction de plusieurs problèmes dans le workflow de création d’activités liés à la dénomination des offres et à la traduction du contenu dans les activités [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Multivariate Testing] (MVT) :

  Principales questions abordées :

   * La création de plusieurs offres HTML portant le même nom (par exemple, « Expérience ») a déclenché une erreur « Les noms d’offres en double ne sont pas autorisés », mais l’interface utilisateur n’indiquait pas clairement quelles offres étaient à l’origine du conflit.
   * Le changement de nom des offres par le biais du panneau de droite a mis à jour le nom dans l’interface utilisateur, mais la modification n’a pas été répercutée dans l’onglet [!UICONTROL Manage Content] ou l’onglet [!UICONTROL Offers] , ce qui entraîne des erreurs de validation persistantes.
   * Dans les activités MVT, bien que l’erreur de nom en double n’ait pas persisté après le changement de nom, l’interface utilisateur ne reflétait toujours pas les noms d’offre mis à jour de manière cohérente dans les onglets. (TGT-52933)

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
