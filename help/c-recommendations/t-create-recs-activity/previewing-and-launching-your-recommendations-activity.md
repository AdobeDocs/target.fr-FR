---
keywords: Recommendations;offer;preview;launch
description: 'Après avoir créé votre activité Recommendations, Test A/B ou Ciblage d’expérience (XT) contenant des offres Adobe Target Recommendations, vous souhaiterez la prévisualisation pour vous assurer que les résultats sont disponibles avant de lancer l’activité. Cible Recommendations offre plusieurs façons de prévisualisation de vos recommandations. '
title: 'Après avoir créé votre activité Recommendations, Test A/B ou Ciblage d’expérience (XT) contenant des offres Adobe Target Recommendations, vous souhaiterez la prévisualisation pour vous assurer que les résultats sont disponibles avant de lancer l’activité. Cible Recommendations offre plusieurs façons de prévisualisation de vos recommandations. '
feature: recs creation
subtopic: Recommendations
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 19%

---


# Prévisualisation et lancement de votre activité de recommandations

Après avoir créé votre activité [!UICONTROL Recommendations], Test A/B ou Ciblage [!UICONTROL d’] expérience (XT) contenant des offres [Recommendations, vous devez prévisualisation vos recommandations afin de vous assurer que les résultats sont disponibles avant de lancer l’activité. ](/help/c-recommendations/recommendations-as-an-offer.md) [!DNL Target Recommendations] offre plusieurs façons de prévisualisation de vos recommandations.

## Vérification de l’état de l’algorithme Recommendations

Après avoir créé une activité, [!DNL Recommendations] exécute un algorithme pour générer des recommandations. L’exécution de cet algorithme peut prendre quelques heures.

Vous pouvez vérifier si l’exécution de l’algorithme est terminée dans le diagramme de présentation de l’ [!UICONTROL Activité] , où l’état des critères est répertorié. L’illustration suivante présente l’état du diagramme d’activité sur une page [!DNL Recommendations] Aperçu [!UICONTROL d’une] activité :

![Page Aperçu de l’activité Recommendations](/help/c-recommendations/t-create-recs-activity/assets/recs-overview.png)

L’illustration suivante illustre l’état de la page [!UICONTROL Présentation] d’une activité [!UICONTROL A/B Test] ou XT :

![Page Aperçu du test A/B](/help/c-recommendations/t-create-recs-activity/assets/ab-overview.png)

Les résultats de l’état sont les suivants, comme illustré ci-dessous :

* [!UICONTROL Résultats prêts]: Indique que l’algorithme a renvoyé des résultats
* [!UICONTROL Résultats non prêts]: Indique que l’exécution de l’algorithme n’est pas terminée.
* [!UICONTROL Échec]du flux : Indique que le fichier de flux de critères personnalisés n’a pas pu être récupéré.

![Boîte de dialogue Résultats](/help/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## Combien de temps l’algorithme prendra-t-il pour s’exécuter ?

Après avoir enregistré une activité contenant un critère, [!DNL Target] calcule les recommandations en fonction de la collection, des critères, de la conception et des promotions sélectionnés. Ce calcul prend du temps et la durée varie selon la logique de recommandation sélectionnée, la plage de données, le nombre d’éléments dans votre catalogue, la quantité de données comportementales générées par vos clients et la source de données comportementales sélectionnée.

La source de données comportementales a l’impact le plus important sur le temps de traitement, comme suit :

### mbox régionales classiques

Si des mbox sont sélectionnées en tant que source de données comportementales, les critères s’exécutent immédiatement une fois créés. Selon la quantité de données comportementales utilisées et la taille du catalogue, l’algorithme peut mettre jusqu’à 12 heures pour s’exécuter. Si des changements sont effectués dans la configuration des critères, l’exécution des de l’algorithme reprend généralement au début. Selon la modification apportée, il est possible que les recommandations précédemment calculées ne soient pas disponibles tant qu’une nouvelle exécution n’est pas terminée ou, pour les modifications plus importantes, seul le contenu de sauvegarde ou par défaut est disponible jusqu’à ce qu’une nouvelle exécution soit terminée. Si un algorithme n’est pas modifié, il est automatiquement réexécuté par [!DNL Target] toutes les 12 à 48 heures, selon la plage de données sélectionnée.

### Adobe Analytics

Lorsque les critères utilisent [!DNL Adobe Analytics] comme source de données comportementales, le temps qu’ils mettent à être disponibles une fois créés dépend de l’utilisation ou pas de la suite de rapports et de périodes d’analyse sur d’autres critères.

* **Configuration unique d’une suite de rapports** : la première fois qu’une suite de rapports est utilisée avec une fenêtre de recherche de plage de données spécifique, [!DNL Target Recommendations] peut prendre de deux à sept jours pour télécharger complètement les données comportementales de la suite de rapports sélectionnée depuis [!DNL Analytics]. Cette période dépend de la charge du système [!DNL Analytics].
* **Critères nouveaux ou modifiés à l’aide d’une suite** de rapports déjà disponible : Lors de la création d’un nouveau critère ou de la modification d’un critère existant, si la suite de rapports sélectionnée a déjà été utilisée avec [!DNL Target Recommendations]une plage de données égale ou inférieure à la plage de données sélectionnée, les données sont immédiatement disponibles et aucune configuration unique n’est requise. Dans ce cas ou si les paramètres d’un algorithme sont modifiés sans changer la suite de rapports ou la plage de données sélectionnée, l’algorithme s’exécute ou se réexécute dans les 12 heures.
* **Exécutions d’algorithme en cours** : les données sont transmises quotidiennement d’[!DNL Analytics] à [!DNL Target Recommendations]. Par exemple, pour la recommandation [!UICONTROL Affinité consultée], lorsqu’un utilisateur consulte un produit, un appel de suivi de consultation de produit est transmis à [!DNL Analytics] pratiquement en temps réel. The [!DNL Analytics] data is pushed to [!DNL Target] early the next day and [!DNL Target] runs the algorithm in fewer than 12 hours.

>[!NOTE]
>
>[!UICONTROL Les éléments] récemment consultés ne nécessitent aucune exécution d’algorithme hors ligne et les résultats sont instantanément disponibles. [!UICONTROL Les algorithmes Meilleures ventes] et [!UICONTROL Meilleures ventes] basés sur les données de mbox produisent généralement des résultats très rapidement en raison d’un calcul plus simple. Il peut s’agir de bonnes options lorsque vous souhaitez prévisualisation une modification de la conception ou confirmer que les données comportementales sont collectées correctement.

## Utilisation des liens d’assurance qualité pour la prévisualisation Recommendations

Une fois les résultats prêts pour l’algorithme, vous pouvez les prévisualisation à l’aide de la fonctionnalité de lien [](/help/c-activities/c-activity-qa/activity-qa.md) QA de [!DNL Adobe Target]. Les liens d’assurance qualité sont disponibles dans la section AQ [!UICONTROL de l’] Activité de la page d’aperçu de l’Activité :

![Liens de l’AQ d’activité](/help/c-recommendations/t-create-recs-activity/assets/qa-link.png)

>[!NOTE]
>
>Par défaut, [!DNL Target] vous ajoute automatiquement à l’audience requise pour le lien d’assurance qualité. Si ce paramètre est désactivé et que votre activité comporte des règles de ciblage, votre profil utilisateur doit respecter ces règles de ciblage pour voir l’expérience contenant des recommandations.

L’utilisation d’un lien d’assurance qualité vous permet de prévisualisation des recommandations sur votre page :

![Produits présentés](/help/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>Le mode de contrôle qualité de la cible est &quot;collant&quot; et enregistré dans un cookie. Si vous ne quittez pas le mode AQ, vous verrez toujours les résultats de l’AQ sur l’ensemble du site. Pour quitter le mode AQ, utilisez le [signet d’applet](/help/c-activities/c-activity-qa/activity-qa-bookmark.md).

>[!NOTE]
>
>En mode AQ, la navigation sur le site n’affectera pas les articles  récemment consultés ou les articles récemment achetés de votre profil. Ce comportement se produit par conception pour éviter la pollution involontaire des données comportementales de production. Pour prévisualisation les résultats d’éléments  récemment consultés ou de critères Recommendations [!UICONTROL basés sur l’] utilisateur, parcourez d’abord le site en dehors du mode AQ, puis utilisez la même session pour ouvrir un lien de mode AQ.

## Utilisation du téléchargement CSV pour les recommandations de prévisualisation

Dans certains cas, vous pouvez contrôler les éléments spécifiques recommandés. Cela s’avère particulièrement utile lors de l’utilisation d’algorithmes tels que [!UICONTROL Personnes qui ont consulté ceci, consulté cela], où un ensemble d’éléments différent est recommandé en fonction de l’élément actuellement consulté par l’utilisateur et où vous pouvez avoir des milliers ou des millions d’éléments différents dans votre catalogue.

Les résultats ne sont pas disponibles au téléchargement tant qu’un état [!UICONTROL Résultats prêts] n’est pas affiché pour au moins un algorithme dans l’activité.

Pour télécharger les résultats de la prévisualisation, cliquez sur l’icône de menu dans le coin supérieur droit de la page d’aperçu de l’Activité, puis cliquez sur **[!UICONTROL Télécharger les données]**.

![Télécharger les données, option](/help/c-recommendations/t-create-recs-activity/assets/download-data.png)

Un fichier CSV est téléchargé. Ouvrez-la pour afficher les éléments recommandés :

![Fichier CSV d’éléments recommandés](/help/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

De gauche à droite est une liste d&#39;éléments recommandés, dans ce cas la plus fréquemment consultée. Les recommandations sont séparées par environnement, dans ce cas, seul l&#39;environnement de production a des recommandations. Pour cet algorithme, nous n’avons appliqué aucune restriction basée sur la valeur de clé. Par conséquent, la ligne marquée d’un astérisque (*) contient l’ensemble complet des recommandations. Pour d’autres types d’algorithmes basés sur une valeur de clé, tels que [!UICONTROL Personnes ayant affiché ceci et consulté cela], les valeurs de clé (c’est-à-dire les éléments &quot;Ceci&quot;) sont répertoriées dans la colonne la plus à gauche et les éléments recommandés (c’est-à-dire les éléments &quot;Que&quot;) sont répertoriés de gauche à droite dans les colonnes de Recommendations_X.

>[!NOTE]
>
>Les téléchargements de résultats ne sont pas disponibles pour les activités contenant un algorithme Recommendations [!UICONTROL basé sur] l’utilisateur. Les téléchargements de résultats ne sont pas disponibles pour les critères utilisant la logique de recommandation Éléments  récemment consultés.

## Activation de votre activité Recommendations

Dans l’onglet Aperçu [!UICONTROL des] Activités, cliquez sur la flèche déroulante en regard de l’état, puis sélectionnez **[!UICONTROL Activer]**.

![Option Activer](/help/c-recommendations/t-create-recs-activity/assets/activate.png)

Notez que l’état devient [!UICONTROL Activation]:

![Activation](/help/c-recommendations/t-create-recs-activity/assets/activating.png)

Après quelques secondes à quelques minutes, l’état passe à [!UICONTROL Live]:

![En direct](/help/c-recommendations/t-create-recs-activity/assets/live.png)

Notez que vous pouvez également désactiver ou archiver l’activité à l’aide de la même liste déroulante.

## Éviter les interruptions lors de la modification des paramètres Recommendations

La modification de [!DNL Recommendations] collections, de critères, de promotions ou de paramètres de conception dans une activité active peut entraîner la non-validité des résultats de l’algorithme et la modification de l’état d’un algorithme en [!UICONTROL Résultats non prêts].

Pour éviter de perturber une activité en direct, nous vous recommandons d’adopter l’approche suivante lors de la modification d’une activité en direct :

1. Duplicata l’activité et les critères que vous souhaitez modifier.
1. Apportez des modifications à l’activité et aux critères dupliqués et attendez que l’algorithme génère des résultats.
1. Prévisualisation la nouvelle activité modifiée et confirme que les résultats sont conformes aux attentes.
1. Activez la nouvelle activité.
1. Désactivez l’ancienne activité.

Si vous devez conserver les résultats du rapports historique dans la même activité, une autre approche est possible, ce qui peut entraîner une interruption temporaire de la disponibilité des recommandations :

1. Duplicata l’activité et les critères que vous souhaitez modifier.
1. Apportez des modifications à l’activité et aux critères dupliqués et attendez que l’algorithme génère des résultats.
1. Prévisualisation la nouvelle activité modifiée et confirme que les résultats sont conformes aux attentes.
1. Mettez l’activité existante en pause et remplacez les paramètres/critères par les nouveaux critères.
1. Prévisualisation de l’activité existante et confirmer que les résultats sont conformes aux attentes.
1. Réactivez l’activité.
