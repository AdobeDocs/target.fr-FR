---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version de [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 362fac25f04028dff0fb0233d418ef9ce88e53d6
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 56%

---

# Notes de mise à jour de [!DNL Target] (version préliminaire)

Cet article contient des informations sur les prochaines versions d’[!DNL Adobe Target], y compris les SDK, les API et les bibliothèques JavaScript.

**Dernière mise à jour : 4 septembre 2023**

>[!NOTE]
>
>Les dates de publication, fonctions et autres informations peuvent changer sans préavis.
>
>Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target] Standard/Premium 23.9.1 (6-11 septembre 2023)

Cette version sera disponible selon le calendrier échelonné suivant :

* **6 septembre** : région des Amériques
* **7 septembre** : région Europe, Moyen-Orient et Afrique (EMEA)
* **11 septembre** : région Asie-Pacifique (APAC)

Cette version comprend les améliorations et correctifs suivants :

* Correction d’un problème en raison duquel les données de rapport étaient incohérentes dans la variable [!DNL Target] l’interface utilisateur et la fonction [!DNL Adobe Analytics] Interface utilisateur pour [!UICONTROL Affectation automatique] activités qui utilisent [!UICONTROL Analytics pour Target] (A4T) comme source des rapports. (TGT-46112)
* Augmentation du délai d’attente des appels du PUT à l’API de diffusion Target à 15 secondes afin d’éviter les erreurs de délai d’attente. (TGT-46091)
* Correction d’un problème en raison duquel un nom de rapport incorrect s’affichait lors du basculement entre la variable [!UICONTROL Vue Tableau] et la variable [!UICONTROL Segments automatisés] et [!UICONTROL Attributs importants] rapports. (TGT-46040)
* Amélioration de la fonction [!UICONTROL Compositeur d’expérience visuelle] (VEC) pour la prise en charge de Lightning DOM (Web Components). (TGT-45422)
* Correction d’un problème en raison duquel les actions du compositeur d’expérience visuelle étaient appliquées dans un ordre incorrect. Dans certains cas, le VEC appliquait certaines modifications de manière asynchrone et l’ajout de modifications supplémentaires à un élément provoquait des erreurs si cet élément s’affichait après un événement [!UICONTROL Insérer] action. (TGT-45983)
* Ajout de la possibilité de spécifier un sélecteur CSS dans le VEC. (TGT-45958 et TGT-46017)
* Correction d’un problème lors de l’ouverture d’une page d’application d’une seule page (SPA) dans le VEC, puis du passage en mode Parcourir en raison duquel les flèches Précédent et Suivant ne fonctionnaient pas correctement. (TGT-45956)
* Correction d’un problème qui empêchait la mise à jour cohérente de l’URL lors de la navigation sur un site web d’application d’une seule page (SPA). (TGT-45417)

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions d’at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update] :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
