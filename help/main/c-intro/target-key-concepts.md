---
keywords: Présentation et référence;types d’activité;introduction
description: Apprenez les bases d’Adobe Target. Cet article vous présente Target, ses types d’activité, ainsi que d’autres fonctionnalités.
title: Comment utiliser Target ?
feature: Overview
exl-id: c9555d79-d505-41ff-ba4b-ab94793f9efa
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1523'
ht-degree: 99%

---

# Concepts clés de Target

Informations sur les concepts clés qui vous aideront à mieux comprendre les fonctionnalités d’[!DNL Adobe Target].

## Activités et tests {#section_BEA0A0C51A8847579B566060206DE7E8}

Une activité détermine les expériences qu’un visiteur de site peut rencontrer.

Vous pouvez par exemple concevoir une activité qui teste deux pages d’entrée distinctes : l’une qui met en évidence les informations sur les chaussures d’été pour femmes, l’autre qui met en évidence des éléments d’été plus généraux. L’activité détermine les conditions qui contrôlent quand s’affiche chacune de ces pages d’entrée, ainsi que les mesures qui déterminent la page qui réussit le mieux. L’activité est configurée pour démarrer et se terminer lorsque des conditions spécifiques sont remplies : par exemple, démarrer et terminer une activité entre des dates spécifiques ou démarrer l’activité lorsqu’elle est approuvée et y mettre fin lorsqu’elle est désactivée.

La planification est une étape importante du processus de conception d’une activité. Déterminez le moment auquel l’activité doit débuter, ainsi que sa durée. Répertoriez ensuite vos offres et attribuez une audience cible à chacune d’elles.

Target comprend plusieurs types d’activité. Le tableau suivant présente un aperçu de chaque type d’activité avec des liens pour vous aider à en savoir plus. Pour vous aider à choisir le type d’activité le mieux adapté à vos besoins, l’équipe Target a également créé le [Guide des activités Adobe Target](/help/main/c-activities/target-activities-guide.md).

| Type d’activité | Description |
|--- |--- |
| [Test A/B](/help/main/c-activities/t-test-ab/test-ab.md) | Le test A/B compare plusieurs versions du contenu de votre site web afin de déterminer la version qui améliore le mieux vos conversions au cours d’une période de test prédéfinie.<br>**Remarque :** vous pouvez désormais inclure des [recommandations dans les activités de test A/B](/help/main/c-recommendations/recommendations-as-an-offer.md). Cette fonctionnalité requiert une licence [Target Premium](/help/main/c-intro/intro.md#premium). |
| [Affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | L’affectation automatique identifie un gagnant parmi plusieurs expériences et réaffecte automatiquement du trafic supplémentaire vers le gagnant afin d’augmenter les conversions pendant que le test se poursuit et apprend.<br>**Remarque :** vous pouvez désormais inclure des [recommandations dans les activités d’affectation automatique](/help/main/c-recommendations/recommendations-as-an-offer.md). Cette fonctionnalité requiert une licence [Target Premium](/help/main/c-intro/intro.md#premium). |
| [Ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md)<br>![Target Premium](/help/main/assets/premium.png) | Le ciblage automatique utilise l’apprentissage automatique (machine learning) avancé pour identifier plusieurs expériences à hautes performances définies par les marketeurs. Les activités de ciblage automatique proposent à chaque visiteur l’expérience la plus adaptée en fonction de son profil client individuel et du comportement des visiteurs précédents présentant des profils similaires, et ce, afin de personnaliser le contenu et de générer des conversions.<br>**Remarque** : vous pouvez désormais inclure des [recommandations dans les activités de ciblage automatique](/help/main/c-recommendations/recommendations-as-an-offer.md). Cette fonctionnalité requiert une licence [Target Premium](/help/main/c-intro/intro.md#premium). |
| [Utilisation des données Analytics](/help/main/c-activities/t-test-ab/t-test-create-ab/create-a4t.md) (A4T) | Vous pouvez configurer une activité pour utiliser [!DNL Adobe Analytics] en tant que source de création de rapports. Ce type d’activité requiert que vous liiez votre compte [!DNL Adobe Experience Cloud] avec [!DNL Analytics] et [!DNL Target]. |
| [Test multivarié](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | Multivariate Testing (MVT) compare des combinaisons d’offres d’éléments sur une page afin de déterminer la combinaison offrant les meilleures performances pour une audience spécifique. Il identifie l’élément qui impacte le plus le succès de l’activité. |
| [Ciblage d’expérience](/help/main/c-activities/t-experience-target/experience-target.md) | Le ciblage d’expérience (XT) diffuse le contenu à une audience spécifique selon un ensemble de règles et de critères définis par les responsables du marketing.<br>**Remarque :** vous pouvez désormais inclure des [recommandations dans les activités de ciblage d’expérience](/help/main/c-recommendations/recommendations-as-an-offer.md). Cette fonctionnalité requiert une licence [Target Premium](/help/main/c-intro/intro.md#premium). |
| [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<br>![Target Premium](/help/main/assets/premium.png) | Automated Personalization (AP) associe des offres ou des messages et utilise le machine learning avancé pour mettre en correspondance différentes variations avec chaque visiteur selon son profil client afin de personnaliser le contenu et de générer des conversions. |
| [Recommendations](/help/main/c-recommendations/recommendations.md)<br>![Target Premium](/help/main/assets/premium.png) | Une recommandation détermine comment un produit est proposé à l’utilisateur d’un site web, en fonction de ses activités sur le site.<br>Par exemple, vous pouvez encourager les personnes qui achètent un sac à dos à envisager l’achat de chaussures et de bâtons de randonnée. Vous pouvez créer une recommandation qui affiche les éléments qui sont souvent achetés ensemble à l’aide de l’algorithme « Les personnes qui ont acheté ceci ont également acheté ». Ou, vous souhaitez peut-être encourager les visiteurs à passer plus de temps sur votre site multimédia en recommandant une vidéo similaire à celle qu’ils regardent, à l’aide de l’algorithme « Les personnes qui ont regardé cette vidéo ont également regardé ».<br>**Remarque :** vous pouvez désormais inclure des recommandations dans les activités de test A/B (dont l’affectation automatique et le ciblage automatique) et de ciblage d’expérience.  [Recommandations en tant qu’offre](/help/main/c-recommendations/recommendations-as-an-offer.md). |

## Emplacements {#section_F18FBF1ED23340ED9F39C51971A4E874}

Essentiellement, un emplacement est une page de votre site web. Ce terme peut également faire référence à un emplacement dans une application mobile, dans une adresse e-mail ou tout autre emplacement où vous exécutez une optimisation.

Les emplacements sont essentiels aux activités et expériences. Vous décidez s’ils ont l’une des fonctions suivantes, les deux ou aucune :

* Afficher et permuter le contenu pour les visiteurs.
* Consigner le comportement des visiteurs.

Dans [!DNL Target Standard], un emplacement peut être n’importe quel élément d’une page tant que celle-ci contient une seule ligne de code qui active [!DNL Target] dans la section `<head>` de chaque page dont vous souhaitez effectuer le suivi. Cette ligne de code appelle les bibliothèques JavaScript requises pour collecter des informations et diffuser des expériences ciblées aux visiteurs.

Les emplacements sont combinés aux audiences afin de fournir un nombre d’options presque infini pour le ciblage des informations sur vos clients. Par exemple, si un visiteur n’a jamais été sur le site auparavant, vous pouvez afficher un coupon de remise pour les nouveaux clients. De même, la page peut être modifiée afin d’afficher des offres qui sont plus optimisées pour les clients qui reviennent.

Vous pouvez également utiliser des emplacements pour suivre le cheminement d’un visiteur sur votre site web. Vous pouvez également utiliser des emplacements pour déterminer si le visiteur réalise une mesure de succès spécifique, telle que l’ajout d’un article dans son panier ou l’exécution d’un achat.

## Expériences et conception de pages {#section_B806FB752EC1470784755C1EB3D4AC70}

Une expérience, parfois appelée « recette », définit le contenu qui s’affiche sur votre page, ainsi que d’autres éléments de la page, tels que les liens.

Une expérience détermine l’offre qui s’affiche à un emplacement donné lorsque des données de ciblage spécifiques sont réunies. Par exemple, l’expérience détermine que, lorsqu’un visiteur récurrent navigue sur votre site, une offre de livraison en 48 h s’affiche en haut de la page. L’expérience détermine également que, lorsqu’un nouveau visiteur visualise la page, une remise de 10 % s’affiche au même emplacement.

Une expérience est composée d’offres, de ressources image ou d’autres éléments HTML (tels que les liens) qui s’affichent sur la page pour permettre de diriger le visiteur vers le résultat souhaité. [!DNL Target] combine des emplacements, des offres et des expériences afin de déterminer le contenu qui s’affiche sur votre site durant un test spécifique.

Une expérience peut également être une conception de page différente. Par exemple, une expérience peut comporter un jeu de liens en haut de la page alors qu’une autre expérience comporte des liens différents ou les mêmes liens organisés dans un ordre différent. Vous pouvez tester si une image crée un effet élévateur plus important qu’une autre ou s’il y a plus de chance de cliquer sur une publicité près du haut de la page ou à un autre emplacement.

[!DNL Target] optimise les expériences pour chaque visiteur sur l’ensemble de vos points de contact numériques et teste différentes expériences afin de déterminer lesquelles seront les plus réussies. En planifiant soigneusement le ciblage d’expérience, vous pouvez vous assurer que les visiteurs de votre site voient les offres les plus pertinentes aux emplacements appropriés de la page, améliorant ainsi vos chances de succès.

## Offres  {#section_973D4CC4CEB44711BBB9A21BF74B89E9}

Une offre est le contenu affiché sur vos pages web lors des campagnes ou activités.

Lorsque vous testez vos pages web, vous mesurez le succès de chaque expérience selon les différentes offres dans les emplacements.

Une offre peut contenir différents types de contenu, notamment :

* Image
* Texte
* HTML
* Lien
* Bouton

Par exemple, une page web peut afficher l’une des deux offres, selon si le visiteur a déjà été sur votre site auparavant.

Une *expérience* détermine le contenu qui s’affiche lorsque des conditions spécifiques sont réunies.

## Audiences {#section_3F32DA46BDF947878DD79DBB97040D01}

Optimisez votre contenu ciblé pour les participants à l’activité qui respectent des critères spécifiques.

Les audiences définissent la cible de votre activité ; elles sont utilisées partout où le ciblage est disponible.

[!DNL Target] Les audiences cibles sont un jeu défini de critères de visiteurs. Les offres peuvent être ciblées sur des audiences (ou des segments) spécifiques. Seuls les visiteurs qui appartiennent à cette audience visualisent l’expérience qui est ciblée sur eux.

Par exemple, vous pouvez cibler une activité sur une audience constituée de visiteurs qui utilisent un navigateur ou un système d’exploitation spécifique.

Ou, votre activité peut être ciblée sur des visiteurs d’une région géographique ou sur des personnes qui accèdent à votre page à partir d’un certain moteur de recherche.

Les audiences peuvent être enregistrées pour réutilisation dans plusieurs activités ou elles peuvent être créées pour une activité spécifique.

| Type d’audience | Description |
|--- |--- |
| Audiences réutilisables | Les audiences réutilisables peuvent être sélectionnées pour n’importe quelle activité. La modification d’une de ces audiences la modifie pour toutes les activités qui l’utilisent. |
| Segments personnalisés | Les segments personnalisés (ou segments propres à une campagne) sont spécifiques à une campagne Target Classic. Ils sont créés dans le cadre d’une campagne et ne peuvent pas être réutilisés dans d’autres campagnes. |
| Audiences partagées | Les audiences peuvent être partagées dans l’ensemble des solutions [!DNL Adobe Experience Cloud]. Consultez [Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=fr) pour voir des exemples. |

Pour plus d’informations sur la manière dont le profil du visiteur effectue le suivi des informations relatives aux visiteurs sur votre site, voir [Profils de visiteurs](/help/main/c-target/c-visitor-profile/visitor-profile.md#concept_5E53D1A6DF224D7BAE76F4AE390B9DA1).

## Vidéos de formation :

Les vidéos suivantes contiennent davantage d’informations sur les concepts abordés dans cet article.

### Types d’activités (9:03) ![Badge d’aperçu](/help/main/assets/overview.png)

Cette vidéo explique les types d’activités disponibles dans [!DNL Target Standard/Premium].

* Décrire les types d’activités inclus dans [!DNL Adobe Target]
* Sélectionner le type d’activité approprié pour atteindre vos objectifs
* Décrire le processus assisté en trois étapes qui s’applique à tous les types d’activités

>[!VIDEO](https://video.tv.adobe.com/v/29340?captions=fre_fr)

### Utilisation des audiences dans Adobe Target (6:21) ![Badge d’aperçu](/help/main/assets/overview.png)

Cette vidéo explique de quelle façon utiliser les audiences dans [!DNL Target Standard/Premium].

* Explication du terme « audience »
* Explication des deux façons d’utiliser les audiences pour l’optimisation
* Recherche d’audiences dans la liste des audiences
* Ciblage d’une activité sur une audience
* Utilisation d’audiences à des fins de création passive de rapports dans une activité

>[!VIDEO](https://video.tv.adobe.com/v/30143?captions=fre_fr)
