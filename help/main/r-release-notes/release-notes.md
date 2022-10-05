---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bogues
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: dea956fe5d28200515a9638306a7d879585cb794
workflow-type: tm+mt
source-wordcount: '841'
ht-degree: 43%

---

# Notes de mise à jour de Target (actualisées)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API [!DNL Target], les SDK, l’[!DNL Adobe Experience Platform Web SDK], at.js, ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## [!DNL Target] Standard/Premium 22.10.1 (version échelonnée du 5 au 7 octobre 2022)

Cette version sera disponible selon le calendrier échelonné suivant :

* **5 octobre**: Région Asie-Pacifique (APAC)
* **6 octobre**: Région des Amériques
* **7 octobre**: Région Europe, Moyen-Orient et Afrique (EMEA)

Cette version contient les nouvelles fonctionnalités, améliorations et correctifs suivants :

| Fonctionnalité | Détails |
| --- | --- |
| [!DNL Adobe Experience Manager] (AEM) fragments d’expérience | Les mises à jour de la fonctionnalité de fragments d’expérience AEM incluent les suivantes :<ul><li>Ajout de la possibilité de filtrer AEM fragments d’expérience par type (HTML ou JSON) dans le [!UICONTROL Offres] liste. (TGT-43121)</li><li>Correction d’un problème en raison duquel les clients pouvaient insérer JSON. [!UICONTROL Fragment d’expérience] offres lors de l’utilisation du VEC, qui n’est pas pris en charge. Les offres JSON ne peuvent être insérées que lors de l’utilisation de la variable [!UICONTROL Expérience d’après les formulaires] compositeur. (TGT-43846)</li></ul>Pour plus d’informations, voir AEM [fragments d’expérience](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md). |
| Nouveau [!UICONTROL Compositeur d’expérience visuelle] extension pour Google Chrome | Une nouvelle [!DNL Adobe Target] [!UICONTROL Compositeur d’expérience visuelle] (VEC) pour Chrome est disponible dans Chrome Web Store.<br>À compter de janvier 2023, la variable [!DNL Target] L’extension d’assistance de VEC cessera de fonctionner dans Google Chrome, car Google n’autorise pas les extensions utilisant Manifest V2. Téléchargez la nouvelle extension pour continuer à créer visuellement vos sites web dans [!DNL Target] à partir de la nouvelle année.<br>Les liens suivants présentent les deux extensions dans Chrome Web Store :<ul><li>[Nouvelle extension](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}</li><li>[Ancienne extension](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak){target=_blank}</li></ul>Pour plus d’informations, voir [Extension Visual Editing Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). |
| Mesures A4T optimisées pour [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique]<br>(Date exacte de publication à déterminer.) | Tenez compte des modifications suivantes :<ul><li>Ajout de la prise en charge des mesures binaires et de maximisation dans [!UICONTROL Analytics pour Target] Rapports A4T pour [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique] activités</li><li>Comportement conservé pour les activités existantes jusqu’au 20 février 2023. À compter de cette date, les activités seront interrompues pour forcer la migration des activités existantes vers un nouveau comportement.</li><li>À compter du 20 février 2023, la prise en charge de `averagetimespentonsite`, `bouncerate`, et `entries` mesures dans [!DNL Target] Les activités seront obsolètes.</li></ul> |
| Mises à jour de la documentation | Les principales mises à jour de la documentation sont les suivantes :<ul><li>Nouveautés et mises à jour [Documentation de l’API d’administration et de création de rapports d’Adobe Target](https://developer.adobe.com/target/administer/admin-api/){target=_blank} comprend une couverture complète des points de terminaison de l’API d’administration et de création de rapports, y compris les propriétés, les offres, les hôtes, les environnements, les clients, les audiences, les activités, etc.<br>Voir ceci et le contenu développeur supplémentaire dans la section [[!DNL Adobe Target] [!UICONTROL Guide du développeur]](https://developer.adobe.com/target/){target=_blank}.</li><li>[Calculs statistiques dans les tests A/B](/help/main/c-reports/statistical-methodology/statistical-calculations.md)<br>Cet article documente les calculs statistiques détaillés utilisés dans les tests A/B manuels dans [!DNL Adobe Target].<br>Les informations de cet article remplacent la variable *Calculs Adobe Target pour les tests A/B* fichier pdf auparavant disponible en téléchargement sur ce site.</li></ul> |

* Correction d’un problème qui empêchait l’affichage correct des informations des règles d’audience dans la variable [!UICONTROL Amélioration des audiences] fenêtre d’informations. (TGT-43917)
* Amélioration des performances de la fonction [!DNL Target] de l’interface utilisateur lors du chargement d’audiences approchant la variable [limite recommandée des règles de ciblage](/help/main/r-troubleshooting-target/target-limits.md#targeting-rules). (TGT-43675)
* Correction d’un problème en raison duquel certains composants ne s’affichaient pas correctement dans la variable [!UICONTROL Modifications] du panneau [!UICONTROL Expériences] lors de la création ou de la modification d’activités dans le compositeur d’expérience visuelle après le passage de [!UICONTROL Composer] to [!UICONTROL Parcourir] mode . (TGT-43300)
* Correction d’un problème qui empêchait certains clients d’archiver [!UICONTROL Test A/B] activités qui utilisent [!UICONTROL Ciblage automatique]. (TGT-40978)
* Ajout de la possibilité d’utiliser automatiquement une seule offre à plusieurs emplacements au sein d’un seul groupe de génération de rapports. (TGT-40689)

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
