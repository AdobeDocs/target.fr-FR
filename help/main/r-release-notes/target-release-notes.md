---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version de [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: b103d912b1ae953c44f2ad35da8a7ae83e7be2ae
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 64%

---

# Notes de mise à jour de [!DNL Target] (version préliminaire)

Cet article contient des informations sur les prochaines versions d’[!DNL Adobe Target], y compris les SDK, les API et les bibliothèques JavaScript.

**Dernière mise à jour : 11 septembre 2023**

>[!NOTE]
>
>Les dates de publication, fonctions et autres informations peuvent changer sans préavis.
>
>Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target] Standard/Premium 23.9.3 (18 septembre 2023)

Cette version comprend les améliorations et correctifs suivants :

* Amélioration du compositeur d’expérience visuelle (VEC) pour la prise en charge de Lightning DOM (composants web). (TGT-45422)
* Correction d’un problème en raison duquel les actions du compositeur d’expérience visuelle étaient appliquées dans un ordre incorrect. Dans certains cas, le VEC appliquait certaines modifications de manière asynchrone et l’ajout de modifications supplémentaires à un élément provoquait des erreurs si cet élément s’affichait après un événement [!UICONTROL Insérer] action. (TGT-45983)
* Correction d’un problème avec le compositeur d’expérience visuelle. [!UICONTROL Incrustation] pour prendre en charge les éléments dans les DOM fantômes. (TGT-46217)
* Correction d’un problème lors de l’ouverture d’une page d’application d’une seule page (SPA) dans le VEC, puis du passage en mode Parcourir en raison duquel les flèches Précédent et Suivant ne fonctionnaient pas correctement. (TGT-45956)
* Correction d’un problème en raison duquel certaines pages web échouaient lors du chargement dans le VEC.

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions d’at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update] :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
