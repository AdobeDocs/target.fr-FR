---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bugs;mises à jour
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: d2aac088d5f1ae60a4b0e7ac1fff9960e2959130
workflow-type: ht
source-wordcount: '495'
ht-degree: 100%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API [!DNL Target], les SDK, l’[!DNL Adobe Experience Platform Web SDK], at.js, ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## [!DNL Target] Standard/Premium 23.11.1 (13 et 14 novembre 2023)

Cette version est programmée pour les jours suivants :

* **13 novembre** : région Asie-Pacifique (APAC)
* **14 novembre**: région des Amériques
* **14 novembre** : région Europe, Moyen-Orient et Afrique (EMEA)

Cette version comprend les améliorations et correctifs suivants :

* Amélioration de la fonction [QA d’activité](/help/main/c-activities/c-activity-qa/activity-qa.md), de sorte à prendre en charge l’[interdiction des offres dupliquées](/help/main/c-activities/t-automated-personalization/managing-exclusions.md) pour les expériences dans les activités [!UICONTROL Automated Personalization]. (TGT-46627)
* Ajout d’une info-bulle dans l’interface utilisateur de [!DNL Target] pour aider les clientes et clients à comprendre pourquoi il se peut qu’il n’y ait pas de données disponibles dans les rapports d’activité si aucun trafic n’est affecté à l’expérience de contrôle. Un lien vers plus d’informations est inclus dans l’info-bulle : [Pourquoi n’existe-t-il aucune donnée disponible pour le rapport de mon activité ?](/help/main/c-reports/reporting-frequently-asked-questions.md#section_E4722F6445884130951DF79981C8289B). (TGT-46610)
* Correction d’un problème en raison duquel les activités ne s’affichaient pas correctement sur la page [!UICONTROL Activités] pour quelques clientes et clients. (TGT-46830)
* Correction des problèmes suivants qui affectaient les activités utilisant [[!UICONTROL Analytics for Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) comme source de création de rapports :
   * Correction d’un problème qui empêchait certaines personnes d’afficher des données de rapport. (TGT-46557)
   * Correction d’un problème en raison duquel le lien [!UICONTROL Afficher dans Analytics] sur les pages de rapports d’activité ne fonctionnait pas correctement. (TGT-46731)
   * Correction d’un problème qui empêchait les données [!UICONTROL Effet élévateur] et [!UICONTROL Confiance] de s’afficher correctement dans l’interface utilisateur de [!DNL Target]. (TGT-46592, TGT-46554, et TGT-46586)

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions d’at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

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
