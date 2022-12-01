---
keywords: Recommendations;offre;aperçu;lancement;état;critères;algorithme
description: Découvrez comment prévisualiser votre Adobe [!DNL Target] Activité Recommendations pour s’assurer que les résultats sont disponibles avant de lancer l’activité.
title: Comment prévisualiser et lancer une activité Recommendations ?
feature: Recommendations
exl-id: 60391778-4d48-4c41-a7c5-fedcfabf2530
source-git-commit: 7732f3af0fd995309035a8a214afd438ab7a1823
workflow-type: tm+mt
source-wordcount: '1381'
ht-degree: 17%

---

# Prévisualisation et lancement de votre activité Recommendations

Après avoir créé votre [!UICONTROL Recommendations], [!UICONTROL Test A/B]ou [!UICONTROL Ciblage d’expérience] (XT) activité contenant [Offres Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md), vous souhaitez prévisualiser vos recommandations pour vous assurer que les résultats sont disponibles avant de lancer l’activité. [!DNL Target Recommendations] propose plusieurs méthodes pour prévisualiser vos recommandations.

## Vérification de l’état de l’algorithme Recommendations

Après la création d’une activité, [!DNL Recommendations] exécute un algorithme pour générer des recommandations. L’exécution de cet algorithme peut prendre quelques heures.

Vous pouvez vérifier si l’exécution de l’algorithme est terminée dans la variable [!UICONTROL Activité] diagramme d’aperçu, où l’état des critères est répertorié. L’illustration suivante présente l’état dans le diagramme d’activité sur un [!DNL Recommendations] de l’activité [!UICONTROL Présentation] page :

![Page Aperçu de l’activité Recommendations](/help/main/c-recommendations/t-create-recs-activity/assets/recs-overview.png)

L’illustration suivante illustre l’état d’une [!UICONTROL Test A/B] ou de l’activité XT [!UICONTROL Présentation] page :

![Page Aperçu du test A/B](/help/main/c-recommendations/t-create-recs-activity/assets/ab-overview.png)

Les résultats de l’état sont les suivants, comme illustré ci-dessous :

* [!UICONTROL Résultats prêts]: Indique que l’algorithme a renvoyé des résultats
* [!UICONTROL Résultats non prêts]: Indique que l’exécution de l’algorithme n’est pas terminée.
* [!UICONTROL Échec du flux]: Indique que le fichier de flux de critères personnalisés n’a pas pu être récupéré.

![Boîte de dialogue Résultats](/help/main/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## Combien de temps l’algorithme prendra-t-il pour s’exécuter ?

Après avoir enregistré une activité contenant un critère, [!DNL Target] calcule les recommandations en fonction de la collection, des critères, de la conception et des promotions sélectionnés. Ce calcul prend un certain temps et la période varie en fonction de la logique de recommandation sélectionnée, de la plage de données, du nombre d’éléments dans votre catalogue, de la quantité de données comportementales générées par vos clients et de la source de données comportementales sélectionnée.

La source de données comportementales a l’impact le plus important sur le temps de traitement, comme suit :

### mbox régionales classiques

Si des mbox sont sélectionnées en tant que source de données comportementales, les critères s’exécutent immédiatement une fois créés. Selon la quantité de données comportementales utilisées et la taille du catalogue, l’algorithme peut mettre jusqu’à 12 heures pour s’exécuter. Si des changements sont effectués dans la configuration des critères, l’exécution des de l’algorithme reprend généralement au début. Selon la modification apportée, les recommandations précédemment calculées peuvent ne pas être disponibles tant qu’une nouvelle exécution n’est pas terminée. Pour les modifications plus importantes, seule la sauvegarde ou le contenu par défaut est disponible jusqu’à la fin d’une nouvelle exécution. Si un algorithme n’est pas modifié, il est automatiquement réexécuté par [!DNL Target] toutes les 12 à 48 heures, selon la plage de données sélectionnée.

### Adobe Analytics

Lorsque les critères utilisent [!DNL Adobe Analytics] comme source de données comportementales, le temps qu’ils mettent à être disponibles une fois créés dépend de l’utilisation ou pas de la suite de rapports et de périodes d’analyse sur d’autres critères.

* **Configuration unique d’une suite de rapports** : la première fois qu’une suite de rapports est utilisée avec une fenêtre de recherche de plage de données spécifique, [!DNL Target Recommendations] peut prendre de deux à sept jours pour télécharger complètement les données comportementales de la suite de rapports sélectionnée depuis [!DNL Analytics]. Cette période dépend de la charge du système [!DNL Analytics].
* **Critères nouveaux ou modifiés à l’aide d’une suite de rapports déjà disponible**: Lors de la création d’un nouveau critère ou de la modification d’un critère existant, si la suite de rapports sélectionnée a déjà été utilisée avec [!DNL Target Recommendations], avec une plage de données inférieure ou égale à la plage sélectionnée, les données sont immédiatement disponibles et aucune configuration unique n’est requise. Dans ce cas ou si les paramètres d’un algorithme sont modifiés sans changer la suite de rapports ou la plage de données sélectionnée, l’algorithme s’exécute ou se réexécute dans les 12 heures.
* **Exécutions d’algorithme en cours** : les données sont transmises quotidiennement d’[!DNL Analytics] à [!DNL Target Recommendations]. Par exemple, pour la recommandation [!UICONTROL Affinité consultée], lorsqu’un utilisateur consulte un produit, un appel de suivi de consultation de produit est transmis à [!DNL Analytics] pratiquement en temps réel. Le [!DNL Analytics] Les données sont transmises à [!DNL Target] dès le lendemain et [!DNL Target] exécute l’algorithme en moins de 12 heures.

>[!NOTE]
>
>[!UICONTROL Éléments récemment consultés] ne nécessite aucune exécution d’algorithme hors ligne et les résultats sont instantanément disponibles. [!UICONTROL Meilleures vues] et [!UICONTROL Meilleurs vendeurs] les algorithmes reposant sur les données de mbox produisent généralement des résultats très rapidement en raison d’un calcul plus simple. Il peut s’agir de bonnes options lorsque vous souhaitez prévisualiser un changement de conception ou confirmer que les données comportementales sont collectées correctement.

## Utilisation de liens AQ pour prévisualiser Recommendations

Une fois que les résultats de l’algorithme sont prêts, vous pouvez les prévisualiser à l’aide de la variable [Lien AQ](/help/main/c-activities/c-activity-qa/activity-qa.md) fonctionnalité de [!DNL Adobe Target]. Les liens d’assurance qualité sont disponibles dans la section [!UICONTROL AQ d’activité] de la page d’aperçu de l’activité :

![Liens de l’AQ d’activité](/help/main/c-recommendations/t-create-recs-activity/assets/qa-link.png)

>[!NOTE]
>
>Par défaut, [!DNL Target] vous ajoute automatiquement à l’audience requise pour le lien AQ. Si ce paramètre est désactivé et que votre activité comporte des règles de ciblage, votre profil utilisateur doit respecter ces règles de ciblage pour afficher l’expérience contenant des recommandations.

L’utilisation d’un lien AQ vous permet de prévisualiser les recommandations sur votre page :

![Produits présentés](/help/main/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>* Le mode AQ de Target est &quot;attractif&quot; et enregistré dans un cookie. Si vous ne quittez pas le mode AQ, vous continuerez à voir les résultats de l’AQ sur l’ensemble du site. Pour quitter le mode AQ, utilisez la méthode [signet](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md).
>
>* En mode AQ, la navigation sur le site n’affecte pas le [!UICONTROL Éléments récemment consultés] ou [!UICONTROL Éléments récemment achetés]. Ce comportement se produit par conception afin d’éviter une pollution involontaire des données comportementales de production. Pour prévisualiser les résultats d’un [!UICONTROL Éléments récemment consultés] ou [!UICONTROL Recommendations basé sur les utilisateurs] , parcourez d’abord le site en dehors du mode AQ, puis utilisez la même session pour ouvrir un lien de mode AQ.


## Utilisation du téléchargement CSV pour prévisualiser les recommandations

Dans certains cas, vous pouvez contrôler les éléments spécifiques recommandés. Cela s’avère particulièrement utile lors de l’utilisation d’algorithmes tels que [!UICONTROL Les personnes ayant consulté ceci ont consulté cela], où un ensemble différent d’éléments est recommandé en fonction de l’élément actuellement consulté par l’utilisateur, et vous pouvez avoir des milliers ou des millions d’éléments différents dans votre catalogue.

Les résultats ne peuvent être téléchargés qu’après un événement [!UICONTROL Résultats prêts] est affiché pour au moins un algorithme de l’activité.

Pour télécharger les résultats pour la prévisualisation, cliquez sur l’icône de menu dans le coin supérieur droit de la page d’aperçu de l’activité, puis cliquez sur **[!UICONTROL Téléchargement de données]**.

![Option Télécharger les données](/help/main/c-recommendations/t-create-recs-activity/assets/download-data.png)

Un fichier CSV est téléchargé. Ouvrez-le pour afficher les éléments recommandés :

![Fichier CSV d’éléments recommandés](/help/main/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

De gauche à droite est une liste d’éléments recommandés, dans ce cas le plus fréquemment consultés. Les recommandations sont séparées par environnement. Dans ce cas, seul l’environnement de production comporte des recommandations. Pour cet algorithme, nous n’avons appliqué aucune restriction basée sur la valeur de clé. Par conséquent, la ligne étiquetée avec un astérisque (*) contient l’ensemble complet des recommandations. Pour d’autres types d’algorithme basés sur une valeur de clé, comme [!UICONTROL Les personnes ayant consulté ceci ont consulté cela], les valeurs clés (c’est-à-dire les éléments &quot;This&quot;) sont répertoriées dans la colonne la plus à gauche et les éléments recommandés (c’est-à-dire les éléments &quot;That&quot;) sont répertoriés de gauche à droite dans les colonnes de Recommendations_X.

>[!NOTE]
>
>Les téléchargements de résultats ne sont pas disponibles pour les activités contenant un [!UICONTROL Recommendations basé sur les utilisateurs] algorithme. Les téléchargements de résultats ne sont pas disponibles pour les critères utilisant la variable [!UICONTROL Éléments récemment consultés] logique de recommandation.

## Activation de votre activité Recommendations

Dans la [!UICONTROL Présentation de l’activité] , cliquez sur la flèche déroulante en regard de l’état, puis sélectionnez **[!UICONTROL Activer]**.

![Option Activer](/help/main/c-recommendations/t-create-recs-activity/assets/activate.png)

Notez que l’état devient [!UICONTROL Activation]:

![Activation](/help/main/c-recommendations/t-create-recs-activity/assets/activating.png)

Après quelques secondes à quelques minutes, l’état passe à [!UICONTROL En direct]:

![En direct](/help/main/c-recommendations/t-create-recs-activity/assets/live.png)

Vous pouvez également désactiver ou archiver l’activité à l’aide de la même liste déroulante.

## Eviter les interruptions lors de la modification des paramètres de Recommendations

Modification [!DNL Recommendations] collections, critères, promotions ou paramètres de conception dans une activité active peuvent entraîner la non-validité des résultats de l’algorithme et la modification de l’état d’un algorithme en [!UICONTROL Résultats non prêts].

Pour éviter de perturber une activité en direct, nous vous recommandons de suivre la méthode suivante lors de la modification d’une activité en direct :

1. Dupliquez l&#39;activité d&#39;origine (activité 1) et les critères à modifier pour créer une activité (activité 2).
1. Apportez des modifications à l’activité dupliquée (activité 2) et aux critères et attendez que l’algorithme génère des résultats.
1. Prévisualisez la nouvelle activité modifiée (activité 2) et vérifiez que les résultats sont à votre convenance.
1. Activez la nouvelle activité (activité 2).
1. Désactivez l&#39;activité d&#39;origine (activité 1).

Si vous devez conserver les résultats des rapports historiques dans la même activité, une autre approche est possible, ce qui peut entraîner une interruption temporaire de la disponibilité des recommandations :

1. Dupliquez l&#39;activité d&#39;origine (activité 1) et les critères à modifier pour créer une activité (activité 2).
1. Apportez des modifications à l’activité dupliquée (activité 2) et aux critères et attendez que l’algorithme génère des résultats.
1. Prévisualisez la nouvelle activité modifiée (activité 2) et vérifiez que les résultats sont à votre convenance.
1. Suspendre la nouvelle activité modifiée (activité 2) et passer les paramètres/critères à l’activité d’origine (activité 1).
1. Prévisualisez l’activité d’origine (activité 1) et vérifiez que les résultats correspondent à vos besoins.
1. Réactivez l’activité d’origine (activité 1).
