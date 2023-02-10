---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;correctifs;correctifs;correctifs;mises à jour
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: abf4c005a3c0e3b2e0e9f1402bb2af3444634942
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 84%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API [!DNL Target], les SDK, l’[!DNL Adobe Experience Platform Web SDK], at.js, ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## [!DNL Target] Standard/Premium 22.14.5 (13-15 février 2023)

Cette version sera disponible selon le planning échelonné suivant :

* **13 février**: Région des Amériques
* **15 février**: Région Europe, Moyen-Orient et Afrique (EMEA)
* **15 février**: Région Asie-Pacifique (APAC)

Cette version contient les correctifs suivants :

* Correction d’un problème qui provoquait le message d’erreur suivant même si une propriété était spécifiée dans les activités Automated Personalization (AP) : &quot;Erreurs : Au moins une propriété doit appartenir à un espace de travail autre que celui par défaut&quot; (TGT-44607)
* Correction d’un problème de sécurité potentiel affectant les flux Recommendations côté serveur. (TGT-43769)

## at.js version 2.10.1 (2 février 2023)

* Correction d’un bogue en raison duquel les activités impliquant des règles d’audience contenant des paramètres dont le nom contient des points ne renvoyaient pas l’expérience attendue pour la prise de décision sur l’appareil.
* Correction d’un bogue introduit dans at.js 2.6.0, en raison duquel at.js déclenchait un appel de diffusion, même lorsque `mboxDisable` a été activé.

Pour plus d’informations sur toutes les versions d’at.js, voir [Informations détaillées sur les versions du fichier at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.

## [!DNL Target] Standard/Premium 22.13.3 (25-26 janvier 2023)

Cette version sera disponible selon le planning échelonné suivant :

* **25 janvier** : région Europe, Moyen-Orient et Afrique (EMEA)
* **25 janvier** : région Asie-Pacifique (APAC)
* **26 janvier** : région des Amériques

Cette version comprend de nouvelles fonctionnalités, améliorations et de nouveaux correctifs :

| Fonctionnalité | Détails |
| --- | --- |
| Prise en charge des [offres JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md) dans Automated Personalization (AP) | Ajout de la prise en charge des offres JSON dans [!UICONTROL Automated Personalization] (AP) à l’aide du compositeur d’expérience basé sur les formulaires. (TGT-41460) |
| [Fragments d’expérience AEM](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) | Ajout de la possibilité de distinguer les types de fragment de [!DNL Adobe Experience Manager] (AEM XF) exportés vers [!DNL Target]. Au lieu de l’option « Fragment d’expérience », [!DNL Target] vous permet désormais de filtrer et de rechercher par « HTML XF » et « JSON XF ». (TGT-44132) |

* Correction d’un problème qui provoquait une « erreur 500 » dans les activités [!UICONTROL Test A/B] et [!UICONTROL Ciblage d’expérience] (XT) contenant des recommandations. Ce problème survenait lorsque [!DNL Target] n’avait pas réussi à supprimer correctement les objets de critère de l’interface utilisateur de [!DNL Target] et du serveur principal [!DNL Recommendations] qui ne sont plus utilisés. (TGT-44383)
* Suppression de l’emplacement du nom de l’offre affiché dans le rapport [!UICONTROL Niveau de l’offre] pour les activités [!UICONTROL Automated Personalization]. Cette modification rend le rapport plus lisible. (TGT-44294)
* Suppression des options de calendrier de 45 jours et de 90 jours des rapports AP et [!UICONTROL Ciblage automatique], [!UICONTROL Informations sur la personnalisation] et [!UICONTROL Attributs importants] dans l’interface utilisateur de [!DNL Target]. En raison des schémas d’utilisation et afin d’améliorer les performances, ces périodes sont désormais obsolètes. L’interface utilisateur a été mise à jour pour prendre en compte les périodes actuellement autorisées : 15, 30 et 60 jours. (TGT-39357)
* Suppression de la possibilité de modifier le paramètre [!UICONTROL Identique à l’objectif d’optimisation] sur la page [!UICONTROL Objectifs et paramètres] une fois l’activité activée. (TGT-43923)
* Correction d’un problème qui provoquait des problèmes avec le lieu de travail par défaut dans le serveur principal de [!DNL Target] lors de la mise à niveau de [!DNL Target Standard] vers [!DNL Target Premium]. (TGT-44081 et TGT-44306)
* Une modification a été effectuée pour autoriser les suites de rapports de [!DNL Analytics] contenant un caractère point « . » dans leur nom d’être utilisées dans l’interface utilisateur de [!DNL Target] pour créer des flux de classification de [!DNL Analytics].
* Modification du lien sur la page [!UICONTROL Implémentation] ([!UICONTROL Administration] > [!UICONTROL Implémentation]) pour « Méthodes d’implémentation avec la prise de décision sur l’appareil »; afin de pointer vers la page qui explique comment utiliser la prise de décision sur l’appareil pour tous les SDK pris en charge : Node.js, Java, .NET et Python. Pour plus d’informations, voir [Prise en main des SDK de Target](https://developer.adobe.com/target/implement/server-side/sdk-guides/getting-started/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.
* Correction d’un problème qui provoquait des problèmes de chargement de fichier lors de l’utilisation de [!DNL Scene7] et de [!DNL Target].
* Amélioration de l’accessibilité de l’interface utilisateur de [!DNL Target] pour les personnes présentant un handicap en utilisant les résultats d’un audit interne sur l’accessibilité. Ces améliorations de l’accessibilité incluent l’accès via le clavier à des fonctionnalités qui n’étaient pas accessibles auparavant, des améliorations de texte de remplacement, la possibilité de zoomer sur des parties de l’interface utilisateur pour qu’elles soient plus faciles à utiliser, un focus du clavier amélioré, etc.   (TGT-42759)
* Plusieurs correctifs de localisation ont été apportés dans l’ensemble de l’interface utilisateur de [!DNL Target].

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions d’at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| Modifications de la documentation | Obtenez des informations détaillées sur les mises à jour apportées à ce guide qui ne sont pas incluses dans les notes de mise à jour.<br>Pour plus d’informations, voir [Modifications de la documentation](/help/main/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notes de mise à jour pour les versions antérieures | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium.<br>Pour plus d’informations, voir [Notes de mise à jour des versions précédentes](/help/main/r-release-notes/release-notes-for-previous-releases.md). |
| Notes de mise à jour d’Adobe Experience Cloud | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud.<br>Pour plus d’informations, consultez [Notes de mise à jour d’Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr). |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| Mise à jour prioritaire des produits Adobe | Pour recevoir des notifications avancées sur les améliorations à venir des produits Target et d’autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour produit prioritaire Adobe :<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Notes de mise à jour à venir | Pour plus d’informations sur les versions de Target du mois en cours, notamment les informations de version préliminaire, voir la page [Notes de mise à jour de Target (préliminaires)](/help/main/r-release-notes/target-release-notes.md). |
