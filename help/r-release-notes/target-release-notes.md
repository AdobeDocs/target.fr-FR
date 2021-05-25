---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités sont incluses dans la prochaine version ?
feature: Notes de mise à jour
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 14e1a71bbebbf8baec09df41e3e08f89bb64a4e0
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 28%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations préliminaires. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 25er mai 2021**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations contenues dans ces pages peuvent être identiques, selon le calendrier des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vie** de mbox.js : À compter du 31 mars 2021,  [!DNL Adobe Target] ne prendra plus en charge la bibliothèque mbox.js. Depuis le 31 mars 2021, tous les appels effectués à partir de mbox.js échouent et impactent de manière élégante vos pages comportant des activités [!DNL Target] exécutées en diffusant du contenu par défaut.
>
>Pour éviter tout problème potentiel sur vos sites, migrez vers la version la plus récente de la nouvelle [!DNL Adobe Experience Platform Web SDK] ou de la bibliothèque JavaScript at.js. Pour plus d’informations, consultez [Aperçu : implémentation de Target pour le Web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## ![Badgegeversion 2.5.0 ](/help/assets/platform.png) [!DNL Adobe Experience Platform Web SDK] du SDK Web Adobe Experience Platform (1er juin 2021)

Cette version de [!DNL Platform Web SDK] prend en charge les éléments suivants :

| Fonctionnalité | Détails |
| --- | --- |
| Prise en charge des redirections avec [!UICONTROL Analytics pour Target] (A4T) | Le SDK Web Platform prend désormais en charge les redirections [!DNL Target] lors de l’utilisation d’A4T. Les offres de redirection dans [!DNL Adobe Target] entraînent la redirection d’un navigateur vers une nouvelle page. |
| Jetons de réponse | Le SDK Web Platform prend désormais en charge les jetons de réponse [!DNL Target]. Les jetons de réponse permettent de générer automatiquement des informations spécifiques à [!DNL Adobe Target] sur la page web de votre marque. Ces informations peuvent inclure des détails sur l’activité, l’offre, l’expérience, le profil utilisateur, des informations géographiques, etc. Ces détails fournissent des données de réponse supplémentaires à partager avec des systèmes internes ou tiers ou à utiliser pour le débogage. |

## [!DNL Target Standard/Premium] 21.5.1 (8 juin 2021)

| Fonctionnalité | Détails |
| --- | --- |
| ![Badge Premium ](/help/assets/premium.png) [!DNL Recommendations] [!UICONTROL Catalog ] SearchAPI | Recherchez votre [!DNL Recommendations] catalogue de contenu et de produit par programmation via l’API pour identifier les éléments qui correspondent à des critères de recherche et simplifier l’administration de votre catalogue.<br>**Limites et remarques** :<ul><li>La recherche catalogue via l’API n’est pas prise en charge pour les environnements comportant plus de 2 000 000 éléments.</li><li>Les résultats de la recherche catalogue via l’API sont mis à jour plus rapidement que les résultats de la recherche catalogue via l’interface utilisateur [!DNL Target]. La recherche catalogue dans l’interface utilisateur [!DNL Target] peut prendre plus de temps pour refléter les derniers résultats.</li></ul>Pour plus d’informations, voir [Recherche d’entités](http://developers.adobetarget.com/api/recommendations/#tag/Searching-Entities) dans le guide *[!DNL Adobe Target][!DNL Recommendations] API*. |

## [!DNL Target Standard/Premium] 21.5.2 (Date à déterminer)

Cette version contient les nouvelles fonctionnalités et améliorations suivantes. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

| Fonctionnalité | Détails |
| --- | --- |
| ![Premium](/help/assets/premium.png) [!DNL Recommendations] | Les améliorations suivantes ont été apportées aux algorithmes de popularité [!DNL Recommendations] :<ul><li>Une nouvelle option &quot;Intervalle de recherche en amont&quot; (période de données) de six heures est disponible pour tous les algorithmes de popularité (Les plus consultés/Les plus vendus) lorsque [!DNL Target] est la source de données comportementales. (Cette fenêtre rétroactive n’est *pas* disponible lorsque [!DNL Adobe Analytics] est la source de données comportementales.)</li><li>Lorsqu’ils sont sélectionnés, les algorithmes suivants s’exécutent environ toutes les trois heures (au lieu de toutes les 12 heures).<ul><li>Le plus consulté</li><li>Le plus acheté</li><li>Les plus consultés par catégorie</li><li>Le plus acheté par catégorie</li><li>Les plus consultés par attribut personnalisé (à l’aide de la fonction groupBy )</li><li>La plus achetée par attribut personnalisé (à l’aide de la fonction groupBy )</li></ul></ul>(TOP-1086) |

Cette version contient les correctifs suivants.

* Le contenu sera ajouté à l’approche de la date de publication.

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
