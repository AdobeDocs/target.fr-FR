---
keywords: notes de mise à jour;versions;mises à jour;futures versions;améliorations;nouvelles fonctionnalités;correctifs;mises à jour;version préliminaire;accès anticipé
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version de [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 065220af5c8e3b6cc25ef7289d006a901d2e932a
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 15%

---

# Notes de mise à jour de [!DNL Target] (version préliminaire)

Cet article contient des informations sur les prochaines versions d’[!DNL Adobe Target], y compris les SDK, les API et les bibliothèques JavaScript.

**Dernière mise à jour : 22 juillet 2025**

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
* Ajout d’un nouveau point d’entrée d’API qui permet aux utilisateurs de restaurer des options d’activité supprimées précédemment d’une base de données secondaire. Cette fonctionnalité tire parti de l’infrastructure existante fournie par les classes `RemovedCampaignElements` et `RemovedOptionInfo`, assurant ainsi une réintégration transparente des options supprimées dans les activités actives. (TGT-52903)
* Correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour en raison duquel les offres supprimées dans les activités [!UICONTROL Automated Personalization] (AP) s’affichaient sous la forme `Deleted option with ID: X` au lieu de leurs noms d’origine (par exemple, `Offer Name [Deleted]` comme indiqué dans l’interface utilisateur héritée). Ce correctif restaure l’étiquetage significatif pour les offres supprimées, améliorant ainsi la clarté et rendant les rapports plus précis et plus conviviaux. (TGT-52921)
* Correction d’un problème dans la couche de persistance du serveur principal en raison duquel les options supprimées étaient correctement stockées, mais non accessibles via les points d’entrée de l’API existants. Par conséquent, les applications frontales ne pouvaient pas récupérer de noms significatifs pour les options supprimées, ce qui affectait les vues de rapports historiques. Ce correctif garantit que les données des options supprimées conservées peuvent désormais être correctement affichées dans l’interface utilisateur. (TGT-52973)
* Correction d’un problème en raison duquel certaines activités migrées du système frontal de Target vers le système central présentaient des configurations de mesures incohérentes en raison d’un bug de synchronisation précédemment corrigé. Plus précisément, les activités qui utilisaient à l’origine une mesure de conversion et qui ont ensuite été mises à jour vers une mesure basée sur les analyses conservaient des valeurs obsolètes dans les champs `primaryMetricType` et `successCriteria`. (TGT-52643)

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
* Correction d’un problème en raison duquel les activités [!DNL Recommendations] contenant des noms de mesures de plus de 25 caractères ne pouvaient pas être ouvertes ni modifiées en raison des limitations de l’API. Ce correctif garantit la compatibilité avec les noms de mesures dépassant la limite de caractères et restaure un accès complet aux activités affectées. (TGT-52839)
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

* Mise en œuvre d’un nouveau point d’entrée de migration pour prendre en charge le transfert des options d’activité supprimées des activités basées sur JCR vers [!DNL Target] Central. Cette fonctionnalité permet un suivi et des rapports cohérents entre les systèmes. Cette fonctionnalité garantit que les options supprimées sont préservées et synchronisées sur le serveur frontal et le serveur principal [!DNL Target], ce qui améliore les rapports historiques et l’intégrité des données. (TGT-53217)

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

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
