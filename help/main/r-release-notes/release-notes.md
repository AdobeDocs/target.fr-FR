---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifs de bogues;mises à jour,mises à jour actuelles
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle dʼ [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
landing-page-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
short-description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’ [!DNL Adobe Target].
title: Que contient la version actuelle ?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: dc9797cc0afdb3fed5b4bb95cf134e702cec42d7
workflow-type: tm+mt
source-wordcount: '1372'
ht-degree: 26%

---

# Notes de mise à jour [!DNL Target] (actuelles)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API [!DNL Target], les SDK, l’[!DNL Adobe Experience Platform Web SDK], at.js, ainsi que d’autres modifications de plateforme sont également incluses, le cas échéant.

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne à [!DNL Adobe].)

## [!DNL Target Standard/Premium] 25.5.3 (22 mai 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’un problème en raison duquel la fonction de recherche par nom dans la liste [!UICONTROL Activities] ne fonctionnait pas correctement avec les requêtes à plusieurs mots. (TGT-52529)
* Correction d’un problème qui empêchait l’exclusion d’expériences des activités [!UICONTROL Automated Personalization] (AP). (TGT-52383)
* Correction d’un problème en raison duquel l’option « [!UICONTROL Contains] » était absente des [!UICONTROL Filter Rules] lors de la gestion du contenu dans les activités AP. (TGT-52384)
* Correction d’une incohérence dans les rapports des activités [!UICONTROL Automated Personalization] (AP), spécifiquement liée à la manière dont les offres par défaut sont suivies et signalées à l’aide de valeurs `optionLocalId` du système interne de [!DNL Target].
* Correction d’un problème en raison duquel les liens d’assurance qualité ne fournissaient pas l’expérience d’activité prévue. (TGT-52163)
* Correction d’un problème en raison duquel les utilisateurs disposant d’autorisations [!UICONTROL Approver] étaient incorrectement bloqués lors de la modification des activités en direct, et recevaient un message d’erreur « Accès refusé ». (TGT-52416)
* Correction d’un problème en raison duquel les ajustements d’audience ne s’affichaient pas pour certaines activités dans l’interface utilisateur de [!DNL Target] mise à jour. (TGT-52057)
* Correction d’un problème en raison duquel les affinements d’audience et les audiences d’activité étaient inversés dans l’interface utilisateur mise à jour. (TGT-52158)
* Correction d’un problème en raison duquel la génération d’offres ad hoc entraînait des offres en double. (TGT-51938)
* Correction d’un problème qui bloquait les mises à jour d’offre et affichait incorrectement une erreur « Utilisateur non valide ». (TGT-52361)
* Correction d’un problème qui empêchait l’enregistrement des activités existantes et déclenchait une erreur « Entrée utilisateur non valide ». (TGT-52422)
* Correction d’un problème qui bloquait la modification des offres HTML existantes et déclenchait une erreur « Entrée utilisateur non valide » lors de l’enregistrement, même si aucune modification de code n’était apportée. (TGT-52351)
* Correction d’un problème qui empêchait [!DNL Target] de reconnaître le caractère « # » dans l’URL d’un site web. (TGT-52093)
* Correction d’un problème qui empêchait la modification des activités [!DNL Recommendations] pour ajouter ou mettre à jour des promotions, ce qui provoquait des échecs d’enregistrement et des promotions en double. (TGT-52343)
* Correction d’un problème qui empêchait les modifications apportées aux critères ou aux conceptions dans les activités [!DNL Recommendations], ce qui entraînait une erreur « JSON non valide : nom de propriété non reconnu ». (TGT-52375)
* Correction d’un problème en raison duquel les critères de séquence ne s’affichaient pas correctement dans le [!UICONTROL Visual Experience Composer] (VEC) pour les activités [!DNL Recommendations]. (TGT-52435)
* Correction d’un problème en raison duquel les vues n’étaient pas correctement identifiées sur les pages SPA lors de l’utilisation du [!DNL Adobe Experience Platform Web SDK] . (TGT-52106)
* Correction d’un problème en raison duquel les détails d’ODS (On-Device Decisioning) n’étaient pas enregistrés correctement, bien qu’ils aient été inclus dans la payload de l’opération par lots. (TGT-52406)
* Ajout d’un champ `audienceMetadata` aux activités, permettant sa lecture et sa mise à jour lors de la modification. (TGT-51004)
* Ajout d’un message d’erreur pour alerter les utilisateurs lorsqu’une période d’audience n’est pas valide. (TGT52522)
* Mise à jour de la structure des activités pour prendre en charge les audiences en double de différents types. (TGT-51200)

## Version [!DNL Adobe Target] [!DNL AI Assistant] (16 mai 2025)

Nous sommes ravis d&#39;annoncer le lancement du [!DNL AI Assistant] en [!DNL Adobe Target] ! Cette puissante fonctionnalité d’interface utilisateur est conçue pour vous aider à parcourir et à comprendre facilement [!DNL Target] concepts. Disponible sur plusieurs produits en [!DNL Adobe Experience Cloud], dont [!DNL Target], [!DNL AI Assistant] est là pour révolutionner votre expérience.

[!DNL AI Assistant] dans [!UICONTROL Target] est un outil de conversation que vous pouvez utiliser pour accélérer vos workflows avec des applications et des services [!DNL Experience Platform]. Utilisez [!DNL AI Assistant] pour accroître votre productivité globale et améliorer votre compréhension des connaissances sur les produits

En [!DNL Target], la première phase d’[!DNL AI Assistant] fournit une connaissance inestimable des produits, basée sur la documentation [!DNL Experience League]. Que vous configuriez un script de profil, résolviez les erreurs ou envisagiez une mise à niveau vers AEP Web SDK, [!DNL AI Assistant] a tout prévu.

Pour plus d’informations, consultez la présentation de l’assistant d’IA de Adobe Experience Platform [&#128279;](/help/main/c-intro/ai-assistant.md).

## [!DNL Target Standard/Premium] 25.5.2 (8 mai 2025)

Cette version comprend les correctifs et mises à jour suivants :

* [!DNL Target] utilisateurs disposant de droits [!UICONTROL Product Administrator] et [!UICONTROL System Administrator] peuvent désormais modifier tous les paramètres des pages [!UICONTROL Administration], quel que soit leur rôle dans [!DNL Target]. Les utilisateurs ne disposant pas de ces autorisations ont accès en lecture seule à ces paramètres. Cette mise à jour garantit un contrôle d’accès plus strict sur les [paramètres d’administration](/help/main/administrating-target/administrating-target.md). (TGT-48179)
* Correction d’un problème de mise en cache qui empêchait l’enregistrement de l’activité [Préférences du site](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#settings). (TGT-52213)
* Correction d’un problème en raison duquel les clients ne pouvaient pas activer la sélection par ID et classe dans la section [!UICONTROL Site Preferences] après le chargement du site dans le VEC. Le paramètre [!UICONTROL Site Preferences] est automatiquement rétabli à désactivé même après activation. (TGT-52207)
* Correction d’un problème en raison duquel le [!UICONTROL Visual Experience Composer] (VEC) n’affichait pas la page correcte lorsque les URL [diffusion de page](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#settings) se terminaient par une barre oblique (/). (TGT-52237)
* Correction d’un problème qui empêchait la suppression des modifications de code personnalisé lors du changement d’expériences. (TGT-52240)
* Correction d’un problème en raison duquel les modifications d’HTML dans le VEC recouvraient des éléments de page existants. (TGT-52265)
* Correction d’un problème qui empêchait la modification du code personnalisé dans le VEC mis à jour en raison du fait que le code personnalisé existant n’était pas visible dans l’éditeur. (TGT-52272)
* Correction d’un problème entraînant l’affichage d’un message d’erreur « Les noms en double ne sont pas autorisés » lors de l’enregistrement d’une activité Recommendations. (TGT-52318)
* Correction d’un problème dans le VEC mis à jour qui empêchait les clients et clientes de modifier des éléments de texte ou de supprimer des objets conteneur. (TGT-52348)
* Correction d’un problème qui empêchait l’affichage correct des [!DNL Customer Journey Analytics] sur une page de [!UICONTROL Overview] d’activités. (TGT-52359)
* Correction d’un problème qui empêchait les groupes de génération de rapports de persister dans les activités [!UICONTROL Automated Personalization] (AP). (TGT-52368)
* Correction d’un problème qui empêchait l’enregistrement des activités qui incluaient Offer Decisioning. (TGT-52390)
* Correction d’un problème où l’offre par défaut était sélectionnée, mais où le contenu d’autres offres était affiché dans les activités [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Multivariate Test] (MVT). (TGT-52372)
* Correction de la logique des autorisations GET pour vérifier avec OU entre l’accès complet à l’organisation et l’accès spécifique organisation + utilisateur. (TGT-52374)
* Correction d’un problème en raison duquel les noms d’audience ne s’affichaient pas après la sélection d’une audience pour [!UICONTROL Managed Content] et [!UICONTROL Reporting Audiences], même si [!UICONTROL Show Only Selected] était activé. (TGT-52393)

## [!DNL Target Standard/Premium] 25.5.1 (5 mai 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’un problème qui empêchait l’affichage d’ajustements d’audience pour certaines activités dans l’interface utilisateur mise à jour. (TGT-52057)
* Correction d’un problème qui empêchait l’utilisation d’audiences combinées dans les activités . (TGT-52346)
* Correction d’un problème qui empêchait la création d’une activité dans un espace de travail autre que celui par défaut à l’aide d’une audience d’activité unique du même espace de travail. (TGE-52349)
* Correction d’un problème en raison duquel les audiences d’activité uniquement disparaissaient de l’interface utilisateur mise à jour après la création et la sélection d’une nouvelle audience. (TGT=52091)
* Correction d’un problème qui empêchait l’utilisation d’audiences en double dans les activités . (TGT-51200 et TGT-52057)
* Correction d’un problème en raison duquel les affinements d’audience et les audiences d’activité étaient inversés dans l’interface utilisateur mise à jour. (TGT-52158)
* Correction d’un problème qui empêchait la création d’une nouvelle activité en raison de l’erreur de saisie utilisateur : « Espace de travail non par défaut non autorisé pour cet utilisateur ». (TGT-52267)
* Correction d’un problème qui empêchait l’affichage des offres dans l’interface utilisateur mise à jour pour les espaces de travail par défaut et non par défaut. [!DNL Target] affiche désormais les offres des deux espaces de travail. (TGT-52339)
* Correction d’un problème en raison duquel [!DNL Target] n’avertissait pas les clients lors de la modification d’une activité et d’un élément de site web modifié. (TGT-52100)
* Correction d’un problème en raison duquel la modification d’une offre avec des offres ad hoc créait une nouvelle offre au lieu de mettre à jour l’offre existante. (TGT-52135)
* Correction d’un problème qui provoquait une erreur de payload non valide lors du déplacement d’offres vers des dossiers. (TGT-52325)
* Correction d’un problème qui provoquait une erreur de saisie de l’utilisateur lors du déplacement d’offres vers des dossiers. (TGT-52296)
* Ajout d’un champ `audienceMetadata` pour chaque activité et vérification de sa lecture et de sa mise à jour lors de sa modification. (TGT-51004)

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : SDK web Experience Platform Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=fr) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| [Modifications de la documentation](/help/main/r-release-notes/doc-change.md) | Obtenez des informations détaillées sur les mises à jour apportées à ce guide qui ne sont pas incluses dans les notes de mise à jour. |
| [Notes de mise à jour pour les versions antérieures](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium. |
| [Notes De Mise À Jour De Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr){target=_blank} | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud. |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| [Mise à jour prioritaire des produits Adobe](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Recevez des notifications anticipées sur les améliorations à venir de [!DNL Target] et d’autres solutions [!DNL Adobe Experience Cloud]. |
| [Notes de mise à jour de Target (version préliminaire)](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Informations sur les versions de Target du mois en cours, y compris des informations sur la version préliminaire. |
