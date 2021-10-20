---
keywords: critères ; algorithme ; industrie verticale ; type de page ; clé de recommandation ; logique de recommandation ; logique ; plage de données ; fenêtre de rétrospection ; source de données de comportement ; conception partielle ; recommandations de sauvegarde ; règles d'inclusion ; pondération d'attribut ; catégorie actuelle ; attribut personnalisé ; dernier élément acheté ; dernier élément consulté ; élément le plus consulté ; catégorie préférée ; popularité ; élément récemment consulté ; dernier élément acheté ; favori ; favori récemment consulté
description: Découvrez comment créer des critères qui contrôlent le contenu de vos activités Adobe Recommendations pour afficher les recommandations les plus appropriées à votre activité.
title: Comment créer des critères dans Recommendations ?
feature: Recommendations
exl-id: 3f4f59b2-6637-4c33-bf17-bff11bef7173
source-git-commit: 68670f0b7753ee34c186a380004620ae4ba0cfd1
workflow-type: tm+mt
source-wordcount: '2797'
ht-degree: 53%

---

# ![PREMIUM](/help/assets/premium.png) Création de critères

Critères dans [!UICONTROL Adobe Target] [!UICONTROL Recommendations] contrôler le contenu de votre [!UICONTROL Recommendations] activités. Créez des critères pour afficher les recommandations qui sont les plus appropriées à votre activité. Ces critères utilisent les actions du visiteur pour déterminer le contenu ou les produits à afficher.

Les sections suivantes expliquent comment créer de nouveaux critères.

## Accédez à l’écran Créer de nouveaux critères.

Il existe plusieurs méthodes pour accéder à l’écran [!UICONTROL Créer des critères]. Certaines options de l’écran varient en fonction de l’accès à ce dernier.

* Sur la **[!UICONTROL Recommendations]** > **[!UICONTROL Critères]** écran de bibliothèque, cliquez sur **[!UICONTROL Créer des critères]** > **[!UICONTROL Créer des critères]**. Les critères que vous créez à cet emplacement deviennent automatiquement disponibles pour toutes les activités [!DNL Recommendations].
* Lorsque vous créez un [!DNL Recommendations] à l’aide de la [!UICONTROL Compositeur d’expérience visuelle] (VEC), vous êtes immédiatement amené au [!UICONTROL Sélectionner des critères] après avoir sélectionné un élément sur votre page, cliquez sur [!UICONTROL Remplacer par Recommendations], [!UICONTROL Insérer Recommendations avant], ou [!UICONTROL Insérer Recommendations après]. Vous pouvez ensuite sélectionner un critère disponible ou cliquer sur **[!UICONTROL Créer des critères]**. Si vous créez un nouveau critère, vous avez la possibilité d’enregistrer vos critères pour les utiliser avec d’autres [!DNL Recommendations] activités. Pour plus d’informations, voir [Création d’une activité Recommendations](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* Lorsque vous modifiez une [!DNL Recommendations] activité, cliquez sur la zone [!UICONTROL Emplacement des recommandations] sur votre page, puis sélectionnez **[!UICONTROL Changer les critères]**. Sur la [!UICONTROL Sélectionner des critères] , cliquez sur **[!UICONTROL Créer des critères]**. Vous avez la possibilité d’enregistrer les nouveaux critères afin de les utiliser avec d’autres activités [!DNL Recommendations].

Les étapes suivantes supposent que vous accédez au fichier [!UICONTROL Créer de nouveaux critères] en utilisant la première méthode : le **[!UICONTROL Recommendations]** > **[!UICONTROL Critères]** écran de bibliothèque.

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Critères]**.

1. Cliquez sur **[!UICONTROL Créer des critères]** > **[!UICONTROL Créer des critères]**.

   ![Créer de nouveaux critères](assets/CreateNewCriteria_full-new.png)

1. Configurez les informations dans les sections suivantes.

## [!UICONTROL Informations fondamentales ] {#info}

1. Saisissez un **[!UICONTROL Nom de critère]**.

   C’est le nom « interne » utilisé pour décrire ce critère. Par exemple, vous voulez peut-être appeler votre critère « Produits générant la marge la plus élevée », mais vous ne voulez pas que ce titre soit affiché publiquement. Reportez-vous à la prochaine étape pour configurer le titre destiné au public.

   ![Section Informations de base](assets/basic-information.png)

1. Saisissez un **[!UICONTROL Titre d’affichage]** destiné à l’audience qui apparaîtra sur la page pour n’importe quelle recommandation qui utilise ce critère.

   Vous pouvez par exemple souhaiter afficher « Les personnes qui ont consulté cet article ont aussi consulté celui-ci » ou « Produits similaires » lorsque vous utilisez ce critère pour afficher des recommandations.

1. Saisissez une courte **[!UICONTROL Description]** du critère.

   La description doit vous aider à identifier les critères et peut inclure des informations sur l&#39;objet des critères.

1. Sélectionnez un secteur vertical en fonction des objectifs de votre activité de recommandations.

   | Secteur industriel vertical | Objectif |
   |--- |--- |
   | Vente au détail / commerce électronique | Conversion entraînant un achat |
   | Génération de piste / B2B / Services financiers | Conversion sans achat |
   | Médias / Publication | Engagement |

   Les autres options de critère sont modifiées en fonction du secteur industriel vertical que vous sélectionnez.

1. Sélectionnez un **[!UICONTROL Type de page]**.

   Vous pouvez sélectionner plusieurs types de page.

   Le secteur industriel vertical et les types de page sont utilisés pour classer les critères enregistrés, ce qui facilite la réutilisation des critères pour d’autres activités [!DNL Recommendations].

## [!UICONTROL Algorithme Recommendations] {#rec-algo}

1. Sélectionnez un **[!UICONTROL Type d&#39;algorithme]** et **[!UICONTROL Algorithme]**:

   ![Section Algorithme recommandé](assets/recommended-algorithm.png)

   | Type d’algorithme | Quand utiliser | Algorithmes disponibles |
   | --- | --- | --- |
   | [!UICONTROL Basé sur la popularité] | Faites des recommandations basées sur la popularité globale d’un élément sur votre site ou sur la popularité des éléments dans la catégorie préférée ou la plus regardée d’un utilisateur, la marque, le genre, etc. | <ul><li>Le plus consulté sur le site</li><li>Les plus regardés par catégorie</li><li>Plus consulté par attribut d&#39;article</li><li>Principaux vendeurs sur le site</li><li>Principaux vendeurs par catégorie</li><li>Principaux vendeurs par objet</li><li>Mesure Top by Analytics</li></ul> |
   | [!UICONTROL Basé sur un article] | Faites des recommandations en fonction de la recherche d’éléments similaires à un élément actuellement consulté ou récemment consulté par l’utilisateur. | <ul><li>Les personnes ayant consulté ceci ont consulté cela</li><li>Les personnes ayant consulté ceci ont acheté cela</li><li>Les personnes ayant acheté ceci ont acheté cela</li><li>Éléments avec des attributs similaires</li></ul> |
   | [!UICONTROL Basé sur l’utilisateur] | Faites des recommandations en fonction du comportement de l’utilisateur. | <ul><li>Éléments récemment consultés</li><li>Recommandé pour vous</li></ul> |
   | Basé sur le panier | Faites des recommandations en fonction du contenu du panier de l’utilisateur. | <ul><li>Les Personnes Qui Les Ont Visualisées, Les Ont Vu</li><li>Les Personnes Qui Les Ont Vu, Les Ont Achetées</li><li>Des gens qui les ont achetés, qui les ont achetés</li></ul> |
   | [!UICONTROL Critères personnalisés] | Faites des recommandations en fonction d’un fichier personnalisé que vous chargez. | <ul><li>Algorithme personnalisé</li></ul> |


   >[!NOTE]
   >
   >Si vous sélectionnez **[!UICONTROL Éléments]**/ **[!UICONTROL Média avec attributs similaires]**, vous avez la possibilité de définir [règles de similarité de contenu](#similarity).

1. Si nécessaire, sélectionnez un **Attribut d&#39;article** et **Attribut de profil à faire correspondre**, une **Clé de recommandation**, **Clé de filtrage**, et/ou **Mesure analytique** pour configurer l’algorithme.

Pour plus d’informations sur la sélection d’une clé de recommandation, voir [Baser la recommandation sur une clé de recommandation](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

## [!UICONTROL Source de données] {#data-source}

1. Sélectionnez la **[!UICONTROL Source de données comportementale]**: [!UICONTROL Adobe Target] ou [!UICONTROL Analytics].

   >[!NOTE]
   >
   >Le [!UICONTROL Source de données comportementale] s’affiche uniquement si votre implémentation utilise [Analytics pour Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T).

   ![Section Source de données comportementale](assets/data-source.png)

   Si vous choisissez [!UICONTROL Analytics], sélectionnez la suite de rapports souhaitée.

   Si le critère utilise [!DNL Adobe Analytics] en tant que source de données comportementale, une fois créée, la durée de disponibilité des critères dépend de l&#39;utilisation de la suite de rapports et de la fenêtre de consultation sélectionnées pour d&#39;autres critères, comme expliqué ci-dessous :

   * **Configuration unique d’une suite de rapports** : la première fois qu’une suite de rapports est utilisée avec une fenêtre de recherche de plage de données spécifique, [!DNL Target Recommendations] peut prendre de deux à sept jours pour télécharger complètement les données comportementales de la suite de rapports sélectionnée depuis [!DNL Analytics]. Cette période dépend de la [!DNL Analytics] charge système.
   * **Critères nouveaux ou modifiés à l’aide d’une suite de rapports déjà disponible** : lors de la création d’un critère ou de la modification d’un critère existant, si la suite de rapports sélectionnée a déjà été utilisée avec [!DNL Target Recommendations], avec une plage de données inférieure ou égale à celle sélectionnée, les données sont immédiatement disponibles et aucune configuration unique n’est requise. Dans ce cas ou si les paramètres d’un algorithme sont modifiés sans changer la suite de rapports ou la plage de données sélectionnée, l’algorithme s’exécute ou se réexécute dans les 12 heures.
   * **Exécutions d’algorithme en cours** : les données sont transmises quotidiennement d’[!DNL Analytics] à [!DNL Target Recommendations]. Par exemple, pour la recommandation [!UICONTROL Affinité consultée], lorsqu’un utilisateur consulte un produit, un appel de suivi de consultation de produit est transmis à [!DNL Analytics] pratiquement en temps réel. Les données [!DNL Analytics] sont envoyées à [!DNL Target] tôt le lendemain matin et [!DNL Target] exécute l’algorithme en moins de 12 heures.

   Pour plus d’informations, voir [Utiliser Adobe Analytics avec Target Recommendations](/help/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md).

1. Définissez la **[!UICONTROL Fenêtre de recherche]** pour déterminer la plage temporelle des données de comportement utilisateur historiques disponibles à utiliser lors de la détermination des recommandations à afficher. Cette option est disponible pour tous les algorithmes, à l’exception des éléments avec des attributs similaires et des algorithmes personnalisés.

   ![Curseur de la fenêtre de consultation](assets/data-range.png)

   Si votre site reçoit un volume de trafic important et que les comportements changent fréquemment, sélectionnez une fenêtre de données plus courte. Une fenêtre plus courte permet [!DNL Recommendations] d’être plus réactif aux changements du marché et de votre entreprise. Par exemple, une fenêtre plus courte signifie que [!DNL Recommendations] détectera les changements de comportement des visiteurs lorsque ces derniers commencent des achats saisonniers, tels que les achats de la rentrée ou de la période des fêtes, et recommanderont les articles appropriés à ces saisons.

   Si vous n’avez pas beaucoup de données ou que le comportement des visiteurs ne change pas fréquemment, vous pouvez sélectionner une fenêtre plus longue. Toutefois, pour de nombreux sites, une fenêtre plus courte donne lieu à des recommandations de meilleure qualité.

   Les périodes de données disponibles sont :

   | Option de fenêtre de recherche | Fréquence mise à jour (affichée sur le survol) | Boîtiers pris en charge |
   | --- | --- | --- |
   | Six heures | Algorithme s&#39;exécute toutes les 3-6 heures | [!UICONTROL Basé sur la popularité] algorithme lorsque la [!UICONTROL Source de données comportementale] est [!DNL Adobe Target] |
   | Un jour | Algorithme s&#39;exécute toutes les 12-24 heures | [!UICONTROL Basé sur la popularité] algorithmes |
   | Deux jours | Algorithme s&#39;exécute toutes les 12-24 heures | <ul><li>[!UICONTROL Basé sur la popularité] algorithmes</li><li>[!UICONTROL Basé sur un article] algorithmes</li><li>[!UICONTROL Basé sur l’utilisateur] algorithmes</li><li>[!UICONTROL Basé sur le panier] algorithmes</li></ul> |
   | Une semaine | Algorithme s&#39;exécute toutes les 24-48 heures | <ul><li>[!UICONTROL Basé sur la popularité] algorithmes</li><li>[!UICONTROL Basé sur un article] algorithmes</li><li>[!UICONTROL Basé sur l’utilisateur] algorithmes</li><li>[!UICONTROL Basé sur le panier] algorithmes</li></ul> |
   | Deux semaines | Algorithme s&#39;exécute toutes les 24-48 heures | <ul><li>[!UICONTROL Basé sur la popularité] algorithmes</li><li>[!UICONTROL Basé sur un article] algorithmes</li><li>Tout [!UICONTROL Basé sur l’utilisateur] algorithmes</li><li>[!UICONTROL Basé sur le panier] algorithmes</li></ul> |
   | Un mois (30 jours) | Algorithme s&#39;exécute toutes les 24-48 heures | <ul><li>[!UICONTROL Basé sur la popularité] algorithmes</li><li>[!UICONTROL Basé sur un article] algorithmes</li><li>[!UICONTROL Basé sur l’utilisateur] algorithmes</li><li>[!UICONTROL Basé sur le panier] algorithmes</li></ul> |
   | Deux mois (61 jours) | Algorithme s&#39;exécute toutes les 24-48 heures | <ul><li>[!UICONTROL Basé sur la popularité] algorithmes</li><li>[!UICONTROL Basé sur un article] algorithmes</li><li>[!UICONTROL Basé sur l’utilisateur] algorithmes</li><li>[!UICONTROL Basé sur le panier] algorithmes</li></ul> |

## [!UICONTROL Contenu de sauvegarde] {#content}

[!UICONTROL Contenu de sauvegarde] les règles déterminent ce qui se passe si le nombre d’éléments recommandés ne remplit pas votre [conception des recommandations](/help/c-recommendations/c-design-overview/design-overview.md). Il est possible de [!DNL Recommendations] pour renvoyer moins de recommandations que votre design ne le demande. Par exemple, si votre design comporte des emplacements pour quatre éléments, mais que vos critères entraînent la recommandation de deux éléments seulement, vous pouvez laisser les emplacements restants vides, vous pouvez utiliser des recommandations de sauvegarde pour remplir les emplacements supplémentaires, ou vous pouvez choisir d’afficher aucune recommandation.

![Section Contenu](assets/content.png)

1. (Facultatif) Faites glisser la **[!UICONTROL Rendu partiel de la conception]** basculez vers la position &quot;activé&quot;.

   Le plus grand nombre possible d’emplacements sera rempli, mais le modèle de conception peut inclure un espace vide pour les emplacements restants. Si cette option est désactivée et qu’il n’y a pas assez de contenu pour remplir tous les emplacements disponibles, les recommandations ne sont pas servies et le contenu par défaut s’affiche à la place.

   Activez cette option si vous souhaitez que les recommandations soient servies avec des emplacements vides. Utilisez les recommandations de sauvegarde si vous souhaitez que les emplacements de recommandation soient remplis avec du contenu basé sur vos critères, avec des emplacements vides remplis avec du contenu similaire ou populaire de votre site, comme expliqué à l’étape suivante.

1. (Facultatif) Faites glisser la **[!UICONTROL Afficher le contenu de sauvegarde]** basculez vers la position &quot;activé&quot;.

   Remplissez les emplacements vides restants dans le design avec une sélection aléatoire des produits les plus consultés sur l’ensemble de votre site.

   L’utilisation des recommandations de sauvegarde garantit que votre conception de recommandation remplit tous les emplacements disponibles. Supposons que vous ayez une conception 4 x 1, comme illustré ci-dessous :

   ![4 x 1](/help/c-recommendations/c-design-overview/assets/velocity_example.png)

   Supposons que vos critères ne recommandent que deux éléments. Si vous activez l’option [!UICONTROL Rendu partiel de la conception] , les deux premiers emplacements sont remplis, mais les deux autres emplacements restent vides. Toutefois, si vous activez l’option [!UICONTROL Afficher le Recommendations de sauvegarde] , les deux premiers emplacements sont remplis en fonction de vos critères spécifiés et les deux autres emplacements sont remplis en fonction de vos recommandations de sauvegarde.

   La matrice suivante affiche le résultat que vous observerez lors de l’utilisation de la [!UICONTROL Rendu partiel de la conception] et [!UICONTROL Contenu de sauvegarde] options :

   | Rendu de conception partiel | Contenu de sauvegarde | Résultats |
   |--- |--- |--- |
   | Désactivé | Désactivé | Si un nombre inférieur de recommandations est renvoyé par rapport à celui attendu par la conception, cette dernière est remplacée par le contenu par défaut et aucune recommandation n’est affichée. |
   | Activé | Désactivé | La conception est rendue, mais elle peut inclure des espaces vides si un nombre inférieur de recommandations par rapport à celui attendu est renvoyé. |
   | Activé | Activé | Les recommandations de sauvegarde remplissent les emplacements de la conception, en affichant entièrement celle-ci.<br>Si l’application des règles d’inclusion aux recommandations de sauvegarde limite le nombre de recommandations de sauvegarde incluses de sorte que la conception ne puisse pas être remplie, cette dernière est partiellement affichée.<br>Si le critère ne renvoie aucune recommandation et si les règles d’inclusion limitent les recommandations de sauvegarde à zéro, la conception est remplacée par le contenu par défaut. |
   | Désactivé | Activé | Les recommandations de sauvegarde remplissent les emplacements de la conception, en affichant entièrement celle-ci.<br>Si l’application des règles d’inclusion aux recommandations de sauvegarde limite le nombre de recommandations de sauvegarde incluses de sorte que la conception ne puisse pas être remplie, cette dernière est replacée par le contenu par défaut et aucune recommandation n’est affichée. |

   Pour plus d’informations, voir [Utiliser une recommandation de sauvegarde](/help/c-recommendations/c-algorithms/backup-recs.md).

1. (Conditionnel) Si vous avez sélectionné **[!UICONTROL Afficher le contenu de sauvegarde]** à l’étape précédente, vous pouvez activer **[!UICONTROL Appliquer les règles d&#39;inclusion aux recommandations de sauvegarde]**.

   Les règles d’inclusion déterminent quels éléments sont inclus dans vos recommandations. Les options disponibles dépendent du secteur industriel vertical.

   Pour plus d’informations, voir [Spécification des règles d’inclusion](#inclusion) ci-dessous.

1. (Facultatif) Faites glisser la **[!UICONTROL Recommander les articles précédemment achetés]** basculez vers la position &quot;activé&quot;.

   Ce paramètre est basé sur `productPurchasedId`. Le comportement par défaut est de ne pas recommander des articles précédemment achetés. En général, vous ne souhaitez pas promouvoir des articles qu’un client a récemment achetés. Il est utile si vous vendez des articles que les gens n’achètent en général qu’une fois, comme des kayaks. Si vous vendez des objets que les gens reviennent acheter à plusieurs reprises, comme du shampooing ou d’autres objets personnels, vous devez activer cette option.

## Similarité de contenu {#similarity}

Utilisez les règles de [!UICONTROL similarité de contenu] pour effectuer des recommandations en fonction des attributs d’élément ou de média.

>[!NOTE]
>
>Si vous avez sélectionné **[!UICONTROL Basé sur un article]**/ **[!UICONTROL Média avec attributs similaires]** en tant que type d’algorithme et algorithme, vous avez la possibilité de définir des règles de similarité de contenu.

La similarité de contenu compare des mots-clés d’attributs d’éléments et effectue des recommandations basées sur le nombre de mots-clés que différents éléments ont en commun. Les recommandations basées sur la similarité de contenu ne nécessitent pas d’anciennes données pour fournir des résultats solides.

L’utilisation de la similarité de contenu pour générer des recommandations est particulièrement efficace pour les nouveaux éléments, qui ne sont pas susceptibles d’apparaître dans des recommandations en utilisant la logique *Les personnes ayant consulté ceci ont consulté cela* et une autre logique basée sur le comportement passé. Vous pouvez également utiliser la similarité de contenu pour générer des recommandations utiles pour les nouveaux visiteurs, qui n’ont pas d’achats antérieurs ni d’autres données historiques.

Lorsque vous sélectionnez **[!UICONTROL Basé sur un article]**/ **[!UICONTROL Média avec attributs similaires]**, vous avez la possibilité de créer des règles pour augmenter ou diminuer l&#39;importance des attributs d&#39;élément spécifiques dans la détermination des recommandations. Pour des éléments tels que des livres, vous pouvez augmenter l’importance d’attributs tels que le *genre*, l’*auteur*, la *série* et ainsi de suite, pour recommander des livres similaires.

![](assets/ContentSimilarity.png)

Étant donné que la similarité de contenu utilise des mots-clés pour comparer des éléments, certains attributs, tels que *message* ou *description*, peuvent parasiter la comparaison. Vous pouvez créer des règles pour ignorer ces attributs.

Par défaut, tous les attributs sont définis sur *De base*. À moins de vouloir modifier ce paramètre, vous ne devez pas créer de règle.

>[!NOTE]
>
>L&#39;algorithme de similarité de contenu peut utiliser un échantillonnage aléatoire pour calculer la similarité entre les éléments. En conséquence, les cotes de similarité entre les éléments peuvent varier d’un exécution d’algorithme à l’autre.

## Règles d’inclusion {#inclusion}

Plusieurs options vous aident à préciser les éléments qui s’affichent dans vos recommandations. Vous pouvez utiliser des règles d’inclusion lors de la création de critères ou de promotions.

![Règles d’inclusion](/help/c-recommendations/c-algorithms/assets/inclusion-rules.png)

Les règles d’inclusion sont facultatives. Cependant, le fait de définir ces détails vous permet de mieux contrôler les éléments qui apparaissent dans vos recommandations. Chaque détail configuré précise les critères d’affichage.

Vous pouvez, par exemple, choisir d’afficher uniquement les chaussures pour femmes dont le stock est supérieur à 50 et le prix compris entre 25 € et 45 €. Vous pouvez également pondérer chaque attribut, de telle sorte que la probabilité d’affichage soit plus élevée pour les éléments qui présentent plus d’intérêt pour vos activités.

Par exemple, vous pouvez choisir d’afficher les offres d’emploi pour les visiteurs qui visitent votre site uniquement à partir de certaines villes et qui possèdent les diplômes universitaires requis.

Les options de règle d’inclusion varient selon le secteur industriel vertical. Par défaut, les règles d’inclusion sont appliquées aux recommandations de sauvegarde.

>[!IMPORTANT]
>
>Veuillez utiliser les règles d’inclusion avec prudence. Elles se révèlent utiles si, par exemple, des règles en vigueur dans votre entreprise interdisent la recommandation d’une marque pendant la consultation d’une autre marque. L’utilisation de cette fonctionnalité a toutefois un coût. Si vous empêchez l’affichage de certains éléments alors qu’ils devraient normalement être affichés selon les critères d’activité, l’effet élévateur risque d’être amoindri.

Les règles d’inclusion sont jointes par l’opérateur ET. Toutes les règles doivent être respectées pour inclure un élément dans une recommandation.

Pour créer une règle d’inclusion simple, comme mentionné précédemment, afin d’afficher seulement les chaussures pour femmes dont le stock est supérieur à 50 et le prix compris entre 25 et 45 €, procédez comme suit :

1. Définissez une gamme de prix pour les produits que vous souhaitez recommander.
1. Définissez la valeur de stock minimale pour les produits que vous souhaitez recommander.
1. Configurez la recommandation de manière à afficher uniquement les éléments qui répondent à certains critères.

   ![](assets/Recs_InclusionRules.png)

   Vous pouvez indiquer que les éléments sont inclus uniquement lorsque l’un des attributs de la liste répond (ou ne répond pas) à l’une ou plusieurs des conditions spécifiées.

   Les évaluateurs disponibles dépendent de la valeur que vous sélectionnez dans la première liste déroulante. Vous pouvez inclure plusieurs éléments. Ces éléments sont évalués par l’opérateur OU.

   Plusieurs règles sont associées à l’aide de l’opérateur ET.

   >[!NOTE]
   >
   >Cette option limite les éléments affichés dans la recommandation. Elle n’affecte pas les pages sur lesquelles la recommandation est affichée. Pour limiter l’emplacement d’affichage de la recommandation, sélectionnez les pages dans le compositeur d’expérience.

Pour plus d’informations, voir [Utilisation des règles d’inclusion dynamiques et statiques](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

## Pondération d’attribut {#weighting}

Vous pouvez ajouter plusieurs règles pour &quot;décaler&quot; l’algorithme en fonction d’informations ou de métadonnées importantes concernant le catalogue de contenu afin que certains éléments soient plus susceptibles d’être affichés.

Par exemple, vous pouvez appliquer une plus forte pondération sur les articles en soldes pour qu’ils apparaissent plus souvent dans les recommandations. Les articles non soldés ne sont pas complètement exclus, mais ils apparaîtront moins souvent. Plusieurs attributs pondérés peuvent être appliqués au même algorithme et les attributs pondérés peuvent être testés dans un trafic partagé dans la recommandation.

1. Sélectionnez une valeur.

   La valeur détermine le type d’élément le plus susceptible de s’afficher, selon l’un des critères disponibles.

1. Sélectionnez un évaluateur.

1. Saisissez le mot clé pour compléter les attributs de règle.

   Par exemple, la règle complète peut être &quot;Catégorie contient des chaussures de sous-chaîne&quot;.

   ![](assets/Recs_AttributeWeighting.png)

1. Sélectionnez le poids à assigner à la règle.

   Les options sont comprises entre 0 et 100, avec des incréments de 25.

1. Ajoutez d’autres règles si nécessaire.

Lorsque vous avez terminé, cliquez sur **[!UICONTROL Enregistrer]**.

Si vous créez une activité de [!UICONTROL Recommandations] ou que vous en modifiez une, la case **[!UICONTROL Enregistrer les critères pour plus tard]** est cochée par défaut. Si vous ne souhaitez pas utiliser les critères dans d’autres activités, décochez la case avant de procéder à l’enregistrement.

## Vidéo de formation : Création de critères dans Recommendations (12:33) ![Pastille du tutoriel](/help/assets/tutorial.png)

Cette vidéo traite des sujets suivants :

* Création de critères
* Création d’une séquence de critères
* Téléchargement de critères personnalisés

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
