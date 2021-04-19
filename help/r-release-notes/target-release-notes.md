---
keywords: notes de mise à jour ; versions ; mises à jour ; versions futures ; améliorations ; nouvelles fonctionnalités ; correctifs ; mises à jour ; pré-version
description: Découvrez les nouvelles fonctionnalités, les améliorations et les correctifs inclus dans la prochaine version d’Adobe Target, y compris les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités sont incluses dans la prochaine version ?
feature: Notes de mise à jour
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
translation-type: tm+mt
source-git-commit: 9b6123fd0f9d44e43bd8e6bae1ddd7ef8c00d2e3
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 20%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations de pré-version. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 16 avril 2021**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations de ces pages peuvent être les mêmes, selon le moment où elles sont publiées. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vie** de mbox.js : A compter du 31 mars 2021, la bibliothèque mbox.js  [!DNL Adobe Target] ne sera plus prise en charge. Après le 31 mars 2021, tous les appels effectués à partir de mbox.js échouent et impactent de manière gracieuse vos pages qui comportent [!DNL Target] activités s’exécutant en diffusant le contenu par défaut.
>
>Pour éviter tout problème potentiel sur vos sites, migrez vers la version la plus récente de la nouvelle bibliothèque JavaScript [!DNL Adobe Experience Platform Web SDK] ou at.js. Pour plus d&#39;informations, voir [Présentation : implémenter la Cible pour le web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## Target Standard/Premium 21.4.1 (19 avril 2021)

Cette version comprend les nouvelles fonctionnalités et améliorations suivantes. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

| Fonctionnalité | Détails |
| --- | --- |
| Prise en charge de la prise de décision sur périphérique pour at.js | La prise de décision sur périphérique permet aux marketeurs et aux développeurs de proposer des expériences et de la personnalisation sur le navigateur d’un utilisateur avec une latence proche de zéro.<br>Pour plus d’informations, voir Prise de décision  [sur périphérique pour at.js.](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) |
| ![Opérateurs basés sur ](/help/assets/premium.png) PremiumList pour les règles de filtrage d’entité | [!DNL Target Recommendations] prend en charge les nouveaux opérateurs basés sur les listes pour les règles de filtrage d’entité. (TGT-39234)<br>Les opérateurs récemment ajoutés sont :<br><ul><li>Contient Dans La Liste</li><li>N’est pas contenu dans la Liste</li><li>La liste Contient Un Élément Dans</li><li>La liste Ne Contient Pas D&#39;Élément Dans</li><li>La liste Contient Tous Les Éléments Dans</li><li>La liste Ne Contient Pas Tous Les Éléments Dans</li></ul>Pour plus d’informations, voir &quot;Opérateurs disponibles&quot; dans [Utilisation de règles d’inclusion dynamiques et statiques](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#operators). |

Cette version contient les correctifs suivants.

* Correction d’un problème qui empêchait la synchronisation d’une activité après avoir modifié l’audience en [!UICONTROL Tous les Visiteurs]. (TGT-40259)
* Correction d’un problème en raison duquel les offres ne pouvaient pas être dupliquées lorsqu’elles étaient utilisées à différents emplacements dans les activités [!UICONTROL Automated Personalization] même si l’option [!UICONTROL Interdire les Duplicata] était activée. (TGT-39567)
* Correction d’un problème qui empêchait le chargement correct de la page [!UICONTROL Administration] > [!UICONTROL Configuration de Scene7]. (TGT-39918)
* Correction d’un problème en raison duquel les propriétés étaient mises en correspondance avec un espace de travail incorrect. (TGT-39869)
* Correction d’un problème qui entraînait un chargement infini si la requête échouait après avoir modifié l’environnement lors de la création d’une exclusion de recommandations. (TGT-39948)

## at.js version 2.5.0 (19 avril 2021)

Cette version d’at.js comprend les améliorations et modifications suivantes :

* [Prise en ](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) charge de la prise de décision sur périphérique pour at.js.
* [Prévisualisation ](/help/c-activities/c-activity-qa/activity-qa.md) linksprise en charge des activités Automated Personalization

Cette version supprime également la prise en charge de Microsoft Internet Explorer 10 et versions ultérieures.

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
