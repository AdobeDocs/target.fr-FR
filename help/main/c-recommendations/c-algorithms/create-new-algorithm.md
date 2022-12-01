---
keywords: critères;algorithme;secteur industriel vertical;type de page;clé de recommandation;logique de recommandation;logique;plage de données;intervalle de recherche en amont;source de données de comportement;conception partielle;recommandations de sauvegarde;règles d’inclusion;pondération d’attribut;catégorie actuelle;attribut personnalisé;dernier article acheté;dernier article consulté;article le plus consulté;élément le plus consulté;catégorie préférée;popularité;article récemment consulté;dernier article le plus consulté;favori
description: Découvrez comment créer des critères qui contrôlent le contenu de vos activités Adobe Recommendations pour afficher les recommandations les plus appropriées à votre activité.
title: Comment créer des critères dans Recommendations ?
feature: Recommendations
exl-id: 3f4f59b2-6637-4c33-bf17-bff11bef7173
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '2843'
ht-degree: 52%

---

# ![PREMIUM](/help/main/assets/premium.png) Création de critères

Critères dans [!UICONTROL Adobe Target] [!UICONTROL Recommendations] contrôler le contenu de votre [!UICONTROL Recommendations] activités. Créez des critères pour afficher les recommandations qui sont les plus appropriées à votre activité. Ces critères utilisent les actions du visiteur pour déterminer le contenu ou les produits à afficher.

Les sections suivantes expliquent comment créer un nouveau critère.

## Accès à l’écran Créer des critères

Il existe plusieurs méthodes pour accéder à l’écran [!UICONTROL Créer des critères]. Certaines options de l’écran varient en fonction de l’accès à ce dernier.

* Sur le **[!UICONTROL Recommendations]** > **[!UICONTROL Critères]** écran de bibliothèque, cliquez sur **[!UICONTROL Création de critères]** > **[!UICONTROL Création de critères]**. Les critères que vous créez à cet emplacement deviennent automatiquement disponibles pour toutes les activités [!DNL Recommendations].
* Lorsque vous créez une [!DNL Recommendations] à l’aide de la fonction [!UICONTROL Compositeur d’expérience visuelle] (VEC), vous êtes immédiatement dirigé vers le [!UICONTROL Sélectionner des critères] une fois que vous avez sélectionné un élément sur votre page, cliquez sur [!UICONTROL Remplacer par Recommendations], [!UICONTROL Insérer Recommendations avant]ou [!UICONTROL Insérer Recommendations après]. Vous pouvez ensuite sélectionner un critère disponible ou cliquer sur **[!UICONTROL Création de critères]**. Si vous créez un nouveau critère, vous avez la possibilité d’enregistrer le critère pour l’utiliser avec d’autres [!DNL Recommendations] activités. Pour plus d’informations, voir [Création d’une activité Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* Lorsque vous modifiez une [!DNL Recommendations] activité, cliquez sur la zone [!UICONTROL Emplacement des recommandations] sur votre page, puis sélectionnez **[!UICONTROL Changer les critères]**. Sur le [!UICONTROL Sélectionner des critères] écran, cliquez sur **[!UICONTROL Création de critères]**. Vous avez la possibilité d’enregistrer les nouveaux critères afin de les utiliser avec d’autres activités [!DNL Recommendations].

Les étapes suivantes supposent que vous accédez au [!UICONTROL Création de critères] écran en utilisant la première méthode : la valeur **[!UICONTROL Recommendations]** > **[!UICONTROL Critères]** écran de la bibliothèque.

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Critères]**.

1. Cliquez sur **[!UICONTROL Création de critères]** > **[!UICONTROL Création de critères]**.

   ![Créer de nouveaux critères](assets/CreateNewCriteria_full-new.png)

1. Configurez les informations dans les sections suivantes.

## [!UICONTROL Informations fondamentales] {#info}

1. Saisissez un **[!UICONTROL Nom de critère]**.

   C’est le nom « interne » utilisé pour décrire ce critère. Par exemple, vous voulez peut-être appeler votre critère « Produits générant la marge la plus élevée », mais vous ne voulez pas que ce titre soit affiché publiquement. Reportez-vous à la prochaine étape pour configurer le titre destiné au public.

   ![Section Informations de base](assets/basic-information.png)

1. Saisissez un **[!UICONTROL Titre d’affichage]** destiné à l’audience qui apparaîtra sur la page pour n’importe quelle recommandation qui utilise ce critère.

   Vous pouvez par exemple souhaiter afficher « Les personnes qui ont consulté cet article ont aussi consulté celui-ci » ou « Produits similaires » lorsque vous utilisez ce critère pour afficher des recommandations.

1. Saisissez une courte **[!UICONTROL Description]** du critère.

   La description doit vous aider à identifier le critère et peut inclure des informations sur l’objet du critère.

1. Sélectionnez un secteur industriel vertical en fonction des objectifs de votre activité de recommandations.

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

1. Sélectionnez une **[!UICONTROL Type d’algorithme]** et **[!UICONTROL Algorithme]**:

   ![Section Algorithme recommandé](assets/recommended-algorithm.png)

   | Type d’algorithme | Quand utiliser | Algorithmes disponibles |
   | --- | --- | --- |
   | [!UICONTROL Basé sur le panier] | Effectuez des recommandations en fonction du contenu du panier de l’utilisateur. | <ul><li>Les personnes qui les ont consultés ont consulté ceux-ci</li><li>Les personnes qui les ont consultés ont acheté ces</li><li>Les personnes qui ont acheté ceux-ci ont acheté ceux-là</li></ul> |
   | [!UICONTROL Basé sur la popularité] | Effectuez des recommandations en fonction de la popularité globale d’un élément sur votre site ou de la popularité des éléments au sein de la catégorie, de la marque, du genre, préférée ou la plus consultée d’un utilisateur, etc. | <ul><li>Les plus consultés sur le site</li><li>Les plus consultés par catégorie</li><li>Attribut d’élément le plus consulté</li><li>Meilleurs vendeurs sur le site</li><li>Meilleurs vendeurs par catégorie</li><li>Meilleurs vendeurs par attribut d’article</li><li>Mesure Début par Analytics</li></ul> |
   | [!UICONTROL Basé sur des éléments] | Effectuez des recommandations sur la base de la recherche d’éléments similaires à un élément que l’utilisateur consulte actuellement ou a récemment consulté. | <ul><li>Les personnes ayant consulté ceci ont consulté cela</li><li>Les personnes ayant consulté ceci ont acheté cela</li><li>Les personnes ayant acheté ceci ont acheté cela</li><li>Éléments avec des attributs similaires</li></ul> |
   | [!UICONTROL Basé sur les utilisateurs] | Effectuez des recommandations en fonction du comportement de l’utilisateur. | <ul><li>Éléments récemment consultés</li><li>Recommandé pour vous</li></ul> |
   | [!UICONTROL Critères personnalisés] | Faites des recommandations en fonction d’un fichier personnalisé que vous chargez. | <ul><li>Algorithme personnalisé</li></ul> |

   >[!NOTE]
   >
   >Si vous sélectionnez **[!UICONTROL Éléments]**/ **[!UICONTROL Média avec des attributs similaires]**, vous aurez la possibilité de définir [règles de similarité de contenu](#similarity).

1. Si nécessaire, sélectionnez une **Attribut d’élément** et **Attribut de profil à faire correspondre**, un **Clé de recommandation**, **Clé de filtrage**, et/ou **Mesure Analytics** pour configurer l’algorithme.

Les options de configuration d’algorithme restantes varient en fonction de l’algorithme sélectionné. Pour terminer la configuration de l’algorithme, sélectionnez une [!UICONTROL Clé de recommandation], [!UICONTROL Clé de filtrage], [!UICONTROL Base des cooccurrences], [!UICONTROL Mesure Analytics], et/ou [!UICONTROL Attribut d’élément] et [!UICONTROL Attribut de profil à faire correspondre].

Pour plus d’informations sur le choix d’un [!UICONTROL Clé de recommandation], voir [Baser la recommandation sur une clé de recommandation](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

## [!UICONTROL Source de données] {#data-source}

1. Sélectionnez la **[!UICONTROL Source de données comportementales]**: [!UICONTROL Adobe Target] ou [!UICONTROL Analytics].

   >[!NOTE]
   >
   >Le [!UICONTROL Source de données comportementales] s’affiche uniquement si votre mise en oeuvre utilise [Analytics pour Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T).

   ![Section Source de données comportementales](assets/data-source.png)

   Si vous choisissez [!UICONTROL Analytics], sélectionnez la suite de rapports souhaitée.

   Si le critère utilise [!DNL Adobe Analytics] en tant que source de données comportementales, une fois créée, la disponibilité des critères dépend de l’utilisation ou non de la suite de rapports et de l’intervalle de recherche en amont sélectionnés pour tout autre critère, comme expliqué ci-dessous :

   * **Configuration unique d’une suite de rapports** : la première fois qu’une suite de rapports est utilisée avec une fenêtre de recherche de plage de données spécifique, [!DNL Target Recommendations] peut prendre de deux à sept jours pour télécharger complètement les données comportementales de la suite de rapports sélectionnée depuis [!DNL Analytics]. Cette période dépend de la variable [!DNL Analytics] charge du système.
   * **Critères nouveaux ou modifiés à l’aide d’une suite de rapports déjà disponible** : lors de la création d’un critère ou de la modification d’un critère existant, si la suite de rapports sélectionnée a déjà été utilisée avec [!DNL Target Recommendations], avec une plage de données inférieure ou égale à celle sélectionnée, les données sont immédiatement disponibles et aucune configuration unique n’est requise. Dans ce cas ou si les paramètres d’un algorithme sont modifiés sans changer la suite de rapports ou la plage de données sélectionnée, l’algorithme s’exécute ou se réexécute dans les 12 heures.
   * **Exécutions d’algorithme en cours** : les données sont transmises quotidiennement d’[!DNL Analytics] à [!DNL Target Recommendations]. Par exemple, pour la recommandation [!UICONTROL Affinité consultée], lorsqu’un utilisateur consulte un produit, un appel de suivi de consultation de produit est transmis à [!DNL Analytics] pratiquement en temps réel. Les données [!DNL Analytics] sont envoyées à [!DNL Target] tôt le lendemain matin et [!DNL Target] exécute l’algorithme en moins de 12 heures.

   Pour plus d’informations, voir [Utilisation d’Adobe Analytics avec Target Recommendations](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md).

1. Définissez la variable **[!UICONTROL Intervalle de recherche en amont]** pour déterminer la période des données historiques de comportement des utilisateurs disponibles à utiliser lors de la détermination des recommandations à afficher. Cette option est disponible pour tous les algorithmes, à l’exception des éléments avec des attributs similaires et des algorithmes personnalisés.

   ![Curseur de fenêtre de recherche en amont](assets/data-range.png)

   Si votre site reçoit un volume de trafic important et que les comportements changent fréquemment, sélectionnez une fenêtre de données plus courte. Une fenêtre plus courte permet [!DNL Recommendations] d’être plus réactif aux changements du marché et de votre entreprise. Par exemple, une fenêtre plus courte signifie que [!DNL Recommendations] détectera les changements de comportement des visiteurs lorsque ces derniers commencent des achats saisonniers, tels que les achats de la rentrée ou de la période des fêtes, et recommanderont les articles appropriés à ces saisons.

   Si vous n’avez pas beaucoup de données ou que le comportement des visiteurs ne change pas fréquemment, vous pouvez sélectionner une fenêtre plus longue. Cependant, pour de nombreux sites, une fenêtre plus courte donne des recommandations de meilleure qualité.

   Les périodes de données disponibles sont :

   | Option Intervalle de recherche en amont | Fréquence mise à jour (affichée au survol) | Algorithmes pris en charge |
   | --- | --- | --- |
   | Six heures | L’algorithme s’exécute toutes les 3 à 6 heures | [!UICONTROL Basé sur la popularité] algorithmes lorsque la [!UICONTROL Source de données comportementales] is [!DNL Adobe Target] |
   | Un jour | L’algorithme s’exécute toutes les 12 à 24 heures | [!UICONTROL Basé sur la popularité] algorithmes |
   | Deux jours | L’algorithme s’exécute toutes les 12 à 24 heures | <ul><li>[!UICONTROL Basé sur la popularité] algorithmes</li><li>[!UICONTROL Basé sur des éléments] algorithmes</li><li>[!UICONTROL Basé sur les utilisateurs] algorithmes</li><li>[!UICONTROL Basé sur le panier] algorithmes</li></ul> |
   | Une semaine | L’algorithme s’exécute toutes les 24 à 48 heures | <ul><li>[!UICONTROL Basé sur la popularité] algorithmes</li><li>[!UICONTROL Basé sur des éléments] algorithmes</li><li>[!UICONTROL Basé sur les utilisateurs] algorithmes</li><li>[!UICONTROL Basé sur le panier] algorithmes</li></ul> |
   | Deux semaines | L’algorithme s’exécute toutes les 24 à 48 heures | <ul><li>[!UICONTROL Basé sur la popularité] algorithmes</li><li>[!UICONTROL Basé sur des éléments] algorithmes</li><li>Tous [!UICONTROL Basé sur les utilisateurs] algorithmes</li><li>[!UICONTROL Basé sur le panier] algorithmes</li></ul> |
   | Un mois (30 jours) | L’algorithme s’exécute toutes les 24 à 48 heures | <ul><li>[!UICONTROL Basé sur la popularité] algorithmes</li><li>[!UICONTROL Basé sur des éléments] algorithmes</li><li>[!UICONTROL Basé sur les utilisateurs] algorithmes</li><li>[!UICONTROL Basé sur le panier] algorithmes</li></ul> |
   | Deux mois (61 jours) | L’algorithme s’exécute toutes les 24 à 48 heures | <ul><li>[!UICONTROL Basé sur la popularité] algorithmes</li><li>[!UICONTROL Basé sur des éléments] algorithmes</li><li>[!UICONTROL Basé sur les utilisateurs] algorithmes</li><li>[!UICONTROL Basé sur le panier] algorithmes</li></ul> |

## [!UICONTROL Contenu de sauvegarde] {#content}

[!UICONTROL Contenu de sauvegarde] les règles déterminent ce qui se passe si le nombre d’articles recommandés ne remplissent pas votre [conception des recommandations](/help/main/c-recommendations/c-design-overview/design-overview.md). Il est possible pour [!DNL Recommendations] critères pour renvoyer moins de recommandations que ce que votre conception exige. Par exemple, si votre conception comporte des emplacements pour quatre éléments, mais que vos critères entraînent seulement la recommandation de deux éléments, vous pouvez laisser les emplacements restants vides, utiliser les recommandations de sauvegarde pour remplir les emplacements supplémentaires ou choisir d’afficher aucune recommandation.

![Section Contenu](assets/content.png)

1. (Facultatif) Faites glisser le **[!UICONTROL Rendu de conception partiel]** basculez sur la position &quot;activé&quot;.

   Le plus grand nombre d’emplacements possible sera rempli, mais le modèle de conception peut inclure un espace vide pour les emplacements restants. Si cette option est désactivée et qu’il n’y a pas assez de contenu pour remplir tous les emplacements disponibles, les recommandations ne sont pas diffusées et le contenu par défaut s’affiche à la place.

   Activez cette option si vous souhaitez que les recommandations soient servies avec des emplacements vides. Utilisez les recommandations de sauvegarde si vous souhaitez que les emplacements de recommandations soient remplis avec du contenu en fonction de vos critères, avec des emplacements vides remplis avec du contenu similaire ou populaire provenant de votre site, comme expliqué à l’étape suivante.

1. (Facultatif) Faites glisser le **[!UICONTROL Afficher le contenu de sauvegarde]** basculez sur la position &quot;activé&quot;.

   Remplissez les créneaux vides restants dans la conception avec une sélection aléatoire des produits les plus consultés sur l’ensemble de votre site.

   L’utilisation de recommandations de sauvegarde permet de s’assurer que votre conception de recommandations remplit tous les emplacements disponibles. Supposons que vous ayez une conception 4 x 1, comme illustré ci-dessous :

   ![Conception 4 x 1](/help/main/c-recommendations/c-design-overview/assets/velocity_example.png)

   Supposons que vos critères entraînent la recommandation de deux éléments seulement. Si vous activez la variable [!UICONTROL Rendu de conception partiel] , les deux premiers emplacements sont remplis, mais les deux autres restent vides. Toutefois, si vous activez la variable [!UICONTROL Afficher Recommendations de sauvegarde] , les deux premiers emplacements sont remplis en fonction des critères que vous avez spécifiés et les deux autres sont remplis en fonction de vos recommandations de sauvegarde.

   Le tableau suivant montre le résultat que vous constaterez lors de l’utilisation de la variable [!UICONTROL Rendu de conception partiel] et [!UICONTROL Contenu de sauvegarde] options :

   | Rendu de conception partiel | Contenu de sauvegarde | Résultats |
   |--- |--- |--- |
   | Désactivé | Désactivé | Si un nombre inférieur de recommandations est renvoyé par rapport à celui attendu par la conception, cette dernière est remplacée par le contenu par défaut et aucune recommandation n’est affichée. |
   | Activé | Désactivé | La conception est rendue, mais elle peut inclure des espaces vides si un nombre inférieur de recommandations par rapport à celui attendu est renvoyé. |
   | Activé | Activé | Les recommandations de sauvegarde remplissent les emplacements de la conception, en affichant entièrement celle-ci.<br>Si l’application des règles d’inclusion aux recommandations de sauvegarde limite le nombre de recommandations de sauvegarde incluses de sorte que la conception ne puisse pas être remplie, cette dernière est partiellement affichée.<br>Si le critère ne renvoie aucune recommandation et si les règles d’inclusion limitent les recommandations de sauvegarde à zéro, la conception est remplacée par le contenu par défaut. |
   | Désactivé | Activé | Les recommandations de sauvegarde remplissent les emplacements de la conception, en affichant entièrement celle-ci.<br>Si l’application des règles d’inclusion aux recommandations de sauvegarde limite le nombre de recommandations de sauvegarde incluses de sorte que la conception ne puisse pas être remplie, cette dernière est replacée par le contenu par défaut et aucune recommandation n’est affichée. |

   Pour plus d’informations, voir [Utilisation d’une recommandation de sauvegarde](/help/main/c-recommendations/c-algorithms/backup-recs.md).

1. (Conditionnel) Si vous avez sélectionné **[!UICONTROL Afficher le contenu de sauvegarde]** à l’étape précédente, vous pouvez activer **[!UICONTROL Application des règles d’inclusion aux recommandations de sauvegarde]**.

   Les règles d’inclusion déterminent les éléments qui sont inclus dans vos recommandations. Les options disponibles dépendent du secteur industriel vertical.

   Pour plus d’informations, voir [Spécification de règles d’inclusion](#inclusion) ci-dessous.

## Similarité de contenu {#similarity}

Utilisez les règles de [!UICONTROL similarité de contenu] pour effectuer des recommandations en fonction des attributs d’élément ou de média.

>[!NOTE]
>
>Si vous avez sélectionné **[!UICONTROL Basé sur des éléments]**/ **[!UICONTROL Média avec des attributs similaires]** en tant que Type d’algorithme et Algorithme, vous avez la possibilité de définir des règles de similarité de contenu.

La similarité de contenu compare des mots-clés d’attributs d’éléments et effectue des recommandations basées sur le nombre de mots-clés que différents éléments ont en commun. Les recommandations basées sur la similarité de contenu ne nécessitent pas d’anciennes données pour fournir des résultats solides.

L’utilisation de la similarité de contenu pour générer des recommandations est particulièrement efficace pour les nouveaux éléments, qui ne sont pas susceptibles d’apparaître dans des recommandations en utilisant la logique *Les personnes ayant consulté ceci ont consulté cela* et une autre logique basée sur le comportement passé. Vous pouvez également utiliser la similarité de contenu pour générer des recommandations utiles pour les nouveaux visiteurs, qui n’ont pas d’achats antérieurs ni d’autres données historiques.

Lorsque vous sélectionnez **[!UICONTROL Basé sur des éléments]**/ **[!UICONTROL Média avec des attributs similaires]**, vous avez la possibilité de créer des règles afin d’augmenter ou de diminuer l’importance des attributs d’élément spécifiques pour déterminer les recommandations. Pour des éléments tels que des livres, vous pouvez augmenter l’importance d’attributs tels que le *genre*, l’*auteur*, la *série* et ainsi de suite, pour recommander des livres similaires.

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

1. (Conditionnel) Glissez le **[!UICONTROL Autoriser les articles récemment achetés à être recommandés ?]** basculez sur la position &quot;activé&quot;.

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

Par exemple, vous pouvez appliquer une plus forte pondération sur les articles en soldes pour qu’ils apparaissent plus souvent dans les recommandations. Les articles non soldés ne sont pas complètement exclus, mais ils apparaîtront moins souvent. Plusieurs attributs pondérés peuvent être appliqués au même algorithme et les attributs pondérés peuvent être testés dans un trafic partagé dans la recommandation.

1. Sélectionnez une valeur.

   La valeur détermine le type d’élément le plus susceptible de s’afficher, selon l’un des critères disponibles.

1. Sélectionnez un évaluateur.

1. Saisissez le mot clé pour compléter les attributs de règle.

   Par exemple, la règle complète peut être &quot;La catégorie contient des sous-chaînes de chaussures&quot;.

   ![Image Recs_AttributeWeighting](assets/Recs_AttributeWeighting.png)

1. Sélectionnez le poids à assigner à la règle.

   Les options sont comprises entre 0 et 100, avec des incréments de 25.

1. Ajoutez d’autres règles si nécessaire.

Lorsque vous avez terminé, cliquez sur **[!UICONTROL Enregistrer]**.

Si vous créez une activité de [!UICONTROL Recommandations] ou que vous en modifiez une, la case **[!UICONTROL Enregistrer les critères pour plus tard]** est cochée par défaut. Si vous ne souhaitez pas utiliser les critères dans d’autres activités, décochez la case avant de procéder à l’enregistrement.

## Vidéo de formation : Création de critères dans Recommendations (12:33) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo traite des sujets suivants :

* Création de critères
* Création d’une séquence de critères
* Téléchargement de critères personnalisés

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
