---
keywords: notes de mise à jour;versions;mises à jour;futures versions;améliorations;nouvelles fonctionnalités;correctifs;mises à jour;version préliminaire;accès anticipé
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version dʼ [!DNL Target], notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités et améliorations sont incluses dans la prochaine version de [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: fda279c909e2bb35e919d1bb4f4b611401a367cf
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 17%

---

# Notes de mise à jour de [!DNL Target] (version préliminaire)

Cet article contient des informations sur les prochaines versions d’[!DNL Adobe Target], y compris les SDK, les API et les bibliothèques JavaScript.

**Dernière mise à jour : 29 août 2025**

>[!NOTE]
>
>* Les dates de publication, fonctions et autres informations peuvent changer sans préavis. Les informations de cet article sont mises à jour fréquemment, en particulier avant les versions .
>
>* Pour afficher des informations sur la version actuelle, voir [ Notes de mise à jour de Target ](release-notes.md).
>
>* Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.8.4 (1er septembre 2025)

Cette version comprend les mises à jour et correctifs suivants :

**[!UICONTROL Activities]**

+++Afficher les détails
* **Les clients ne pouvaient pas copier les noms d’activité ou de document à partir du[!UICONTROL Activity Overview]** : auparavant, les clients ne pouvaient pas copier le nom d’une activité ou l’offre/le document associé directement à partir du [!UICONTROL Activity Overview] dans le processus de création d’activité mis à jour. Cette limitation affectait la convivialité, en particulier sur les écrans plus petits. Les clients peuvent désormais facilement copier les noms des activités et des documents sans solution. (TGT-51850)
* **Ingestion proactive des données client [!DNL Target] traitées lors de la création de l’activité** : amélioration du processus de création d’activité en permettant la collecte proactive de rapports, de contenu et de captures d’écran de clients [!DNL Target]. Cette amélioration corrige les lacunes en matière de données identifiées dans les cas d’utilisation existants et permet d’obtenir des informations plus précises lors de la configuration des activités et des expériences. (TGT-52415)
* **Les activités AP ne récupéraient pas les données prêtes pour le modèle dans la section [!UICONTROL Reports]** : les clients qui visualisaient les activités Automated Personalization (AP) dans la section [!UICONTROL Reports] ne pouvaient pas voir les indicateurs prêts pour le modèle au niveau du groupe de rapports et de l’offre. Ce problème se produisait car les données prêtes pour le modèle n’étaient pas correctement récupérées à partir du serveur principal. La fonctionnalité a été restaurée et les données prêtes pour le modèle apparaissent désormais comme prévu. (TGT-53600 et TGT-53601)

+++

**[!UICONTROL Recommendations]**

+++Afficher les détails
* **Liste de produits n’était pas visible dans la boîte de dialogue [!UICONTROL View Collection] :** auparavant, les clients ne pouvaient pas voir la liste de produits lors de l’affichage d’une collection dans l’onglet [!UICONTROL Recommendations] . La boîte de dialogue [!UICONTROL View Collection] affiche désormais correctement les produits associés, ce qui améliore la transparence et la convivialité dans l’interface utilisateur de Recommendations mise à jour. (TGT-50531)
* **Correction d’un problème qui provoquait un filtrage sensible à la casse dans [!UICONTROL Product Catalog Search] recherche avancée** : le filtrage de recherche avancé dans la page [!UICONTROL Product Catalog Search] ignore désormais correctement le respect de la casse, en s’alignant sur le comportement du serveur principal et des services GraphQL. Cette mise à jour garantit des résultats de suggestions cohérents et précis pour les clients, quelle que soit la casse du texte. (TGT-53585)
* **La recherche avancée dans l’interface utilisateur de [!UICONTROL Product Catalog Search] mise à jour n’a pas fourni de suggestions** : les clients qui utilisaient la fonctionnalité de recherche avancée dans l’interface utilisateur de [!UICONTROL Product Catalog Search] mise à jour devaient saisir des valeurs exactes avec une orthographe correcte, car aucune suggestion ne s’affichait. Cela rendait difficile la localisation efficace des produits. Les suggestions s’affichent désormais comme prévu lors de la saisie de la recherche avancée. (TGT-52008)

+++

**[!UICONTROL Reports]**

+++Afficher les détails
* **Échec du chargement des rapports pour l’audience de bureau en raison d’une erreur de nom d’audience non valide** : les clients et clientes ont rencontré une erreur GraphQL lors de la tentative d’affichage des rapports pour l’audience du processus de création d’activité. Le système a renvoyé un message « Nom d’audience non valide : XXXXX », empêchant l’accès aux données de rapports. Les rapports se chargent désormais correctement pour l’audience Desktop. (TGT-53371)
* **Le changement d’audience sur la page Rapports provoquait des erreurs dans l’interface utilisateur de Target** : les clients et clientes rencontraient des erreurs lors de la sélection de certaines audiences dans la section Reports de l’interface utilisateur de Target mise à jour. Ce problème était dû à une gestion des audiences non valide dans les appels GraphQL principaux, ce qui entraînait des erreurs inattendues et des données manquantes. Le problème a été résolu et les audiences de bureau se chargent désormais sans erreurs, même lorsqu’aucune donnée n’est disponible. (TGT-53370)
+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Afficher les détails
* **Échec du clic sur « Accepter les cookies » à l’aide de l’[!UICONTROL Enhanced Experience Composer] (EEC) en raison d’une fonction manquante** : les clients ont signalé qu’une tentative d’acceptation de cookies via l’EEC entraînait une erreur de console : `handleclickAcceptAllButton is not defined`. La fonctionnalité d’acceptation des cookies fonctionne désormais comme prévu, assurant une expérience plus fluide lors de la création de l’activité dans l’interface utilisateur mise à jour. (TGT-52794)
* **La nouvelle interface utilisateur CEE n’a pas pu charger certaines pages qui étaient auparavant prises en charge dans l’interface utilisateur héritée** : les clients ont signalé que la nouvelle interface n’a pas pu charger certaines pages, qui étaient accessibles dans l’interface utilisateur héritée, malgré le code qui démolissait le iframe présent sur le site. Le processus de création d’activités mis à jour prend désormais en charge le chargement de ces pages, ce qui restaure la compatibilité des workflows de création d’activités. (TGT-53061)
* **Le compositeur d’expérience visuelle affichait un écran blanc vierge lors de la modification d’expériences** : les clients d’un certain client ont signalé que l’écran du compositeur d’expérience visuelle était vide lors de la tentative de modification d’expériences dans le compositeur d’expérience visuelle mis à jour. Ce problème affectait les activités nouvellement créées et les activités plus anciennes, empêchant la continuité du workflow. Le compositeur d’expérience visuelle se charge désormais correctement, ce qui permet aux clients de modifier les expériences sans interruption. (TGT-53547)
* **Le compositeur d’expérience visuelle s’est bloqué et a affiché un écran vide lors du chargement de certaines activités** : les clients d’un certain client ont signalé que le compositeur d’expérience visuelle n’a pas pu charger des activités spécifiques. L’éditeur d’expérience est resté bloqué sur « Application des modifications initiales » avant de se bloquer et d’afficher un écran vide. Les erreurs de console indiquent une échec de lecture des propriétés non définies. L’éditeur charge désormais les activités affectées sans erreur dans le VEC mis à jour. (TGT-53548)

+++

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour : Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Informations détaillées sur les modifications apportées à chaque version du SDK web Platform. |
| [Informations détaillées sur les versions du fichier at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=fr){target=_blank} | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications avancées sur les améliorations à venir de [!DNL Target] et des autres solutions [!DNL Adobe Experience Cloud], inscrivez-vous à [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
