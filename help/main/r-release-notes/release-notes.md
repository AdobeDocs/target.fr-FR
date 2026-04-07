---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bugs;mises à jour;mises à jour actuelles
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
hold: true
source-git-commit: cad8c365028b28bd9349d2d283370e2c8a750180
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 35%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Découvrez les dernières fonctionnalités, améliorations et correctifs d’[!DNL Adobe Target]. Ces notes de mise à jour couvrent également les mises à jour des API [!DNL Target], des SDK, de la [!DNL Adobe Experience Platform Web SDK], d’at.js et d’autres composants de plateforme, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## Mises à jour sensibles à l’heure que vous devez connaître {#time-sensitive}

[!BADGE Important]{type=Informative}

Pour les mises à jour urgentes relatives à [!DNL Adobe Target] et à votre implémentation, [!DNL Adobe] fournit des notes de mise à jour détaillées et une documentation via [!UICONTROL Experience League]. Voici quelques points forts importants liés à votre implémentation :

### Obsolescence du bouton (bascule) de version de l’interface utilisateur [!DNL Target]

Pour plus d’informations, voir [[!DNL Target] FAQ sur la mise à jour de l’interface utilisateur](/help/main/c-intro/updated-ui-faq.md).


## [!DNL Target Standard/Premium] 26.4.1 (vendredi 2 avril 2026)

**Activités**

+++Afficher les détails

* **Attributs d’audience visibles dans la vue Activités.** Correction d’un problème où les détails des règles d’audience affichés à partir d’un **[!UICONTROL Activity]** n’affichaient pas certains attributs qui s’affichaient lors de l’ouverture de la même audience à partir de la section **[!UICONTROL Audiences]** . (TGT-54742)

* **Le code personnalisé est conservé lorsqu’il est appliqué à des vues supplémentaires.** Correction d’un problème en raison duquel le code personnalisé appliqué à un **[!UICONTROL View]** pouvait être supprimé lors de l’ajout ou de l’enregistrement de code personnalisé pour un autre **[!UICONTROL View]** du même **[!UICONTROL Activity]**. (TGT-53933)

* **Exporter au format CSV dans les pages de liste Activités et Audiences.** Ajout d’une action **[!UICONTROL Export CSV]** afin que vous puissiez exporter des listes d’activités à partir de l’interface utilisateur, y compris lorsque des filtres sont appliqués, sans vous fier uniquement aux API pour les exportations de routine. (TGT-51466)

* **Modifications de l’expérience marquées lorsque les sélecteurs sont introuvables.Les modifications de l’expérience** exécutent désormais une vérification d’existence du sélecteur ; lorsqu’un sélecteur est introuvable sur la page, la modification est marquée comme non valide. (TGT-54815)

* activités **[!UICONTROL Automated personalization].** Correction de problèmes de chargement des activités et de l’interface qui empêchaient les utilisateurs de créer, de modifier ou de gérer de manière fiable des activités Automated Personalization, ce qui bloquait la configuration des campagnes et retardait les cas d’utilisation de la personnalisation. (TGT-54421)

+++

**Audiences**

+++Afficher les détails

* **Nom et description de l’audience visibles lors de la création d’audiences à partir d’une activité.** Correction d’un problème où les champs **[!UICONTROL Name]** et **[!UICONTROL Description]** de l’audience ne se démarquaient pas clairement lors de la création ou de la modification d’une audience à partir du flux d’activité, par rapport à la création de l’audience directement sous **[!UICONTROL Audiences]**. (TGT-54837)

+++

**Informations**

+++Afficher les détails

* **[!UICONTROL Live Activities]comptez sur Insights.** Correction d’un problème en raison duquel la mesure **[!UICONTROL Live Activities]** sur le tableau de bord Insights pouvait signaler un total plus élevé que le nombre d’activités qui apparaissaient comme étant en ligne dans **[!UICONTROL All Activities]**. (TGT-54788)

+++

**Recommandations**

+++Afficher les détails

* **Listes d’ID longues dans [!UICONTROL Global Exclusions].** Correction d’un problème en raison duquel le collage ou la saisie d’une longue liste d’identifiants dans **[!UICONTROL Global Exclusions]** pouvaient être tronqués dans l’interface mise à jour par rapport à l’ancienne version, ce qui entraînait une liste d’exclusion incomplète. (TGT-54422)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++Afficher les détails

* **Indicateur de statut du compositeur d’expérience amélioré (EEC) dans la [!UICONTROL Visual Experience Composer].** L’indicateur EEC indique si le compositeur d’expérience avancé est activé. Sa présentation a été révisée afin qu’elle ne ressemble plus à un bouton bascule interactif, car elle sert uniquement d’affichage d’état non interactif. (TGT-54828)

* **Rail de gauche réductible dans le [!UICONTROL Visual Experience Composer].** Le rail de gauche peut maintenant être réduit lorsqu’une activité est ouverte pour modification. Cela améliore l’accès aux **[!UICONTROL Components]** et aux **[!UICONTROL Properties]** pour les activités qui incluent plusieurs audiences et pages, y compris sur des affichages plus petits. (TGT-54269)

+++

## [!DNL Target Standard/Premium] 26.3.7 (26 mars 2026)

**Audiences**

+++Afficher les détails

* **Précision du libellé de la source d’audience dans l’interface Audiences.** Correction d’un problème où les audiences provenant de la destination Adobe Target v2 dans Adobe Experience Platform pouvaient apparaître avec **Adobe Experience Cloud** comme source au lieu de **Adobe Experience Platform**. Cette mise à jour améliore la cohérence source-libellé lors du filtrage et de la révision des audiences. (TGT-54802)

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
| [Notes De Mise À Jour De ](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr){target=_blank} | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud. |

## Informations en version préliminaire {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| [Mise à jour prioritaire des produits Adobe](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Recevez des notifications anticipées sur les améliorations à venir de [!DNL Target] et d’autres solutions [!DNL Adobe Experience Cloud]. |
| [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Informations sur les versions de Target du mois en cours, y compris des informations sur la version préliminaire. |
