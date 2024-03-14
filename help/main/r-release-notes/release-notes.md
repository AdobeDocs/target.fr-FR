---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bugs;mises à jour
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 5df9ba6eb249dfc690279177ecb5936aaefa7bdd
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 57%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API [!DNL Target], les SDK, l’[!DNL Adobe Experience Platform Web SDK], at.js, ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## Mises à jour pour `Browser:iPad` et `Browser:iPhone` in [!UICONTROL Browser] Attributs d’audience (30 avril 2024)

| Mises à jour | Détails |
|--- |--- |
| [!UICONTROL Browser:iPad] et [!UICONTROL Browser:iPhone] mis à jour dans [Attributs du navigateur](/help/main/c-target/c-audiences/c-target-rules/browser.md) utilisé lors de la création d’audiences. | [!DNL Adobe Target] vous permet de [cibler sur l’un des attributs de catégorie les plus courants](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), y compris les visiteurs qui utilisent une variable [options de navigateur ou de navigateur](/help/main/c-target/c-audiences/c-target-rules/browser.md) lorsqu’ils visitent votre page.<P>Commencer avec la méthode [!DNL Target] Standard/Premium 24.3.1 (4-6 mars 2024), audiences intégrées créées à l’aide de l’interface utilisateur de Target, telles que `Browser:iPad` et `Browser:iPhone` sera mis à jour afin d’effectuer un ciblage correct pour [!DNL iPad] et [!DNL iPhone] using `profile.mobile.deviceVendor`, `profile.mobile.isMobilePhone` et `profile.mobile.isTablet`.<P>Cette mise à jour ne nécessite aucune action du côté des clients.<p><B>Important</b>: pour que les clients effectuent un ciblage correct pour [!DNL iPad] et [!DNL iPhone] dans les scripts de profil (et les segments JavaScript), les modifications manuelles doivent être effectuées par le client **30 avril 2024**. Pour obtenir des exemples d’autres paramètres qui doivent être modifiés manuellement, voir [Mises à jour pour [!DNL iPad] et [!DNL iPhone] in [!UICONTROL Browser] attributs d’audience](/help/main/c-target/c-audiences/c-target-rules/browser.md#updates). |

## [!UICONTROL Visual Editing Helper] extension (14 mars 2023)

Cette version de contient les améliorations et correctifs suivants pour le [[!DNL Adobe Experience Cloud Editing Helper]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) extension pour [!DNL Google Chrome]:

* Amélioration du mécanisme de chargement des iFrames lors de la création sur les sites web des clients.
* Correction d’un problème en raison duquel l’extension dupliquait les cookies lors de la création dans le [!UICONTROL Visual Experience Composer] (VEC).
* Suppression de la dépendance de téléchargement d’at.js pour les clients qui utilisent la variable [SDK Web Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank}.

## [!DNL Target] Standard/Premium 24.3.1 (4-6 mars 2024)

Cette version est programmée pour les jours suivants :

* **4 mars** : région Europe, Moyen-Orient et Afrique (EMEA)
* **5 mars** : région Asie-Pacifique (APAC)
* **6 mars** : région Amériques

Cette version comprend les améliorations et correctifs suivants :

* Correction de la logique qui calcule le nombre de sélecteurs uniques dans une activité. (TGT-47878)
* Correction d’un problème qui provoquait [!UICONTROL Multivariate] (MVT) activités configurées avec [!UICONTROL Analytics for Target] (A4T) de ne pas s’afficher correctement. (TGT-47490)
* Amélioration du message d’avertissement affiché dans les rapports lorsqu’une expérience sans trafic est utilisée comme expérience de contrôle. (TGT-47537)
* Ajout de nombreux correctifs d’arrière-plan et de localisation.

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
