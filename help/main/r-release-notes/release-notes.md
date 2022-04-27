---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifsde bogues
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 25dac5f4712fec80323df9b0e00feb9750f5b155
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 56%

---

# Notes de mise à jour de Target (actualisées)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, les notes de mise à jour pour [!DNL Target] API, SDK, le [!DNL Adobe Experience Platform Web SDK], at.js et d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].)

## [!DNL Target] version de la plateforme (27 avril 2022)

Cette version contient les modifications suivantes :

* Avec cette version, vous pouvez prérécupérer du contenu pour [!UICONTROL Personnalisation automatique] (AP) et [!UICONTROL Ciblage automatique] (AT) activités (précédemment non renvoyées par [!DNL Target]). Cela peut modifier les expériences que voient les utilisateurs finaux en cas d’appel de prérécupération (aucune modification du flux &quot;exécuter&quot;) si une activité AP/AT se trouve sur le chemin de diffusion et est plus prioritaire que les autres activités AB/XT qui utilisent le même emplacement pour la diffusion de contenu.

## Version de la plateforme Target (13 avril 2022)

Cette version contient les mises à jour suivantes :

* Correction d’un problème pour s’assurer que le dernier octet des adresses IP est correctement obscurci lors de la capture à l’aide de scripts de profil. (TNT-44076)

## [!DNL Target Standard/Premium] 22.3.1 (5 avril 2022)

Cette version contient les modifications et améliorations suivantes :

* Correction d’un problème en raison duquel la variable [!UICONTROL Inclure] et [!UICONTROL Exclure] options à désactiver pour les audiences combinées lors de la modification d’une activité. (TGT-43422)
* Correction d’un problème qui empêchait certains clients d’afficher la liste des audiences disponibles lors de la modification d’une activité. (TGT-43404)
* Correction d’un problème qui empêchait certains clients de supprimer une adresse IP du[!UICONTROL IP à exclure de [!DNL Target] données de reporting]&quot; list in [!UICONTROL Administration] > [!UICONTROL Reporting]. (TGT-43384)
* Correction d’un problème qui empêchait l’utilisation de nombres négatifs dans le critère d’audience qui vérifiaient que toute variable était &quot;supérieure ou égale à&quot;, &quot;supérieure ou égale à&quot;, &quot;inférieure à&quot; ou &quot;inférieure ou égale à&quot;. (TGT-43367)
* Correction d’un problème qui empêchait les clients d’afficher la variable [!UICONTROL Détails de l’audience] lors de la création d’audiences combinées. (TGT-43303)

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
