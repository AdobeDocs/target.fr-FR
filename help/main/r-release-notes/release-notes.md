---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bogues
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: c351044163a6fb32ca72fa015724d3b0388c059a
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 93%

---

# Notes de mise à jour de Target (actualisées)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API [!DNL Target], les SDK, l’[!DNL Adobe Experience Platform Web SDK], at.js, ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## Version de la plateforme Target (25 mai 2022)

Cette version comprend les améliorations et correctifs suivants :

* Ajout [Informations sur le client de l’agent utilisateur](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/user-agent-and-client-hints.md) prise en charge.
* Correction d’un problème qui provoquait par intermittence des dépassements de délai lors du rendu. [!UICONTROL Décisions sur les offres] in [!UICONTROL Ciblage d’expérience] (XT). (TNT-44611)

## at.js version 2.9.0 (27 mai 2022)

* Ajout [Informations sur le client de l’agent utilisateur](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/user-agent-and-client-hints.md) prise en charge.
* Correction d’un bogue en raison duquel plusieurs requêtes de mbox sur la même page avaient des ID d’impression différents.

## [!DNL Target Standard/Premium] 22.5.1 (sortie échelonnée ; 11-13 mai 2022)

Cette version sera disponible selon le calendrier échelonné suivant :

* **11 mai** : région Asie-Pacifique (APAC)
* **12 mai**: Région des Amériques
* **13 mai** : région Europe, Moyen-Orient et Afrique (EMEA)

Cette version comprend les améliorations et correctifs suivants :

* Correction d’un problème qui provoquait une erreur JavaScript et empêchait certains clients d’accéder aux détails de certaines activités [!UICONTROL Automated Personalization] (AP). (TGT-43526)
* Correction d’un problème qui empêchait certains clients d’ajouter (ou de modifier) une offre spécifique à une activité AP. (TGT-43503)
* Correction d’un problème dans l’interface utilisateur [!DNL Target] qui affichait le message d’erreur suivant : « Votre mbox globale peut ne pas être synchronisée. Réessayez de lʼenregistrer ». Ce problème était un problème de l’interface utilisateur et n’avait aucune incidence sur les implémentations des clients. (TGT-43475)
* Correction d’un problème qui empêchait un client de modifier des ajustements et des audiences au niveau de l’expérience pour une activité si ceux-ci étaient créés avant le déploiement de la nouvelle interface utilisateur [!UICONTROL Audiences]. (TGT-43433)
* Correction d’un problème en raison duquel les clients pouvaient sélectionner des audiences [!DNL Adobe Audience Manager] (AAM) en double lors de la modification des audiences avec création de rapports pour une activité. (TGT-43430)
* Correction d’un problème qui empêchait les clients de créer des audiences en double, mais dans différents espaces de travail. (TGT-43423)
* Correction d’un problème qui empêchait les clients de supprimer les emplacements où des offres ad hoc étaient créées dans les activités créées dans le [!UICONTROL Compositeur d’expérience d’après les formulaires]. (TGT-43315)
* Correction d’un problème qui empêchait les clients d’accéder aux offres de code après avoir cliqué sur des offres d’image, puis avoir actualisé l’interface utilisateur. (TGT-43566)
* Correction d’un problème en raison duquel les modifications apportées aux scripts de profil revenaient au script original non modifié après l’édition, l’activation et la désactivation du script. Le script de profil reste désormais à l’état modifié. (TGT-43249)
* Correction d’un problème qui provoquait l’erreur suivante lors de la tentative de déplacement d’une audience vers un autre espace de travail : « Nous ne pouvons pas terminer votre demande. Si le problème persiste, contactez l’assistance clientèle Adobe. » (TGT-43212)
* Correction d’une erreur qui provoquait une erreur lors du clonage des modifications de code personnalisé pour les pages Application d’une seule page (SPA). (TGT-43137)
* Correction d’un problème en raison duquel la promotion d’origine était affectée après la duplication d’une expérience, puis la modification de la promotion. (TGT-41775)

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
