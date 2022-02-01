---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifsde bogues
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que comprend la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 211540256d2bbaddf3053eb1cba2b30b058af8fd
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Notes de mise à jour de Target (actualisées)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API, les SDK, le [!DNL Adobe Experience Platform Web SDK] et la bibliothèque at.js de Target, et ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].)

## Target Standard/Premium 22.2.1 (1 février 2022)

Cette version de maintenance contient les correctifs et améliorations suivants pour la nouvelle version [!UICONTROL Audiences] L’interface utilisateur a été annoncée dans la version 22.1.2 de Target Standard/Premium, qui sera diffusée aux clients de toutes les régions au cours des six prochaines semaines. Ces correctifs alignent les fonctionnalités des audiences créées dans [!DNL Adobe Target Standard/Premium].

* Correction d’un problème qui empêchait les audiences importées depuis [!DNL Adobe Experience Platform], [!DNL Adobe Experience Cloud], et [!DNL Adobe Target Classic] d’être affectée en tant qu’audiences pour les rapports. (TGT-43140)
* Ajout d’une [!UICONTROL Supprimer] dans le [!UICONTROL Audiences] Liste des audiences importées depuis [!DNL Adobe Experience Platform], [!DNL Adobe Experience Cloud], et [!DNL Adobe Target Classic]. Ajout également d’une fonctionnalité de suppression en bloc. (TGT-42914)

## at.js version 2.8.1 (28 janvier 2022)

* Fixe `pageLoad` non mappé à target-global-mbox dans [!UICONTROL Sur la prise de décision du périphérique] (ODD) mode d’exécution hybride.
* Correction d’un problème lié aux détails d’analyse pour la requête de mbox.
* Mise à niveau des dépendances de développement pour corriger les vulnérabilités de sécurité.

## [!DNL Target Standard/Premium] 22.1.2 (26 janvier 2022)

| Fonctionnalité | Détails |
| --- | --- |
| [!DNL Adobe Experience Platform] audiences dans [!DNL Target] | Vous pouvez désormais consommer et utiliser des [!DNL Adobe Experience Platform] audiences dans [!DNL Target]. Le [!DNL Target] l&#39;équipe, [!DNL Experience Platform] [!DNL Destinations] et l’équipe [!DNL Unified Profile Service] L’équipe est heureuse d’annoncer la disponibilité générale des cas d’utilisation de la personnalisation &quot;Même page/Page suivante&quot;.<br>Utilisation des audiences créées dans [!DNL Adobe Experience Platform] fournir des données client plus riches qui mènent à une personnalisation plus impactée. Le [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html){target=_blank} (RTCP), basé sur [!DNL Adobe Experience Platform] permet aux entreprises de rassembler des données connues et anonymes provenant de plusieurs sources d’entreprise afin de créer des profils clients qui peuvent être utilisés pour offrir des expériences client personnalisées sur tous les canaux et appareils en temps réel.<br>Pour plus d’informations, voir [Utilisation des audiences de Adobe Experience Platform](/help/c-target/c-audiences/audiences.md#aep) in *Créer des audiences*.<br>N&#39;oubliez pas de lire le blog Adobe et de regarder la vidéo : [[!DNL Adobe] announces Same Page Enhanced Personalization with [!DNL Adobe Target] et [!DNL Real-time Customer Data Platform]](https://blog.adobe.com/en/publish/2021/10/05/adobe-announces-same-page-enhanced-personalization-with-adobe-target-real-time-customer-data-platform){target=_blank}. |
| Actualisation de l’interface utilisateur d’[!UICONTROL Audiences] | Sʼinscrivant dans le cadre dʼefforts continus réalisés par lʼéquipe [!DNL Adobe Target] pour améliorer lʼexpérience utilisateur pour les utilisateurs de [!DNL Target], cette version donne un coup de jeune aux pages [!UICONTROL Audiences] et [!UICONTROL Scripts de profil] dans lʼinterface utilisateur de [!DNL Target]. Cette mise à jour harmonise et uniformise les modèles de conception qui étaient auparavant incohérents. Elle apporte également de nouvelles améliorations, notamment :<ul><li>Possibilité de sélectionner et de supprimer plusieurs audiences simultanément</li><li>[Conception du créateur dʼaudiences](/help/c-target/c-audiences/create-audience.md) actualisée</li><li>Prise en charge des règles dʼexclusion dans le créateur de règles de la bibliothèque dʼ[!UICONTROL Audiences]</li><li>Nouveau filtre « Source de lʼaudience », pour permettre une détection plus rapide des audiences</li><li>Options de recherche et de filtrage persistantes dans la session</li><li>La possibilité de déplacer des audiences entre les espaces de travail pour [!DNL Target Premium] clients.</li></ul>Pour plus d’informations, consultez [Audiences](/help/c-target/target.md).<br>**REMARQUE**: Cette fonctionnalité sera déployée pour les clients de différentes régions au cours des huit prochaines semaines. |
| Actualisation de lʼinterface utilisateur des [!UICONTROL Scripts de profil] | La bibliothèque de [!UICONTROL Scripts de profil] a également été mise à jour. Elle comprend une interface actualisée ainsi que plusieurs mises à jour relatives à la productivité :<ul><li>Possibilité de sélectionner et de supprimer plusieurs scripts de profil simultanément</li><li>Nouvel éditeur de code pour les scripts de profil</li><li>Mise en évidence de la syntaxe et vérification des erreurs dans lʼéditeur de code</li><li>Paramètres (mbox ou de profil) de saisie automatique des jetons à lʼaide de raccourcis clavier</li></ul>Pour plus dʼinformations, consultez la section [Profils des visiteurs](/help/c-target/c-visitor-profile/visitor-profile.md).<br>**REMARQUE**: Cette fonctionnalité sera déployée pour les clients de différentes régions au cours des huit prochaines semaines. |

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| Modifications de la documentation | Obtenez des informations détaillées sur les mises à jour apportées à ce guide qui ne sont pas incluses dans les notes de mise à jour.<br>Pour plus d’informations, voir [Modifications de la documentation](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notes de mise à jour pour les versions antérieures | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium.<br>Pour plus d’informations, voir [Notes de mise à jour des versions précédentes](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Notes de mise à jour d’Adobe Experience Cloud | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud.<br>Pour plus d’informations, consultez [Notes de mise à jour d’Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr). |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| Mise à jour prioritaire des produits Adobe | Pour recevoir des notifications avancées sur les améliorations à venir des produits Target et d’autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour produit prioritaire Adobe :<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Notes de mise à jour à venir | Pour plus d’informations sur les versions de Target du mois en cours, notamment les informations de version préliminaire, voir la page [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md). |
