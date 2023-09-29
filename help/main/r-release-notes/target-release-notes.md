---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version de [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: d68337b9f19801efa593f85a62791423e98d13f2
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 87%

---

# Notes de mise à jour de [!DNL Target] (version préliminaire)

Cet article contient des informations sur les prochaines versions d’[!DNL Adobe Target], y compris les SDK, les API et les bibliothèques JavaScript.

**Dernière mise à jour : 29 septembre 2023**

>[!NOTE]
>
>Les dates de publication, fonctions et autres informations peuvent changer sans préavis.
>
>Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target] Standard/Premium 23.9.4 (2-4 octobre 2023)

Cette version sera disponible selon le calendrier échelonné suivant :

* **2 octobre** : région Europe, Moyen-Orient et Afrique (EMEA)
* **3 octobre** : région des Amériques
* **4 octobre** : région Asie-Pacifique (APAC)

Cette version comprend les améliorations et correctifs suivants :

* Ajout [!UICONTROL Compositeur d’expérience visuelle] Améliorations apportées aux structures dynamiques. (TGT-44064)
* Correction d’un problème en raison duquel la date sélectionnée dans la variable `getViewInAnalyticsId` de ne pas mettre à jour correctement. Ce correctif permet de recalculer la variable [!DNL Analytics] dans les rapports lorsque les paramètres des rapports de la période et des mesures sont modifiés. (TGT-46246)

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

## [!DNL Target] Standard/Premium 23.5.2 (Date à déterminer)

Cette version comprend les améliorations et correctifs suivants :

* Sélection des critères d’optimisation activée pour [!DNL Adobe Analytics] mesures.
* Activation de la synchronisation des audiences externes à l’aide de tâches sling.
* Correction d’un problème en raison duquel les suites de rapports SC contenant un caractère de point dans le nom n’étaient pas prises en charge.
* Activation de la fonctionnalité permettant aux clients de supprimer et de modifier des audiences intégrées.

## [!DNL Target] Standard/Premium 23.5.3 (Date à déterminer)

Les améliorations suivantes ont été apportées à cette version :

| Fonctionnalité | Détails |
|--- |--- |
| [!UICONTROL Mode assurance qualité] pour les activités de [!UICONTROL personnalisation automatique] | Le [!UICONTROL mode assurance qualité] [!DNL Adobe Target] est désormais disponible pour les activités de [!UICONTROL personnalisation automatique], et remplace la fonctionnalité [!UICONTROL Aperçu des liens].<P>Pour plus d’informations, voir [AQ d’activité](/help/main/c-activities/c-activity-qa/activity-qa.md). |

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions d’at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update] :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
