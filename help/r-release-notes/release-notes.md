---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifsde bogues
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la version actuelle d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités sont incluses dans la version actuelle ?
feature: Notes de mise à jour
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: ea5a451e71f390ddacc6ccea583112dd831184dc
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 50%

---

# Notes de mise à jour de Target (actualisées)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API, les SDK et la bibliothèque JavaScript (at.js) de Target et d’autres modifications de plateforme sont également incluses, le cas échéant.

>[!IMPORTANT]
>
>**Fin de vie** de mbox.js : À compter du 31 mars 2021,  [!DNL Adobe Target] ne prendra plus en charge la bibliothèque mbox.js. Après le 31 mars 2021, tous les appels effectués à partir de mbox.js échoueront et auront une influence sur vos pages qui comportent des activités [!DNL Target] qui s’exécutent en diffusant le contenu par défaut.
>
>Migrez vers la version la plus récente de la nouvelle bibliothèque JavaScript [!DNL Adobe Experience Platform Web SDK] ou at.js afin d’éviter tout problème potentiel sur vos sites. Pour plus d’informations, consultez [Aperçu : implémentation de Target pour le Web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].)

## ![Badgegeversion 2.6.0 ](/help/assets/platform.png) [!DNL Adobe Experience Platform Web SDK] du SDK Web Adobe Experience Platform (1er juin 2021)

Cette version de [!DNL Platform Web SDK] prend en charge les éléments suivants :

| Fonctionnalité | Détails |
| --- | --- |
| Prise en charge des redirections avec [!UICONTROL Analytics pour Target] (A4T) | Le SDK Web Platform prend désormais en charge les redirections [!DNL Target] lors de l’utilisation de [A4T](/help/c-integrating-target-with-mac/a4t/a4t.md).<br>Pour plus d’informations, voir  [Analytics  [!DNL Target] pour la mise en oeuvre](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). |
| Jetons de réponse | Le SDK Web Platform prend désormais en charge les jetons de réponse [!DNL Target].<br>Pour plus d’informations, voir  [Jetons de réponse](/help/administrating-target/response-tokens.md). |

## at.js version 2.5.0 (13 mai 2021)

Cette version d’at.js comprend les améliorations et modifications suivantes :

* [Prise en ](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) charge de la prise de décision sur l’appareil pour at.js.
* [Prévisualiser le ](/help/c-activities/c-activity-qa/activity-qa.md) support des liens pour les activités Automated Personalization

Cette version supprime également la prise en charge de Microsoft Internet Explorer 10, d’Internet Explorer 11 et de toutes les versions antérieures. Microsoft Edge est toujours pris en charge dans at.js 2.5.0 et versions ultérieures.

## Target Standard/Premium 21.4.1 (19 avril 2021)

Cette version contient les nouvelles fonctionnalités et améliorations suivantes. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

| Fonctionnalité | Détails |
| --- | --- |
| Prise en charge de la prise de décision sur appareil pour at.js<br>(Date à annoncer) | La prise de décision sur appareil permet aux marketeurs et aux développeurs de proposer des expériences et de la personnalisation sur le navigateur d’un utilisateur avec une latence proche de zéro.<br>Pour plus d’informations, voir Prise de décision  [sur les périphériques pour at.js.](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) |
| ![](/help/assets/premium.png) Opérateurs PremiumList pour les règles de filtrage d’entités | [!DNL Target Recommendations] prend en charge les nouveaux opérateurs de type liste pour les règles de filtrage d’entités. (TGT-39234)<br>Les opérateurs nouvellement ajoutés sont les suivants :<br><ul><li>Contient Dans La Liste</li><li>Ne Se Trouve Pas Dans La Liste</li><li>La Liste Contient Un Élément Dans</li><li>La Liste Ne Contient Pas D’Élément Dans</li><li>La Liste Contient Tous Les Éléments De</li><li>La Liste Ne Contient Pas Tous Les Éléments De</li></ul>Pour plus d’informations, voir &quot;Opérateurs disponibles&quot; dans [Utilisation de règles d’inclusion dynamiques et statiques](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#operators). |

Cette version contient les correctifs suivants.

* Correction d’un problème qui empêchait la synchronisation d’une activité après le changement de l’audience en [!UICONTROL Tous les visiteurs]. (TGT-40259)
* Correction d’un problème qui empêchait la duplication des offres lorsqu’elles étaient utilisées à différents emplacements dans les activités [!UICONTROL Automated Personalization] même si l’option [!UICONTROL Interdire les doublons] était activée. (TGT-39567)
* Correction d’un problème qui empêchait le chargement correct de la page [!UICONTROL Administration] > [!UICONTROL Configuration Scene7]. (TGT-39918)
* Correction d’un problème en raison duquel les propriétés étaient mappées à un espace de travail incorrect. (TGT-39869)
* Correction d’un problème qui provoquait un chargement infini si la requête échouait après avoir modifié l’environnement lors de la création d’une exclusion de recommandations. (TGT-39948)

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| Modifications de la documentation | Obtenez des informations détaillées sur les mises à jour apportées à ce guide qui ne sont pas incluses dans les notes de mise à jour.<br>Pour plus d’informations, voir [Modifications de la documentation](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notes de mise à jour pour les versions antérieures | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium.<br>Pour plus d’informations, voir [Notes de mise à jour des versions précédentes](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Notes de mise à jour d’Adobe Experience Cloud | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud.<br>Pour plus d’informations, consultez [Notes de mise à jour d’Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr). |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| Mise à jour prioritaire des produits Adobe | Pour recevoir des notifications avancées sur les améliorations à venir des produits Target et d’autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour produit prioritaire Adobe :<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Notes de mise à jour à venir | Pour plus d’informations sur les versions de Target du mois en cours, notamment les informations de version préliminaire, voir la page [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md). |
