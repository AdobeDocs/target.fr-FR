---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bugs;mises à jour
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 6fa553c7179cd2a6d500bdc53cc77dc01ee906e7
workflow-type: ht
source-wordcount: '623'
ht-degree: 100%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API [!DNL Target], les SDK, l’[!DNL Adobe Experience Platform Web SDK], at.js, ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## [!DNL Target] Standard/Premium 23.9.3 (18 septembre 2023)

Cette version comprend les améliorations et correctifs suivants :

* Amélioration de la fonction [!UICONTROL Compositeur d’expérience visuelle] (VEC) pour la prise en charge des composants web Lightning (Light DOM). (TGT-45422)
* Correction d’un problème en raison duquel les actions du compositeur d’expérience visuelle étaient appliquées dans un ordre incorrect. Dans certains cas, le compositeur d’expérience visuelle appliquait certaines modifications de manière asynchrone. L’ajout de modifications supplémentaires à un élément provoquait des erreurs si cet élément s’affichait après une action [!UICONTROL Insérer]. Corrige également l’URL du compositeur d’expérience visuelle, qui se met à présent à jour lorsque l’utilisateur ou l’utilisatrice clique sur les liens. (TGT-45983)
* Correction d’un problème avec la fonction [!UICONTROL Incrustation] du compositeur d’expérience visuelle, qui prend désormais en charge les éléments dans les Shadow DOM. (TGT-45202 et TGT-45262)
* Correction d’un problème lors de l’ouverture d’une page d’application d’une seule page (SPA) dans le compositeur d’expérience visuelle, en raison duquel les flèches Précédent et Suivant ne fonctionnaient pas correctement en mode [!UICONTROL Parcourir]. (TGT-45956)
* Correction d’un problème qui empêchait le chargement de certaines pages web dans le compositeur d’expérience visuelle. (TGT-45983)

## [!DNL Target] Standard/Premium 23.9.2 (du 12 au 14 septembre 2023)

Cette version sera disponible selon le calendrier échelonné suivant :

* **12 septembre** : région des Amériques
* **13 septembre** : région Asie-Pacifique (APAC)
* **14 septembre** : région Europe, Moyen-Orient et Afrique (EMEA)

Cette version comprend les améliorations et correctifs suivants :

* Passage de l’API [!DNL Analytics] à la nouvelle version 2.0 de l’API [!DNL Analytics]. (TGT-45345)
* Correction des problèmes qui avaient un impact sur les activités [!UICONTROL Automated Personalization] (AP) pour des clientes et clients, y compris la synchronisation opportune de l’activité sur le serveur principal [!DNL Target] et la fourniture de l’expérience attendue dans les liens d’aperçu. (TGT-46202)

## [!DNL Target] Standard/Premium 23.9.1 (du 6 au 11 septembre 2023)

Cette version sera disponible selon le calendrier échelonné suivant :

* **6 septembre** : région des Amériques
* **7 septembre** : région Europe, Moyen-Orient et Afrique (EMEA)
* **11 septembre** : région Asie-Pacifique (APAC)

Cette version comprend les améliorations et correctifs suivants :

* Correction d’un problème en raison duquel les données de rapport étaient incohérentes dans l’interface utilisateur [!DNL Target] et l’interface utilisateur [!DNL Adobe Analytics] pour des activités d&#39;[!UICONTROL Affectation automatique] qui utilisent [!UICONTROL Analytics for Target] (A4T) comme source des rapports. (TGT-46112)
* Augmentation du délai d’expiration des appels du PUT à l’API Target Delivery à 15 secondes afin d’éviter les erreurs de temporisation. (TGT-46091)
* Correction d’un problème qui empêchait la mise à jour cohérente de l’URL lors de la navigation sur un site Web d’application Une seule page (SPA). (TGT-45417)

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
