---
keywords: Recommendations;Recommendations criteria;recommendations algorithms;recommendations activity;criteria;recommendations targeting;recs
description: Les activités Recommendations de Adobe Target affichent automatiquement les produits ou le contenu susceptibles d’intéresser vos clients, en fonction de l’activité d’utilisateurs précédents ou d’autres algorithmes. Les recommandations aident à diriger les clients vers des éléments qu’ils ne connaîtraient pas autrement.
title: Adobe Target
feature: recommendations general
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 59%

---


# ![PREMIUM](/help/assets/premium.png) Recommandations{#recommendations}

[!DNL Adobe Target Recommendations] Les activités affichent automatiquement les produits, les services ou le contenu susceptibles d’intéresser vos visiteurs en fonction de l’activité, des préférences ou d’autres critères d’utilisateur précédents. [!DNL Target Recommendations] aide à diriger le visiteur vers les éléments pertinents qu’il ne connaîtrait pas autrement. [!DNL Recommendations] vous permet de fournir à vos visiteurs un contenu pertinent au bon moment et au bon endroit.

>[!NOTE]
>
>[!DNL Recommendations] Les activités sont disponibles dans le cadre de la [solution Target Premium](/help/c-intro/intro.md#premium). Elle n’est pas disponible dans [!DNL Target Standard] sans une licence [!DNL Target Premium].
>
>Si vous disposez actuellement de [!DNL Recommendations Classic], voir [Différences entre Recommendations Classic et les activités de recommandations de Target Premium](/help/c-recommendations/c-recommendations-faq/recommendations-classic-versus-recommendations-activities-target-premium.md#concept_A80223EF66634EA380580C2823A581C5) pour en savoir plus sur les deux solutions.

[!DNL Recommendations] vous aide à optimiser et à personnaliser les suggestions en temps réel sur les canaux, applications, pages, courriers électroniques et autres options de diffusion pour augmenter l’engagement et la conversion tout en réduisant l’effort de gestion.

[!DNL Recommendations] vous aide à :

* créer des critères (règles) élaboré(e)s permettant d’automatiser les recommandations ;
* afficher automatiquement les recommandations à l’aide d’extraits de code JavaScript ;
* tester et optimiser les critères et conceptions de recommandations qui affichent les recommandations ;
* créer des rapports relatifs aux résultats de votre activité de recommandations.

L’illustration suivante présente les recommandations sur une page web :

![](assets/velocity_example.png)

Une recommandation détermine comment un produit est proposé à un visiteur, en fonction des activités de ce visiteur sur le site. Par exemple :

| Action souhaitée | Recommandation |
|--- |--- |
| Encouragez les utilisateurs qui achètent un sac à dos à envisager l’achat de chaussures ou de bâtons de randonnée. | Créez une recommandation qui affiche les éléments qui sont souvent achetés ensemble à l’aide du critère « Les personnes qui ont acheté ceci ont également acheté ». |
| Augmentez le temps que les visiteurs passent sur votre site multimédia en recommandant un contenu multimédia similaire à celui qu’ils visionnent. | Créez une recommandation qui suggère d’autres vidéos en utilisant le critère « Les personnes qui ont consulté ceci ont également consulté ». |
| Suggérez aux clients qui ont consulté des informations sur les plans d’épargne de votre banque de lire également les informations relatives aux plans d’épargne retraite personnels. | Affichez les autres produits que les utilisateurs ont achetés après avoir consulté un produit sans afficher le premier produit dans les recommandations, en utilisant le critère « Les personnes qui ont consulté ceci ont également acheté ». |

Pour plus d’informations à ce sujet et sur les autres [!DNL Recommendations]critères, voir [Critères](/help/c-recommendations/c-algorithms/algorithms.md).

## Termes

Avant de commencer à utiliser [!DNL Recommendations], il est utile de vous familiariser avec certains termes utilisés dans cette section. Ne vous inquiétez pas si vous ne comprenez pas encore entièrement ces termes, vous les connaîtrez davantage lors de la configuration de vos activités [!DNL Recommendations].

| Terme | Définition |
| --- | --- |
| Activité | Les Activités de [!DNL Target] vous permettent de personnaliser le contenu en fonction d’audiences spécifiques et de tester les conceptions de page. [!DNL Recommendations] n&#39;est qu&#39;un des nombreux types d&#39;activités disponibles dans  [!DNL Target]. Pour plus d’informations, voir [Cible activités types](/help/c-activities/target-activities-guide.md). |
| Entités | Les entités font référence aux éléments que vous voulez recommander. Les entités peuvent être tout ce qui concerne les produits, le contenu (articles, diaporamas, images, films et émissions de télévision), les listes de tâches, les restaurants, etc. Pour plus d&#39;informations, voir [Entités](/help/c-recommendations/c-products/products.md). |
| Flux | Les flux sont utilisés pour obtenir des entités importées dans [!DNL Recommendations]. Les entités peuvent être envoyées sous forme de fichiers CSV, via le format de flux Google Shopping et avec des classifications de produits Adobe Analytics. Pour plus d’informations, voir [Flux](/help/c-recommendations/c-products/feeds.md). |
| Catalogue | Les catalogues font référence à l’ensemble de votre ensemble de produits (entités). Votre catalogue peut contenir de nombreuses collections, ce qui permet d’organiser vos produits dans des intervalles logiques. |
| Collecte | Les collections se rapportent à un ensemble d’éléments similaires ou connexes, tels qu’une catégorie de produits unique. Néanmoins, vous pouvez regrouper n’importe quels éléments dans une catégorie qui est logique pour votre entreprise, par exemple des produits appartenant à une certaine plage de prix ou d’une certaine couleur, ou encore des éléments qui sont susceptibles d’intéresser une zone géographique spécifique. Pour plus d&#39;informations, voir [Collections](/help/c-recommendations/c-products/collections.md). |
| Critères | Les critères sont des règles qui déterminent quels produits recommander selon un jeu prédéterminé de comportements de visiteurs.<br>Voici quelques exemples de critères : <ul><li>Les personnes ayant acheté ceci ont acheté cela</li><li>Les personnes ayant consulté ceci ont consulté cela</li><li>Articles avec des attributs similaires</li><li>Dernier article acheté</li><li>Catégorie préférée</li></ul>  Pour plus d’informations, voir [Critères](/help/c-recommendations/c-algorithms/algorithms.md). |
| Conceptions | Les conceptions définissent l’aspect des recommandations dans une activité [!DNL Recommendations], telle qu’une ligne, une colonne, un tableau ou une grille. L’illustration au haut de cet article présente une conception 4 x 1. Pour plus d’informations, voir [Création d’une conception](/help/c-recommendations/c-design-overview/create-design.md). |
| Emplacements | Les emplacements font référence à une zone de contenu spécifique sur une page Web, une application mobile ou un courrier électronique où vous exécutez une activité à des fins de personnalisation et d’optimisation. |
| Audiences | Les Audiences sont des groupes de participants à des activités similaires qui verront une activité ciblée. Une audience est un groupe de personnes ayant les mêmes caractéristiques, telles qu’un nouveau visiteur, un visiteur récurrent ou des visiteurs récurrents du Midwest. Pour optimiser votre marketing web, la fonctionnalité Audience vous permet de cibler différents contenus et expériences selon les audiences, afin de présenter les messages adéquats aux personnes appropriées au moment opportun. Pour plus d’informations, voir [Audiences](/help/c-target/target.md). |
| Recommendations en tant qu’offre | Cette fonctionnalité vous permet d’inclure des recommandations dans les activités Test A/B (y compris l’affectation automatique et la Cible automatique) et Ciblage d’expérience (XT). Pour plus d’informations, voir [Recommendations en tant qu’offre](/help/c-recommendations/recommendations-as-an-offer.md). |

## Vidéo de formation : Types d&#39;Activité ![badge Aperçu](/help/assets/overview.png)

Cette vidéo explique les types d’activités disponibles dans [!DNL Target Standard/Premium]. [!DNL Recommendations] est abordé à partir de 7:20.

* Décrire les types d’activités inclus dans [!DNL Adobe Target]
* Sélectionner le type d’activité approprié pour atteindre vos objectifs
* Décrire le processus assisté en trois étapes qui s’applique à tous les types d’activités

>[!VIDEO](https://video.tv.adobe.com/v/17386)

## Webinaire sur les bases d’Adobe Target : Introduction à Recommendations ![Badge didactique ](/help/assets/tutorial.png) {#intro-to-recs}

Le webinaire *Introduction à Recommendations* comprend une exploration en profondeur de la manière de tirer parti de la valeur de [!DNL Adobe Target Recommendations]. Découvrez comment cette activité [!DNL Target] affiche automatiquement les produits ou le contenu susceptibles d’intéresser vos clients en optimisant les suggestions en temps réel basées sur les visites précédentes. Vous pouvez ensuite approfondir l’analyse de l’interface utilisateur de [!DNL Target] pour une présentation détaillée de la création d’une activité [!DNL Recommendations].

[Présentation de Recommendations](https://adobecustomersuccess.adobeconnect.com/p8gt31drhs3e/?OWASP_CSRFTOKEN=4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)