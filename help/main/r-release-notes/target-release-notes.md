---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version de [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: f44514c0b5ab643dec35aa230e46b88428f9e42b
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 52%

---

# Notes de mise à jour de [!DNL Target] (version préliminaire)

Cet article contient des informations sur les prochaines versions d’[!DNL Adobe Target], y compris les SDK, les API et les bibliothèques JavaScript.

**Dernière mise à jour : 22 mai 2023**

>[!NOTE]
>
>Les dates de publication, fonctions et autres informations peuvent changer sans préavis.
>
>Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target] Standard/Premium 23.5.1 (23-25 mai 2023)

Cette version sera disponible selon le planning échelonné suivant :

23 mai : Région Europe, Moyen-Orient et Afrique (EMEA) 24 mai : Région Asie-Pacifique (APAC) 25 mai : Région des Amériques

Cette version comprend de nouvelles fonctionnalités, de nouvelles améliorations et de nouveaux correctifs :

| Fonctionnalité | Détails |
|--- |--- |
| Attributs de profil Real-Time CDP partagés avec [!DNL Target] | Les [!UICONTROL Attributs de profil Real-Time CDP] peut être transmis à [!DNL Target] afin d’être utilisés dans les offres HTML et JSON.<P>Pour plus d’informations, consultez la section [Partager des attributs de profil Real-Time CDP avec [!DNL Target]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#rtcdp-profile-attributes). |

* Correction d’un problème qui empêchait certains clients de créer des audiences avec des profils de visiteur utilisant des opérateurs &quot;supérieur à&quot; ou &quot;inférieur à&quot;. (TGT-45271)
* Plusieurs correctifs de localisation ont été apportés dans l’ensemble de l’interface utilisateur de [!DNL Target].
* Mise à jour de l’interface utilisateur de Target à différents emplacements pour une actualisation prochaine de l’interface utilisateur (les modifications se trouvent derrière un indicateur de fonctionnalité jusqu’à ce que les mises à jour soient publiées).

## [!DNL Target] Standard/Premium 23.5.2 (31 mai 2023)

Cette version comprend les améliorations et correctifs suivants :

* Correction d’un problème en raison duquel une page vierge s’affichait lors de la génération d’un jeton d’autorisation d’API Profile. (TGT-45387)
* Correction d’un problème qui empêchait l’affichage d’une image dans la variable [!UICONTROL Créer une conception] si le nom de l’image contient 18 030 caractères GB. (TGT-44614)
* Correction d’un problème en raison duquel les rapports pour [!UICONTROL Personnalisation automatique] activités à geler pendant l&#39;analyse. (TGT-44820)
* Correction d’un problème en raison duquel aucune activité ne s’affichait dans l’interface utilisateur de Target pour l’espace de travail par défaut pour certains clients. (TGT-45286)
* Mise à jour du comportement de l’indicateur &quot;Ne pas autoriser les doublons&quot;. Les indicateurs d’offres répétées exclus sont mis à jour afin d’autoriser les offres répétées si elles sont l’offre de contenu par défaut (pour les API v3, v4) et d’autoriser les options en double si les options font référence à l’offre de contenu par défaut et si aucun modèle n’est défini. (TNT-46617)
* Correction d’un problème en raison duquel un paramètre de requête était ajouté à une URL qui empêchait le chargement de la page dans le compositeur d’expérience visuelle (VEC). (TGT-44873)
* Correction d’un problème en raison duquel certains caractères étaient incorrectement placés dans une séquence d’échappement dans le texte/HTML dans les expériences. (TGT-44600)

## [!DNL Target] Standard/Premium 23.5.3 (Date à déterminer)

Les améliorations suivantes ont été apportées à cette version :

| Fonctionnalité | Détails |
|--- |--- |
| [!UICONTROL Mode AQ] pour [!UICONTROL Automated Personalization] activités | [!DNL Adobe Target] [!UICONTROL Mode AQ] est désormais disponible pour [!UICONTROL Automated Personalization] activités, remplacement [!UICONTROL Aperçu des liens] .<P>Pour plus d’informations, voir [AQ d’activité](/help/main/c-activities/c-activity-qa/activity-qa.md).. |

* Améliorations des performances pour interdire les doublons (notamment la réduction du temps de chargement) pendant que [gestion des exclusions](/help/main/c-activities/t-automated-personalization/managing-exclusions.md#concept_4EF78013F80E48EFA024AE0274C9F037) in [!UICONTROL Automated Personalization] activités.

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions d’at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update] :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
