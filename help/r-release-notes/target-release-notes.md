---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités sont incluses dans la prochaine version ?
feature: Notes de mise à jour
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 146395f5453093ca34b259a143ff4e4c63be949b
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 69%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations préliminaires. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 7 juin 2021**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vie de mbox.js** : depuis le 31 mars 2021, la bibliothèque mbox.js n’est plus prise en charge par [!DNL Adobe Target]. Depuis le 31 mars 2021, tous les appels effectués à partir de mbox.js échouent et ont une incidence sur les pages comportant des activités [!DNL Target] qui s’exécutent en diffusant le contenu par défaut.
>
>Pour éviter tout problème potentiel sur vos sites, migrez vers la version la plus récente du nouveau [!DNL Adobe Experience Platform Web SDK] ou de la bibliothèque JavaScript at.js. Pour plus d’informations, voir [Aperçu : implémentation de Target pour le web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 21.5.2 (Date à déterminer)

Cette version comprend les nouvelles fonctionnalités et améliorations suivantes : Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

| Fonctionnalité | Détails |
| --- | --- |
| ![Premium](/help/assets/premium.png) [!DNL Recommendations] | Les améliorations suivantes ont été apportées aux algorithmes de popularité [!DNL Recommendations] :<ul><li>Une nouvelle option &quot;Intervalle de recherche en amont&quot; (période de données) de six heures est disponible pour tous les algorithmes de popularité (Les plus consultés/Les plus vendus) lorsque [!DNL Target] est la source de données comportementales. (Cette fenêtre rétroactive n’est *pas* disponible lorsque [!DNL Adobe Analytics] est la source de données comportementales.)</li><li>Lorsqu’ils sont sélectionnés, les algorithmes suivants s’exécutent environ toutes les trois heures (au lieu de toutes les 12 heures).<ul><li>Le plus consulté</li><li>Le plus acheté</li><li>Les plus consultés par catégorie</li><li>Le plus acheté par catégorie</li><li>Les plus consultés par attribut personnalisé (à l’aide de la fonction groupBy )</li><li>La plus achetée par attribut personnalisé (à l’aide de la fonction groupBy )</li></ul></ul>(TOP-1086) |

Cette version comprend les correctifs suivants :

* Le contenu sera ajouté à l’approche de la date de publication.

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
