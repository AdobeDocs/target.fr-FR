---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bugs;mises à jour
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 351ed1e51b0a253476c6cda456781351333e8da5
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 98%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API [!DNL Target], les SDK, l’[!DNL Adobe Experience Platform Web SDK], at.js, ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## [!DNL Target] Standard/Premium 23.5.2 (31 mai 2023)

Cette version comprend les améliorations et correctifs suivants :

* Correction d’un problème en raison duquel une page vierge s’affichait lors de la génération d’un jeton d’autorisation de l’API Profile. (TGT-45387 et TGT-45423)
* Correction d’un problème qui empêchait l’affichage d’une image dans le panneau [!UICONTROL Créer une conception] si le nom de l’image contenait des caractères GB 18030. (TGT-44614)
* Correction d’un problème en raison duquel certains caractères GB 18030 étaient incorrectement placés dans une séquence d’échappement en texte/HTML dans les expériences. (TGT-44600)
* Correction d’un problème qui entraînait le blocage des rapports pour les activités de [!UICONTROL personnalisation automatique] pendant l’analyse. (TGT-44820)
* Correction d’un problème qui empêchait la recherche d’une activité sur la page [!UICONTROL Activité] si le nom de l’activité contenait un crochet ([ ou ]). (TGT-44777)
* Correction d’un problème qui empêchait la synchronisation d’une activité si l’objectif de l’activité contenait des caractères spéciaux. (TGT-44982)
* Correction d’un problème en raison duquel aucune activité ne s’affichait dans l’interface utilisateur de [!DNL Target] pour l’espace de travail par défaut de certains clients et clientes. (TGT-45286)
* Mise à jour du comportement de l’indicateur « Refuser les doublons ». Les indicateurs d’offres répétées exclues sont mis à jour afin d’autoriser les offres répétées si elles sont l’offre de contenu par défaut (pour les API v3, v4) et d’autoriser les options en double si les options font référence à l’offre de contenu par défaut et si aucun modèle n’est défini. (TNT-46617)
* Correction d’un problème en raison duquel un paramètre de requête était ajouté à une URL qui empêchait le chargement de la page dans le [!UICONTROL compositeur d’expérience visuelle] (VEC). (TGT-44873)
* Plusieurs correctifs de localisation ont été apportés dans l’ensemble de l’interface utilisateur de [!DNL Target].

## Attributs de profil Real-Time CDP partagés avec [!DNL Target]|[!UICONTROL Attributs de profil Real-Time CDP] (13 juin 2023)

L’amélioration suivante a été apportée à cette version :

| Fonctionnalité | Détails |
|--- |--- |
| Attributs de profil Real-Time CDP partagés avec [!DNL Target] | Les [!UICONTROL Attributs de profil Real-Time CDP] peut être transmis à [!DNL Target] afin d’être utilisés dans les offres HTML et JSON.<P>Pour plus d’informations, consultez la section [Partager des attributs de profil Real-Time CDP avec [!DNL Target]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#rtcdp-profile-attributes). |

## [!DNL Target] Standard/Premium 23.5.1 (23-25 mai 2023)

Cette version sera disponible selon le planning échelonné suivant :

23 mai : région Europe, Moyen-Orient et Afrique (EMEA)
24 mai : région Asie-Pacifique (APAC)
25 mai : Région Amériques

Cette version comprend les nouvelles améliorations et nouveaux correctifs suivants :

* Correction d’un problème qui empêchait certains clients et certaines clientes de créer des audiences avec des profils visiteur utilisant des opérateurs « supérieur à » ou « inférieur à ». (TGT-45271)
* Plusieurs correctifs de localisation ont été apportés dans l’ensemble de l’interface utilisateur de [!DNL Target].
* Mise à jour de l’interface utilisateur de Target à différents emplacements pour une prochaine actualisation de l’interface utilisateur (les modifications se trouvent derrière un indicateur de fonctionnalité jusqu’à ce que les mises à jour soient publiées).

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions d’at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| [Modifications de la documentation](/help/main/r-release-notes/doc-change.md) | Obtenez des informations détaillées sur les mises à jour apportées à ce guide qui ne sont pas incluses dans les notes de mise à jour. |
| [Notes de mise à jour pour les versions antérieures](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium. |
| [Notes de mise à jour d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr){target=_blank} | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud. |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| [Mise à jour prioritaire des produits Adobe](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Recevez des notifications anticipées sur les améliorations à venir de [!DNL Target] et d’autres solutions [!DNL Adobe Experience Cloud]. |
| [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Informations sur les versions de Target du mois en cours, y compris des informations sur la version préliminaire. |
