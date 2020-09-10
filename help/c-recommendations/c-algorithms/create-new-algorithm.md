---
keywords: criteria;algorithm;industry vertical;page type;recommendation key;recommendation logic;logic;data range;behavior data source;partial design;backup recommendations;inclusion rules;attribute weighting;current category;current category;custom attribute;last purchased item;last viewed item;most viewed item;most viewed item;favorite category;popularity;recently viewed item;last purchased;last viewed;most viewed;favorite;recently viewed
description: Les critères contrôlent le contenu de vos activités Adobe Recommendations. Créez des critères pour afficher les recommandations qui sont les plus appropriées à votre activité.
title: Création de critères
feature: criteria
mini-toc-levels: 2
uuid: 603d4b02-cdb6-40aa-9654-0086c23b0c8e
translation-type: tm+mt
source-git-commit: 31ee320c3a5d81a4d859881666ab098253f9047e
workflow-type: tm+mt
source-wordcount: '3609'
ht-degree: 85%

---


# ![PREMIUM](/help/assets/premium.png) Création de critères{#create-criteria}

Les critères contrôlent le contenu de vos activités de [!UICONTROL Recommandations]. Créez des critères pour afficher les recommandations qui sont les plus appropriées à votre activité.

## Créer des critères

Les sections suivantes expliquent comment créer un nouveau critère.

### Accès à l’écran Créer des critères

Il existe plusieurs méthodes pour accéder à l’écran [!UICONTROL Créer des critères]. Certaines options de l’écran varient en fonction de l’accès à ce dernier.

* On the **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** library screen, click **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**. Les critères que vous créez à cet emplacement deviennent automatiquement disponibles pour toutes les activités [!DNL Recommendations].
* When you are creating a [!DNL Recommendations] activity, click **[!UICONTROL Create Criteria]** on the [!UICONTROL Select Criteria] screen. Vous avez la possibilité d’enregistrer les nouveaux critères afin de les utiliser avec d’autres activités [!DNL Recommendations].
* Lorsque vous modifiez une [!DNL Recommendations] activité, cliquez sur la zone [!UICONTROL Emplacement des recommandations] sur votre page, puis sélectionnez **[!UICONTROL Changer les critères]**. On the [!UICONTROL Select Criteria] screen, click **[!UICONTROL Create Criteria]**. Vous avez la possibilité d’enregistrer les nouveaux critères afin de les utiliser avec d’autres activités [!DNL Recommendations].

Les étapes suivantes supposent que vous accédez à l’écran [!UICONTROL Créer de nouveaux critères] en utilisant la première méthode : l’écran **[!UICONTROL Recommendations]** > **[!UICONTROL Critères]** de bibliothèque.

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Critères]**.

1. Cliquez sur **[!UICONTROL Créer des critères]** > **[!UICONTROL Créer des critères]**.

   ![Créer de nouveaux critères](/help/c-recommendations/c-algorithms/assets/CreateNewCriteria_full-new.png)

### Renseignez la section Informations de base. {#info}

1. Saisissez un **[!UICONTROL Nom de critère]**.

   C’est le nom « interne » utilisé pour décrire ce critère. Par exemple, vous voulez peut-être appeler votre critère « Produits générant la marge la plus élevée », mais vous ne voulez pas que ce titre soit affiché publiquement. Reportez-vous à la prochaine étape pour configurer le titre destiné au public.

   ![Section Informations de base](/help/c-recommendations/c-algorithms/assets/basic-information.png)

1. Saisissez un **[!UICONTROL Titre d’affichage]** destiné à l’audience qui apparaîtra sur la page pour n’importe quelle recommandation qui utilise ce critère.

   Vous pouvez par exemple souhaiter afficher « Les personnes qui ont consulté cet article ont aussi consulté celui-ci » ou « Produits similaires » lorsque vous utilisez ce critère pour afficher des recommandations.

1. Saisissez une courte **[!UICONTROL Description]** du critère.

   La description doit vous aider à identifier les critères et peut inclure des informations sur l’objectif des critères.

1. Sélectionnez un **[!UICONTROL Secteur industriel vertical]** :

   * [!UICONTROL Vente au détail / commerce électronique]
   * [!UICONTROL Génération de piste / B2B / Services financiers]
   * [!UICONTROL Médias / Publication]

   Les autres options de critère sont modifiées en fonction du secteur industriel vertical que vous sélectionnez.

1. Sélectionnez un **[!UICONTROL Type de page]**.

   Vous pouvez sélectionner plusieurs types de page.

   Le secteur industriel vertical et les types de page sont utilisés pour classer les critères enregistrés, ce qui facilite la réutilisation des critères pour d’autres activités [!DNL Recommendations].

1. Sélectionnez une **[!UICONTROL Clé de recommandation]**.

   Pour plus d’informations sur la base des critères sur une clé, voir [Baser la recommandation sur une clé de recommandation](#task_2B0ED54AFBF64C56916B6E1F4DC0DC3B).

1. Sélectionnez la **[!UICONTROL Logique de recommandation]**.

   Pour plus d’informations sur les options de logique de recommandation, consultez les [Critères](../../c-recommendations/c-algorithms/algorithms.md).

   >[!NOTE]
   >
   >If you select **[!UICONTROL Items]**/ **[!UICONTROL Media with Similar Attributes]**, you will have the option to set [content similarity rules](#similarity).

### Définition des options de la source de données

1. Définissez la **[!UICONTROL plage de données]** afin de déterminer la période des données d’historique de comportement des utilisateurs disponibles, qui pourront être utilisées pour définir les recommandations à afficher.

   ![Curseur de plage de données](/help/c-recommendations/c-algorithms/assets/data-range.png)

   Si votre site reçoit un volume de trafic important et que les comportements changent fréquemment, sélectionnez une fenêtre de données plus courte. Une fenêtre plus courte permet [!DNL Recommendations] d’être plus réactif aux changements du marché et de votre entreprise. Par exemple, une fenêtre plus courte signifie que [!DNL Recommendations] détectera les changements de comportement des visiteurs lorsque ces derniers commencent des achats saisonniers, tels que les achats de la rentrée ou de la période des fêtes, et recommanderont les articles appropriés à ces saisons.

   Si vous n’avez pas beaucoup de données ou que le comportement des visiteurs ne change pas fréquemment, vous pouvez sélectionner une fenêtre plus longue. Néanmoins, pour de nombreux sites, une fenêtre plus courte permet d’obtenir de meilleures recommandations.

   Les périodes de données disponibles sont :

   * Deux jours
   * Une semaine
   * Deux semaines
   * Un mois
   * Deux mois

1. (Conditional) Select the desired **[!UICONTROL Behavioral Data Source]**: [!UICONTROL mboxes] or [!UICONTROL Analytics].

   >[!NOTE]
   >
   >La section Source [!UICONTROL de données] comportementale s’affiche uniquement si votre implémentation utilise [Analytics pour la Cible](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T).

   ![Section Source de données comportementale](/help/c-recommendations/c-algorithms/assets/behavioural-data-source.png)

   Si vous choisissez [!UICONTROL Analytics], sélectionnez la suite de rapports souhaitée.

   If the criteria uses [!DNL Adobe Analytics] as the behavioral data source, once created, the time for criteria availability depends on whether the selected report suite and lookback window has been used for any other criteria, as explained below:

   * **Configuration unique d’une suite de rapports** : la première fois qu’une suite de rapports est utilisée avec une fenêtre de recherche de plage de données spécifique, [!DNL Target Recommendations] peut prendre de deux à sept jours pour télécharger complètement les données comportementales de la suite de rapports sélectionnée depuis [!DNL Analytics]. This time frame is dependent on the [!DNL Analytics] system load.
   * **Critères nouveaux ou modifiés à l’aide d’une suite de rapports déjà disponible** : lors de la création d’un critère ou de la modification d’un critère existant, si la suite de rapports sélectionnée a déjà été utilisée avec [!DNL Target Recommendations], avec une plage de données inférieure ou égale à celle sélectionnée, les données sont immédiatement disponibles et aucune configuration unique n’est requise. Dans ce cas ou si les paramètres d’un algorithme sont modifiés sans changer la suite de rapports ou la plage de données sélectionnée, l’algorithme s’exécute ou se réexécute dans les 12 heures.
   * **Exécutions d’algorithme en cours** : les données sont transmises quotidiennement d’[!DNL Analytics] à [!DNL Target Recommendations]. Par exemple, pour la recommandation [!UICONTROL Affinité consultée], lorsqu’un utilisateur consulte un produit, un appel de suivi de consultation de produit est transmis à [!DNL Analytics] pratiquement en temps réel. Les données [!DNL Analytics] sont envoyées à [!DNL Target] tôt le lendemain matin et [!DNL Target] exécute l’algorithme en moins de 12 heures.

   Pour plus d’informations, voir [Utilisation d’Adobe Analytics avec Cible Recommendations](/help/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md).

### Définition des paramètres de contenu {#content}

Les règles de contenu déterminent ce qui se passe lorsque le nombre d’éléments recommandés ne remplissent pas votre conception. Il est possible que les critères de recommandation renvoient un nombre inférieur de recommandations par rapport à celui prévu par votre conception. Par exemple, si votre conception comporte cinq éléments, mais que vos critères ne recommandent que trois éléments, vous pouvez laisser l’espace restant vide ou utiliser des recommandations de sauvegarde pour remplir l’espace supplémentaire.

![Section Contenu](/help/c-recommendations/c-algorithms/assets/content.png)

1. (Facultatif) Faites glisser la bascule Rendu **[!UICONTROL de conception]** partiel vers la position &quot;Activé&quot;.

   Le plus grand nombre d’emplacements possible sera rempli, mais le modèle de conception peut inclure un espace vide pour les emplacements restants.

1. (Facultatif) Faites glisser la bascule **[!UICONTROL Afficher le Recommendations]** de sauvegarde vers la position &quot;Activé&quot;.

   Remplissez les emplacements vides restants de la conception avec une sélection aléatoire des produits les plus consultés sur l’ensemble du site.

   Pour plus d’informations, voir [Utilisation d’une recommandation](/help/c-recommendations/c-algorithms/backup-recs.md)de sauvegarde.

1. (Conditionnel) Si vous avez sélectionné **[!UICONTROL Afficher la Recommendations]** de sauvegarde à l’étape précédente, vous pouvez activer l’option **[!UICONTROL Appliquer les règles d’inclusion aux recommandations]** de sauvegarde.

   Les règles d’inclusion déterminent quels éléments sont inclus dans vos recommandations. Les options disponibles dépendent du secteur industriel vertical.

   For more details, see [Specify inclusion rules](#inclusion) below.

1. (Facultatif) Faites glisser l’option **[!UICONTROL Recommander les articles]** achetés précédemment vers la position &quot;Activé&quot;.

   Ce paramètre est basé sur `productPurchasedId`. Le comportement par défaut est de ne pas recommander des articles précédemment achetés. En général, vous ne souhaitez pas promouvoir des articles qu’un client a récemment achetés. Il est utile si vous vendez des articles que les gens n’achètent en général qu’une fois, comme des kayaks. Si vous vendez des articles que les gens reviennent acheter à plusieurs reprises, comme du shampoing ou d&#39;autres articles personnels, vous devez activer cette option.

La matrice suivante montre le résultat que vous observerez lors de l’utilisation des options de rendu [!UICONTROL de conception] partiel et de Recommendations [!UICONTROL de] sauvegarde :

| Rendu de conception partiel | Recommandations de sauvegarde | Résultats |
|--- |--- |--- |
| Désactivé | Désactivé | Si un nombre inférieur de recommandations est renvoyé par rapport à celui attendu par la conception, cette dernière est remplacée par le contenu par défaut et aucune recommandation n’est affichée. |
| Activé | Désactivé | La conception est rendue, mais elle peut inclure des espaces vides si un nombre inférieur de recommandations par rapport à celui attendu est renvoyé. |
| Activé | Activé | Les recommandations de sauvegarde remplissent les emplacements de la conception, en affichant entièrement celle-ci.<br>Si l’application des règles d’inclusion aux recommandations de sauvegarde limite le nombre de recommandations de sauvegarde incluses de sorte que la conception ne puisse pas être remplie, cette dernière est partiellement affichée.<br>Si le critère ne renvoie aucune recommandation et si les règles d’inclusion limitent les recommandations de sauvegarde à zéro, la conception est remplacée par le contenu par défaut. |
| Désactivé | Activé | Les recommandations de sauvegarde remplissent les emplacements de la conception, en affichant entièrement celle-ci.<br>Si l’application des règles d’inclusion aux recommandations de sauvegarde limite le nombre de recommandations de sauvegarde incluses de sorte que la conception ne puisse pas être remplie, cette dernière est replacée par le contenu par défaut et aucune recommandation n’est affichée. |

### Specify content similarity rules {#similarity}

Utilisez les règles de [!UICONTROL similarité de contenu] pour effectuer des recommandations en fonction des attributs d’élément ou de média.

>[!NOTE]
>
>If you selected **[!UICONTROL Items]**/ **[!UICONTROL Media with Similar Attributes]** as your [recommendation logic](#info), you will have the option to set content similarity rules.

La similarité de contenu compare des mots-clés d’attributs d’éléments et effectue des recommandations basées sur le nombre de mots-clés que différents éléments ont en commun. Les recommandations basées sur la similarité de contenu ne nécessitent pas d’anciennes données pour fournir des résultats solides.

L’utilisation de la similarité de contenu pour générer des recommandations est particulièrement efficace pour les nouveaux éléments, qui ne sont pas susceptibles d’apparaître dans des recommandations en utilisant la logique *Les personnes ayant consulté ceci ont consulté cela* et une autre logique basée sur le comportement passé. Vous pouvez également utiliser la similarité de contenu pour générer des recommandations utiles pour les nouveaux visiteurs, qui n’ont pas d’achats antérieurs ni d’autres données historiques.

Lorsque vous sélectionnez **[!UICONTROL Éléments]**/**[!UICONTROL Médias avec des attributs similaires]**, vous avez la possibilité de créer des règles pour augmenter ou diminuer l’importance des attributs d’éléments spécifiques pour déterminer les recommandations. Pour des éléments tels que des livres, vous pouvez augmenter l’importance d’attributs tels que le *genre*, l’*auteur*, la *série* et ainsi de suite, pour recommander des livres similaires.

![](assets/ContentSimilarity.png)

Étant donné que la similarité de contenu utilise des mots-clés pour comparer des éléments, certains attributs, tels que *message* ou *description*, peuvent parasiter la comparaison. Vous pouvez créer des règles pour ignorer ces attributs.

Par défaut, tous les attributs sont définis sur *De base*. À moins de vouloir modifier ce paramètre, vous ne devez pas créer de règle.

>[!NOTE]
>
>L’algorithme de similarité de contenu peut utiliser un échantillonnage aléatoire pour calculer la similarité entre les éléments. Par conséquent, les évaluations de similarité entre les éléments peuvent varier d’une exécution d’algorithme à l’autre.

### Spécification des règles d’inclusion {#inclusion}

![Règles d’inclusion](/help/c-recommendations/c-algorithms/assets/inclusion-rules.png)

Plusieurs options vous aident à préciser les éléments qui s’affichent dans vos recommandations. Vous pouvez utiliser des règles d’inclusion lors de la création de critères ou de promotions.

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

For more information, see [Use dynamic and static inclusion rules](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

### Spécifier la pondération d’attribut

Vous pouvez ajouter plusieurs règles pour &quot;pousser&quot; l’algorithme en fonction d’une description importante ou de métadonnées relatives au catalogue de contenu afin que certains éléments soient plus susceptibles d’être affichés.

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

## Baser la recommandation sur une clé de recommandation {#task_2B0ED54AFBF64C56916B6E1F4DC0DC3B}

Les recommandations fondées sur des clés exploitent le contexte comportemental des visiteurs pour afficher les résultats pertinents.

Il existe deux types de recommandations :

* **Popularité :** dresse la liste des éléments d’après les critères Les plus consultés, Les plus vendus et Mesure maximale. La clé est vide pour les critères de popularité.
* **Basé sur une clé :** inclut le reste des critères. Recommandations propose un large éventail de choix de types de clé. Les options vont de « élément actif » à « paramètres de profil » pour vous permettre de définir par voie programmatique la clé des valeurs à recommander. Vous pouvez tester plusieurs critères les uns par rapport aux autres en basant chaque critère sur une clé différente.

Chaque critère est défini dans son propre onglet. Le trafic est réparti uniformément entre vos différents tests de critères. En d’autres termes, si vous avez deux critères, le trafic est réparti uniformément entre les deux. Si vous avez deux critères et deux conceptions, le trafic est réparti uniformément entre les quatre combinaisons. Vous pouvez également spécifier le pourcentage des visiteurs du site qui visualisent le contenu par défaut, à des fins de comparaison. Dans ce cas, le pourcentage spécifié des visiteurs du site qui visualisent le contenu par défaut et les autres sont répartis entre vos combinaisons critère/conception.

1. Créez une recommandation ou sélectionnez une recommandation existante, puis cliquez sur **[!UICONTROL Modifier]**.
1. Pour changer de clé de recommandation, sélectionnez la nouvelle clé dans la liste déroulante [!UICONTROL Clé de recommandation] puis cliquez sur **[!UICONTROL Sauvegarder]**.

   Différentes logiques renvoient vers différentes clés de recommandation. Par conséquent, différentes recommandations renvoient à des emplacements sur différents types de page. Pour plus d’informations sur chaque clé, consultez les sections suivantes.

### Article actuel

La recommandation est déterminée par l’article que le visiteur consulte actuellement.

Les recommandations présentent d’autres articles susceptibles d’intéresser les visiteurs qui consultent l’article spécifié.

Lorsque cette option est sélectionnée, la valeur `entity.id` doit être transmise comme un paramètre à la mbox d’affichage.

#### Logique (critère)

* [!UICONTROL Articles avec des attributs similaires]
* [!UICONTROL Les personnes ayant consulté ceci ont consulté cela]
* [!UICONTROL Les personnes ayant consulté ceci ont acheté cela]
* [!UICONTROL Les personnes ayant acheté ceci ont acheté cela]
* [!UICONTROL Affinité du site]

#### Où l’utiliser sur votre site

Pages d’un seul article (pages de produit, par exemple).

Ne PAS l’utiliser sur les pages de résultats de recherche nulles.

### Catégorie en cours

La recommandation est déterminée par la catégorie de produits que le visiteur consulte actuellement.

Les recommandations présentent des articles dans la catégorie de produits spécifiée.

Lorsque cette option est sélectionnée, la valeur `entity.categoryId` doit être transmise comme paramètre à la mbox d’affichage.

#### Logique (critère)

* Meilleurs vendeurs
* Les plus consultés

#### Où l’utiliser sur votre site

Pages d’une seule catégorie.

Ne PAS l’utiliser sur les pages de résultats de recherche nulles.

### Attribut personnalisé {#custom}

La recommandation est déterminée par un article stocké dans un profil de visiteur, utilisant les attributs user.*x>* ou profile.attributs *x*.

Si cette option est sélectionnée, la valeur `entity.id` doit être présente dans l’attribut de profil.

#### Logique (critère)

* [!UICONTROL Les personnes ayant consulté ceci ont consulté cela]
* [!UICONTROL Les personnes ayant consulté ceci ont acheté cela]
* [!UICONTROL Les personnes ayant acheté ceci ont acheté cela]
* [!UICONTROL Comportement global]
* [!UICONTROL Les plus consultés]
* [!UICONTROL Meilleurs vendeurs]

Si la clé est un attribut de profil personnalisé et que le type d’algorithme est Le plus consulté ou Meilleurs vendeurs, une nouvelle liste déroulante intitulée « Grouper par valeur unique de » s’affiche et indique la liste des attributs d’entité connus (ID d’exception, catégorie, marge, valeur, inventaire et environnement). Ce champ est obligatoire.

#### Où l’utiliser sur votre site

Peut être utilisé sur n’importe quelle page.

#### Utilisation d’une clé de recommandations personnalisée

Vous pouvez axer les recommandations sur la valeur d’un attribut de profil personnalisé. Supposons, par exemple, que vous souhaitiez afficher les films recommandés en fonction de la séquence que le visiteur a ajoutée le plus récemment à sa file d’attente.

1. Sélectionnez votre attribut de profil personnalisé dans la liste déroulante **[!UICONTROL Clé de recommandation]** (par exemple, « Dernier affichage ajouté à la liste de surveillance »).
1. Sélectionnez ensuite la **[!UICONTROL logique de recommandation]** (par exemple « Personnes qui ont vu ceci, vu cela »).

   ![Boîte de dialogue Créer de nouveaux critères](/help/c-recommendations/c-algorithms/assets/create-new-criteria-1.png)

Si votre attribut de profil personnalisé ne correspond pas directement à un ID d’entité unique, il est nécessaire d’expliquer à [!DNL Recommendations] la manière dont vous souhaitez que la correspondance à une entité se produise. Supposons, par exemple, que vous souhaitiez afficher les principaux articles de la marque préférée d’un visiteur.

1. Sélectionnez votre attribut de profil personnalisé dans la liste déroulante **[!UICONTROL Clé de recommandation]** (par exemple, « Marque préférée »).

1. Sélectionnez ensuite la **[!UICONTROL logique de recommandation]** que vous souhaitez utiliser avec cette clé (par exemple, « Meilleurs vendeurs »).

   L’option [!UICONTROL Groupe par valeur unique de] s’affiche.

1. Sélectionnez l’attribut d’entité correspondant à la clé choisie. Dans ce cas, « Marque préférée » correspond à `entity.brand`.

   [!DNL Recommendations] génère désormais une liste des « Meilleurs vendeurs » pour chaque marque et montre au visiteur la liste des « Meilleurs vendeurs » en fonction de la valeur stockée dans l’attribut de profil Marque préférée du visiteur.

   ![Boîte de dialogue Créer de nouveaux critères 2](/help/c-recommendations/c-algorithms/assets/create-new-criteria-2.png)

### Dernier article acheté

La recommandation est déterminée par le dernier article acheté par chaque visiteur unique. Ces données sont capturées automatiquement. Aucune valeur ne doit donc être transmise sur la page.

#### Logique (critère)

* [!UICONTROL Articles avec des attributs similaires]
* [!UICONTROL Les personnes ayant consulté ceci ont consulté cela]
* [!UICONTROL Les personnes ayant consulté ceci ont acheté cela]
* [!UICONTROL Les personnes ayant acheté ceci ont acheté cela]
* [!UICONTROL Affinité du site]

#### Où l’utiliser sur votre site

Page d’accueil, page Mon compte, publicités hors site.

Ne PAS l’utiliser sur les pages de produit ou les pages liées aux achats.

### Dernier article consulté

La recommandation est déterminée par le dernier élément consulté par chaque visiteur unique. Ces données sont capturées automatiquement. Aucune valeur ne doit donc être transmise sur la page.

#### Logique (critère)

* [!UICONTROL Articles avec des attributs similaires]
* [!UICONTROL Les personnes ayant consulté ceci ont consulté cela]
* [!UICONTROL Les personnes ayant consulté ceci ont acheté cela]
* [!UICONTROL Les personnes ayant acheté ceci ont acheté cela]
* [!UICONTROL Affinité du site]

#### Où l’utiliser sur votre site

Page d’accueil, page Mon compte, publicités hors site.

Ne PAS l’utiliser sur les pages de produit ou les pages liées aux achats.

### Article le plus consulté

La recommandation est déterminée par l’élément le plus souvent consulté, à l’aide de la même méthode que celle de la catégorie préférée.

Cela est déterminé par le critère de récence/fréquence qui fonctionne comme suit :

* 10 points pour la première consultation de produit
* 5 points pour chaque consultation consécutive
* À la fin de la session, toutes les valeurs sont divisées par 2

Par exemple, l’affichage de surfboardA, puis de surfboardB dans une même session donne A : 10, B : 5. À la fin de la session, vous avez A : 5, B : 2,5. Si vous consultez les mêmes éléments au cours de la prochaine session, les valeurs deviennent A : 15 B : 7,5.

#### Logique (critère)

* [!UICONTROL Articles avec des attributs similaires]
* [!UICONTROL Les personnes ayant consulté ceci ont consulté cela]
* [!UICONTROL Les personnes ayant consulté ceci ont acheté cela]
* [!UICONTROL Les personnes ayant acheté ceci ont acheté cela]
* [!UICONTROL Affinité du site]

#### Où l’utiliser sur votre site

Pages générales, telles les pages d’accueil et les publicités hors site.

### Catégorie préférée

La recommandation est déterminée par la catégorie associée au plus haut niveau d’activité, à l’aide de la même méthode que celle utilisée pour « Article le plus consulté », sauf que le score porte sur les catégories et non sur les produits.

Cela est déterminé par le critère de récence/fréquence qui fonctionne comme suit :

* 10 points pour la première consultation de catégorie
* 5 points pour chaque consultation consécutive

Les catégories consultées pour la première fois reçoivent dix points. Les visites suivantes dans la même catégorie reçoivent cinq points. À chaque visite, les catégories non actuelles qui ont été consultées auparavant sont décrémentées de 1.

Par exemple, l’affichage de categorieA, puis de categorieB dans une même session donne A : 9, B : 10. Si vous affichez les mêmes éléments lors de la session suivante, les valeurs passent à A : 20, B : 9.

#### Logique (critère)

* [!UICONTROL Meilleurs vendeurs]
* [!UICONTROL Les plus consultés]

#### Où l’utiliser sur votre site

Pages générales, telles les pages d’accueil et les publicités hors site.

### Popularité

La recommandation est déterminée par la popularité des éléments de votre site. La popularité comprend les articles les plus vendus et les plus consultés selon les données de la mbox et, si vous utilisez Adobe Analytics, toutes les mesures disponibles dans le rapport sur les produits. Les articles sont classés en fonction de la logique de recommandation sélectionnée.

#### Logique (critère)

* [!UICONTROL Meilleurs vendeurs]
* [!UICONTROL Les plus consultés]
* Mesures de rapport de produit (si vous utilisez Adobe Analytics)

#### Où l’utiliser sur votre site

Pages générales, telles les pages d’accueil et les publicités hors site.

### Éléments récemment consultés {#recently-viewed}

Utilise l’historique du visiteur (sur plusieurs sessions) pour présenter les *x* derniers éléments consultés par le visiteur, en fonction du nombre d’emplacements dans la conception.

Le critère Éléments récemment consultés renvoie désormais des résultats spécifiques à un [environnement](/help/administrating-target/hosts.md) donné. Si deux sites appartiennent à différents environnements et qu’un visiteur bascule entre les deux sites, chaque site n’affiche que les éléments récemment consultés du site approprié. Si deux sites se trouvent dans le même environnement et qu’un visiteur bascule entre les deux sites, le visiteur voit les mêmes éléments récemment consultés pour les deux sites.

#### Où l’utiliser sur votre site

Pages générales, telles les pages d’accueil et les publicités hors site.

>[!NOTE]
>
>Les éléments récemment consultés respectent les paramètres globaux Exclusions et le paramètre Collection sélectionné pour l’activité. Si un élément est exclu par une exclusion globale ou ne figure pas dans la collection sélectionnée, il ne sera pas affiché. Par conséquent, lors de l’utilisation d’un critère Eléments récemment consultés, le paramètre « Toutes les collections » doit généralement être utilisé.

## Training video: Create criteria in Recommendations (12:33) ![Tutorial badge](/help/assets/tutorial.png)

Cette vidéo traite des sujets suivants :

* Création de critères
* Création d’une séquence de critères
* Téléchargement de critères personnalisés

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
