---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifsde bogues
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Quelles nouvelles fonctionnalités sont incluses dans la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 7cb6baeb7ef9e9cf0efb76866a3eae8dfd38af34
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 44%

---

# Notes de mise à jour de Target (actualisées)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API, les SDK, le [!DNL Adobe Experience Platform Web SDK] et la bibliothèque at.js de Target, et ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

>[!IMPORTANT]
>
>**Fin de vie de mbox.js** : depuis le 31 mars 2021, la bibliothèque mbox.js n’est plus prise en charge par [!DNL Adobe Target]. Après le 31 mars 2021, tous les appels effectués à partir de mbox.js échoueront et auront une influence sur vos pages qui comportent des activités [!DNL Target] qui s’exécutent en diffusant le contenu par défaut.
>
>Migrez vers la version la plus récente du nouveau [!DNL Adobe Experience Platform Web SDK] ou vers la bibliothèque JavaScript at.js afin dʼéviter tout problème potentiel avec vos sites. Pour plus d’informations, consultez [Aperçu : implémentation de Target pour le Web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].)

## [!DNL Target Standard/Premium] 21.10.3 (19 octobre 2021)

Cette version de maintenance comprend les améliorations, modifications et correctifs suivants :

* Correction de problèmes empêchant les clients d’ouvrir le fichier [!UICONTROL A4T] dans [!DNL Analysis Workspace] en cliquant sur le bouton [!UICONTROL Affichage dans Analytics] bouton dans [!DNL Target] rapports d&#39;activités. (TGT-42099, TGT-42100)
* Correction d’un problème qui provoquait le [!UICONTROL Modifier la conception] bouton à ne pas afficher lors de la modification [!UICONTROL Test A/B] et [!UICONTROL Ciblage d’expérience] (XT) à l&#39;aide de la [!UICONTROL Compositeur d’expérience basé sur des formulaires]. (TGT-41980)
* Correction d’un problème qui empêchait la [!UICONTROL Compatible] case à cocher d’affichage dans la sélection de critères lors de la création d’un [!UICONTROL Recommendations] activité. (TGT-42053)
* Correction d’un message d’erreur incorrect qui s’affichait lorsque vous ne pouviez pas sélectionner [!DNL Analytics] comme source de déclaration (A4T) en raison d&#39;un manque de [!DNL Analytics] autorisations. (TGT-41954)
* Mise en oeuvre de plusieurs correctifs d’accessibilité pour améliorer la navigation au clavier dans l’ensemble du [!DNL Target] Interface utilisateur.

## [!DNL Target Standard/Premium] 21.10.2 (13 octobre 2021)

Les améliorations suivantes ont été ajoutées lors de l’utilisation [!DNL Target] [!UICONTROL Audiences] avec la [!DNL Adobe Experience Platform Web SDK]:

* Ajout d’icônes d’avertissement, de fenêtres contextuelles et de messages à divers endroits dans le fichier [!DNL Target] Interface utilisateur pour indiquer que l’audience a été supprimée à la source et n’est plus disponible pour une utilisation dans [!DNL Target] activités.

   Les illustrations suivantes montrent certains des endroits où les icônes, les fenêtres contextuelles et les messages s’affichent :

   * [!UICONTROL Activité] page de liste

      ![Public supprimé au message source sur la page de liste Activités](assets/deleted-at-source-audiences-list.png)

   * Activité [!UICONTROL Présentation] pages :

      ![Public supprimé au message source sur la page de présentation](assets/deleted-at-source-overview.png)

   * [!UICONTROL Expériences] étape du processus de création d&#39;activité :

      ![Public supprimé au message source sur [!UICONTROL Expériences] page](assets/deleted-at-source-experiences.png)

   * [!UICONTROL Ciblage] étape du processus de création d&#39;activité :

      ![Public supprimé au message source sur [!UICONTROL Ciblage] page](assets/deleted-at-source-targeting.png)

   * [!UICONTROL Objectifs et paramètres] étape du processus de création d&#39;activité :

      ![Public supprimé au message source sur [!UICONTROL Objectifs et paramètres] page](assets/deleted-at-source-goals-settings.png)

   * Améliorations du public ([!UICONTROL Remplacer le public] sur [!UICONTROL Ciblage] étape du processus de création d&#39;activité) :

* Si vous tentez d’utiliser la fonction Combiner les publics et qu’un public a été supprimé à la source, [!UICONTROL Enregistrer] est désactivé.

## [!DNL Target Standard/Premium] 21.10.1 (6 octobre 2021)

Cette version comprend les nouvelles fonctionnalités suivantes :

| Fonctionnalité | Détails |
| --- | --- |
| [!UICONTROL Audiences] Actualisation de l’interface utilisateur | En tant que composant du noeud [!DNL Adobe Target] effort continu de l&#39;équipe pour améliorer l&#39;expérience utilisateur pour [!DNL Target] utilisateurs, cette version actualise la [!UICONTROL Audiences] et [!UICONTROL Scripts de profil] dans la boîte de dialogue [!DNL Target] Interface utilisateur. Cette mise à jour unifie et normalise les modèles de conception qui étaient auparavant incohérents, tout en ajoutant de nouvelles améliorations, telles que :<ul><li>Possibilité de sélectionner et de supprimer plusieurs publics simultanément</li><li>Une [design du générateur d’audience](/help/c-target/c-audiences/create-audience.md)</li><li>Prise en charge des règles d’exclusion dans le noeud [!UICONTROL Public] créateur de règles de bibliothèque</li><li>Un nouveau filtre &quot;Source de l’audience&quot;, pour permettre une découverte plus rapide de l’audience</li><li>Options de recherche permanente et de filtre de session</li></ul>Pour plus d’informations, consultez [Audiences](/help/c-target/target.md).<br>**NOTE**: Le nouveau [!UICONTROL Audiences] L’interface utilisateur a été temporairement désactivée pour tous les clients, à l’exception de ceux qui se trouvent actuellement dans un [!DNL Target] Programme bêta. Cette actualisation de l’interface utilisateur sera réactivée pour un sous-ensemble de clients le mardi 19 octobre et pour tous les clients restants le jeudi 21 octobre 2021. |
| [!UICONTROL Scripts de profil] Actualisation de l’interface utilisateur | Le [!UICONTROL Scripts de profil] a également été mise à jour et comprend une interface actualisée ainsi que plusieurs mises à jour de productivité :<ul><li>Possibilité de sélectionner et de supprimer plusieurs scripts de profil simultanément</li><li>Un nouvel éditeur de code pour les scripts de profil</li><li>Mise en surbrillance de la syntaxe et vérification des erreurs dans l’éditeur de code</li><li>Remplissage automatique des paramètres de jetons (mbox ou profile) à l’aide des raccourcis clavier</li></ul>Pour plus d’informations, voir [Profils des visiteurs](/help/c-target/c-visitor-profile/visitor-profile.md). |
| ![Pastille Premium](/help/assets/premium.png) Critères Recommendations : création et modification | Le [!UICONTROL Critères de Recommendations] le workflow de création et d’édition a été simplifié afin de simplifier le choix de l’algorithme et des paramètres de recommandations appropriés pour atteindre vos objectifs.<br>Pour plus d’informations, voir [Créer des critères](/help/c-recommendations/c-algorithms/create-new-algorithm.md). |
| ![Pastille Premium](/help/assets/premium.png) Amélioration de la fréquence de rafraîchissement de la fenêtre de lecture Recommendations et de l’algorithme | Vous pouvez désormais exécuter les algorithmes &quot;Les plus regardés&quot; et &quot;Les meilleurs vendeurs&quot; avec une fenêtre de rétrospection de six heures pour capturer le contenu qui est en tendance dernièrement. Lorsque la fenêtre de consultation de six heures est sélectionnée, les résultats de vos recommandations sont mis à jour toutes les 3 à 6 heures de la journée.<br>Pour plus d’informations, voir [Source de données](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source) dans *Créer des critères*. |

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
