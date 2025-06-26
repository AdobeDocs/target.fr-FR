---
keywords: notes de mise à jour;versions;mises à jour;futures versions;améliorations;nouvelles fonctionnalités;correctifs;mises à jour;version préliminaire;accès anticipé
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version de [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 926a045e5bcebc8d094ea41a6c1b7c59568a35ab
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 27%

---

# Notes de mise à jour de [!DNL Target] (version préliminaire)

Cet article contient des informations sur les prochaines versions d’[!DNL Adobe Target], y compris les SDK, les API et les bibliothèques JavaScript.

**Dernière mise à jour : 26 juin 2025**

>[!NOTE]
>
>* Les dates de publication, fonctions et autres informations peuvent changer sans préavis.
>
>* Pour afficher des informations sur la version actuelle, voir [ Notes de mise à jour de Target ](release-notes.md).
>
>* Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.6.4 (vendredi 26 juin 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Ajout de l’option [!UICONTROL Rearrange] à l’interface utilisateur du [!UICONTROL Visual Experience Composer] mis à jour pour s’aligner sur les fonctionnalités disponibles dans l’ancien compositeur d’expérience visuelle. (TGT-46957 et TGT-52876)
* Correction d’un problème en raison duquel les modifications apportées aux variantes d’expériences (par exemple, l’expérience B) dans une activité [!UICONTROL A/B Test] n’étaient pas conservées. Après avoir basculé entre les expériences, les modifications apportées à la variante disparaissaient. Ce problème n’a pas affecté l’expérience de contrôle. (TGT-52664)
* Correction d’un problème en raison duquel certains clients ne pouvaient pas créer ou enregistrer d’activités, tandis que d’autres pouvaient effectuer les mêmes actions sans problème. Le problème était incohérent entre les comptes.(TGT-52842)
* Correction d’un problème en raison duquel, dans le VEC mis à jour, les utilisateurs ne pouvaient pas déplacer les modifications vers le [!UICONTROL Page Load event], une fonctionnalité qui existait dans l’interface utilisateur héritée. (TGT-52617)
* Correction d’un problème qui empêchait l’affichage correct de certaines modifications d’activité dans le VEC mis à jour. (TGT-52818)
* Correction d’une exception de pointeur nul qui se produisait lors de la récupération des données de rapport pour les activités [!UICONTROL Automated Personalization] (AP). (TGT-52362)
* Correction d’un problème qui empêchait l’affichage des détails au niveau de l’offre dans le fichier .CSV pour les activités [!UICONTROL Automated Personalization] (AP). (TGT-52675)
* Correction d’un problème lors de l’application de modifications dans le VEC mis à jour. Les modifications s’affichaient initialement correctement, y compris les [!UICONTROL Experience Fragment] attendues. Cependant, lors du changement d’expérience ou de la réalisation de modifications supplémentaires, certaines modifications ne s’appliquent pas en raison de problèmes de sélecteur. (TGT-52679)
* Correction d’un problème en raison duquel, lorsqu’une nouvelle activité était créée en clonant une activité existante, les liens d’assurance qualité de l’activité clonée conservaient incorrectement les URL de page de l’activité d’origine. (TGT-52775)
* Correction d’un problème qui empêchait involontairement [!UICONTROL On-device Decisioning] d’être disponible dans le VEC mis à jour. (TGT-52371)
* Correction d’un problème qui empêchait la modification d’une activité de [!DNL Recommendations] de produit. Lors de la tentative d’accès au VEC via l’interface utilisateur de Target, une erreur s’est produite sur la page [!UICONTROL Overview], empêchant toute modification. (TGT-52823)
* Correction d’un problème qui empêchait l’enregistrement d’une activité [!DNL Recommendations] lorsque les noms d’expérience dépassaient 50 caractères. (TGT-52619)
* Correction d’un problème en raison duquel les clients et clientes ne pouvaient pas enregistrer une activité Recommendations après avoir modifié les critères dans la nouvelle interface utilisateur. Le problème semble être lié aux autorisations et n’affecte pas tous les utilisateurs ayant des rôles similaires. (TGT-52816)
* Correction d’un problème en raison duquel les utilisateurs dotés du rôle [!UICONTROL Editor] ne pouvaient pas modifier une activité [!DNL Recommendations]. Toute tentative de modification de la conception et d’enregistrement de l’activité a provoqué une erreur 403 Interdit, indiquant que le privilège « [editor] » était requis, même si l’utilisateur jouait déjà ce rôle dans l’espace de travail approprié. (TGT-52836)

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
