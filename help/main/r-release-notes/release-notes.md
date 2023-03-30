---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bugs;mises à jour
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Learn about the new features, enhancements, and fixes included in the current release of [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 1c9728b447ee1402cc133d38845a25da3038d0ca
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 59%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API [!DNL Target], les SDK, l’[!DNL Adobe Experience Platform Web SDK], at.js, ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## [!DNL Target] Standard/Premium 23.3.1 (28-30 mars 2023)

Cette version sera disponible selon le planning échelonné suivant :

* **28 mars** : région Europe, Moyen-Orient et Afrique (EMEA)
* **29 mars** : région Asie-Pacifique (APAC)
* **30 mars** : région Amériques

Cette version comprend de nouvelles fonctionnalités, améliorations et de nouveaux correctifs :

| Fonctionnalité | Détails |
|--- |--- |
| Mesures A4T optimisées pour [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique]<p>(Date de publication : 30 mars 2023) | [!DNL Target] vous permet de choisir des mesures en fonction d’événements binomiaux ou d’événements continus lors de l’utilisation de [!UICONTROL A4T] pour les activités d’[!UICONTROL affectation automatique] et de [!UICONTROL ciblage automatique].<P>Tenez compte du changement suivant prochainement programmé concernant les mesures prises en charge :<ul><li>[!DNL Target] a conservé le comportement précédent des activités existantes jusqu’au 9 septembre 2023. À compter de cette date, les activités utilisant des mesures non prises en charge seront interrompues pour forcer la migration des activités existantes vers un nouveau comportement.</li></ul>Pour plus d’informations, voir &quot;Mesures prises en charge&quot; dans [Prise en charge d’A4T pour [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] activités](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#supported).<P>En plus de cette fonctionnalité, les tutoriels suivants ont été mis à jour :<ul><li>[Configuration de rapports A4T dans  [!DNL Analysis Workspace]  pour les activités d’[!UICONTROL affectation automatique]](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=fr){target=_blank}</li><li>[Configuration de rapports A4T dans  [!DNL Analysis Workspace]  pour les activités de [!UICONTROL ciblage automatique]](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=fr){target=_blank}</li></ul> |

* Amélioration de la synchronisation des audiences et des activités afin que les éléments créés dans [!DNL Adobe Experience Platform] et [!DNL Adobe Audience Manager] sont disponibles dans la variable [!DNL Target] Interface utilisateur plus rapide. (TGT-44568)
* Modification apportée pour permettre aux utilisateurs de supprimer la variable [!UICONTROL URL par défaut] under [!UICONTROL Administration] > [!UICONTROL Compositeur d’expérience visuelle] > [!UICONTROL URL par défaut]. Cette modification permet aux clients de redéfinir l’URL par défaut sur une chaîne vide, ce qui était auparavant impossible après la configuration initiale. (TGT-44577)
* Suppression des restrictions qui empêchaient les clients de modifier ou supprimer les audiences d’usine (audiences avec des noms réservés). (TGT-44655)
* Désactivé le &quot;[!UICONTROL Terminé]&quot; lors du chargement des moteurs de balayage étaient visibles dans la variable [!DNL Target] Interface utilisateur lors de la création [audiences combinées](/help/main/c-target/combining-multiple-audiences.md). (TGT-44079)
* Correction de la fonction [!UICONTROL Langue] en bas de la page [!UICONTROL Audiences] afin qu’il pointe correctement vers le &quot;&quot;[!UICONTROL Préférences de communication du compte]&quot;. (TGT-43562)
* Correction d’un problème qui empêchait parfois les clients de créer [!UICONTROL Test A/B] activités après avoir sélectionné la variable [!UICONTROL Adobe Analytics] option sous [!UICONTROL Administration] > [!UICONTROL Reporting] > [!UICONTROL Solution Experience Cloud de création de rapports]. (TGT-44844)
* Correction d’un problème qui empêchait les clients d’afficher la dernière expérience dans une [!UICONTROL Test multivarié] d’une activité comportant de nombreuses expériences depuis l’ [!UICONTROL Compositeur d’expérience visuelle] (VEC). Le [Chemin d’accès DOM](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) au bas du compositeur d’expérience visuelle empêchait parfois les clients de voir la dernière expérience. (TGT-44578)
* Correction d’un problème en raison duquel l’URL de navigation dans le VEC ne reflétait pas la page active visible dans une session de navigateur normale si la page nécessitait une autorisation ou appelait des redirections. (TGT-44350)
* Correction d’un problème qui empêchait les clients de modifier la variable [!UICONTROL Filtrer les critères incompatibles] définition dans [!UICONTROL Recommendations] > [!UICONTROL Paramètres]. (TGT-44398)
* Correction d’un problème en raison duquel les demandes de POST créaient de nouvelles [!DNL Recommendations] échec des flux lors de l’utilisation de [!UICONTROL Classifications Analytics] avec des suites de rapports dont le nom contient des points. (TGT-44598)
* Mise à jour des liens dans [!DNL Target] Interface utilisateur pour pointer vers la nouvelle [Extension Visual Editing Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). (TGT-44459)
* Amélioration de la sécurité afin d’empêcher les tentatives SSRF (Server Side Request Forgery) dans [!DNL Recommendations] flux. (TGT-43769)
* Correction d’un problème qui empêchait les clients d’afficher des images d’aperçu dans [!DNL Recommendations] conceptions si le nom de l’image contient [Caractères GB18030](https://en.wikipedia.org/wiki/GB_18030){target=_blank}. (TGT-44614)
* Correction d’un problème en raison duquel certains [Caractères GB18030](https://en.wikipedia.org/wiki/GB_18030){target=_blank} à échapper dans la variable [!UICONTROL Modifications] panneau lors de la modification [!UICONTROL Texte/HTML] sur le [!UICONTROL Expériences] page. (TGT-44600)
* Plusieurs correctifs de localisation ont été apportés dans l’ensemble de l’interface utilisateur de [!DNL Target].

## at.js version 2.10.2 (7 mars 2023)

* Correction d’un problème en raison duquel la fonction `trackEvent` renvoyait toujours une erreur.

Pour plus d’informations sur toutes les versions d’at.js, voir [Informations détaillées sur les versions d’at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.

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
