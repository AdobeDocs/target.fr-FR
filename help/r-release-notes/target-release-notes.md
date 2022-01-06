---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités sont incluses dans la prochaine version ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 7336522ab5fbe96b887b990437de105a579d9fd8
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 86%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations préliminaires. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 6 janvier 2022**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vie de mbox.js** : depuis le 31 mars 2021, la bibliothèque mbox.js n’est plus prise en charge par [!DNL Adobe Target]. Depuis le 31 mars 2021, tous les appels effectués à partir de mbox.js échouent et ont une incidence sur les pages comportant des activités [!DNL Target] qui s’exécutent en diffusant le contenu par défaut.
>
>Pour éviter tout problème potentiel sur vos sites, migrez vers la version la plus récente du nouveau [!DNL Adobe Experience Platform Web SDK] ou de la bibliothèque JavaScript at.js. Pour plus d’informations, voir [Aperçu : implémentation de Target pour le web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 22.1.1 (6 janvier 2022)

Cette version contient les nouvelles fonctionnalités suivantes :

| Fonctionnalité | Détails |
| --- | --- |
| Utilisation des décisions d’offre dans [!DNL Target] activités | Vous pouvez désormais utiliser [!DNL Adobe Journey Optimizer] décisions d’offre dans [!DNL Target] [!UICONTROL Test A/B] et [!UICONTROL Ciblage d’expérience] (XT) pour déterminer et diffuser la meilleure offre qui s’offre à vos visiteurs sur le web et les appareils mobiles.<br>Pour plus d’informations, voir [Utilisation des décisions d’offre](/help/c-integrating-target-with-mac/ajo/offer-decision.md).<br>**Remarque**: Cette fonctionnalité est disponible pour [!DNL Target] les clients qui ont également accès à un Offer decisioning et qui ont un [!DNL Target] mise en oeuvre basée sur le SDK Web de Adobe Experience Platform. |

## at.js version 2.7.0 (28 octobre 2021)

L’amélioration suivante a été apportée à cette version :

* Ajout de la prise en charge des [Composants web](https://developer.mozilla.org/fr/docs/Web/Web_Components). Cette version dʼat.js est requise pour créer et tester des expériences et des offres personnalisées sur des éléments personnalisés et sur des éléments à lʼintérieur dʼéléments personnalisés. Cette fonctionnalité est incluse dans [!DNL Target Standard/Premium] version 21.10.5.

## [!DNL Target Standard/Premium] version 21.10.5 (28 octobre 2021)

Lʼamélioration suivante a été apportée à cette version de maintenance :

| Fonctionnalité | Détails |
| --- | --- |
| [!UICONTROL Compositeur d’expérience visuelle] (VEC) | Ajout de la prise en charge des [Composants web](https://developer.mozilla.org/en-US/docs/Web/Web_Components). Des expériences et des offres personnalisées peuvent être créées et testées sur des éléments personnalisés et sur des éléments à lʼintérieur dʼéléments personnalisés.<br>Pour plus dʼinformations, consultez la section relative aux [Options du compositeur dʼexpérience visuelle](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#custom). |

## [!DNL Target Standard/Premium] version 21.10.4 (21 octobre 2021)

Lʼamélioration suivante a été apportée à cette version de maintenance :

| Fonctionnalité | Détails |
| --- | --- |
| Recommandations basées sur le panier | Ajout dʼune nouvelle famille dʼalgorithmes pour proposer des recommandations basées sur le contenu du panier du visiteur.<br>Pour plus dʼinformations, consultez la section « Basé sur le panier » dans [Création de critères](/help/c-recommendations/c-algorithms/create-new-algorithm.md), ainsi que les sections « Ajouts au panier / consultations du panier / pages de passage en caisse » et « Exclusion des articles déjà présents dans le panier du visiteur » dans [Planification et implémentation de Recommendations](/help/c-recommendations/plan-implement.md). |

## [!DNL Target Standard/Premium] version 21.10.3 (19 octobre 2021)

Cette version de maintenance comprend les améliorations, modifications et correctifs suivants :

* Correction de problèmes en raison desquels les clients ne parvenaient pas à ouvrir le panneau [!UICONTROL A4T] dans [!DNL Analysis Workspace] en cliquant sur le bouton [!UICONTROL Afficher dans Analytics] dans le rapport dʼactivité de [!DNL Target]. (TGT-42099, TGT-42100)
* Correction dʼun problème en raison duquel le bouton [!UICONTROL Modifier la conception] ne sʼaffichait pas lors de la modification des activités de [!UICONTROL Test A/B] et de [!UICONTROL Ciblage dʼexpérience] (XT) à lʼaide du [!UICONTROL Compositeur dʼexpérience d’après les formulaires]. (TGT-41980)
* Correction dʼun problème en raison duquel la case à cocher [!UICONTROL Compatible] ne sʼaffichait pas dans la sélection de critères lors de la création dʼune activité [!UICONTROL Recommendations]. (TGT-42053)
* Correction dʼun message dʼerreur incorrect qui sʼaffichait lorsque lʼutilisateur ne parvenait pas à sélectionner [!DNL Analytics] en tant que source de rapport (A4T) en raison dʼun manque dʼautorisations [!DNL Analytics]. (TGT-41954)
* Implémentation de plusieurs correctifs en matière dʼaccessibilité pour améliorer la navigation au clavier dans lʼensemble de lʼinterface utilisateur de [!DNL Target].

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
