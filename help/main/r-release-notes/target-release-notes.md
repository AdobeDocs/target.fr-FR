---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: da159c10bd5100519b58cf2cb9c3d4ce15c4b2d0
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations préliminaires. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 26 janvier 2023**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target] Standard/Premium 22.13.3 (25-26 janvier 2023)

Cette version sera disponible selon le planning échelonné suivant :

* **25 janvier**: Région Europe, Moyen-Orient et Afrique (EMEA)
* **25 janvier**: Région Asie-Pacifique (APAC)
* **26 janvier**: Région des Amériques

Cette version comprend de nouvelles fonctionnalités, améliorations et de nouveaux correctifs :

| Fonctionnalité | Détails |
| --- | --- |
| [Offre JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md) Prise en charge dans Automated Personalization (AP) | Ajout de la prise en charge des offres JSON dans [!UICONTROL Automated Personalization] (AP) à l’aide du compositeur d’expérience basé sur les formulaires. (TGT-41460) |
| [Fragments d’expérience AEM](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) | Ajout de la possibilité de distinguer les [!DNL Adobe Experience Manager] les types de fragment (AEM XF) exportés vers [!DNL Target]. Au lieu de l’option &quot;Fragment d’expérience&quot;, [!DNL Target] vous permet désormais de filtrer et de rechercher par &quot;HTML XF&quot; et &quot;JSON XF&quot;. (TGT-44132) |

* Correction d’un problème qui provoquait une « erreur 500 » dans les activités [!UICONTROL Test A/B] et [!UICONTROL Ciblage d’expérience] (XT) contenant des recommandations. Ce problème survenait lorsque [!DNL Target] n’avait pas réussi à supprimer correctement les objets de critère de l’interface utilisateur de [!DNL Target] et du serveur principal [!DNL Recommendations] qui ne sont plus utilisés. (TGT-44383)
* Suppression de l’emplacement du nom de l’offre affiché dans le rapport [!UICONTROL Niveau de l’offre] pour les activités [!UICONTROL Automated Personalization]. Cette modification rend le rapport plus lisible. (TGT-44294)
* Suppression des options de calendrier de 45 jours et de 90 jours des rapports AP et [!UICONTROL Ciblage automatique], [!UICONTROL Informations sur la personnalisation] et [!UICONTROL Attributs importants] dans l’interface utilisateur de [!DNL Target]. En raison des schémas d’utilisation et afin d’améliorer les performances, ces périodes sont désormais obsolètes. L’interface utilisateur a été mise à jour pour prendre en compte les périodes actuellement autorisées : 15, 30 et 60 jours. (TGT-39357)
* Suppression de la possibilité de modifier le paramètre [!UICONTROL Identique à l’objectif d’optimisation] sur la page [!UICONTROL Objectifs et paramètres] une fois l’activité activée. (TGT-43923)
* Correction d’un problème qui provoquait des problèmes avec le lieu de travail par défaut dans le serveur principal de [!DNL Target] lors de la mise à niveau de [!DNL Target Standard] vers [!DNL Target Premium]. (TGT-44081 et TGT-44306)
* Apport d’une modification pour autoriser [!DNL Analytics] suites de rapports contenant un caractère point &quot;.&quot; dans leur nom à utiliser dans la variable [!DNL Target] Interface utilisateur pour créer [!DNL Analytics] flux de classification.
* Modification du lien sur la page [!UICONTROL Implémentation] ([!UICONTROL Administration] > [!UICONTROL Implémentation]) pour « Méthodes d’implémentation avec la prise de décision sur l’appareil »; afin de pointer vers la page qui explique comment utiliser la prise de décision sur l’appareil pour tous les SDK pris en charge : Node.js, Java, .NET et Python. Pour plus d’informations, voir [Prise en main des SDK de Target](https://developer.adobe.com/target/implement/server-side/sdk-guides/getting-started/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.
* Correction d’un problème qui provoquait des problèmes de chargement de fichier lors de l’utilisation de [!DNL Scene7] et de [!DNL Target].
* Amélioration de l’accessibilité de l’interface utilisateur de [!DNL Target] pour les personnes présentant un handicap en utilisant les résultats d’un audit interne sur l’accessibilité. Ces améliorations de l’accessibilité incluent l’accès via le clavier à des fonctionnalités qui n’étaient pas accessibles auparavant, des améliorations de texte de remplacement, la possibilité de zoomer sur des parties de l’interface utilisateur pour qu’elles soient plus faciles à utiliser, un focus du clavier amélioré, etc.   (TGT-42759)
* Plusieurs correctifs de localisation ont été apportés dans l’ensemble de l’interface utilisateur de [!DNL Target].

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions d’at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |


## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update] :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
