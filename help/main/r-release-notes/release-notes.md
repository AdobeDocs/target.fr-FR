---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bugs;mises à jour;mises à jour actuelles
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 7d73870275c266055825c2fce90489ef82825fca
workflow-type: tm+mt
source-wordcount: '1700'
ht-degree: 17%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Découvrez les dernières fonctionnalités, améliorations et correctifs d’[!DNL Adobe Target]. Ces notes de mise à jour couvrent également les mises à jour des API [!DNL Target], des SDK, de la [!DNL Adobe Experience Platform Web SDK], d’at.js et d’autres composants de plateforme, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## Mises à jour sensibles à l’heure que vous devez connaître {#time-sensitive}

[!BADGE Important]{type=Informative}

Pour les mises à jour urgentes relatives à [!DNL Adobe Target] et à votre implémentation, [!DNL Adobe] fournit des notes de mise à jour détaillées et une documentation via [!UICONTROL Experience League]. Voici quelques points forts importants liés à votre implémentation :

### Obsolescence du bouton (bascule) de version de l’interface utilisateur [!DNL Target]

Pour plus d’informations, voir [[!DNL Target] FAQ sur la mise à jour de l’interface utilisateur](/help/main/c-intro/updated-ui-faq.md).

## [!DNL Target Standard/Premium] 25.10.1 (22 octobre 2025)

Cette version comprend les mises à jour et correctifs suivants :

**Activités**

+++ Afficher les détails
* **Résolution d’un problème d’utilisation dans l’interface utilisateur mise à jour**. [!UICONTROL Observers] pouvez désormais prévisualiser les activités à l’aide de l’option [!UICONTROL View Activity] , comme dans l’interface utilisateur héritée. (TGT-51741)
* **[!UICONTROL Observer]utilisateurs peuvent désormais afficher le contenu de l’activité dans l’interface utilisateur mise à jour.** Visibilité rétablie pour les utilisateurs dotés du rôle d’observateur dans l’interface utilisateur d’Activity mise à jour. Auparavant, les observateurs ne pouvaient pas afficher les modifications, les offres et les changements de contenu, une fonctionnalité disponible dans l’interface utilisateur héritée. (TGT-53785)
* **[!UICONTROL Approver]utilisateurs peuvent désormais modifier les objectifs des activités sans erreur de privilège d’éditeur.** Résolution d’un problème d’autorisations dans l’interface utilisateur de création d’activité qui empêchait les utilisateurs au niveau de l’approbateur d’enregistrer les modifications apportées aux paramètres d’objectif avancés. Les utilisateurs concernés ont reçu une erreur `403 Forbidden.Resource` nécessitant des privilèges d’éditeur, alors qu’ils disposaient d’un accès suffisant. (TGT-53819)

+++

**Audiences**

+++Afficher les détails
* **Sélection multi-audience restaurée dans les rapports « Cette activité uniquement ».** Correction d’un problème dans l’interface utilisateur de création d’activité qui empêchait les utilisateurs de sélectionner plusieurs audiences sous la section [!UICONTROL This activity only] dans [!UICONTROL Goals & Settings]. (TGT-53283)
* **Les graphiques de création de rapports basés sur les audiences affichent désormais correctement les données de conversion.** Correction d’un problème dans l’onglet [!UICONTROL Reports] en raison duquel les graphiques échouaient lors de la sélection d’audiences non par défaut. Bien que les données et les mesures de confiance soient disponibles, le graphique visuel ne présente qu’une ligne continue, ce qui rend l’analyse difficile. (TGT-53769)
* **L’interface utilisateur de [!UICONTROL Targeting] indique désormais clairement les règles d’audience exclues.** Correction d’un problème dans la section [!UICONTROL Targeting] de l’interface utilisateur de création d’activité où les règles d’audience définies sur [!UICONTROL Exclude] n’étaient pas clairement affichées. Cela entraînait une certaine confusion lors de la révision de la logique de ciblage, en particulier pour les audiences excluant des URL spécifiques. (TGT-53809)
* **Les valeurs de définition d’audience peuvent désormais être sélectionnées et copiées dans l’onglet [!UICONTROL Targeting] .** Correction d’un problème dans l’interface de création d’activité qui empêchait les utilisateurs de sélectionner et de copier les valeurs des règles d’audience dans l’onglet [!UICONTROL Targeting] . Cette fonctionnalité était disponible dans l’interface utilisateur héritée, mais elle était absente de l’interface utilisateur mise à jour. (TGT-53856)

+++

**Localisation**

+++Afficher les détails
* **Correction d’une erreur de traduction de « guillemet » dans le contexte de l’éditeur de page zh_CN.** Correction d’une erreur de traduction contextuelle dans le paramètre régional zh_CN où le terme « quote » était incorrectement traduit par « 报价 », ce qui sous-entendait un devis commercial. Dans la section Typographie > Style de titre > Guillemet-bloc , la signification prévue fait référence à un élément de mise en forme (le bloc de citation), et non à un prix. (TGT-53841)
* **Correction d’une erreur de traduction de « guillemet supprimé » dans le contexte de l’éditeur de page zh_CN.** Correction d&#39;une erreur de traduction dans le paramètre régional zh_CN où « devis supprimé » était incorrectement rendu comme « 移除了报价 », ce qui impliquait un devis commercial. Dans la section Typographie > Style de titre > Citation, le terme fait référence à un élément de mise en forme (le bloc de citation), et non à un prix. (TGT-53843)
* **Correction d’une erreur de traduction de « quote rearrangée » dans le contexte de l’éditeur de page zh_CN.** Correction d&#39;une erreur de traduction contextuelle dans le paramètre régional zh_CN où « quote rearrangée » était incorrectement traduite en « 重新排列了报价 », ce qui impliquait un devis commercial. Dans la section Typographie > Style de titre > Citation, le terme fait référence à un élément de mise en forme (le bloc de citation), et non à un prix. (TGT-53844)
* **Correction d’une erreur de traduction de « modification de guillemet » dans le contexte de l’éditeur de page zh_CN.** Correction d&#39;une erreur de traduction dans le paramètre régional zh_CN où le rendu de « cotation modifiée » était inexact comme « 更改了报价 », suggérant une cotation commerciale. Dans la section Typographie > Style de titre > Citation, le terme fait référence à un élément de mise en forme (le bloc de citation), et non à un prix. (TGT-53845)

+++

**Recommendations**

+++Afficher les détails
* Les modifications apportées au sélecteur CSS d’**pour Recommendations sont désormais correctement enregistrées.** Correction d’un problème dans l’interface utilisateur de création d’activité qui empêchait les utilisateurs de mettre à jour le sélecteur CSS pour les emplacements de recommandations. Annulation des modifications après l’enregistrement, bloquant les mises à jour des conteneurs de ciblage. (TGT-53835)
* La sélection de l’événement de chargement de page **persiste désormais dans les modifications de recommandation.** a résolu un problème dans l’interface utilisateur de création d’activité qui empêchait les utilisateurs d’enregistrer les modifications lors du changement de type d’événement d’une recommandation de [!UICONTROL View] à [!UICONTROL Page Load]. Bien que la sélection semble avoir réussi, elle est rétablie après avoir quitté l’application, bloquant la publication de l’activité. (TGT-53957)

+++

**Rapports**

+++Afficher les détails
* **« [!UICONTROL Export order details to CSV] » télécharge désormais les données complètes.** Correction d’un problème dans l’interface utilisateur de [!UICONTROL Overview] mise à jour qui entraînait le téléchargement de fichiers vides par l’option « [!UICONTROL Export Order details to CSV] », même en présence de données de rapport valides. (TGT-53787)

+++

**Sécurité**

+++Afficher les détails
* Ajout d’un préfiltre **IMS pour protéger les points d’entrée GQL de l’exposition des données inter-organisations.** Correction d’une vulnérabilité de sécurité dans l’onglet Admin qui affectait les points d’entrée GraphQL licenseGroups et targetProperties. Le problème provenait de l’utilisation de l’API JIL avec un jeton client d’administration qui pouvait être exploité pour accéder aux données de produit inter-organisations. (TGT-53837)

+++

**Compositeur d’expérience visuelle**

+++Afficher les détails
* **La stabilité de création a été restaurée dans l’interface utilisateur de création d’activité.** Correction d’un problème intermittent dans l’interface utilisateur du VEC en raison duquel la création échouait et les liens devenaient inopinément cliquables, redirigeant les utilisateurs et utilisatrices vers la page. (TGT-53153)
* **Modification restaurée pour les activités enregistrées dans l’interface utilisateur de création d’activité.** Correction d’un problème qui empêchait les utilisateurs de modifier les activités après avoir enregistré les modifications. Les activités affectées sont restées bloquées dans « [!UICONTROL Applying initial modifications] », bloquant les mises à jour supplémentaires et masquant le bouton [!UICONTROL Cancel] . (TGT-53631)
* **Le compositeur d’expérience visuelle ne se bloque plus sur « [!UICONTROL Applying initial modifications] ».** Correction d’un problème de performances dans le VEC qui entraînait de longs retards lors du chargement d’expériences avec un grand nombre de modifications. Les utilisateurs affectés ont vu l’interface utilisateur bloquée sur « [!UICONTROL Applying initial modifications] » pendant plusieurs minutes, en particulier dans les scénarios de l’expérience B. (TGT-53727)
* **Le compositeur d’expérience visuelle charge désormais les modifications sans éléments racine.**
Correction d’un problème dans le VEC en raison duquel les expériences se bloquaient lors du chargement de modifications sans élément racine clair. Ces modifications avaient auparavant pour effet de suspendre indéfiniment l’interface utilisateur sur « A [!UICONTROL pplying initial modifications] ». (TGT-53799)
* **L’enregistrement des modifications dans les activités fonctionne désormais comme prévu.** a résolu un problème lié aux autorisations dans la nouvelle interface utilisateur de création qui empêchait les utilisateurs d’enregistrer les modifications lors de la modification des objectifs et des paramètres avancés dans les activités . Un ruban d’erreur rouge et un message « Forbidden.Resource » s’affichaient pour les utilisateurs concernés, bien qu’ils disposaient des droits d’accès appropriés. (TGT-53816)
* L’interface utilisateur du compositeur d’expérience visuelle **conserve désormais les modifications d’expérience dans les vues.** Résolution de plusieurs problèmes dans le VEC mis à jour qui affectaient le développement de l’expérience. Les modifications ne persistaient pas correctement, en particulier lors de l’utilisation des offres HTML ou du changement d’affichage. (TGT-53825)
* **Toutes les vues s’affichent désormais correctement lorsqu’une modification couvre plusieurs expériences.** Correction d’un problème dans l’interface utilisateur de création d’activité où une seule vue était affichée lorsqu’une modification était appliquée à plusieurs vues. L’info-bulle de pointage n’a pas permis de répertorier toutes les vues associées, même si la modification a été correctement appliquée. (TGT-53827)
* **Le compositeur d’expérience visuelle ne se bloque plus par intermittence sur « [!UICONTROL Applying initial modifications] ».** Correction d’un problème intermittent dans le VEC où les expériences ne se chargeaient pas et restaient bloquées sur « [!UICONTROL Applying initial modifications] ». Ce comportement était incohérent et déclenchait parfois des boucles de redirection ou nécessitait un effacement manuel du cache. (TGT-53916)
* **Impossible de reproduire le problème de chargement du compositeur d’expérience visuelle.** Nous avons enquêté sur un problème signalé en raison duquel le compositeur d’expérience visuelle restait bloqué sur « [!UICONTROL Applying initial modifications] » lors de la modification des activités existantes. Le comportement était suspecté d’être lié à un contenu HTML dépourvu d’élément parent. Nous continuerons à surveiller la périodicité et vous recommandons d’utiliser des conteneurs structurés pour les offres HTML afin d’assurer la stabilité. (TGT-53972)
* **[!UICONTROL Design]mode du compositeur d’expérience visuelle ne se comporte plus comme [!UICONTROL Browse] mode par intermittence.** Correction d’un problème dans l’interface utilisateur où le mode [!UICONTROL Design] se comportait comme le mode [!UICONTROL Browse] par intermittence, ce qui permettait les liens `<a>` cliquables et empêchait la sélection d’éléments. Cela entraînait la disparition de la zone de survol et bloquait les workflows de modification. (TGT-53136)
* **Les clics de bouton en mode [!UICONTROL Composer] ne déclenchent plus la redirection de page.** Correction d’un problème dans l’interface utilisateur mise à jour du VEC en raison duquel le fait de cliquer sur un bouton en mode [!UICONTROL Composer] provoquait une redirection inattendue vers l’URL cible du bouton. Cela empêchait les utilisateurs de modifier les éléments de call-to-action (CTA) et perturbait le workflow de création. (TGT-53137)
* **Les mises à jour du code d’offre dans les activités de personnalisation automatisée s’enregistrent désormais sans erreur.** Correction d’un problème dans la nouvelle interface utilisateur de création qui provoquait une erreur « [!UICONTROL Invalid user input] » lors de la mise à jour du code d’offre dans les activités [!UICONTROL Automated Personalization]. L’erreur a empêché les utilisateurs d’enregistrer les modifications, même si l’entrée était valide. (TGT-53586)
* Le mode **[!UICONTROL Design]du VEC bloque désormais la navigation des liens pour les composants modifiables.** Correction d’un problème dans le VEC mis à jour en raison duquel les éléments cliquables, tels que les boutons et les liens, déclenchaient une redirection de page même en mode [!UICONTROL Design]. Ce comportement imitait le mode [!UICONTROL Browse] et empêchait les utilisateurs et utilisatrices de modifier les composants clés. (TGT-53696)
* **mesure « [!UICONTROL Clicked an element] » fonctionne désormais sans redirection ni erreur.** Correction d’un problème dans la nouvelle interface utilisateur de création qui entraînait des redirections inattendues et des écrans vides lors de la sélection de la mesure de conversion « [!UICONTROL Clicked an element] ». Cliquer sur un bouton pendant la configuration a déclenché la navigation au lieu d’enregistrer l’élément, ce qui a entraîné une erreur « [!UICONTROL element not found] ». (TGT-53817)
* **Les activités existantes ne sont plus bloquées dans une boucle de chargement infinie lors de la modification.** Correction d’un problème dans la nouvelle interface utilisateur de création, en raison duquel la modification d’une activité existante dans le VEC entraînait le blocage de la page dans une boucle de chargement infinie. Ce problème n’affectait pas les activités nouvellement créées et a été déclenché par des modifications préexistantes sur la page. (TGT-53913)
* **Les pages d’activité existantes avec des modifications se chargent désormais correctement dans le VEC.** Correction d’un problème dans le VEC mis à jour en raison duquel les pages restaient bloquées en phase de chargement lors de la modification d’une activité existante avec des modifications enregistrées. Nouvelles activités chargées sans problème, mais dont le rendu des activités configurées précédemment a échoué. (TGT-53967)

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
