---
keywords: règles d’inclusion;critères d’inclusion;recommandations;créer des critères;promotion;promotions;filtrage dynamique;dynamique;valeurs vides;ignorer la règle de filtrage;filtre statique;filtrer par valeur;correspondance des attributs d’entité;correspondance des attributs de profil;correspondance de paramètres;filtrer par valeur;filtre statique
description: Découvrez comment créer des règles d’inclusion dans Adobe Target pour les critères et les promotions. Pour obtenir de meilleurs résultats, ajoutez des règles de filtrage plus dynamiques ou plus statiques.
title: Comment utiliser les règles d’inclusion dynamique et statique dans Recommendations ?
feature: Recommandations
mini-toc-levels: 3
exl-id: 49b20e75-ee55-4239-94a0-6d175e2d4811
translation-type: tm+mt
source-git-commit: 5fcc5776e69222e0a232bd92ddfd10cee748e577
workflow-type: tm+mt
source-wordcount: '1841'
ht-degree: 19%

---

# ![PREMIUM](/help/assets/premium.png) Utilisation de règles d’inclusion dynamiques et statiques

Informations sur la création de règles d’inclusion pour les critères et les promotions dans [!DNL Adobe Target] et l’ajout de règles de filtrage dynamique ou statique pour obtenir de meilleurs résultats pour vos recommandations.

Le processus de création et d’utilisation de règles d’inclusion pour les critères et les promotions est similaire, de même que les cas d’utilisation et les exemples. Les critères et les promotions ainsi que l&#39;utilisation des règles d&#39;inclusion sont traités dans cette section.

## Ajout de règles de filtrage à des critères {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

Lorsque vous [créez des critères](/help/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE), cliquez sur **[!UICONTROL Ajouter une règle de filtrage]** sous **[!UICONTROL Règles d’inclusion]**.

![](assets/inclusion_options_new.png)

Les options disponibles varient en fonction du secteur industriel vertical et de la clé de recommandation sélectionnés.

## Ajout de règles de filtrage à des promotions {#section_D59AFB62E2EE423086281CF5D18B1076}

Lors de la [création d’une promotion](/help/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14), sélectionnez **[!UICONTROL Promouvoir par attribut]**, puis cliquez sur **[!UICONTROL Ajouter une règle de filtrage]**.

![](assets/inclusion_options.png)

## Types de filtre {#section_0125F1ED10A84C0EB45325122460EBCD}

Les sections suivantes liste les types d’options de filtrage pour [!UICONTROL Filtrage dynamique] et [!UICONTROL Filtrer par valeur] pour les critères et les promotions :

### Filtrage dynamique

Les règles d’inclusion dynamique sont plus puissantes que les règles d’inclusion statique et elles produisent de meilleurs résultats et un meilleur engagement. Tenez compte des points suivants :

* Les règles d’inclusion dynamique fournissent des recommandations en faisant correspondre un attribut au paramètre de profil d’un utilisateur ou dans un appel de mbox.

   Par exemple, vous pouvez créer une recommandation &quot;Critères les plus populaires&quot;. Dans l’ensemble de recommandations renvoyées, vous pouvez filtrer toutes les recommandations (en temps réel) par rapport à un attribut transmis lorsque l’utilisateur accède à une page où les recommandations sont affichées.

* Utilisez des règles statiques pour limiter les éléments qui sont inclus dans la recommandation (au lieu d’utiliser des collections).

* Vous pouvez créer autant de règles d’inclusion dynamiques que nécessaire. Les règles d’inclusion sont jointes par l’opérateur ET. Toutes les règles doivent être respectées pour inclure un élément dans une recommandation.

Les options suivantes sont disponibles pour le filtrage dynamique :

| Option de filtrage dynamique | Détails |
| --- | --- |
| [Correspondance des attributs d’entité](/help/c-recommendations/c-algorithms/entity-attribute-matching.md) | Filtrez dynamiquement en comparant un groupe d’éléments de recommandations potentiels à un élément spécifique avec lequel les utilisateurs ont interagi.<br>Utilisez la  [!UICONTROL correspondance des attributs ] d’entité lorsque vous souhaitez afficher des recommandations susceptibles d’intéresser le visiteur, telles que la marque préférée du visiteur. |
| [Correspondance des attributs de profil](/help/c-recommendations/c-algorithms/profile-attribute-matching.md) | Filtrez dynamiquement en comparant des éléments (entités) à une valeur du profil de l’utilisateur.<br>Utilisez la  [!UICONTROL correspondance des attributs de ] Profil lorsque vous souhaitez afficher des recommandations qui correspondent à une valeur stockée dans le profil du visiteur, telle que la taille ou la marque préférée. |
| [Correspondance de paramètres](/help/c-recommendations/c-algorithms/parameter-matching.md) | Filtrez dynamiquement en comparant des éléments (entités) à une valeur dans la requête (API ou mbox).<br>Utilisez  [!UICONTROL la ] correspondance des paramètres pour recommander le contenu qui correspond aux paramètres de page ou aux paramètres du visiteur, tels que les dimensions du périphérique ou la géolocalisation. |

### Filtrer par valeur

L’option suivante est disponible pour le filtrage par valeur :

| Filtrage par valeur, option | Détails |
| --- | --- |
| [Filtre statique](/help/c-recommendations/c-algorithms/static-value.md) | Saisissez manuellement une ou plusieurs valeurs statiques à filtrer. |

## Opérateurs disponibles {#operators}

Les critères et les promotions dynamiques sont beaucoup plus puissants que les critères statiques et les promotions et produisent de meilleurs résultats et un meilleur engagement.

Les exemples suivants fournissent des idées générales sur la manière d’utiliser les promotions et exclusions dynamiques dans vos efforts marketing :

| Opérateur | Exemples |
| --- | --- |
| Est égal à<br>(Disponible avec Correspondance d’attributs d’entité, Correspondance d’attributs de Profil, Correspondance de paramètres et Filtre statique). | En utilisant l&#39;opérateur &quot;égal à&quot; dans les promotions dynamiques, lorsqu&#39;un visiteur consulte un article sur votre site Web (tel qu&#39;un produit, un article ou un film), vous pouvez promouvoir d&#39;autres éléments à partir de :<ul><li>Même marque</li><li>La même catégorie</li><li>La même catégorie ET de la maison</li><li>Même magasin</li></ul> |
| N’est pas égal à<br> (disponible avec les attributs d’entité correspondants, les attributs de Profil correspondants, les paramètres correspondants et le filtre statique). | En utilisant l&#39;opérateur &quot;n&#39;est pas égal à&quot; dans les promotions dynamiques, lorsqu&#39;un visiteur consulte un élément de votre site Web (tel qu&#39;un produit, un article ou un film), vous pouvez promouvoir d&#39;autres éléments à partir de :<ul><li>Une série télévisée différente</li><li>Un genre différent</li><li>Une autre série de produits</li><li>Un ID de style différent</li></ul> |
| Contient une sous-chaîne<br> (disponible avec les attributs d’entité correspondants, les attributs de Profil correspondants, les paramètres correspondants et le filtre statique). | En utilisant l’opérateur &quot;contient la sous-chaîne&quot;, lorsqu’un visiteur consulte un élément de votre site Web (tel qu’un produit), vous pouvez promouvoir d’autres éléments qui :<ul><li></li></ul> |  |
| Ne contient pas de sous-chaîne<br>(disponible avec correspondance d’attributs d’entité, correspondance d’attributs de Profil, correspondance de paramètres et filtre statique). | En utilisant l’opérateur &quot;ne contient pas de sous-chaîne&quot;, lorsqu’un visiteur consulte un élément de votre site Web (tel qu’un produit), vous pouvez promouvoir d’autres éléments qui :<ul><li></li></ul> |
| Débuts avec <br> (disponibles avec correspondance d’attributs d’entité, correspondance d’attributs de Profil, correspondance de paramètres et filtre statique). | En utilisant l’opérateur &quot;débuts avec&quot;, lorsqu’un visiteur consulte un élément de votre site Web (tel qu’un produit), vous pouvez promouvoir d’autres éléments qui :<ul><li></li></ul> |
| Se termine par <br> (disponible avec les attributs d’entité correspondants, les attributs de Profil correspondants, les paramètres correspondants et le filtre statique). | En utilisant l’opérateur &quot;se termine par&quot;, lorsqu’un visiteur consulte un élément de votre site Web (tel qu’un produit), vous pouvez promouvoir d’autres éléments qui :<ul><li></li></ul> |
| Est supérieur ou égal à<br> (disponible avec les attributs d’entité correspondants, les attributs de Profil correspondants, les paramètres correspondants et le filtre statique). | En utilisant l’opérateur &quot;est supérieur ou égal à&quot;, lorsqu’un visiteur consulte un élément de votre site Web (tel qu’un produit), vous pouvez promouvoir d’autres éléments qui :<ul><li>Coûts identiques ou plus chers</li></ul> |
| Est inférieur ou égal à <br> (disponible avec les attributs d’entité correspondants, les attributs de Profil correspondants, les paramètres correspondants et le filtre statique). | En utilisant l’opérateur &quot;est inférieur ou égal à&quot;, lorsqu’un visiteur consulte un élément de votre site Web (tel qu’un produit), vous pouvez promouvoir d’autres éléments qui :<ul><li>Coût identique ou moins cher</li><li>Exclure les articles moins chers</li></ul> |
| Est compris entre <br>(disponible avec correspondance d’attributs d’entité, correspondance d’attributs de Profil et correspondance de paramètres). | En utilisant l&#39;opérateur &quot;se situe entre&quot; dans les promotions dynamiques, lorsqu&#39;un visiteur consulte un élément de votre site Web (tel qu&#39;un produit, un article ou un film), vous pouvez promouvoir d&#39;autres éléments qui sont :<ul><li>Plus cher</li><li>Moins cher</li><li>Coût plus ou moins 30 %</li><li>Épisodes ultérieurs de la même saison</li><li>Livres antérieurs dans une série</li></ul> |
| Est contenu dans Liste<br> (disponible avec Profil Attribute Matching et Parameter Matching.) | En utilisant l’opérateur &quot;est contenu dans la liste&quot; dans la correspondance d’attributs de profil, lorsqu’un visiteur consulte un élément de votre site Web (tel qu’un produit, un article ou un film), vous pouvez promouvoir d’autres éléments qui sont :<ul><li>Disponible dans la géographie du visiteur</li></ul>Lorsque vous utilisez cet opérateur, une liste est attendue dans le [côté droit](#caveats) de la règle. |
| Ne figure pas dans la Liste<br> (disponible avec Profil Attribute Matching et Parameter Matching.) | En utilisant l’opérateur &quot;n’est pas contenu dans la liste&quot; dans la correspondance d’attributs de profil, lorsqu’un visiteur consulte un article sur votre site Web (tel qu’un produit, un article ou un film), vous pouvez exclure d’autres éléments qui sont :<ul><li>À la liste des dix derniers éléments que le visiteur a consultés</li></ul></ul>Lorsque vous utilisez cet opérateur, une liste est attendue dans le [côté droit](#caveats) de la règle. |
| La liste contient un élément dans <br> (disponible avec les attributs d’entité correspondants, les attributs de Profil correspondants et les paramètres correspondants). | En utilisant l’opérateur &quot;liste contient un élément dans&quot; dans la correspondance d’attributs de profil, lorsqu’un visiteur affiche un élément sur votre site Web (tel qu’un produit, un article ou un film), vous pouvez recommander d’autres éléments qui sont :<ul><li>Associé à l’une des équipes favorites des visiteurs</li></ul></ul>Lorsque vous utilisez cet opérateur, une liste est attendue dans [les deux côtés](#caveats) de la règle. |
| La liste ne contient pas d&#39;élément dans <br> (disponible avec les attributs d&#39;entité correspondants, les attributs de Profil correspondants et les paramètres correspondants). | En utilisant l’opérateur &quot;liste ne contient pas d’élément dans&quot; dans la correspondance d’attributs de paramètre, lorsqu’un visiteur consulte un élément sur votre site Web (tel qu’un produit, un article ou un film), vous pouvez exclure d’autres éléments qui sont :<ul><li>Contenu dans une liste de types interdits</li></ul>Lorsque vous utilisez cet opérateur, une liste est attendue dans [les deux côtés](#caveats) de la règle. |
| La liste contient tous les éléments dans <br> (disponibles avec les attributs d’entité correspondants, les attributs de Profil correspondants et les paramètres correspondants). | En utilisant l’opérateur &quot;La liste contient tous les éléments dans&quot; dans la correspondance d’attributs de paramètre, lorsqu’un visiteur affiche un élément sur votre site Web (tel qu’un produit, un article ou un film), vous pouvez promouvoir d’autres éléments qui sont :<ul><li></li></ul>Lorsque vous utilisez cet opérateur, une liste est attendue dans [les deux côtés](#caveats) de la règle. |
| La liste ne contient pas tous les éléments dans <br> (disponible avec les attributs d’entité correspondants, les attributs de Profil correspondants et les paramètres correspondants). | En utilisant l’opérateur &quot;La liste ne contient pas tous les éléments dans&quot; dans la correspondance d’attributs de paramètre, lorsqu’un visiteur consulte un élément de votre site Web (tel qu’un produit, un article ou un film), vous pouvez promouvoir d’autres éléments qui sont :<ul><li></li></ul>Lorsque vous utilisez cet opérateur, une liste est attendue dans [les deux côtés](#caveats) de la règle. |

## Gestion des valeurs vides lors du filtrage par correspondance d’attributs d’entité, correspondance d’attributs de Profil et correspondance de paramètres {#section_7D30E04116DB47BEA6FF840A3424A4C8}

Vous pouvez choisir plusieurs options pour gérer les valeurs vides lors du filtrage selon [!UICONTROL Entity Attribute Matching], [!UICONTROL Profil Attribute Matching] et [!UICONTROL Parameter Matching] pour les critères de sortie et les promotions.

Auparavant, aucun résultat n’était renvoyé si une valeur était vide. La liste déroulante « Si *x* est vide » permet de choisir l’action appropriée à exécuter si le critère contient des valeurs vides, comme illustré ci-dessous :

![](assets/empty_value.png)

Pour sélectionner une action spécifique, survolez l’icône représentant un engrenage (![](assets/icon_gear.png)), puis choisissez l’action souhaitée :

| Action | Disponible pour | Détails |
|--- |--- |--- |
| [!UICONTROL Ignorer cette règle de filtrage] | [!UICONTROL Correspondance des attributs de profil ] et  [!UICONTROL des paramètres] | Cette action est la valeur par défaut pour [!UICONTROL attribut de Profil correspondant] et [!UICONTROL paramètre correspondant].<br>Cette option indique que la règle est ignorée. Par exemple, s’il existe trois règles de filtrage et que la troisième règle ne transmet aucune valeur, vous pouvez simplement ignorer la troisième règle avec les valeurs vides au lieu de ne renvoyer aucun résultat. |
| [!UICONTROL Ne pas afficher de résultats pour ce critère]<br> (Critères uniquement) | [!UICONTROL Correspondance] d’attributs d’entité, Correspondance [!UICONTROL  d’attributs ]Profil et Correspondance de  [!UICONTROL paramètres] | Cette action est la valeur par défaut de [!UICONTROL Correspondance d&#39;attribut d&#39;entité].<br>Cette action permet de  [!DNL Target] gérer les valeurs vides avant l’ajout de cette option : aucun résultat n’est affiché pour ce critère. |
| [!UICONTROL Ne pas promouvoir d’éléments<br> (Promotions uniquement)] | [!UICONTROL Correspondance] d’attributs d’entité, Correspondance [!UICONTROL  d’attributs ]Profil et Correspondance de  [!UICONTROL paramètres] | Cette action est la valeur par défaut de [!UICONTROL Correspondance d&#39;attribut d&#39;entité].<br>Cette action permet de  [!DNL Target] gérer les valeurs vides avant l’ajout de cette option : aucun résultat n’est affiché pour ce critère. |
| [!UICONTROL Utiliser une valeur statique] | [!UICONTROL Correspondance] d’attributs d’entité, Correspondance [!UICONTROL  d’attributs ]Profil et Correspondance de  [!UICONTROL paramètres] | Si une valeur est vide, vous pouvez choisir d’utiliser une valeur statique. |

## Avertissements {#caveats}

>[!IMPORTANT]
>
>Différents attributs de type de données peuvent ne pas être compatibles dans les critères ou promotions dynamiques au moment de l’exécution avec les opérateurs « est égal à » et « n’est pas égal à ». Utilisez les valeurs [!UICONTROL Valeur], [!UICONTROL Marge], [!UICONTROL Inventaire] et [!UICONTROL Environnement] judicieusement sur le côté droit si le côté gauche comporte des attributs prédéfinis ou des attributs personnalisés.

![](assets/left_right.png)

Le tableau suivant répertorie les règles efficaces et celles qui peuvent ne pas être compatibles au moment de l’exécution :

| Règles compatibles | Règles potentiellement incompatibles |
|--- |--- |
| value - est compris entre - 90 % et 110 % de l’article actif - salesValue | salesValue - est compris entre - 90 % et 110 % de l’article actif - value |
| value - est compris entre - 90 % et 110 % de l’article actif - value | clearancePrice - est compris entre - 90 % et 110 % de l’article actif - margin |
| margin - est comprise entre - 90 % et 110 % de l’article actif - margin | storeInventory - est égal à - de l’article actif - inventory |
| inventory - est égal à - de l’article actif - inventory |  |
