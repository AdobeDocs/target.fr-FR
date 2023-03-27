---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version de  [!DNL Target]  ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 1cc630f12f4b9dc1d9c5700bc6174b40d4f0dae2
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 48%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations préliminaires. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 27 mars 2023**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target] Standard/Premium 23.3.1 (28-30 mars 2023)

Cette version sera disponible selon le planning échelonné suivant :

* **28 mars** : région Europe, Moyen-Orient et Afrique (EMEA)
* **29 mars** : région Asie-Pacifique (APAC)
* **30 mars** : région Amériques

Cette version comprend de nouvelles fonctionnalités, améliorations et de nouveaux correctifs :

| Fonctionnalité | Détails |
|--- |--- |
| AEM des fragments de contenu pour une personnalisation et une expérimentation sans interface | Utilisation [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Fragments de contenu] in [!DNL Target] activités. Combinez la facilité d’utilisation et la puissance de l’AEM à de puissantes capacités d’intelligence artificielle (AI) et d’apprentissage automatique (ML) dans [!DNL Target] pour tester et personnaliser des expériences à grande échelle. |
| Mesures A4T optimisées pour [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique]<p>(Date de publication : 30 mars 2023) | [!DNL Target] vous permet de choisir des mesures en fonction d’événements binomiaux ou d’événements continus lors de l’utilisation de [!UICONTROL A4T] pour les activités d’[!UICONTROL affectation automatique] et de [!UICONTROL ciblage automatique].<P>Tenez compte du changement suivant prochainement programmé concernant les mesures prises en charge :<ul><li>[!DNL Target] a conservé le comportement précédent des activités existantes jusqu’au 9 septembre 2023. À compter de cette date, les activités utilisant des mesures non prises en charge seront interrompues pour forcer la migration des activités existantes vers un nouveau comportement.</li></ul> |
| [!UICONTROL Affectation automatique] utilisant [!UICONTROL Analytics for Target] (A4T) | Tutoriel mis à jour :<ul><li>[Configuration de rapports A4T dans  [!DNL Analysis Workspace]  pour les activités d’[!UICONTROL affectation automatique]](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=fr){target=_blank}</li></ul> |
| [!UICONTROL Ciblage automatique] utilisant [!UICONTROL Analytics for Target] (A4T) | Tutoriel mis à jour :<ul><li>[Configuration de rapports A4T dans  [!DNL Analysis Workspace]  pour les activités de [!UICONTROL ciblage automatique]](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=fr){target=_blank}</li></ul> |

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


## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions d’at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |


## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update] :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
