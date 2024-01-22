---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bugs;mises à jour
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 99152f66217f66174e8b6a5a7319f11b22c74b8e
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 84%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API [!DNL Target], les SDK, l’[!DNL Adobe Experience Platform Web SDK], at.js, ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## Retrait des iPad et des iPhone de l’attribut d’audience de navigateur (30 avril 2024)

| Retrait | Détails |
|--- |--- |
| Les [!DNL iPad] et [!DNL iPhone] sont retirés de l’[attribut de navigateur](/help/main/c-target/c-audiences/c-target-rules/browser.md), qui est utilisé lors de la création d’audiences.<p>Date de retrait :<P>30 avril 2024 | [!DNL Adobe Target] vous permet de [cibler n’importe quel attribut de catégorie](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), y compris les personnes qui utilisent un [navigateur ou des options de navigateur](/help/main/c-target/c-audiences/c-target-rules/browser.md) spécifiques lorsqu’elles consultent votre page.<P><B>À compter du 30 avril 2024, iPad et iPhone seront retirés de la liste déroulante [!UICONTROL Navigateur] disponible lors de la création de catégories pour les audiences.</b><P>Si vous avez des audiences qui ciblent les iPad ou les iPhone à l’aide de l’attribut [!UICONTROL Navigateur], vous devez modifier ces paramètres avant le 30 avril 2024 pour assurer leur bon fonctionnement.<p>Pour obtenir des exemples d’autres paramètres, voir [Abandon de l’attribut d’audience iPad et iPhone du navigateur (30 avril 2024)](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation). |

## [!DNL Target] Standard/Premium 24.1.1 (22, 23 et 25 janvier 2024)

Cette version est programmée pour les jours suivants :

* **22 janvier** : région Europe, Moyen-Orient et Afrique (EMEA)
* **23 janvier** : région Asie-Pacifique (APAC)
* **25 janvier** : région des Amériques

Cette version comprend les améliorations et correctifs suivants :

* [!UICONTROL Analytics pour Target] (A4T) Les activités avec des mesures d’objectif de recettes n’affichaient pas &quot;Recettes&quot; comme nom de colonne et la mesure de recettes ne s’affichait pas au format ($) dans les rapports. Il s’agissait d’un problème cosmétique auquel on a remédié. (TGT-46995)
* Correction d’un problème en raison duquel les périodes des rapports ne fonctionnaient pas correctement. (TGT-47396)
* Correction d’un problème qui entraîne l’affichage d’un statut incorrect sur la page [!UICONTROL Toutes les activités] après l’activation ou la désactivation d’une activité à l’aide de l’icône [!UICONTROL Plus d’actions]. (TGT-47367)
* Correction d’un problème en raison duquel la variable [!UICONTROL Attributs importants] ne s’affichera pas pour un seul client. (TGT-47272)
* Correction d’un problème en raison duquel un message &quot;Payload non valide&quot; s’affichait lorsqu’un seul client tentait d’activer l’option &quot;Authentification requise&quot;. (TGT-47195)
* Mise à jour de plusieurs chaînes localisées dans l’interface utilisateur de [!DNL Target].

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions d’at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

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
