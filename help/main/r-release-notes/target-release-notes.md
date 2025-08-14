---
keywords: notes de mise à jour;versions;mises à jour;futures versions;améliorations;nouvelles fonctionnalités;correctifs;mises à jour;version préliminaire;accès anticipé
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version dʼ [!DNL Target], notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version de [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: d09e02db4ea94671e2450d1748b07def932916d9
workflow-type: tm+mt
source-wordcount: '1378'
ht-degree: 11%

---

# Notes de mise à jour de [!DNL Target] (version préliminaire)

Cet article contient des informations sur les prochaines versions d’[!DNL Adobe Target], y compris les SDK, les API et les bibliothèques JavaScript.

**Dernière mise à jour : 24 juillet 2025**

>[!NOTE]
>
>* Les dates de publication, fonctions et autres informations peuvent changer sans préavis.
>
>* Pour afficher des informations sur la version actuelle, voir [ Notes de mise à jour de Target ](release-notes.md).
>
>* Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.8.2 (14 août 2025)

Cette version comprend les correctifs et mises à jour suivants :

**[!UICONTROL Activities]**

+++Afficher les détails
* **Correction d’un problème de chargement d’activité dans l’interface utilisateur de [!DNL Target] mise à jour**: correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour où certaines activités ne se chargeaient pas lors de la tentative de modification. Ce problème entraînait le départ des clients dans un écran de chargement indéfini. Ce problème affectait plusieurs activités et il était signalé de manière incohérente parmi les clients. Grâce à ce correctif, les activités affectées se chargent désormais correctement, ce qui permet une modification transparente et réduit l’interruption des workflows d’activité. (TGT-53209)
* **Correction d’une erreur d’enregistrement dans le processus de création d’activités en raison de la validation du `optionLocalId`** : correction d’un problème dans le processus de création d’activités qui empêchait les clients d’enregistrer les modifications en raison d’une erreur de validation du serveur principal : `OptionLocalIdReferentialIntegrity.ABActivity - Invalid optionLocalIds:` ce problème se produisait lors de la modification d’éléments spécifiques dans une activité, ce qui entraînait l’échec de l’opération d’enregistrement. Le correctif garantit que les références `optionLocalId` sont désormais correctement validées, ce qui permet aux clients d’enregistrer les activités sans rencontrer cette erreur. (TGT-53293)
* **Correction du blocage dans le processus de création d’activités en raison de références d’option non valides lors du changement de page** : correction d’un problème dans le processus de création d’activités en raison duquel l’interface utilisateur se bloquait après avoir changé de page trois fois lors de la modification. Le crash a été déclenché par des références d&#39;option non valides, entraînant des erreurs de console telles que « Option avec localId &#39;7&#39; introuvable. » Grâce à cette mise à jour, les clients peuvent désormais basculer entre les pages et appliquer des modifications sans rencontrer de défaillances ou d’interruptions du système. (TGT-53295)
* **Correction d’une erreur d’enregistrement dans le processus de création d’activités due à une entrée utilisateur non valide lors de la modification d’expériences** : correction d’un problème dans le processus de création d’activités en raison duquel les clients et clientes ne pouvaient pas enregistrer les modifications apportées à une activité en raison d’une erreur d’entrée utilisateur non valide. L’erreur s’est produite lors de la modification d’expériences dans l’interface utilisateur mise à jour, empêchant la validation des mises à jour. L’activité peut désormais être enregistrée avec succès, ce qui permet aux clients de la modifier et de la publier sans interruption. (TGT-53267)
* **Correction d’un problème de chargement dans le processus de création d’activités qui bloquait la modification dans l’interface utilisateur mise à jour** : correction d’un problème dans le processus de création d’activités en raison duquel les clients ne pouvaient pas modifier les activités dans l’interface utilisateur mise à jour en raison d’un écran de chargement continu. Les clients peuvent désormais ouvrir et modifier des activités sans rencontrer d’échecs de chargement. (TGT-53415)

+++

**Fragments d’expérience (XF)**

+++Afficher les détails
* **Correction d’un problème dans le processus de création d’activités qui autorisait la modification involontaire par HTML des fragments exportés par AEM** : correction d’un problème dans le processus de création d’activités qui permettait aux clients de modifier l’HTML des [!DNL Experience Fragments] (XF) exportés depuis [!DNL Adobe Experience Manager] (AEM) dans [!DNL Target]. Ce comportement n’était pas prévu, car les fichiers XF doivent rester verrouillés pour modification une fois publiés à partir d’AEM. Le correctif garantit que l’option « Modifier HTML » n’est plus disponible pour les fragments exportés par AEM, préservant ainsi l’intégrité du contenu et la gouvernance attendue. (TGT-53286)

+++

**Mode assurance qualité**

+++Afficher les détails
* **Correction d’un problème dans le processus de création d’activités en raison duquel les espaces de début dans les URL provoquaient des liens d’assurance qualité rompus** : correction d’un problème dans le processus de création d’activités en raison duquel les espaces de début dans l’URL de l’activité n’étaient pas correctement supprimés lors de l’enregistrement. Cela entraînait des liens d’assurance qualité non valides et un formatage incorrect dans le serveur principal. Après la mise à jour, les URL sont désormais enregistrées proprement, ce qui empêche les liens rompus et améliore la fiabilité des workflows d’assurance qualité pour les clients et les clientes. (TGT-53427)

+++

**[!UICONTROL Recommendations]**

+++Afficher les détails
* **Correction d’un problème dans l’interface utilisateur de recherche de catalogue en raison duquel la recherche avancée ne pouvait pas fournir de suggestions** : correction d’un problème dans la nouvelle interface utilisateur de [!UICONTROL Catalog Search] en raison duquel la fonction de [!UICONTROL Advanced Search] ne pouvait pas fournir de suggestions. Les utilisateurs devaient saisir des valeurs exactes avec une orthographe précise, ce qui rendait la recherche difficile et susceptible de contenir des erreurs. Grâce à ce correctif, le [!UICONTROL Advanced Search] offre désormais des suggestions pertinentes au fur et à mesure que les utilisateurs saisissent, améliorant ainsi la convivialité et réduisant le frottement lors de la localisation des produits. (TGT-52008)
* **Résolution de plusieurs problèmes d’interface utilisateur et de filtrage pour améliorer la réactivité et l’interaction des entités** : résolution de plusieurs problèmes, notamment la faible réactivité des détails des critères sur les appareils à petit écran, l’absence de résultats lors de la sélection de « Tous les groupes d’hôtes » dans le filtre Environnement et l’impossibilité d’interagir avec des entités sans nom. Ces correctifs améliorent la convivialité sur toutes les tailles d’écran, assurent un filtrage précis et permettent une interaction complète avec toutes les entités de produit, améliorant ainsi l’expérience globale pour les utilisateurs. (TGT-52992)
* **Correction d’ID de produit manquants dans la vue détaillée Recommendations lors de la création de l’activité** : correction d’un problème dans le processus de création d’activité [!DNL Recommendations] en raison duquel les ID de produit étaient manquants dans l’écran des détails du produit, ce qui rendait difficile pour les clients de copier ou de référencer les ID de produit pendant les workflows. Les identifiants de produit apparaissent désormais clairement dans la vue détaillée, ce qui améliore la visibilité et permet une gestion plus efficace des produits pour les clients. (TGT-51964)
* **Correction d’un problème dans le processus de création d’activités en raison duquel les messages de produit ne s’affichaient pas dans la vue de recommandations**: correction d’un problème dans le processus de création d’activités en raison duquel la colonne [!UICONTROL Message] de la vue de [!DNL Recommendations] n’affichait pas les données de produit, même si des messages étaient présents. Les clients devaient supprimer et ajouter à nouveau manuellement la colonne pour afficher temporairement le contenu, qui disparaissait souvent à nouveau lors du défilement ou de la recherche. Cette mise à jour restaure une visibilité cohérente des messages de produit, améliorant la navigation dans le catalogue et les workflows de révision. (TGT-52777)
* **Correction d’un problème dans le processus de création d’activités, en raison duquel la sélection de « Tous les groupes d’hôtes » n’avait renvoyé aucun résultat dans la vue de recommandations** : correction d’un problème dans le processus de création d’activités, en raison duquel la sélection de l’environnement « Tous les groupes d’hôtes » dans la vue de [!DNL Recommendations] n’avait renvoyé aucun résultat. Les clients peuvent désormais afficher comme prévu les données de produit sur tous les groupes d’hôtes, ce qui améliore la visibilité et la précision du filtrage lors de la configuration des activités. (TGT-53006)
* **Correction d’un problème dans le processus de création d’activités en raison duquel le bouton de promotion front ne persistait pas après l’enregistrement** : correction d’un problème dans le processus de création d’activités en raison duquel la désactivation du bouton de promotion front dans les paramètres d’activité ne persistait pas après l’enregistrement. Les clients qui tentaient de supprimer la promotion principale ont trouvé que le bouton (bascule) était réactivé lors de leur visite de l’activité, empêchant une personnalisation correcte. Cette mise à jour permet d’enregistrer les modifications de manière fiable, ce qui donne aux clients un contrôle total sur les paramètres de promotion. (TGT-53215)

+++

**Compositeur d’expérience visuelle**

+++Afficher les détails
* **Correction des problèmes de chargement des activités et de bouton de [!UICONTROL Cancel] dans le processus de création d’activités** : correction d’un problème dans le processus de création d’activités où le chargement de certaines activités échouait, empêchant les clients d’accéder aux modifications. En outre, le bouton [!UICONTROL Cancel] ne répondait pas, ce qui empêchait les clients d’arrêter le processus de chargement ou de quitter la vue de modification. Ce correctif garantit que les activités se chargent désormais de manière fiable et que le bouton [!UICONTROL Cancel] fonctionne comme prévu, améliorant ainsi la stabilité globale et l’expérience utilisateur du compositeur d’expérience visuelle. (VEC)(TGT-53218)
* **Correction d’un problème de changement d’expérience dans l’interface utilisateur du VEC mise à jour qui bloquait la modification et désactivait [!UICONTROL Cancel] bouton** : correction d’un problème dans l’interface utilisateur du VEC mise à jour où les modifications ne se chargeaient pas lors du changement d’expérience dans une activité de ciblage d’expérience (XT). Les clients ne pouvaient pas modifier les expériences au-delà de celle qu’ils avaient saisie initialement et le bouton [!UICONTROL Cancel] était manquant ou ne répondait pas. Ce correctif garantit que les modifications se chargent désormais correctement sur toutes les expériences et que le bouton [!UICONTROL Cancel] fonctionne de manière fiable, même sans l’extension d’assistance, améliorant les workflows de modification et réduisant la frustration. (TGT-53256)
* **Correction d’un problème d’écran blanc lors du changement entre plusieurs expériences dans le processus de création d’activités** : correction d’un problème en raison duquel le changement entre plusieurs expériences provoquait un écran blanc. Correction également d’un problème dans le processus de création d’activités en raison duquel les clients et clientes rencontraient un écran blanc lorsqu’ils tentaient de modifier plusieurs expériences au sein d’une activité. Ce problème se produisait après l’application des modifications à deux expériences, puis la sélection d’une troisième expérience, ce qui empêchait d’autres modifications. La mise à jour assure des transitions fluides entre les expériences, ce qui permet aux clients d’apporter des modifications sans interruption. (TGT-53266)
* **Correction d’un problème dans le VEC en raison duquel les modifications de code personnalisé n’étaient pas enregistrées de manière fiable dans les sessions de modification** : correction d’un problème en raison duquel les modifications de code personnalisé effectuées dans le compositeur d’expérience visuelle (VEC) n’étaient pas enregistrées de manière fiable en une seule tentative. Les clients ont signalé que des modifications, telles que des mises à jour de style ou des modifications d’HTML, manquaient par intermittence sur le site web et dans les URL d’assurance qualité, même après avoir utilisé les boutons [!UICONTROL Edit Content] et [!UICONTROL Save] final. Cette régression a été résolue, en veillant à ce que toutes les modifications du code personnalisé persistent comme prévu entre les sessions de modification.** (TGT-53418)

+++

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
