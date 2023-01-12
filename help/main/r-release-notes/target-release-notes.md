---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: c12df34c9c7392a0ea50e8d1dea32147e8b7b165
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 37%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations préliminaires. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 12 janvier 2023**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target] Standard/Premium 22.13.3 (25-26 janvier 2023)

Cette version comprend de nouvelles fonctionnalités, améliorations et de nouveaux correctifs :

* Ajout de la prise en charge des offres JSON dans [!UICONTROL Automated Personalization] (AP) à l’aide du compositeur d’expérience d’après les formulaires. (TGT-41460)
* Implémenté [Mode AQ](/help/main/c-activities/c-activity-qa/activity-qa.md) pour les activités AP. (TGT-44341)
* Noms d’expérience dans [!DNL Recommendations] Les activités s’affichent désormais avec des noms conviviaux afin que les clients puissent mieux mettre en relation les données dans [!DNL Adobe Analytics] avec dans la variable [!DNL Target] Interface utilisateur. (TGT-41853)
* Correction d’un problème qui provoquait une &quot;erreur 500&quot; dans [!UICONTROL Test A/B] et [!UICONTROL Ciblage d’expérience] (XT) activités contenant des recommandations. Ce problème survenait lorsque [!DNL Target] n’a pas réussi à supprimer correctement les objets de critère de la [!DNL Target] Interface utilisateur et [!DNL Recommendations] d’arrière-plan qui ne sont plus utilisés. (TGT-44383)
* Suppression de l’emplacement du nom de l’offre affiché dans la fonction [!UICONTROL Niveau de l’offre] rapport pour [!UICONTROL Automated Personalization] activités. Cette modification rend le rapport plus lisible. (TGT-44294)
* Renommé &quot;[!UICONTROL Fragment d’expérience]&quot; dans la variable [!UICONTROL Compositeur d’expérience visuelle] Workflow (VEC). L’option est désormais &quot;[!UICONTROL HTML XF].&quot; (TGT-44132)
* Ajout de la possibilité d’afficher les métadonnées de l’offre de fragments d’expérience dans l’info-bulle de l’offre. (TGT-43838)
* Suppression des options de calendrier de 45 jours et de 90 jours de l’API et [!UICONTROL Ciblage automatique] [!UICONTROL Informations sur la personnalisation] et [!UICONTROL Attributs importants] dans les [!DNL Target] Interface utilisateur. En raison des schémas d’utilisation et pour améliorer les performances, ces plages de dates sont obsolètes. L’interface utilisateur a été mise à jour pour prendre en compte les plages actuellement autorisées : 15, 30 et 60 jours. (TGT-39357)
* La possibilité de modifier la variable [!UICONTROL Identique à l’objectif d’optimisation] sur le [!UICONTROL Objectifs et paramètres] une fois l’activité activée. (TGT-43923)
* Correction d’un problème qui provoquait des problèmes avec le lieu de travail par défaut dans le [!DNL Target] back-end lors de la mise à niveau à partir de [!DNL Target Standard] to [!DNL Target Premium]. (TGT-44081 et TGT-44306)
* Modification du lien sur la variable [!UICONTROL Implémentation] page ([!UICONTROL Administration] > [!UICONTROL Implémentation]) pour &quot;Méthodes de mise en oeuvre avec la prise de décision sur l’appareil&quot; afin de pointer vers la page qui explique comment utiliser la prise de décision sur l’appareil pour tous les SDK pris en charge : Node.js, Java, .NET et Python. Pour plus d’informations, voir [Prise en main des SDK Target](https://developer.adobe.com/target/implement/server-side/sdk-guides/getting-started/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.
* Correction d’un problème qui provoquait des problèmes de chargement de fichier lors de l’utilisation de [!DNL Scene7] et [!DNL Target].
* Amélioration de l’accessibilité du [!DNL Target] Interface utilisateur pour les personnes présentant un handicap en utilisant les résultats d’un audit interne de la convivialité. Ces améliorations de l’accessibilité incluent l’accès aux fonctionnalités qui n’étaient pas accessibles auparavant via le clavier, des améliorations de texte de remplacement, la possibilité de zoomer sur des parties de l’interface utilisateur pour qu’elles soient plus faciles à utiliser, une mise au point améliorée du clavier, etc.   (TGT-42759)
* Plusieurs correctifs de localisation ont été apportés dans l’ensemble des [!DNL Target] Interface utilisateur.

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions d’at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |


## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update] :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
