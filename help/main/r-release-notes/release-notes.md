---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bugs;mises à jour
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: a791fbe805735b278f650ff1f087b85898a66a07
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 100%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API [!DNL Target], les SDK, l’[!DNL Adobe Experience Platform Web SDK], at.js, ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## [!DNL Target] Standard/Premium 23.3.1 (28 et 30 mars 2023)

Cette version sera disponible selon le calendrier échelonné suivant :

* **28 mars** : région Europe, Moyen-Orient et Afrique (EMEA)
* **29 mars** : région Asie-Pacifique (APAC)
* **30 mars** : région Amériques

Cette version comprend de nouvelles fonctionnalités, améliorations et de nouveaux correctifs :

| Fonctionnalité | Détails |
|--- |--- |
| Mesures A4T optimisées pour [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique]<p>(Date de publication : 30 mars 2023) | [!DNL Target] vous permet de choisir des mesures en fonction d’événements binomiaux ou d’événements continus lors de l’utilisation de [!UICONTROL A4T] pour les activités d’[!UICONTROL affectation automatique] et de [!UICONTROL ciblage automatique].<P>Tenez compte du changement suivant prochainement programmé concernant les mesures prises en charge :<ul><li>[!DNL Target] a conservé le comportement précédent des activités existantes jusqu’au 9 septembre 2023. À compter de cette date, les activités utilisant des mesures non prises en charge seront interrompues pour forcer la migration des activités existantes vers un nouveau comportement.</li></ul>Pour plus d’informations, consultez « Mesures d’objectif prises en charge » dans [Prise en charge d’A4T pour les activités d’[!UICONTROL affectation automatique] et de [!UICONTROL ciblage automatique]](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#supported).<br>Depuis l’arrivée de cette fonctionnalité, les tutoriels suivants ont été mis à jour :<ul><li>[Configuration de rapports A4T dans  [!DNL Analysis Workspace]  pour les activités d’[!UICONTROL affectation automatique]](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=fr){target=_blank}</li><li>[Configuration de rapports A4T dans  [!DNL Analysis Workspace]  pour les activités de [!UICONTROL ciblage automatique]](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=fr){target=_blank}</li></ul> |

* Amélioration de la synchronisation des audiences et des activités, de sorte que les éléments créés dans [!DNL Adobe Experience Platform] et [!DNL Adobe Audience Manager] soient disponibles plus rapidement dans l’IU [!DNL Target]. (TGT-44568)
* Amélioration de l’interface utilisateur pour permettre aux utilisateurs et utilisatrices de supprimer l’[!UICONTROL URL par défaut] sous [!UICONTROL Administration] > [!UICONTROL Compositeur d’expérience visuelle] > [!UICONTROL URL par défaut]. Cette modification permet aux clients et clientes de redéfinir l’URL par défaut sur une chaîne vide, ce qui était auparavant impossible après la configuration initiale. (TGT-44577)
* Suppression des restrictions qui empêchaient les clients et clientes de modifier ou de supprimer les audiences prédéfinies (audiences avec des noms réservés). (TGT-44655)
* Désactivation de l’option [!UICONTROL Terminé] lors du chargement des composants Spinner visibles dans l’interface utilisateur [!DNL Target] lors de la création des [audiences combinées](/help/main/c-target/combining-multiple-audiences.md). (TGT-44079)
* Correction du lien [!UICONTROL Langue] en bas de la page [!UICONTROL Audiences], de sorte qu’il pointe correctement vers la page [!UICONTROL Préférences de communication du compte]. (TGT-43562)
* Correction d’un problème qui empêchait parfois les clients et clientes de créer des activités de [!UICONTROL test A/B] après avoir sélectionné l’option [!UICONTROL Adobe Analytics] sous [!UICONTROL Administration] > [!UICONTROL Reporting] > [!UICONTROL Solution Experience Cloud pour le reporting]. (TGT-44844)
* Correction d’un problème qui empêchait les clients et clientes d’afficher la dernière expérience dans une activité de [!UICONTROL test multivarié] comportant de nombreuses expériences depuis le [!UICONTROL Compositeur d’expérience visuelle] (VEC). Le [chemin d’accès DOM](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) au bas du VEC empêchait parfois les clients et clientes de voir la dernière expérience. (TGT-44578)
* Correction d’un problème en raison duquel l’URL de navigation dans le VEC ne reflétait pas la page active visible dans une session de navigateur normale si la page nécessitait une autorisation ou appelait des redirections. (TGT-44350)
* Correction d’un problème qui empêchait les clients et clientes de modifier le paramètre [!UICONTROL Filtrer les critères incompatibles] dans [!UICONTROL Recommandations] > [!UICONTROL Paramètres]. (TGT-44398)
* Correction d’un problème qui entraînait l’échec des requêtes POST de création de flux [!DNL Recommendations] lors de l’utilisation des [!UICONTROL classifications Analytics] avec des suites de rapports dont le nom contenait des points. (TGT-44598)
* Mise à jour des liens dans l’IU [!DNL Target], de façon à pointer vers la nouvelle [Extension Assistant d’édition visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). (TGT-44459)
* Amélioration de la sécurité afin d’empêcher les tentatives SSRF (Server Side Request Forgery) dans les flux [!DNL Recommendations]. (TGT-43769)
* Plusieurs correctifs de localisation ont été apportés dans l’ensemble de l’interface utilisateur de [!DNL Target].

## at.js version 2.10.2 (7 mars 2023)

* Correction d’un problème en raison duquel la fonction `trackEvent` renvoyait toujours une erreur.

Pour plus d’informations sur toutes les versions d’at.js, voir [Informations détaillées sur les versions d’at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr){target=_blank} | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions d’at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

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
