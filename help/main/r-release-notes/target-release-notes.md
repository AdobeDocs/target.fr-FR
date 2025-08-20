---
keywords: notes de mise à jour;versions;mises à jour;futures versions;améliorations;nouvelles fonctionnalités;correctifs;mises à jour;version préliminaire;accès anticipé
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version dʼ [!DNL Target], notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version de [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 7fcff4220f5954614867815fb4a67444dfd595ee
workflow-type: tm+mt
source-wordcount: '1036'
ht-degree: 14%

---

# Notes de mise à jour de [!DNL Target] (version préliminaire)

Cet article contient des informations sur les prochaines versions d’[!DNL Adobe Target], y compris les SDK, les API et les bibliothèques JavaScript.

**Dernière mise à jour : 20 août 2025**

>[!NOTE]
>
>* Les dates de publication, fonctions et autres informations peuvent changer sans préavis. Les informations de cet article sont mises à jour fréquemment, en particulier avant les versions .
>
>* Pour afficher des informations sur la version actuelle, voir [ Notes de mise à jour de Target ](release-notes.md).
>
>* Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.8.3 (21 août 2025)

Cette version comprend les mises à jour et correctifs suivants :

**Décisions d’offre**

+++Afficher les détails
* **Correction d’un problème qui empêchait les clients de modifier les offres de décision et de sélectionner des éléments de page spécifiques dans l’interface utilisateur mise à jour** : dans le processus de création d’activité mis à jour, les clients ne pouvaient pas modifier les offres de décision existantes ni sélectionner des éléments de page spécifiques dans le compositeur d’expérience visuelle (VEC). Les offres de décision s’affichaient incorrectement en tant qu’offres HTML et les modifications apportées lors de la modification n’ont pas été enregistrées. En outre, certaines URL régionales, telles que le site du Japon, n’ont pas pu se charger correctement dans le VEC, ce qui a bloqué la création et les mises à jour d’activités. (TGT-53425)
* **Correction d’un problème en raison duquel les sélecteurs de [!UICONTROL Offer Decision] ne pouvaient pas être modifiés et changés de manière inattendue après l’enregistrement** : dans le processus de création d’activité mis à jour, les clients ne pouvaient pas modifier le sélecteur de [!UICONTROL Offer Decision] comme prévu. Les tentatives de modification du sélecteur ont échoué, et le sélecteur est revenu à une valeur incorrecte après l’enregistrement. Cela entraînait la disparition de l’offre de décision du Compositeur d’expérience visuelle (VEC), bloquant d’autres modifications. (TGT-53433)
* **Correction d’un problème en raison duquel les [!UICONTROL Offer Decisions] disparaissaient de l’activité après l’enregistrement** : les [!UICONTROL Offer Decisions] ajoutées pendant le processus de création d’activité n’étaient pas conservées après l’enregistrement et la réouverture de l’activité. Ce problème se produisait lors de la modification de contenu dynamique et de l’insertion de [!UICONTROL Offer Decisions] avec des sélecteurs et des propriétés spécifiques. (TGT-53434)

+++

**Recommendations**

+++Afficher les détails
* **Correction d’un problème dans l’interface utilisateur des recommandations en raison duquel le téléchargement d’un CSV de critères personnalisés renvoyait une erreur 404** : correction d’un problème en raison duquel les clients et clientes ne pouvaient pas télécharger le CSV de critères personnalisés dans le processus de création d’activités. (TGT-51966)
* **Correction d’un chargement incohérent des images dans[!UICONTROL Catalog Search]** : correction d’un problème en raison duquel les miniatures et les images dans [!UICONTROL &#x200B; Catalog Search] ne se chargeaient pas de manière cohérente dans le processus de création d’activités. Les images ne s’affichaient pas, sauf si la colonne « URL de la miniature » était visible et que certaines images de produit étaient partiellement chargées ou pas du tout après des actions de navigation ou de recherche. (TGT-52778)
* **Correction d’un problème en raison duquel la modification d’une recommandation dans une expérience dupliquée avait un impact sur l’expérience d’origine** : les clients ont signalé que la modification d’une recommandation dans une expérience dupliquée modifiait involontairement l’expérience d’origine. Plus précisément, après avoir dupliqué l’expérience B dans le processus de création d’activité et modifié sa conception ou ses critères, les mêmes modifications ont été répercutées dans l’expérience B d’origine, bien qu’il s’agisse d’entités distinctes. (TGT-53369)
* **Correction d’un problème en raison duquel les modifications apportées à une expérience dupliquée affectaient involontairement l’expérience originale dans une activité :** les clients et clientes ont signalé que lors de la duplication d’une expérience au sein d’une activité et de l’affectation d’une nouvelle audience, toute modification apportée à la conception ou aux critères de l’expérience dupliquée était également répercutée dans l’expérience originale. Cela se produisait même si aucune modification n’était apportée directement à la version d’origine, ce qui affectait la possibilité de créer des variations indépendantes au sein de la même activité. (TGT-53361)
* **Correction d’un problème en raison duquel le [!UICONTROL Recommendation Catalog] échouait par intermittence à afficher les données complètes d’attributs de produit** : dans l’interface utilisateur de [!DNL Recommendations] mise à jour, les clients rencontraient un problème en raison duquel certains attributs de produit, tels que message, n’étaient pas affichés de manière cohérente dans les résultats de la recherche catalogue, même si les données existaient dans le flux. Pour résoudre ce problème, les clients devaient reconfigurer manuellement la visibilité de la colonne pour récupérer les valeurs manquantes. (TGT-52769)
* **Correction d’un problème en raison duquel une [!UICONTROL Front Promotion] ne pouvait pas être désactivée dans une activité active** : les tentatives de désactivation d’une [!UICONTROL Front Promotion] dans une activité active n’étaient pas enregistrées. Après avoir sélectionné [!UICONTROL Change Promotion] et désactivé cette option, la promotion est restée active lors de la modification de l’activité, empêchant la mise à jour des configurations de recommandation. Les paramètres de promotion s’enregistrent désormais correctement, ce qui permet aux clients de désactiver ou de modifier les promotions dans les activités dynamiques comme prévu. (TGT-53231)
* **Correction d’un problème en raison duquel l’activation d’un [!DNL Recommendations] [!UICONTROL Promotion] sans données déclenchait un message d’erreur flou** : l’activation d’un [!UICONTROL Front] ou d’un [!UICONTROL Back Promotion] dans une activité [!DNL Recommendations] sans spécifier les valeurs requises générait un message d’erreur « Entrée non valide » générique. Le problème sous-jacent était l’absence d’un champ de configuration , mais le message d’erreur n’indiquait pas clairement la cause, ce qui rendait le dépannage difficile. Le processus de création d’activités génère désormais un message d’erreur clair et exploitable lorsque des champs obligatoires, tels que des `collectionId` ou des règles, sont manquants, ce qui permet aux clients d’identifier et de résoudre rapidement les problèmes de configuration. (TGT-52616)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Afficher les détails
* **Correction d’un problème dans le processus de création d’activités qui bloquait la progression vers [!UICONTROL Targeting] étape dans les activités AP**: correction d’un problème dans le processus de création d’activités en raison duquel les clients ne pouvaient pas passer à l’étape de [!UICONTROL Targeting] dans les activités [!UICONTROL Automated Personalization] (AP) à moins que deux emplacements ne soient ajoutés. Ce comportement différait de l’expérience précédente, où un seul emplacement avec plusieurs offres était suffisant. Cette exigence a été corrigée, ce qui permet aux clients de continuer à utiliser des configurations à emplacement unique dans le cadre de leurs workflows AP. (TGT-53426)
* **Correction d’un problème en raison duquel le nouveau processus de création d’activités ne définissait pas le paramètre fmt=png-alpha pour les images transparentes** : dans l’interface utilisateur mise à jour, les images insérées pendant le processus de création d’activités n’incluaient plus le paramètre `fmt=png-alpha` par défaut, ce qui entraînait une perte de transparence. Ce comportement était différent de celui de l’interface utilisateur précédente, qui ajoutait automatiquement le paramètre aux URL des images, préservant ainsi les arrière-plans transparents. (TGT-52615)

+++

**[!UICONTROL Workspaces]**

+++Afficher les détails
* **Correction d’un problème en raison duquel un client limité à un seul espace de travail pouvait afficher les activités d’autres espaces de travail** : les clients dont l’accès était limité à un espace de travail pouvaient de manière inattendue afficher les activités de tous les espaces de travail lors de la sélection de [!UICONTROL All Workspaces] dans le processus de création d’activités. Cette visibilité entraînait un risque de modifications involontaires des activités en direct dans d’autres espaces de travail, ce qui pouvait avoir un impact sur les performances du site web. (TGT-53101)
* **Correction d’un problème en raison duquel un client pouvait afficher des activités à partir de l’[!UICONTROL Default Workspace] sans y avoir accès :** un client avec un accès limité à l’espace de travail d’évaluation pouvait afficher des activités à partir de l’[!UICONTROL Default Workspace] via le processus de création d’activités. Cela se produisait malgré une configuration de serveur principal et des droits d’accès corrects. (TGT-53297)

+++

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
