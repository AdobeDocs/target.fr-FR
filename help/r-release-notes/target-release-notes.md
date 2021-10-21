---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités sont incluses dans la prochaine version ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 962464a98f2a7771525d432ba1b51c828f5a8df6
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 57%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations préliminaires. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 20 octobre 2021**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vie de mbox.js** : depuis le 31 mars 2021, la bibliothèque mbox.js n’est plus prise en charge par [!DNL Adobe Target]. Depuis le 31 mars 2021, tous les appels effectués à partir de mbox.js échouent et ont une incidence sur les pages comportant des activités [!DNL Target] qui s’exécutent en diffusant le contenu par défaut.
>
>Pour éviter tout problème potentiel sur vos sites, migrez vers la version la plus récente du nouveau [!DNL Adobe Experience Platform Web SDK] ou de la bibliothèque JavaScript at.js. Pour plus d’informations, voir [Aperçu : implémentation de Target pour le web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 21.10.4 (21 octobre 2021)

Cette version de maintenance contient l’amélioration suivante :

| Fonctionnalité | Détails |
| --- | --- |
| Recommendations basé sur le panier | Ajout d’une nouvelle famille d’algorithmes pour fournir des recommandations basées sur le contenu du panier du visiteur.<br>Pour plus d’informations, voir &quot;Basé sur le panier&quot; dans [Créer des critères](/help/c-recommendations/c-algorithms/create-new-algorithm.md) et &quot;Panier ajoute/panier affichages/pages d’extraction&quot; et &quot;Exclure les éléments déjà dans le panier du visiteur&quot; dans [Planification et mise en oeuvre de Recommendations](/help/c-recommendations/plan-implement.md). |

## [!DNL Target Standard/Premium] 21.10.3 (19 octobre 2021)

Cette version de maintenance comprend les améliorations, modifications et correctifs suivants :

* Correction de problèmes empêchant les clients d’ouvrir le fichier [!UICONTROL A4T] dans [!DNL Analysis Workspace] en cliquant sur le bouton [!UICONTROL Affichage dans Analytics] bouton dans [!DNL Target] rapports d&#39;activités. (TGT-42099, TGT-42100)
* Correction d’un problème qui provoquait le [!UICONTROL Modifier la conception] bouton à ne pas afficher lors de la modification [!UICONTROL Test A/B] et [!UICONTROL Ciblage d’expérience] (XT) à l&#39;aide de la [!UICONTROL Compositeur d’expérience basé sur des formulaires]. (TGT-41980)
* Correction d’un problème qui empêchait la [!UICONTROL Compatible] case à cocher d’affichage dans la sélection de critères lors de la création d’un [!UICONTROL Recommendations] activité. (TGT-42053)
* Correction d’un message d’erreur incorrect qui s’affichait lorsque vous ne pouviez pas sélectionner [!DNL Analytics] comme source de déclaration (A4T) en raison d&#39;un manque de [!DNL Analytics] autorisations. (TGT-41954)
* Mise en oeuvre de plusieurs correctifs d’accessibilité pour améliorer la navigation au clavier dans l’ensemble du [!DNL Target] Interface utilisateur.

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
