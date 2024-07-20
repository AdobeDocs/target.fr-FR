---
keywords: critères;algorithme;secteur industriel vertical;type de page;clé de recommandation;logique de recommandation;logique;plage de données;intervalle de recherche en amont;source de données de comportement;conception partielle;recommandations de sauvegarde;règles d’inclusion;pondération d’attribut;catégorie actuelle;attribut personnalisé;dernier article acheté;dernier article consulté;article le plus consulté;élément le plus consulté;catégorie préférée;popularité;article récemment consulté;dernier article le plus consulté;favori
description: Découvrez comment créer des critères qui contrôlent le contenu de vos activités Adobe Recommendations pour afficher les recommandations les plus appropriées à votre activité.
title: Comment créer des critères dans Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Recommendations
exl-id: 3f4f59b2-6637-4c33-bf17-bff11bef7173
source-git-commit: b5fbf23e9c2dfd76565fd6287ae07df2b7df2e21
workflow-type: tm+mt
source-wordcount: '2694'
ht-degree: 49%

---

# Création de critères

Les critères dans [!UICONTROL Adobe Target] [!UICONTROL Recommendations] contrôlent le contenu de vos activités [!UICONTROL Recommendations]. Créez des critères pour afficher les recommandations les plus appropriées à votre activité. Ces critères utilisent les actions du visiteur pour déterminer le contenu ou les produits à afficher.

Les sections suivantes expliquent comment créer un nouveau critère.

## Accès à l’écran Créer des critères

Il existe plusieurs façons d’accéder à l’écran [!UICONTROL Create New Criteria]. Certaines options de l’écran varient en fonction de l’accès à ce dernier.

* Sur l’écran de la bibliothèque **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**, cliquez sur **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**. Les critères que vous créez à cet emplacement deviennent automatiquement disponibles pour toutes les activités [!DNL Recommendations].
* Lorsque vous créez une activité [!DNL Recommendations] à l’aide du [!UICONTROL Visual Experience Composer] (VEC), vous accédez immédiatement à l’écran [!UICONTROL Select Criteria] après avoir sélectionné un élément sur votre page et cliqué sur [!UICONTROL Replace w/ Recommendations], [!UICONTROL Insert Recommendations Before] ou [!UICONTROL Insert Recommendations After]. Vous pouvez ensuite sélectionner un critère disponible ou cliquer sur **[!UICONTROL Create Criteria]**. Si vous créez un nouveau critère, vous avez la possibilité d&#39;enregistrer vos critères pour les utiliser avec d&#39;autres activités [!DNL Recommendations]. Pour plus d’informations, voir [Création d’une activité Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* Lorsque vous modifiez une activité [!DNL Recommendations], cliquez dans la zone [!UICONTROL Recommendations Location] de votre page, puis sélectionnez **[!UICONTROL Change Criteria]**. Sur l’écran [!UICONTROL Select Criteria], cliquez sur **[!UICONTROL Create Criteria]**. Vous avez la possibilité d’enregistrer les nouveaux critères afin de les utiliser avec d’autres activités [!DNL Recommendations].

Les étapes suivantes supposent que vous accédez à l’écran [!UICONTROL Create New Criteria] à l’aide de la première méthode : l’écran de bibliothèque **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** .

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Cliquez sur **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**.

   ![Créer de nouveaux critères](assets/CreateNewCriteria_full-new.png)

1. Configurez les informations dans les sections suivantes.

## [!UICONTROL Basic Information] {#info}

1. Saisissez un **[!UICONTROL Criteria Name]**.

   C’est le nom « interne » utilisé pour décrire ce critère. Par exemple, vous voulez peut-être appeler votre critère « Produits générant la marge la plus élevée », mais vous ne voulez pas que ce titre soit affiché publiquement. Reportez-vous à la prochaine étape pour configurer le titre destiné au public.

   ![Section d’informations de base](assets/basic-information.png)

1. Saisissez un **[!UICONTROL Display Title]** destiné au public qui apparaîtra sur la page pour toutes les recommandations qui utilisent ce critère.

   Vous pouvez par exemple souhaiter afficher « Les personnes qui ont consulté cet article ont aussi consulté celui-ci » ou « Produits similaires » lorsque vous utilisez ce critère pour afficher des recommandations.

1. Saisissez un **[!UICONTROL Description]** court du critère.

   La description doit vous aider à identifier le critère et peut inclure des informations sur l’objet du critère.

1. Sélectionnez un secteur industriel vertical en fonction des objectifs de votre activité de recommandations.

   | Secteur industriel vertical | Objectif |
   |--- |--- |
   | Vente au détail / commerce électronique | Conversion entraînant un achat |
   | Génération de piste / B2B / Services financiers | Conversion sans achat |
   | Médias / Publication | Engagement |

   Les autres options de critère sont modifiées en fonction du secteur industriel vertical que vous sélectionnez.

1. Sélectionnez un **[!UICONTROL Page Type]**.

   Vous pouvez sélectionner plusieurs types de page.

   Le secteur industriel vertical et les types de page sont utilisés pour classer les critères enregistrés, ce qui facilite la réutilisation des critères pour d’autres activités [!DNL Recommendations].

## [!UICONTROL Recommendations Algorithm] {#rec-algo}

1. Sélectionnez un **[!UICONTROL Algorithm Type]** et un **[!UICONTROL Algorithm]** :

   ![Section Algorithme recommandée](assets/recommended-algorithm.png)

   | Type d’algorithme | Quand utiliser | Algorithmes disponibles |
   | --- | --- | --- |
   | [!UICONTROL Cart-Based] | Effectuez des recommandations en fonction du contenu du panier de l’utilisateur. | <ul><li>Les personnes qui les ont consultés ont consulté ceux-ci</li><li>Les personnes qui les ont consultés ont acheté ces</li><li>Les personnes qui les ont achetés ont acheté ces</li></ul> |
   | [!UICONTROL Popularity-Based] | Effectuez des recommandations en fonction de la popularité globale d’un élément sur votre site ou de la popularité des éléments au sein de la catégorie, de la marque, du genre, préférée ou la plus consultée d’un utilisateur, etc. | <ul><li>Les plus consultés sur l’ensemble du site</li><li>Les plus consultés par catégorie</li><li>Attribut d’élément le plus consulté</li><li>Meilleurs vendeurs sur le site</li><li>Meilleurs vendeurs par catégorie</li><li>Meilleurs vendeurs par attribut d’article</li><li>Mesure Début par Analytics</li></ul> |
   | [!UICONTROL Item-Based] | Effectuez des recommandations sur la base de la recherche d’éléments similaires à un élément que l’utilisateur consulte actuellement ou a récemment consulté. | <ul><li>Les personnes ayant consulté ceci ont consulté cela</li><li>Les personnes ayant consulté ceci ont acheté cela</li><li>Les personnes ayant acheté ceci ont acheté cela</li><li>Éléments avec des attributs similaires</li></ul> |
   | [!UICONTROL User-Based] | Effectuez des recommandations en fonction du comportement de l’utilisateur. | <ul><li>Éléments récemment consultés</li><li>Recommandé pour vous</li></ul> |
   | [!UICONTROL Custom Criteria] | Faites des recommandations en fonction d’un fichier personnalisé que vous chargez. | <ul><li>Algorithme personnalisé</li></ul> |

   >[!NOTE]
   >
   >Si vous sélectionnez **[!UICONTROL Items]**/ **[!UICONTROL Media with Similar Attributes]**, vous aurez la possibilité de définir des [ règles de similarité de contenu ](#similarity).

1. Au besoin, sélectionnez un **attribut d’élément** et un **attribut de profil à faire correspondre**, une **clé de recommandation**, une **clé de filtrage** et/ou une **mesure Analytics** pour configurer l’algorithme.

Les options de configuration d’algorithme restantes varient en fonction de l’algorithme sélectionné. Pour terminer la configuration de l’algorithme, sélectionnez [!UICONTROL Recommendation Key], [!UICONTROL Filtering Key], [!UICONTROL Co-Occurrence Basis], [!UICONTROL Analytics Metric] et/ou [!UICONTROL Item Attribute] et [!UICONTROL Profile Attribute to Match].

Pour plus d&#39;informations sur le choix d&#39;un [!UICONTROL Recommendation Key], voir [Baser la recommandation sur une clé de recommandation](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

## [!UICONTROL Data Source] {#data-source}

1. Sélectionnez le **[!UICONTROL Behavioral Data Source]** : [!UICONTROL Adobe Target] ou [!UICONTROL Analytics] souhaité.

   >[!NOTE]
   >
   >La section [!UICONTROL Behavioral Data Source] s’affiche uniquement si votre mise en oeuvre utilise [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T).

   ![Section Source de données comportementales](assets/data-source.png)

   Si vous choisissez [!UICONTROL Analytics], sélectionnez la suite de rapports de votre choix.

   Si les critères utilisent [!DNL Adobe Analytics] comme source de données comportementales, le temps qu’ils mettent à être disponibles une fois créés dépend de l’utilisation ou non de la suite de rapports et de périodes d’analyse sur d’autres critères, comme expliqué ci-dessous :

   * **Configuration unique d’une suite de rapports** : la première fois qu’une suite de rapports est utilisée avec une fenêtre de recherche de plage de données spécifique, [!DNL Target Recommendations] peut prendre de deux à sept jours pour télécharger complètement les données comportementales de la suite de rapports sélectionnée depuis [!DNL Analytics]. Cette période dépend de la charge du système [!DNL Analytics].
   * **Critères nouveaux ou modifiés à l’aide d’une suite de rapports déjà disponible** : lors de la création d’un critère ou de la modification d’un critère existant, si la suite de rapports sélectionnée a déjà été utilisée avec [!DNL Target Recommendations], avec une plage de données inférieure ou égale à celle sélectionnée, les données sont immédiatement disponibles et aucune configuration unique n’est requise. Dans ce cas ou si les paramètres d’un algorithme sont modifiés sans changer la suite de rapports ou la plage de données sélectionnée, l’algorithme s’exécute ou se réexécute dans les 12 heures.
   * **Exécutions d’algorithme en cours** : les données sont transmises quotidiennement d’[!DNL Analytics] à [!DNL Target Recommendations]. Par exemple, pour la recommandation [!UICONTROL Viewed Affinity], lorsqu’un utilisateur consulte un produit, un appel de suivi de consultation de produit est transmis à [!DNL Analytics] presque en temps réel. Les données [!DNL Analytics] sont envoyées à [!DNL Target] tôt le lendemain matin et [!DNL Target] exécute l’algorithme en moins de 12 heures.

   Pour plus d’informations, voir [Utilisation d’Adobe Analytics avec Target Recommendations](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md).

1. Définissez le **[!UICONTROL Lookback Window]** pour déterminer la période des données historiques de comportement des utilisateurs disponibles à utiliser lors de la détermination des recommandations à afficher. Cette option est disponible pour tous les algorithmes, à l’exception des éléments avec des attributs similaires et des algorithmes personnalisés.

   ![Curseur de fenêtre de recherche en amont](assets/data-range.png)

   Si votre site reçoit un volume de trafic important et que les comportements changent fréquemment, sélectionnez une fenêtre de données plus courte. Une fenêtre plus courte permet [!DNL Recommendations] d’être plus réactif aux changements du marché et de votre entreprise. Par exemple, une fenêtre plus courte signifie que [!DNL Recommendations] détectera les changements de comportement des visiteurs lorsque ces derniers commencent des achats saisonniers, tels que les achats de la rentrée ou de la période des fêtes, et recommanderont les articles appropriés à ces saisons.

   Si vous n’avez pas beaucoup de données ou que le comportement des visiteurs ne change pas fréquemment, vous pouvez sélectionner une fenêtre plus longue. Cependant, pour de nombreux sites, une fenêtre plus courte donne des recommandations de meilleure qualité.

   Les périodes de données disponibles sont :

   | Option Intervalle de recherche en amont | Fréquence mise à jour (affichée au survol) | Algorithmes pris en charge |
   | --- | --- | --- |
   | Six heures | L’algorithme s’exécute toutes les 3 à 6 heures | [!UICONTROL Popularity-Based] algorithmes lorsque le [!UICONTROL Behavioral Data Source] sélectionné est [!DNL Adobe Target] |
   | Un jour | L’algorithme s’exécute toutes les 12 à 24 heures | [!UICONTROL Popularity-Based] algorithmes |
   | Deux jours | L’algorithme s’exécute toutes les 12 à 24 heures | <ul><li>[!UICONTROL Popularity-Based] algorithmes</li><li>[!UICONTROL Item-Based] algorithmes</li><li>[!UICONTROL User-Based] algorithmes</li><li>[!UICONTROL Cart-Based] algorithmes</li></ul> |
   | Une semaine | L’algorithme s’exécute toutes les 24 à 48 heures | <ul><li>[!UICONTROL Popularity-Based] algorithmes</li><li>[!UICONTROL Item-Based] algorithmes</li><li>[!UICONTROL User-Based] algorithmes</li><li>[!UICONTROL Cart-Based] algorithmes</li></ul> |
   | Deux semaines | L’algorithme s’exécute toutes les 24 à 48 heures | <ul><li>[!UICONTROL Popularity-Based] algorithmes</li><li>[!UICONTROL Item-Based] algorithmes</li><li>Tous les [!UICONTROL User-Based] algorithmes</li><li>[!UICONTROL Cart-Based] algorithmes</li></ul> |
   | Un mois (30 jours) | L’algorithme s’exécute toutes les 24 à 48 heures | <ul><li>[!UICONTROL Popularity-Based] algorithmes</li><li>[!UICONTROL Item-Based] algorithmes</li><li>[!UICONTROL User-Based] algorithmes</li><li>[!UICONTROL Cart-Based] algorithmes</li></ul> |
   | Deux mois (61 jours) | L’algorithme s’exécute toutes les 24 à 48 heures | <ul><li>[!UICONTROL Popularity-Based] algorithmes</li><li>[!UICONTROL Item-Based] algorithmes</li><li>[!UICONTROL User-Based] algorithmes</li><li>[!UICONTROL Cart-Based] algorithmes</li></ul> |

## [!UICONTROL Backup Content] {#content}

Les règles [!UICONTROL Backup Content] déterminent ce qui se passe si le nombre d’éléments recommandés ne remplit pas votre [conception de recommandations](/help/main/c-recommendations/c-design-overview/design-overview.md). Il est possible que les critères [!DNL Recommendations] renvoient moins de recommandations que ce que votre conception exige. Par exemple, si votre conception comporte des emplacements pour quatre éléments, mais que vos critères entraînent seulement la recommandation de deux éléments, vous pouvez laisser les emplacements restants vides, utiliser les recommandations de sauvegarde pour remplir les emplacements supplémentaires ou choisir d’afficher aucune recommandation.

![Section de contenu](assets/content.png)

1. (Facultatif) Faites glisser la bascule **[!UICONTROL Partial Design Rendering]** vers la position &quot;activée&quot;.

   Le plus grand nombre d’emplacements possible sera rempli, mais le modèle de conception peut inclure un espace vide pour les emplacements restants. Si cette option est désactivée et qu’il n’y a pas assez de contenu pour remplir tous les emplacements disponibles, les recommandations ne sont pas diffusées et le contenu par défaut s’affiche à la place.

   Activez cette option si vous souhaitez que les recommandations soient servies avec des emplacements vides. Utilisez les recommandations de sauvegarde si vous souhaitez que les emplacements de recommandations soient remplis avec du contenu en fonction de vos critères, avec des emplacements vides remplis avec du contenu similaire ou populaire provenant de votre site, comme expliqué à l’étape suivante.

1. (Facultatif) Faites glisser la bascule **[!UICONTROL Show Backup Content]** vers la position &quot;activée&quot;.

   Remplissez les créneaux vides restants dans la conception avec une sélection aléatoire des produits les plus consultés sur l’ensemble de votre site.

   L’utilisation de recommandations de sauvegarde permet de s’assurer que votre conception de recommandations remplit tous les emplacements disponibles. Supposons que vous ayez une conception 4 x 1, comme illustré ci-dessous :

   ![4 x 1 design](/help/main/c-recommendations/c-design-overview/assets/velocity_example.png)

   Supposons que vos critères entraînent la recommandation de deux éléments seulement. Si vous activez l’option [!UICONTROL Partial Design Rendering], les deux premiers emplacements sont remplis, mais les deux autres restent vides. Cependant, si vous activez l’option [!UICONTROL Show Backup Recommendations], les deux premiers emplacements sont remplis en fonction des critères que vous avez spécifiés et les deux autres sont remplis en fonction des recommandations de sauvegarde.

   La matrice suivante montre le résultat que vous obtiendrez lors de l’utilisation des options [!UICONTROL Partial Design Rendering] et [!UICONTROL Backup Content] :

   | Rendu de conception partiel | Contenu de la sauvegarde | Résultats |
   |--- |--- |--- |
   | Désactivé | Désactivé | Si un nombre inférieur de recommandations est renvoyé par rapport à celui attendu par la conception, cette dernière est remplacée par le contenu par défaut et aucune recommandation n’est affichée. |
   | Activé | Désactivé | La conception est rendue, mais elle peut inclure des espaces vides si un nombre inférieur de recommandations par rapport à celui attendu est renvoyé. |
   | Activé | Activé | Les recommandations de sauvegarde remplissent les emplacements de la conception, en affichant entièrement celle-ci.<br>Si l’application des règles d’inclusion aux recommandations de sauvegarde limite le nombre de recommandations de sauvegarde incluses de sorte que la conception ne puisse pas être remplie, cette dernière est partiellement affichée.<br>Si le critère ne renvoie aucune recommandation et si les règles d’inclusion limitent les recommandations de sauvegarde à zéro, la conception est remplacée par le contenu par défaut. |
   | Désactivé | Activé | Les recommandations de sauvegarde remplissent les emplacements de la conception, en affichant entièrement celle-ci.<br>Si l’application des règles d’inclusion aux recommandations de sauvegarde limite le nombre de recommandations de sauvegarde incluses de sorte que la conception ne puisse pas être remplie, cette dernière est replacée par le contenu par défaut et aucune recommandation n’est affichée. |

   Pour plus d’informations, voir [Utilisation d’une recommandation de sauvegarde](/help/main/c-recommendations/c-algorithms/backup-recs.md).

1. (Conditionnel) Si vous avez sélectionné **[!UICONTROL Show Backup Content]** à l’étape précédente, vous pouvez activer **[!UICONTROL Apply inclusion rules to backup recommendations]**.

   Les règles d’inclusion déterminent les éléments qui sont inclus dans vos recommandations. Les options disponibles dépendent du secteur industriel vertical.

   Pour plus d’informations, voir [Spécification des règles d’inclusion](#inclusion) ci-dessous.

## Similarité de contenu {#similarity}

Utilisez des règles [!UICONTROL Content Similarity] pour effectuer des recommandations basées sur des attributs d’élément ou de média.

>[!NOTE]
>
>Si vous avez sélectionné **[!UICONTROL Item-Based]**/ **[!UICONTROL Media with Similar Attributes]** comme Type d’algorithme et Algorithme, vous avez la possibilité de définir des règles de similarité de contenu.

La similarité de contenu compare des mots-clés d’attributs d’éléments et effectue des recommandations basées sur le nombre de mots-clés que différents éléments ont en commun. Les recommandations basées sur la similarité de contenu ne nécessitent pas d’anciennes données pour fournir des résultats solides.

L’utilisation de la similarité de contenu pour générer des recommandations est particulièrement efficace pour les nouveaux éléments, qui ne sont pas susceptibles d’apparaître dans des recommandations en utilisant la logique *Les personnes ayant consulté ceci ont consulté cela* et une autre logique basée sur le comportement passé. Vous pouvez également utiliser la similarité de contenu pour générer des recommandations utiles pour les nouveaux visiteurs, qui n’ont pas d’achats antérieurs ni d’autres données historiques.

Lorsque vous sélectionnez **[!UICONTROL Item-Based]**/ **[!UICONTROL Media with Similar Attributes]**, vous avez la possibilité de créer des règles pour augmenter ou diminuer l’importance des attributs d’élément spécifiques pour déterminer les recommandations. Pour des éléments tels que des livres, vous pouvez augmenter l’importance d’attributs tels que le *genre*, l’*auteur*, la *série* et ainsi de suite, pour recommander des livres similaires.

![Image ContentSimilarity](assets/ContentSimilarity.png)

Étant donné que la similarité de contenu utilise des mots-clés pour comparer des éléments, certains attributs, tels que *message* ou *description*, peuvent parasiter la comparaison. Vous pouvez créer des règles pour ignorer ces attributs.

Par défaut, tous les attributs sont définis sur *De base*. À moins de vouloir modifier ce paramètre, vous ne devez pas créer de règle.

>[!NOTE]
>
>L’algorithme de similarité de contenu peut utiliser un échantillonnage aléatoire pour calculer la similarité entre les éléments. Par conséquent, les évaluations de similarité entre les éléments peuvent varier entre les exécutions d’algorithme.

## Règles d’inclusion {#inclusion}

Plusieurs options vous aident à préciser les éléments qui s’affichent dans vos recommandations. Vous pouvez utiliser des règles d’inclusion lors de la création de critères ou de promotions.

![Règles d’inclusion](/help/main/c-recommendations/c-algorithms/assets/inclusion-rules.png)

Les règles d’inclusion sont facultatives. Cependant, le fait de définir ces détails vous permet de mieux contrôler les éléments qui apparaissent dans vos recommandations. Chaque détail configuré précise les critères d’affichage.

Vous pouvez, par exemple, choisir d’afficher uniquement les chaussures pour femmes dont le stock est supérieur à 50 et le prix compris entre 25 € et 45 €. Vous pouvez également pondérer chaque attribut, de telle sorte que la probabilité d’affichage soit plus élevée pour les éléments qui présentent plus d’intérêt pour vos activités.

Par exemple, vous pouvez choisir d’afficher les offres d’emploi pour les visiteurs qui visitent votre site uniquement à partir de certaines villes et qui possèdent les diplômes universitaires requis.

Les options de règle d’inclusion varient selon le secteur industriel vertical. Par défaut, les règles d’inclusion sont appliquées aux recommandations de sauvegarde.

>[!IMPORTANT]
>
>Veuillez utiliser les règles d’inclusion avec prudence. Elles se révèlent utiles si, par exemple, des règles en vigueur dans votre entreprise interdisent la recommandation d’une marque pendant la consultation d’une autre marque. L’utilisation de cette fonctionnalité a toutefois un coût. Si vous empêchez l’affichage de certains éléments alors qu’ils devraient normalement être affichés selon les critères d’activité, l’effet élévateur risque d’être amoindri.

Les règles d’inclusion sont jointes par l’opérateur ET. Toutes les règles doivent être respectées pour inclure un élément dans une recommandation.

Pour créer une règle d’inclusion simple, comme mentionné précédemment, afin d’afficher seulement les chaussures pour femmes dont le stock est supérieur à 50 et le prix compris entre 25 et 45 €, procédez comme suit :

1. (Conditionnel) Faites glisser la bascule **[!UICONTROL Allow recently purchased items to be recommended?]** vers la position &quot;activée&quot;.

   Ce paramètre est basé sur `productPurchasedId`. Le comportement par défaut est de ne pas recommander des articles précédemment achetés. En général, vous ne souhaitez pas promouvoir des articles qu’un client a récemment achetés. Il est utile si vous vendez des articles que les gens n’achètent en général qu’une fois, comme des kayaks. Si vous vendez des articles que les gens reviennent acheter à plusieurs reprises, comme du shampooing ou d’autres articles personnels, vous devez activer cette option.

1. Définissez une gamme de prix pour les produits que vous souhaitez recommander.
1. Définissez la valeur de stock minimale pour les produits que vous souhaitez recommander.
1. Configurez la recommandation de manière à afficher uniquement les éléments qui répondent à certains critères.

   ![Image Recs_InclusionRules](assets/Recs_InclusionRules.png)

   Vous pouvez indiquer que les éléments sont inclus uniquement lorsque l’un des attributs de la liste répond (ou ne répond pas) à l’une ou plusieurs des conditions spécifiées.

   Les évaluateurs disponibles dépendent de la valeur que vous sélectionnez dans la première liste déroulante. Vous pouvez inclure plusieurs éléments. Ces éléments sont évalués par l’opérateur OU.

   Plusieurs règles sont associées à l’aide de l’opérateur ET.

   >[!NOTE]
   >
   >Cette option limite les éléments affichés dans la recommandation. Elle n’affecte pas les pages sur lesquelles la recommandation est affichée. Pour limiter l’emplacement d’affichage de la recommandation, sélectionnez les pages dans le compositeur d’expérience.

Pour plus d’informations, voir [Utilisation de règles d’inclusion dynamiques et statiques](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

## Pondération d’attribut {#weighting}

Vous pouvez ajouter plusieurs règles pour &quot;pousser&quot; l’algorithme en fonction d’informations ou de métadonnées importantes sur le catalogue de contenu afin que certains éléments soient plus susceptibles d’être affichés.

Par exemple, vous pouvez appliquer une pondération plus élevée aux articles en vente afin qu’ils apparaissent plus souvent dans la recommandation. Les articles non soldés ne sont pas complètement exclus, mais ils apparaîtront moins souvent. Plusieurs attributs pondérés peuvent être appliqués au même algorithme et les attributs pondérés peuvent être testés dans un trafic partagé dans la recommandation.

1. Sélectionnez une valeur.

   La valeur détermine le type d’élément le plus susceptible de s’afficher, selon l’un des critères disponibles.

1. Sélectionnez un évaluateur.

1. Saisissez le mot clé pour compléter les attributs de règle.

   Par exemple, la règle complète peut être &quot;La catégorie contient des sous-chaînes de chaussures&quot;.

   ![Image Recs_AttributeWeighting](assets/Recs_AttributeWeighting.png)

1. Sélectionnez le poids à assigner à la règle.

   Les options sont comprises entre 0 et 100, avec des incréments de 25.

1. Ajoutez d’autres règles si nécessaire.

Lorsque vous avez terminé, cliquez sur **[!UICONTROL Save]**.

Si vous créez une activité [!UICONTROL Recommendations] ou que vous en modifiez une existante, la case **[!UICONTROL Save criteria for later]** est cochée par défaut. Si vous ne souhaitez pas utiliser les critères dans d’autres activités, décochez la case avant de procéder à l’enregistrement.

## Vidéo de formation : Création de critères dans Recommendations (12:33) ![Badge de tutoriel](/help/main/assets/tutorial.png)

Cette vidéo traite des sujets suivants :

* Création de critères
* Création d’une séquence de critères
* Téléchargement de critères personnalisés

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
