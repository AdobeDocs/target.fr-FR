---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bogues
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 6a2071e08b60db90021239a14a1167f79a3ed879
workflow-type: tm+mt
source-wordcount: '1056'
ht-degree: 94%

---

# Notes de mise à jour de Target (actualisées)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API [!DNL Target], les SDK, l’[!DNL Adobe Experience Platform Web SDK], at.js, ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## Version de l’API Modèles (23 novembre 2022)

La nouvelle [!DNL Adobe Target] L’API Modèles, également appelée API de Liste bloquée, permet aux utilisateurs d’afficher et de gérer la liste des fonctionnalités utilisées dans les modèles d’apprentissage automatique pour [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Ciblage automatique] (AT).

Pour plus d’informations, voir [Présentation de l’API de modèles](https://developer.adobe.com/target/before-administer/models-api/){target=_blank} dans la variable *Guide du développeur d’Adobe Target*.

## [!DNL Target] Standard/Premium 22.10.3 (version échelonnée : 25 - 27 octobre 2022)

Cette version sera disponible selon le planning échelonné suivant :

* **25 octobre** : région Europe, Moyen-Orient et Afrique (EMEA)
* **26 octobre** : région Asie-Pacifique (APAC)
* **27 octobre** : région des Amériques

Cette version comprend de nouvelles fonctionnalités, améliorations et de nouveaux correctifs :

| Fonctionnalité | Détails |
| --- | --- |
| Mesures A4T optimisées pour l’[!UICONTROL affectation automatique] et le [!UICONTROL ciblage automatique]<br> (disponible pour sélectionner des clients pour le test. Sera disponible pour tous les clients dans une prochaine version.) | Tenez compte des changements suivants :<ul><li>Ajout de la prise en charge des mesures non binaires et de maximisation dans les rapports A4T [!UICONTROL Analytics for Target] pour les activités d’[!UICONTROL affectation automatique] et de [!UICONTROL ciblage automatique].</li><li>Comportement conservé pour les activités existantes jusqu’à février 2023. À compter de cette date, les activités seront interrompues pour forcer la migration des activités existantes vers un nouveau comportement.</li><li>À compter du 20 février 2023, les mesures `averagetimespentonsite`, `bouncerate` et `entries` dans les activités [!DNL Target] seront obsolètes.</li></ul> |

* Ajout d’info-bulles dans l’interface utilisateur [!DNL Target] pour aider les clients à accéder plus efficacement au créateur d’audiences et à apprendre à utiliser des fonctionnalités qui ne sont pas familières. (TGT-44139)
* Ajout d’une fonctionnalité pour empêcher les clients de modifier une activité désactivée par [!DNL Target], car il utilise des mesures non prises en charge. Un message dans l’interface utilisateur demande aux clients de dupliquer l’activité, puis de mettre à jour la mesure de conversion.

   Avec cette version, les mesures `averagetimespentonsite`, `bouncerate`, et `entries` dans les activités [!DNL Target] seront abandonnées pour les nouvelles activités. Les activités existantes peuvent utiliser ces mesures jusqu’en mai 2023.

* Ajout d’une info-bulle dans l’interface utilisateur [!DNL Target] pour aider les clients à sélectionner un critère d’optimisation lors de la création ou de la modification d’une activité [!UICONTROL Ciblage automatique] qui utilise A4T.

## [!DNL Target] Standard/Premium 22.10.1 (version échelonnée : 10 - 13 octobre 2022)

Cette version sera disponible selon le planning échelonné suivant :

* **10 octobre** : région Asie-Pacifique (APAC)
* **12 octobre** : région des Amériques
* **13 octobre** : région Europe, Moyen-Orient et Afrique (EMEA)

Cette version comprend de nouvelles fonctionnalités, améliorations et de nouveaux correctifs :

| Fonctionnalité | Détails |
| --- | --- |
| Fragments d’expérience [!DNL Adobe Experience Manager] (AEM) | La fonctionnalité de fragments d’expérience AEM comprend les mises à jour suivantes :<ul><li>Ajout de la possibilité de filtrer les fragments d’expérience AEM par type (HTML ou JSON) dans la liste [!UICONTROL Offres]. (TGT-43121)</li><li>Résolution d’un problème en raison duquel les clients pouvaient insérer les offres de [!UICONTROL fragment d’expérience] JSON lors de l’utilisation du VEC, qui n’est pas pris en charge. Les offres JSON ne peuvent être insérées que lors de l’utilisation du compositeur d’[!UICONTROL expérience basé sur les formulaires]. (TGT-43846)</li></ul>Pour plus d’informations, consultez [Fragments d’expérience](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) AEM. |
| Nouvelle extension [!UICONTROL Compositeur d’expérience visuelle] pour Google Chrome | Une nouvelle extension [!DNL Adobe Target] [!UICONTROL Compositeur d’expérience visuelle] (VEC) pour Chrome est disponible dans Chrome Web Store.<br>À compter de janvier 2023, le compositeur d’expérience visuelle actuelle [!DNL Target] cessera de fonctionner dans Google Chrome, car Google n’autorise pas les extensions utilisant Manifest V2. Téléchargez la nouvelle extension pour continuer à créer visuellement vos sites web dans [!DNL Target] à partir de la nouvelle année.<br>Les liens suivants présentent les deux extensions dans Chrome Web Store :<ul><li>[Nouvelle extension](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}</li><li>[Ancienne extension](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak){target=_blank}</li></ul>Pour plus d’informations, consultez [Extension Assistant d’édition visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). |
| Mises à jour de la documentation | Les principales mises à jour de la documentation sont les suivantes :<ul><li>La nouvelle [Documentation de l’API d’administration et de création de rapports d’Adobe Target](https://developer.adobe.com/target/administer/admin-api/){target=_blank} mise à jour comprend une couverture complète des points d’entrée de l’API d’administration et de création de rapports, y compris les propriétés, les offres, les hôtes, les environnements, les clients, les audiences, les activités, etc.<br>Voir cette rubrique et le contenu développeur supplémentaire dans le [[!DNL Adobe Target] [!UICONTROL Guide du développeur]](https://developer.adobe.com/target/){target=_blank}.</li><li>[Calculs statistiques dans les tests A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md)<br> Cet article documente les calculs statistiques détaillés utilisés dans les tests A/B manuels dans [!DNL Adobe Target].<br>Les informations de cet article remplacent le fichier PDF *Calculs Adobe Target pour les tests A/B* auparavant disponible en téléchargement sur ce site.</li></ul> |

* Résolution d’un problème qui empêchait l’affichage correct des informations relatives aux règles en matière d’audience dans la fenêtre d’informations [!UICONTROL Amélioration des audiences]. (TGT-43917)
* Amélioration des performances de l’interface utilisateur [!DNL Target] lors du chargement d’audiences approchant la [limite recommandée des règles en matière de ciblage](/help/main/r-troubleshooting-target/target-limits.md#targeting-rules). (TGT-43675)
* Résolution d’un problème en raison duquel certains composants ne s’affichaient pas correctement dans le panneau [!UICONTROL Modifications] de la page [!UICONTROL Expériences] lors de la création ou de la modification des activités dans le compositeur d’expérience visuelle après le passage du mode [!UICONTROL Composer] au mode [!UICONTROL Parcourir]. (TGT-43300)
* Résolution d’un problème qui empêchait certains clients d’archiver les activités [!UICONTROL Test A/B] qui utilisent le [!UICONTROL ciblage automatique]. (TGT-40978)
* Ajout de la possibilité d’utiliser automatiquement une seule offre à plusieurs emplacements au sein d’un seul groupe de rapports. (TGT-40689)

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

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
