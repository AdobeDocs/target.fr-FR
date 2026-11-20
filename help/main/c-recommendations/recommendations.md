---
keywords: Recommendations;critères des recommandations;algorithmes de recommandations;activité Recommendations;critères;ciblage des recommandations
description: Découvrez les activités Recommendations dans Adobe [!DNL Target], qui affichent automatiquement le contenu susceptible d’intéresser vos clients selon l’activité précédente de l’utilisateur ou d’autres algorithmes.
title: Qu’est-ce que les recommandations [!DNL Target] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: 0d986e17-bc99-4c08-a963-7f9a6619609a
TQID: 'https://experienceleague.adobe.com/gR3x6ABhdZNZ4lKvBHpJ-edRj7ZdCKBklMITXaLUhTA'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: b31c0a47b82e0b96fa061075f1b8d388b6c0b567
workflow-type: tm+mt
source-wordcount: '861'
ht-degree: 66%
---
# Prise en main de Recommendations {#recommendations}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez la fonction de [!DNL Adobe Target Recommendations], le fonctionnement d’une recommandation et les termes utilisés dans cette section.

>[!ENDSHADEBOX]

Les activités de [!DNL Adobe Target Recommendations] affichent automatiquement les produits, les services ou le contenu susceptibles d’intéresser vos visiteurs selon l’activité précédente de l’utilisateur, ses préférences ou d’autres critères. [!DNL Recommendations] dirige les visiteurs vers des éléments pertinents qu&#39;ils ne connaîtraient pas autrement et fournit du contenu pertinent au bon moment et au bon endroit.

>[!NOTE]
>
>[!DNL Recommendations] Les activités sont disponibles dans le cadre de la [solution Target Premium](/help/main/c-intro/intro.md#premium). Elles ne sont pas disponibles dans [!DNL Target Standard] sans une licence [!DNL Target Premium].
>
>Si vous disposez actuellement de [!DNL Recommendations Classic], voir [Différences entre Recommandations Classic et les activités Recommandations de Target Premium](/help/main/c-recommendations/c-recommendations-faq/recommendations-classic-versus-recommendations-activities-target-premium.md) pour en savoir plus sur les deux solutions.

[!DNL Recommendations] optimise et personnalise les suggestions en temps réel sur les canaux, les applications, les pages, les e-mails et d’autres options de diffusion afin d’augmenter l’engagement et la conversion tout en réduisant les efforts de gestion. Avec [!DNL Recommendations], vous pouvez :

* Créez des critères sophistiqués (règles) pour automatiser les recommandations.
* Affichez automatiquement les recommandations à l’aide de quelques fragments de code JavaScript.
* Testez et optimisez les critères et les conceptions qui affichent les recommandations.
* Générez des rapports sur les résultats de vos activités Recommendations.

L’illustration suivante présente les recommandations sur une page web :

![image velocity_example](assets/velocity_example.png)

Une recommandation détermine comment un produit est proposé à un visiteur, en fonction de ses activités sur le site. Par exemple :

| Action souhaitée | Recommandation |
|--- |--- |
| Encouragez les utilisateurs qui achètent un sac à dos à envisager l’achat de chaussures ou de bâtons de randonnée. | Créez une recommandation qui affiche les éléments qui sont souvent achetés ensemble à l’aide du critère « Les personnes qui ont acheté ceci ont également acheté ». |
| Augmentez le temps que les visiteurs passent sur votre site multimédia en recommandant un contenu multimédia similaire à celui qu’ils visionnent. | Créez une recommandation qui suggère d’autres vidéos en utilisant le critère « Les personnes qui ont consulté ceci ont également consulté ». |
| Suggérez aux clients qui ont consulté des informations sur les plans d’épargne de votre banque de lire également les informations relatives aux plans d’épargne retraite personnels. | Affichez les autres produits que les utilisateurs ont achetés après avoir consulté un produit sans afficher le premier produit dans les recommandations, en utilisant le critère « Les personnes qui ont consulté ceci ont également acheté ». |

Pour plus d’informations à ce sujet et sur les autres [!DNL Recommendations] critères, voir [Critères](/help/main/c-recommendations/c-algorithms/algorithms.md).

## Termes

Avant d&#39;utiliser [!DNL Recommendations], familiarisez-vous avec les termes utilisés dans cette section. Ces termes deviennent plus clairs lorsque vous configurez vos activités [!DNL Recommendations].

| Terme | Définition |
| --- | --- |
| Activité | Les activités de [!DNL Target] vous permettent de personnaliser du contenu pour des audiences spécifiques et de tester des conceptions de page. [!DNL Recommendations] est l&#39;un des types d&#39;activités disponibles dans [!DNL Target]. Pour plus d’informations, consultez [Types d’activités Target](/help/main/c-activities/target-activities-guide.md). |
| Entités | Les entités font référence aux éléments que vous voulez recommander. Il peut s’agir de produits, de contenus (comme des articles, des diaporamas, des photos, des films et des émissions télévisées), d’offres d’emploi, de restaurants, etc. Pour plus d’informations, consultez [Entités](/help/main/c-recommendations/c-products/products.md). |
| Flux | Les flux sont utilisés pour importer des entités dans [!DNL Recommendations]. Les entités peuvent être envoyées sous forme de fichiers CSV, via le format de flux Google Shopping et avec des classifications de produits Adobe Analytics. Pour plus d’informations, consultez [Flux](/help/main/c-recommendations/c-products/feeds.md). |
| Catalogue | Les catalogues font référence à l’ensemble de vos produits (entités). Votre catalogue peut contenir de nombreuses collections, ce qui permet d’organiser vos produits en compartiments logiques. |
| Collection | Les collections se rapportent à un ensemble d’éléments similaires ou connexes, tels qu’une catégorie de produits unique. Néanmoins, vous pouvez regrouper n’importe quels éléments dans une catégorie qui est logique pour votre entreprise, par exemple des produits appartenant à une certaine plage de prix ou d’une certaine couleur, ou encore des éléments qui sont susceptibles d’intéresser une zone géographique spécifique. Pour plus d’informations, consultez [Collections](/help/main/c-recommendations/c-products/collections.md). |
| Critères | Les critères sont des règles qui déterminent quels produits recommander selon un ensemble prédéterminé de comportements de visiteurs.<br>Voici quelques exemples de critères : <ul><li>Les personnes ayant acheté ceci ont acheté cela</li><li>Les personnes ayant consulté ceci ont consulté cela</li><li>Articles avec des attributs similaires</li><li>Dernier article acheté</li><li>Catégorie favorite</li></ul>  Pour plus d’informations, consultez [Critères](/help/main/c-recommendations/c-algorithms/algorithms.md). |
| Conceptions | Les conceptions définissent l’aspect des recommandations dans une activité [!DNL Recommendations], telles qu’une ligne, une colonne, un tableau ou une grille. L’illustration en haut de cet article représente une conception 4 x 1. Pour plus d’informations, consultez [Création d’une conception](/help/main/c-recommendations/c-design-overview/create-design.md). |
| Emplacements | Les emplacements font référence à une zone de contenu spécifique sur une page web, une application mobile ou un e-mail où vous exécutez une activité à des fins de personnalisation et d’optimisation. |
| Audiences | Les audiences sont des groupes de participants à une activité similaire qui voient une activité ciblée. Une audience est un groupe de personnes ayant les mêmes caractéristiques, telles qu’un nouveau visiteur, un visiteur récurrent ou des visiteurs récurrents du Midwest. La fonction Audience vous permet de cibler différents contenus et expériences selon les audiences, afin d’optimiser votre marketing numérique en présentant les messages adéquats aux personnes appropriées et au moment opportun. Pour plus d’informations, consultez [Audiences](/help/main/c-target/target.md). |
| Recommandations en tant qu’offre | Une fonctionnalité qui vous permet d’inclure des recommandations dans les tests A/B (y compris les activités d’affectation automatique et de ciblage automatique) et les activités de ciblage d’expérience (XT). Pour plus d’informations, voir [Recommandations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md). |

## Vidéo de formation : Types d’activités ![Badge d’aperçu](/help/main/assets/overview.png)

Cette vidéo explique les types d’activités disponibles dans [!DNL Target Standard/Premium]. [!DNL Recommendations] est discuté à partir de 7:20.

* Décrire les types d’activités inclus dans [!DNL Adobe Target]
* Sélectionner le type d’activité approprié pour atteindre vos objectifs
* Décrire le processus assisté en trois étapes qui s’applique à tous les types d’activités

>[!VIDEO](https://video.tv.adobe.com/v/17386)

<!--
## Adobe Target Basics Webinar: Introduction to Recommendations ![Tutorial badge](/help/main/assets/tutorial.png) {#intro-to-recs}

The *Introduction to Recommendations* webinar includes an in-depth exploration of how to leverage the value of [!DNL Adobe Target Recommendations]. Find out how this [!DNL Target] activity automatically displays products or content that might interest your customers by optimizing real-time suggestions based on previous visits. Further, dive into the [!DNL Target] UI for a step-by-step overview of how to build a [!DNL Recommendations] activity.

[Introduction to Recommendations](https://adobecustomersuccess.adobeconnect.com/p8gt31drhs3e/?OWASP_CSRFTOKEN=4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)
-->
