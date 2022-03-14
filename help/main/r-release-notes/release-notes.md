---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifsde bogues
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 100%

---

# Notes de mise à jour de Target (actualisées)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API, les SDK, le [!DNL Adobe Experience Platform Web SDK] et la bibliothèque at.js de Target, et ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].)

## Target Standard/Premium 22.2.1 (1er février 2022)

Cette version de maintenance contient les correctifs et améliorations suivants pour la nouvelle interface utilisateur [!UICONTROL Audiences], annoncée dans la version Target Standard/Premium 22.1.2, qui sera déployée auprès des clients de toutes les régions au cours des six prochaines semaines. Ces correctifs harmonisent les fonctionnalités des audiences créées dans [!DNL Adobe Target Standard/Premium].

* Correction d’un problème en raison duquel les audiences importées depuis [!DNL Adobe Experience Platform], [!DNL Adobe Experience Cloud] et [!DNL Adobe Target Classic] nʼétaient pas assignées comme des audiences avec création de rapports. (TGT-43140)
* Ajout d’une option [!UICONTROL Supprimer] dans la liste [!UICONTROL Audiences] pour les audiences importées depuis [!DNL Adobe Experience Platform], [!DNL Adobe Experience Cloud] et [!DNL Adobe Target Classic]. Ajout d’une autre fonctionnalité de suppression en bloc. (TGT-42914)

## at.js version 2.8.1 (28 janvier 2022)

* Correction dʼun problème en raison duquel la fonction `pageLoad` nʼétait pas mappée à target-global-mbox dans le mode d’exécution hybride [!UICONTROL Prise de décision sur le device] (ODD).
* Correction d’un problème lié aux détails des analyses pour les requêtes de mbox.
* Mise à niveau des dépendances de développement pour corriger les vulnérabilités de sécurité.

## [!DNL Target Standard/Premium] 22.1.2 (26 janvier 2022)

| Fonctionnalité | Détails |
| --- | --- |
| Audiences [!DNL Adobe Experience Platform] dans [!DNL Target] | Vous pouvez désormais consommer et utiliser des audiences [!DNL Adobe Experience Platform] dans [!DNL Target]. Les équipes [!DNL Target], [!DNL Experience Platform] [!DNL Destinations] et [!DNL Unified Profile Service] sont ravies dʼannoncer la disponibilité générale des cas d’utilisation « Personnalisation des pages Même page/Page suivante ».<br>Les audiences créées dans [!DNL Adobe Experience Platform] fournissent des données client plus riches, qui conduisent de facto à une personnalisation ayant plus dʼimpact. [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=fr){target=_blank} (RTCDP), qui repose sur [!DNL Adobe Experience Platform], permet aux entreprises de rassembler des données connues et anonymes provenant de plusieurs sources d’entreprise afin de créer des profils clients qui peuvent être utilisés pour offrir des expériences personnalisées aux clients sur tous les canaux et appareils en temps réel.<br>Pour plus d’informations, consultez [Utilisation des audiences d’Adobe Experience Platform](/help/main/c-target/c-audiences/audiences.md#aep) dans *Création d’audiences* et [Cas pratiques de personnalisation de la même page et de la page suivante](https://www.adobe.com/go/destinations-edge-personalization-en){target=_blank} dans le guide *Présentation des destinations*. |
| Actualisation de l’interface utilisateur d’[!UICONTROL Audiences] | Sʼinscrivant dans le cadre dʼefforts continus réalisés par lʼéquipe [!DNL Adobe Target] pour améliorer lʼexpérience utilisateur pour les utilisateurs de [!DNL Target], cette version donne un coup de jeune aux pages [!UICONTROL Audiences] et [!UICONTROL Scripts de profil] dans lʼinterface utilisateur de [!DNL Target]. Cette mise à jour harmonise et uniformise les modèles de conception qui étaient auparavant incohérents. Elle apporte également de nouvelles améliorations, notamment :<ul><li>Possibilité de sélectionner et de supprimer plusieurs audiences simultanément</li><li>[Conception du créateur dʼaudiences](/help/main/c-target/c-audiences/create-audience.md) actualisée</li><li>Prise en charge des règles dʼexclusion dans le créateur de règles de la bibliothèque dʼ[!UICONTROL Audiences]</li><li>Nouveau filtre « Source de lʼaudience », pour permettre une détection plus rapide des audiences</li><li>Options de recherche et de filtrage persistantes dans la session</li><li>Possibilité de déplacer les audiences entre les espaces de travail pour les clients [!DNL Target Premium].</li></ul>Pour plus d’informations, consultez la page [Audiences](/help/main/c-target/target.md).<br>**REMARQUE** : cette fonctionnalité sera déployée auprès des clients de différentes régions au cours des huit prochaines semaines. |
| Actualisation de lʼinterface utilisateur des [!UICONTROL Scripts de profil] | La bibliothèque de [!UICONTROL Scripts de profil] a également été mise à jour. Elle comprend une interface actualisée ainsi que plusieurs mises à jour relatives à la productivité :<ul><li>Possibilité de sélectionner et de supprimer plusieurs scripts de profil simultanément</li><li>Nouvel éditeur de code pour les scripts de profil</li><li>Mise en évidence de la syntaxe et vérification des erreurs dans lʼéditeur de code</li><li>Paramètres (mbox ou de profil) de saisie automatique des jetons à lʼaide de raccourcis clavier</li></ul>Pour plus dʼinformations, consultez la section [Profils des visiteurs](/help/main/c-target/c-visitor-profile/visitor-profile.md).<br>**REMARQUE** : cette fonctionnalité sera déployée auprès des clients de différentes régions au cours des huit prochaines semaines. |

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

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
