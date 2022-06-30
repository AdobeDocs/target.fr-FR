---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bogues
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: fa6324606b32f265084615fd1c13ce6c49921b48
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 72%

---

# Notes de mise à jour de Target (actualisées)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API [!DNL Target], les SDK, l’[!DNL Adobe Experience Platform Web SDK], at.js, ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## [!DNL Target Standard/Premium] 22.6.2 (30 juin 2022)

Cette version contient les fonctionnalités, améliorations et correctifs suivants :

| Fonctionnalité | Description |
| --- | ---  |
| Notifications internes aux produits | Obtenez les notifications internes appropriées suivantes :<ul><li>**Activités**: Notifications pour tous les types d’activité lorsqu’une activité est approuvée ou désactivée, soit manuellement, soit lorsqu’elle atteint sa date de début ou de fin. La notification inclut le nom de l’activité avec un lien vers la page d’aperçu de l’activité.</li><li>**Scripts de profil** Notifications lorsqu’un script de profil est activé ou désactivé, manuellement ou par Target.</li><li>**Flux Recommendations**: Notifications lorsqu’un flux Recommendations est activé ou désactivé, manuellement ou par Target. Des notifications sont également envoyées lorsqu’un flux Recommendations échoue.</li></ul> Par défaut, les notifications sont reçues par les administrateurs de produit, les éditeurs et les approbateurs. Les notifications peuvent être configurées dans les préférences de l’Experience Cloud.<br>Pour plus d’informations, voir [Notifications et annonces](/help/main/c-intro/understand-the-target-ui.md#notifications-announcements). |
| *Guide du développeur d’Adobe Target* | Le *Guide du développeur d’Adobe Target* regroupe tous les [!DNL Target] contenu destiné aux développeurs dans un guide pratique. Ce guide contient des informations sur l’implémentation. [!DNL Target] et [!DNL Recommendations], [!DNL Target] SDK et [!DNL Target] API.<br>Pour plus d’informations, voir [Guide du développeur d’Adobe Target](https://developer.adobe.com/target/){target=_blank}. |

* Les utilisateurs dotés du rôle [!UICONTROL Éditeur] ne peuvent plus modifier les audiences dans les activités dynamiques. (TGT-43582)
* Un message d’avertissement s’affiche si un client tente d’enregistrer une audience sous un nom comportant un point d’exclamation (!) comme premier caractère du nom de l’audience (par exemple, !Londres). (TGT-43643)
* Correction d’un problème en raison duquel les cartes de définition des audiences de certains clients indiquaient qu’une activité terminée était toujours active. (TGT-43527)

## [!DNL Target Standard/Premium] 22.6.1 (version échelonnée : 7-9 juin 2022)

Cette version sera disponible selon le calendrier échelonné suivant :

* **7 juin** : région Asie-Pacifique (APAC)
* **8 juin** : région Amériques
* **9 juin** : région Europe, Moyen-Orient et Afrique (EMEA)

Cette version comprend les améliorations et correctifs suivants :

* Des améliorations ont été apportées à la nouvelle page des [!UICONTROL Audiences] afin d’éviter tout état d’incohérence entre l’ancienne base de données où les audiences étaient stockées dans le passé et la nouvelle architecture qui récupère les informations directement depuis le serveur principal. (TGT-43552)
* Correction d’un problème qui empêchait certains clients d’enregistrer les audiences combinées, car l’interface utilisateur de Target créait des conteneurs « vides ». (TGT-43588)

## Mise à jour de la plateforme Target (25 mai 2022)

Cette version comprend les améliorations et correctifs suivants :

* Ajout [Informations sur le client de l’agent utilisateur](https://developer.adobe.com/target/implement/client-side/atjs/user-agent-and-client-hints/)Prise en charge de {target=_blank}.
* Correction d’un problème qui provoquait, par intermittence, des dépassements de délai lors du rendu des [!UICONTROL Décisions sur les offres] au cours d’activités de [!UICONTROL Ciblage d’expérience] (XT). (TNT-44611)

## at.js version 2.9.0 (27 mai 2022)

* Ajout [Informations sur le client de l’agent utilisateur](https://developer.adobe.com/target/implement/client-side/atjs/user-agent-and-client-hints/)Prise en charge de {target=_blank}.
* Correction d’un bug en raison duquel plusieurs requêtes de mbox sur une même page avaient des ID d’impression différents.

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
