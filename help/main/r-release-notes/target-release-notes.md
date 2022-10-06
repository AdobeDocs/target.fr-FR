---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 36c05ee2531009ea74ef9085404d12e389cef743
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 76%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations préliminaires. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 5 octobre 2022**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target] Standard/Premium 22.10.1 (version échelonnée : 10 - 13 octobre 2022)

Cette version sera disponible selon le planning échelonné suivant :

* **10 octobre** : région Asie-Pacifique (APAC)
* **12 octobre** : région des Amériques
* **13 octobre** : région Europe, Moyen-Orient et Afrique (EMEA)

Cette version comprend de nouvelles fonctionnalités, améliorations et de nouveaux correctifs :

| Fonctionnalité | Détails |
| --- | --- |
| [!DNL Adobe Experience Manager] (AEM) fragments d’expérience | Les mises à jour de la fonctionnalité de fragments d’expérience AEM incluent les suivantes :<ul><li>Ajout de la possibilité de filtrer AEM fragments d’expérience par type (HTML ou JSON) dans le [!UICONTROL Offres] liste. (TGT-43121)</li><li>Résolution d’un problème en raison duquel les clients pouvaient insérer les offres de [!UICONTROL fragment d’expérience] JSON lors de l’utilisation du VEC, qui n’est pas pris en charge. Les offres JSON ne peuvent être insérées que lors de l’utilisation du compositeur d’[!UICONTROL expérience basé sur les formulaires]. (TGT-43846)</li></ul>Pour plus d’informations, voir AEM [fragments d’expérience](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md). |
| Nouvelle extension [!UICONTROL Compositeur d’expérience visuelle] pour Google Chrome | Une nouvelle extension [!DNL Adobe Target] [!UICONTROL Compositeur d’expérience visuelle] (VEC) pour Chrome est disponible dans Chrome Web Store.<br>À compter de janvier 2023, le compositeur d’expérience visuelle actuelle [!DNL Target] cessera de fonctionner dans Google Chrome, car Google n’autorise pas les extensions utilisant Manifest V2. Téléchargez la nouvelle extension pour continuer à créer visuellement vos sites web dans [!DNL Target] à partir de la nouvelle année.<br>Les liens suivants présentent les deux extensions dans Chrome Web Store :<ul><li>[Nouvelle extension](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}</li><li>[Ancienne extension](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak){target=_blank}</li></ul>Pour plus d’informations, voir [Extension Visual Editing Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). |
| Mises à jour de la documentation | Les principales mises à jour de la documentation sont les suivantes :<ul><li>Nouveautés et mises à jour [Documentation de l’API d’administration et de création de rapports d’Adobe Target](https://developer.adobe.com/target/administer/admin-api/){target=_blank} comprend une couverture complète des points de terminaison de l’API d’administration et de création de rapports, y compris les propriétés, les offres, les hôtes, les environnements, les clients, les audiences, les activités, etc.<br>Voir ceci et le contenu développeur supplémentaire dans la section [[!DNL Adobe Target] [!UICONTROL Guide du développeur]](https://developer.adobe.com/target/){target=_blank}.</li><li>[Calculs statistiques dans les tests A/B](/help/main/c-reports/statistical-methodology/statistical-calculations.md)<br>Cet article documente les calculs statistiques détaillés utilisés dans les tests A/B manuels dans [!DNL Adobe Target].<br>Les informations de cet article remplacent la variable *Calculs Adobe Target pour les tests A/B* fichier pdf auparavant disponible en téléchargement sur ce site.</li></ul> |

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


## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update] :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
