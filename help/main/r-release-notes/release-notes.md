---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifsde bogues
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: a03975f8f14db3cb8be0850130aab8d34c4c7fc0
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 47%

---

# Notes de mise à jour de Target (actualisées)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, les notes de mise à jour pour [!DNL Target] API, SDK, le [!DNL Adobe Experience Platform Web SDK], at.js et d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].)

## Version de la plateforme Target (13 avril 2022)

Cette version contient les mises à jour suivantes :

* Correction d’un problème pour s’assurer que le dernier octet des adresses IP est correctement obscurci lors de la capture à l’aide de scripts de profil. (TNT-44076)

## [!DNL Target Standard/Premium] 22.3.1 (version échelonnée, date à déterminer)

Cette version contient les modifications et améliorations suivantes :

* Correction d’un problème en raison duquel les modifications apportées aux scripts de profil revenaient au script original non modifié après l’édition, l’activation et la désactivation du script. Le script de profil reste à l’état modifié. (TGT-43249)
* Correction d’un problème qui provoquait le message d’erreur suivant dans la variable [!DNL Target] Interface utilisateur lors du déplacement d’une audience utilisée dans une activité avec l’état &quot;version préliminaire&quot; : &quot;Nous ne pouvons pas terminer votre demande. Veuillez contacter le service à la clientèle Adobe si le problème persiste.&quot; (TGT-43212)
* Correction d’un problème en raison duquel la variable [!UICONTROL Inclure] et [!UICONTROL Exclure] options à désactiver pour les audiences combinées lors de la modification d’une activité. (TGT-43422)
* Correction d’un problème qui empêchait certains clients d’afficher la liste des audiences disponibles lors de la modification d’une activité. (TGT-43404)
* Correction d’un problème qui empêchait certains clients de supprimer une adresse IP du[!UICONTROL IP à exclure de [!DNL Target] données de reporting]&quot; list in [!UICONTROL Administration] > [!UICONTROL Reporting]. (TGT-43384)
* Correction d’un problème qui empêchait l’utilisation de nombres négatifs dans le critère d’audience qui vérifiaient que toute variable était &quot;supérieure ou égale à&quot;, &quot;supérieure ou égale à&quot;, &quot;inférieure à&quot; ou &quot;inférieure ou égale à&quot;. (TGT-43367)
* Correction d’un problème qui empêchait les clients d’afficher la variable [!UICONTROL Détails de l’audience] lors de la création d’audiences combinées. (TGT-43303)
* Correction d’un problème en raison duquel la variable [!DNL Target] Interface utilisateur ou nouvelle [!UICONTROL Audiences] pour que certains clients expirent prématurément. (TGT-42590 et TGT-43273)

## [!DNL Target] Mise à jour de la plateforme (30 mars)

L’amélioration suivante a été apportée à cette version :

* Les mesures de suivi des clics incluront la charge utile Analytics dans les demandes d’API de diffusion pour les activités qui utilisent Analytics comme source de création de rapports (A4T) et les événements de traitement côté client. (TNT-43073)

## [!DNL Target Standard] Actualisation des audiences (28 mars)

Cette version contient les mises à jour suivantes :

* La nouvelle [!UICONTROL Audiences] L’interface utilisateur sera activée pour tous les [!DNL Target Standard] clients.

## Correctifs de l’ingénierie client Target Standard/Premium (22 mars 2022)

Cette version de maintenance comprend les améliorations suivantes :

* Ajout de la fonctionnalité à renvoyer. [!DNL Analytics] données de payload pour `prefetch` vues et `pageLoad` mesures de clic lors de l’utilisation de la variable [!UICONTROL API de diffusion] avec les activités qui utilisent [!UICONTROL Analytics comme source de création de rapports] (A4T). (TNT-43198)
* Mise à jour de la liste des agents utilisateur de filtrage des robots afin d’autoriser un type de navigateur couramment utilisé au Japon. (TNT-43867)

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
