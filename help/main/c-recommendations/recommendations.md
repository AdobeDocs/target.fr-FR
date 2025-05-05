---
keywords: Recommendations;critères des recommandations;algorithmes de recommandations;activité Recommendations;critères;ciblage des recommandations
description: Découvrez les activités Recommendations dans Adobe  [!DNL Target] . Celles-ci affichent automatiquement le contenu susceptible d’intéresser vos clients selon l’activité précédente de l’utilisateur ou d’autres algorithmes.
title: Qu’est-ce qu’ [!DNL Target]  Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Recommendations
exl-id: 0d986e17-bc99-4c08-a963-7f9a6619609a
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 97%

---

# Recommendations

Les activités de [!DNL Adobe Target Recommendations] affichent automatiquement les produits, les services ou le contenu susceptibles d’intéresser vos visiteurs selon l’activité précédente de l’utilisateur, ses préférences ou d’autres critères. [!DNL Target Recommendations] aident à diriger les visiteurs vers des éléments qu’ils ne connaîtraient pas autrement. [!DNL Recommendations] vous permet de fournir à vos visiteurs un contenu pertinent au bon moment et au bon endroit.

>[!NOTE]
>
>[!DNL Recommendations] Les activités sont disponibles dans le cadre de la [solution Target Premium](/help/main/c-intro/intro.md#premium). Elles ne sont pas disponibles dans [!DNL Target Standard] sans une licence [!DNL Target Premium].
>
>Si vous disposez actuellement de [!DNL Recommendations Classic], voir [Différences entre Recommendations Classic et les activités Recommendations de Target Premium](/help/main/c-recommendations/c-recommendations-faq/recommendations-classic-versus-recommendations-activities-target-premium.md#concept_A80223EF66634EA380580C2823A581C5) pour en savoir plus sur les deux solutions.

[!DNL Recommendations] vous aide à optimiser et à personnaliser les suggestions en temps réel sur les canaux, applications, pages, courriers électroniques et autres options de diffusion pour augmenter l’engagement et la conversion tout en réduisant l’effort de gestion.

[!DNL Recommendations] vous aide à :

* créer des critères (règles) élaboré(e)s permettant d’automatiser les recommandations ;
* afficher automatiquement les recommandations à l’aide d’extraits de code JavaScript ;
* tester et optimiser les critères et conceptions de recommandations qui affichent les recommandations ;
* créer des rapports relatifs aux résultats de votre activité Recommendations.

L’illustration suivante présente les recommandations sur une page web :

![velocity_example image](assets/velocity_example.png)

Une recommandation détermine comment un produit est proposé à un visiteur, en fonction de ses activités sur le site. Par exemple :

| Action souhaitée | Recommandation |
|--- |--- |
| Encouragez les utilisateurs qui achètent un sac à dos à envisager l’achat de chaussures ou de bâtons de randonnée. | Créez une recommandation qui affiche les éléments qui sont souvent achetés ensemble à l’aide du critère « Les personnes qui ont acheté ceci ont également acheté ». |
| Augmentez le temps que les visiteurs passent sur votre site multimédia en recommandant un contenu multimédia similaire à celui qu’ils visionnent. | Créez une recommandation qui suggère d’autres vidéos en utilisant le critère « Les personnes qui ont consulté ceci ont également consulté ». |
| Suggérez aux clients qui ont consulté des informations sur les plans d’épargne de votre banque de lire également les informations relatives aux plans d’épargne retraite personnels. | Affichez les autres produits que les utilisateurs ont achetés après avoir consulté un produit sans afficher le premier produit dans les recommandations, en utilisant le critère « Les personnes qui ont consulté ceci ont également acheté ». |

Pour plus d’informations à ce sujet et sur les autres [!DNL Recommendations] critères, voir [Critères](/help/main/c-recommendations/c-algorithms/algorithms.md).

## Termes

Avant de commencer à utiliser [!DNL Recommendations], il est utile de vous familiariser avec certains termes utilisés dans cette section. Ne vous inquiétez pas si vous ne comprenez pas encore entièrement ces termes, vous les connaîtrez davantage lors de la configuration de vos activités [!DNL Recommendations].

| Terme | Définition |
| --- | --- |
| Activité | Les activités de [!DNL Target] vous permettent de personnaliser du contenu pour des audiences spécifiques et de tester des conceptions de page. [!DNL Recommendations] n’est qu’un des nombreux types d’activités disponibles dans [!DNL Target]. Pour plus d’informations, consultez [Types d’activités Target](/help/main/c-activities/target-activities-guide.md). |
| Entités | Les entités font référence aux éléments que vous voulez recommander. Il peut s’agir de produits, de contenus (comme des articles, des diaporamas, des photos, des films et des émissions télévisées), d’offres d’emploi, de restaurants, etc. Pour plus d’informations, consultez [Entités](/help/main/c-recommendations/c-products/products.md). |
| Flux | Les flux sont utilisés pour importer des entités dans [!DNL Recommendations]. Les entités peuvent être envoyées sous forme de fichiers CSV, via le format de flux Google Shopping et avec des classifications de produits Adobe Analytics. Pour plus d’informations, consultez [Flux](/help/main/c-recommendations/c-products/feeds.md). |
| Catalogue | Les catalogues font référence à l’ensemble de vos produits (entités). Votre catalogue peut contenir de nombreuses collections, ce qui permet d’organiser vos produits en intervalles logiques. |
| Collection | Les collections se rapportent à un ensemble d’éléments similaires ou connexes, tels qu’une catégorie de produits unique. Néanmoins, vous pouvez regrouper n’importe quels éléments dans une catégorie qui est logique pour votre entreprise, par exemple des produits appartenant à une certaine plage de prix ou d’une certaine couleur, ou encore des éléments qui sont susceptibles d’intéresser une zone géographique spécifique. Pour plus d’informations, consultez [Collections](/help/main/c-recommendations/c-products/collections.md). |
| Critères | Les critères sont des règles qui déterminent quels produits recommander selon un jeu prédéterminé de comportements de visiteurs.<br>Voici quelques exemples de critères : <ul><li>Les personnes ayant acheté ceci ont acheté cela</li><li>Les personnes ayant consulté ceci ont consulté cela</li><li>Articles avec des attributs similaires</li><li>Dernier article acheté</li><li>Catégorie préférée</li></ul>  Pour plus d’informations, consultez [Critères](/help/main/c-recommendations/c-algorithms/algorithms.md). |
| Conceptions | Les conceptions définissent l’aspect des recommandations dans une activité [!DNL Recommendations], telles qu’une ligne, une colonne, un tableau ou une grille. L’illustration en haut de cet article représente une conception 4 x 1. Pour plus d’informations, consultez [Création d’une conception](/help/main/c-recommendations/c-design-overview/create-design.md). |
| Emplacements | Les emplacements font référence à une zone de contenu spécifique sur une page web, une application mobile ou un e-mail où vous exécutez une activité à des fins de personnalisation et d’optimisation. |
| Audiences | Les audiences sont des groupes de participants à une activité similaire qui verront une activité ciblée. Une audience est un groupe de personnes ayant les mêmes caractéristiques, telles qu’un nouveau visiteur, un visiteur récurrent ou des visiteurs récurrents du Midwest. Pour optimiser votre marketing web, la fonctionnalité Audience vous permet de cibler différents contenus et expériences selon les audiences, afin de présenter les messages adéquats aux personnes appropriées au moment opportun. Pour plus d’informations, consultez [Audiences](/help/main/c-target/target.md). |
| Recommendations en tant qu’offre | Une fonctionnalité qui vous permet d’inclure des recommandations dans les tests A/B (y compris les activités d’affectation automatique et de ciblage automatique) et les activités de ciblage d’expérience (XT). Pour plus d’informations, consultez [Recommendations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md). |

## Vidéo de formation : Types d’activités ![Badge d’aperçu](/help/main/assets/overview.png)

Cette vidéo explique les types d’activités disponibles dans [!DNL Target Standard/Premium]. [!DNL Recommendations] est abordé à partir de 7:20.

* Décrire les types d’activités inclus dans [!DNL Adobe Target]
* Sélectionner le type d’activité approprié pour atteindre vos objectifs
* Décrire le processus assisté en trois étapes qui s’applique à tous les types d’activités

>[!VIDEO](https://video.tv.adobe.com/v/29340?captions=fre_fr)

## Webinaire sur les bases d’Adobe Target : présentation de Recommendations ![Badge de tutoriel](/help/main/assets/tutorial.png) {#intro-to-recs}

Le webinaire *Présentation de Recommendations* comprend une exploration en profondeur de la manière de tirer parti de la valeur de [!DNL Adobe Target Recommendations]. Découvrez comment cette activité [!DNL Target] affiche automatiquement les produits ou le contenu susceptibles d’intéresser vos clients en optimisant les suggestions en temps réel basées sur les visites précédentes. Vous pouvez ensuite approfondir l’analyse de l’interface utilisateur de [!DNL Target] pour une présentation détaillée de la création d’une activité [!DNL Recommendations].

[Présentation de Recommendations](https://adobecustomersuccess.adobeconnect.com/p8gt31drhs3e/?OWASP_CSRFTOKEN=4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)
