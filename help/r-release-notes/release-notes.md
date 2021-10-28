---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifsde bogues
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Quelles nouvelles fonctionnalités sont incluses dans la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 9f2947355c3857add5ea47d41c1adc2e3e8bba08
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 41%

---

# Notes de mise à jour de Target (actualisées)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API, les SDK, le [!DNL Adobe Experience Platform Web SDK] et la bibliothèque at.js de Target, et ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

>[!IMPORTANT]
>
>**Fin de vie de mbox.js** : depuis le 31 mars 2021, la bibliothèque mbox.js n’est plus prise en charge par [!DNL Adobe Target]. Après le 31 mars 2021, tous les appels effectués à partir de mbox.js échoueront et auront une influence sur vos pages qui comportent des activités [!DNL Target] qui s’exécutent en diffusant le contenu par défaut.
>
>Migrez vers la version la plus récente du nouveau [!DNL Adobe Experience Platform Web SDK] ou vers la bibliothèque JavaScript at.js afin dʼéviter tout problème potentiel avec vos sites. Pour plus d’informations, consultez [Aperçu : implémentation de Target pour le Web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].)

## [!DNL Target Standard/Premium] 21.10.4 (21 octobre 2021)

Cette version de maintenance comprend les améliorations suivantes :

| Fonctionnalité | Détails |
| --- | --- |
| Recommendations au panier | Ajout d’une nouvelle famille d’algorithmes pour fournir des recommandations basées sur le contenu du panier du visiteur.<br>Pour plus d’informations, voir &quot;Basé sur le panier&quot; dans [Création de critères](/help/c-recommendations/c-algorithms/create-new-algorithm.md) et &quot;Ajouts au panier/consultations de panier/pages de passage en caisse&quot; et &quot;Exclure les articles déjà dans le panier du visiteur&quot; dans [Planification et implémentation de Recommendations](/help/c-recommendations/plan-implement.md). |

## [!DNL Target Standard/Premium] 21.10.3 (19 octobre 2021)

Cette version de maintenance comprend les améliorations, modifications et correctifs suivants :

* Correction de problèmes qui empêchaient les clients d’ouvrir la variable [!UICONTROL A4T] dans [!DNL Analysis Workspace] en cliquant sur le bouton [!UICONTROL Afficher dans Analytics] bouton dans [!DNL Target] rapports d’activité. (TGT-42099, TGT-42100)
* Correction d’un problème en raison duquel la variable [!UICONTROL Modifier la conception] bouton pour ne pas afficher lors de la modification [!UICONTROL Test A/B] et [!UICONTROL Ciblage d’expérience] (XT) à l’aide de la fonction [!UICONTROL Compositeur d’expérience d’après les formulaires]. (TGT-41980)
* Correction d’un problème qui empêchait la variable [!UICONTROL Compatible] de l’affichage d’une case à cocher dans la sélection de critères lors de la création d’un [!UICONTROL Recommendations] activité. (TGT-42053)
* Correction d’un message d’erreur incorrect qui s’affichait lorsqu’il n’était pas possible de sélectionner [!DNL Analytics] comme source des rapports (A4T) en raison d’un manque de [!DNL Analytics] autorisations. (TGT-41954)
* Mise en oeuvre de plusieurs correctifs d’accessibilité afin d’améliorer la navigation au clavier [!DNL Target] Interface utilisateur.

## [!DNL Target Standard/Premium] 21.10.2 (13 octobre 2021)

Les améliorations suivantes ont été apportées à l’utilisation de [!DNL Target] [!UICONTROL Audiences] avec le [!DNL Adobe Experience Platform Web SDK]:

* Ajout d’icônes d’avertissement, de fenêtres contextuelles et de messages à différents emplacements dans le [!DNL Target] Interface utilisateur pour indiquer que l’audience a été supprimée à la source et n’est plus disponible dans [!DNL Target] activités.

   Les illustrations suivantes présentent certains des emplacements d’affichage des icônes, des fenêtres contextuelles et des messages :

   * [!UICONTROL Activité] page de liste

      ![Audience supprimée dans le message source sur la page de liste des activités](assets/deleted-at-source-audiences-list.png)

   * Activité [!UICONTROL Présentation] pages :

      ![Audience supprimée dans le message source sur la page d’aperçu](assets/deleted-at-source-overview.png)

   * [!UICONTROL Expériences] de l’étape du workflow de création d’activité :

      ![Audience supprimée au niveau du message source sur [!UICONTROL Expériences] page](assets/deleted-at-source-experiences.png)

   * [!UICONTROL Ciblage] de l’étape du workflow de création d’activité :

      ![Audience supprimée au niveau du message source sur [!UICONTROL Ciblage] page](assets/deleted-at-source-targeting.png)

   * [!UICONTROL Objectifs et paramètres] de l’étape du workflow de création d’activité :

      ![Audience supprimée au niveau du message source sur la [!UICONTROL Objectifs et paramètres] page](assets/deleted-at-source-goals-settings.png)

   * Amélioration de l’audience ([!UICONTROL Remplacer l’audience] sur le [!UICONTROL Ciblage] (étape du workflow de création de l’activité) :

* Si vous tentez d’utiliser la fonction Combiner les audiences et que l’une des audiences a été supprimée à la source, [!UICONTROL Enregistrer] est désactivée.

## [!DNL Target Standard/Premium] 21.10.1 (6 octobre 2021)

Cette version comprend les nouvelles fonctionnalités suivantes :

| Fonctionnalité | Détails |
| --- | --- |
| [!UICONTROL Actualisation de l’interface utilisateur d’Audiences] | Dans le cadre de la [!DNL Adobe Target] Effort continu de l’équipe pour améliorer l’expérience utilisateur pour [!DNL Target] pour les utilisateurs, cette version actualise la variable [!UICONTROL Audiences] et [!UICONTROL Scripts de profil] dans les [!DNL Target] Interface utilisateur. Cette mise à jour unifie et normalise les modèles de conception précédemment incohérents, tout en ajoutant de nouvelles améliorations, telles que :<ul><li>la possibilité de sélectionner et de supprimer plusieurs audiences simultanément ;</li><li>Actualisé [conception du créateur d’audiences](/help/c-target/c-audiences/create-audience.md)</li><li>Prise en charge des règles d’exclusion dans [!UICONTROL Audience] créateur de règles de bibliothèque</li><li>Un nouveau filtre &quot;Source d’audience&quot;, pour permettre une découverte d’audience plus rapide</li><li>Options de recherche persistante et de filtrage de session</li></ul>Pour plus d’informations, consultez [Audiences](/help/c-target/target.md).<br>**REMARQUE**: La nouvelle [!UICONTROL Audiences] L’interface utilisateur est disponible uniquement pour sélectionner des clients. La mise à jour sera progressivement déployée pour tous les clients à partir de janvier 2022. |
| [!UICONTROL Scripts de profil] Actualisation de l’interface utilisateur | Le [!UICONTROL Scripts de profil] La bibliothèque a également été mise à jour. Elle comprend une interface actualisée ainsi que plusieurs mises à jour de productivité :<ul><li>La possibilité de sélectionner et de supprimer plusieurs scripts de profil simultanément</li><li>Un nouvel éditeur de code pour les scripts de profil</li><li>Mise en surbrillance de la syntaxe et vérification des erreurs dans l’éditeur de code</li><li>Saisie automatique des jetons (paramètres de mbox ou de profil) à l’aide de raccourcis clavier</li></ul>Pour plus d’informations, voir [Profils de visiteur](/help/c-target/c-visitor-profile/visitor-profile.md).<br>**REMARQUE**: La nouvelle [!UICONTROL Scripts de profil] L’interface utilisateur est disponible uniquement pour sélectionner des clients. La mise à jour sera progressivement déployée pour tous les clients à partir de janvier 2022. |
| ![Badge Premium](/help/assets/premium.png) Création et modification de critères Recommendations | Le [!UICONTROL Critères Recommendations] le processus de création et de modification a été simplifié afin de simplifier le choix de l’algorithme de recommandations et des paramètres appropriés pour atteindre vos objectifs.<br>Pour plus d’informations, voir [Création de critères](/help/c-recommendations/c-algorithms/create-new-algorithm.md). |
| ![Badge Premium](/help/assets/premium.png) Amélioration de l’intervalle de recherche en amont de Recommendations et du taux d’actualisation de l’algorithme | Vous pouvez désormais exécuter les algorithmes &quot;Les plus consultés&quot; et &quot;Meilleurs vendeurs&quot; avec une période de recherche arrière de six heures pour capturer le contenu qui est en tendance dernièrement. Lorsque l’intervalle de recherche en amont de six heures est sélectionné, les résultats de vos recommandations sont mis à jour toutes les 3 à 6 heures toute la journée.<br>Pour plus d’informations, voir [Source de données](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source) in *Création de critères*. |

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| Modifications de la documentation | Obtenez des informations détaillées sur les mises à jour apportées à ce guide qui ne sont pas incluses dans les notes de mise à jour.<br>Pour plus d’informations, voir [Modifications de la documentation](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notes de mise à jour pour les versions antérieures | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium.<br>Pour plus d’informations, voir [Notes de mise à jour des versions précédentes](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Notes de mise à jour d’Adobe Experience Cloud | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud.<br>Pour plus d’informations, consultez [Notes de mise à jour d’Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr). |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| Mise à jour prioritaire des produits Adobe | Pour recevoir des notifications avancées sur les améliorations à venir des produits Target et d’autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour produit prioritaire Adobe :<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Notes de mise à jour à venir | Pour plus d’informations sur les versions de Target du mois en cours, notamment les informations de version préliminaire, voir la page [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md). |
