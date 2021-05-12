---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités sont incluses dans la prochaine version ?
feature: Notes de mise à jour
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 9bf6dacce317eff03fd295f7f4fc108fa362b993
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 37%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations préliminaires. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 12er mai 2021**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations de ces pages peuvent être les mêmes, selon le moment où elles sont publiées. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vie** de mbox.js : A compter du 31 mars 2021, la bibliothèque mbox.js  [!DNL Adobe Target] ne sera plus prise en charge. Après le 31 mars 2021, tous les appels effectués à partir de mbox.js échouent et impactent de manière gracieuse vos pages qui comportent [!DNL Target] activités s’exécutant en diffusant le contenu par défaut.
>
>Pour éviter tout problème potentiel sur vos sites, migrez vers la version la plus récente de la nouvelle bibliothèque JavaScript [!DNL Adobe Experience Platform Web SDK] ou at.js. Pour plus d’informations, consultez [Aperçu : implémentation de Target pour le Web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Adobe Experience Platform Web SDK] (17 mai 2021)

Cette version de [!DNL Platform Web SDK] prend en charge les redirections [!UICONTROL Analytics pour la Cible] (A4T) pour [!DNL Target].

## [!DNL Target Standard/Premium] 21.5.2 (Date à déterminer)

Cette version comprend les nouvelles fonctionnalités et améliorations suivantes. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

| Fonctionnalité | Détails |
| --- | --- |
| ![Premium](/help/assets/premium.png) [!DNL Recommendations] | Les améliorations suivantes ont été apportées aux algorithmes de popularité [!DNL Recommendations] :<ul><li>Une nouvelle option de &quot;fenêtre de recherche en amont&quot; (plage de données) de six heures sera disponible pour tous les algorithmes de popularité (les plus consultés/les meilleurs vendeurs) lorsque [!DNL Target] est la source de données comportementales. (Cette fenêtre de recherche est *non* disponible lorsque [!DNL Adobe Analytics] est la source de données comportementale.)</li><li>Lorsqu’ils sont sélectionnés, les algorithmes suivants s’exécutent environ toutes les trois heures (au lieu de toutes les 12 heures).<ul><li>Les plus consultés</li><li>Le plus acheté</li><li>Les plus consultés par catégorie</li><li>Le plus acheté par catégorie</li><li>Les plus consultés par attribut personnalisé (à l’aide de la fonction groupBy)</li><li>Le plus acheté par attribut personnalisé (à l’aide de la fonction groupBy)</li></ul></ul>(TOP-1086) |

Cette version contient les correctifs suivants.

* Sera ajouté à l’approche de la date de publication.

## at.js version 2.5.0 (date à déterminer)

Cette version d’at.js comprend les améliorations et modifications suivantes :

* [Prise en ](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) charge de la prise de décision sur périphérique pour at.js.
* [Prévisualisation ](/help/c-activities/c-activity-qa/activity-qa.md) linksprise en charge des activités Automated Personalization

Cette version supprime également la prise en charge de Microsoft Internet Explorer 10 et versions ultérieures.

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
