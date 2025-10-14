---
keywords: Recommendations;offre;prévisualisation;lancement;statut;critères;algorithme
description: Découvrez comment prévisualiser votre activité Adobe [!DNL Target] Recommendations afin de vous assurer que les résultats sont disponibles avant le lancement de l’activité.
title: Comment prévisualiser et lancer une activité Recommendations ?
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: ed400ad0ecf62a74283d2f24038bacab6a275461
workflow-type: tm+mt
source-wordcount: '1316'
ht-degree: 15%

---

# Prévisualisation et lancement de votre activité Recommendations

Après avoir créé votre activité [!UICONTROL Recommendations], [!UICONTROL A/B Test] ou [!UICONTROL Experience Targeting] (XT) contenant des [offres Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md), vous souhaiterez prévisualiser vos recommandations pour vous assurer que les résultats sont disponibles avant de lancer l’activité. [!DNL Target Recommendations] offre plusieurs façons de prévisualiser vos recommandations.

## Vérification du statut de l’algorithme de recommandations

Après avoir créé une activité, [!DNL Recommendations] exécute un algorithme pour générer des recommandations. L’exécution de cet algorithme peut prendre quelques heures.

Vous pouvez vérifier si l’algorithme a fini de s’exécuter dans le diagramme de présentation des [!UICONTROL Activity], où le statut des critères est répertorié. L&#39;illustration suivante présente le statut dans le diagramme d&#39;activité sur la page [!DNL Recommendations] d&#39;une activité [!UICONTROL Overview] :

![Page Aperçu de l’activité Recommendations](/help/main/c-recommendations/t-create-recs-activity/assets/recs-overview-new.png)

Les résultats du statut sont les suivants, comme illustré ci-dessous :

* [!UICONTROL Results Ready] : indique que l’algorithme a renvoyé des résultats
* [!UICONTROL Results Not Ready] : indique que l’algorithme n’a pas terminé son exécution.
* [!UICONTROL Feed Failure] : indique que le fichier de flux de critères personnalisés n’a pas pu être récupéré.

![Boîte de dialogue Résultats](/help/main/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## Combien de temps l’algorithme va-t-il prendre pour s’exécuter ?

Après avoir enregistré une activité contenant un critère , [!DNL Target] calcule les recommandations en fonction de la collection, des critères, de la conception et des promotions sélectionnés. Ce calcul prend un certain temps et la période diffère en fonction de la logique de recommandation sélectionnée, de la plage de données, du nombre d’éléments de votre catalogue, de la quantité de données comportementales générées par vos clients et de la source de données comportementales sélectionnée.

La source de données comportementales a l’impact le plus important sur le temps de traitement, comme suit :

### mbox régionales classiques

Si des mbox sont sélectionnées en tant que source de données comportementales, les critères s’exécutent immédiatement une fois créés. Selon la quantité de données comportementales utilisées et la taille du catalogue, l’algorithme peut mettre jusqu’à 12 heures pour s’exécuter. Si des changements sont effectués dans la configuration des critères, l’exécution des de l’algorithme reprend généralement au début. Selon la modification apportée, les recommandations calculées précédemment peuvent ne pas être disponibles tant qu’une nouvelle exécution n’est pas terminée ou, pour les modifications plus importantes, seul le contenu de sauvegarde ou par défaut est disponible tant qu’une nouvelle exécution n’est pas terminée. Si un algorithme n’est pas modifié, il est automatiquement réexécuté par [!DNL Target] toutes les 12 à 48 heures, selon la plage de données sélectionnée.

### [!DNL Adobe Analytics]

Lorsque les critères utilisent [!DNL Adobe Analytics] comme source de données comportementales, le temps qu’ils mettent à être disponibles une fois créés dépend de l’utilisation ou pas de la suite de rapports et de périodes d’analyse sur d’autres critères.

* **Configuration unique d’une suite de rapports** : la première fois qu’une suite de rapports est utilisée avec une fenêtre de recherche de plage de données spécifique, [!DNL Target Recommendations] peut prendre de deux à sept jours pour télécharger complètement les données comportementales de la suite de rapports sélectionnée depuis [!DNL Analytics]. Cette période dépend de la charge du système [!DNL Analytics].
* **Critères nouveaux ou modifiés à l’aide d’une suite de rapports déjà disponible** : lors de la création d’un critère ou de la modification d’un critère existant, si la suite de rapports sélectionnée a déjà été utilisée avec [!DNL Target Recommendations], avec une plage de données égale ou inférieure à la plage de données sélectionnée, les données sont immédiatement disponibles et aucune configuration unique n’est requise. Dans ce cas ou si les paramètres d’un algorithme sont modifiés sans changer la suite de rapports ou la plage de données sélectionnée, l’algorithme s’exécute ou se réexécute dans les 12 heures.
* **Exécutions d’algorithme en cours** : les données sont transmises quotidiennement d’[!DNL Analytics] à [!DNL Target Recommendations]. Par exemple, pour la recommandation [!UICONTROL Viewed Affinity], lorsqu’un utilisateur consulte un produit, un appel de suivi d’affichage de produit est transmis en [!DNL Analytics] en temps quasi réel. Les données [!DNL Analytics] sont transmises au [!DNL Target] tôt le lendemain et [!DNL Target] exécute l’algorithme en moins de 12 heures.

>[!NOTE]
>
>[!UICONTROL Recently Viewed Items] ne nécessite pas d’exécution d’algorithme hors ligne et les résultats sont immédiatement disponibles. Les algorithmes [!UICONTROL Top Viewed] et [!UICONTROL Top Sellers] basés sur les données mbox produisent généralement des résultats très rapidement en raison de la simplicité de calcul requise. Il peut s’agir d’options intéressantes lorsque vous souhaitez prévisualiser une modification de conception ou confirmer que les données comportementales sont collectées correctement.

## Utilisation des liens d’assurance qualité pour prévisualiser les recommandations

Une fois que l’algorithme a des résultats prêts, vous pouvez prévisualiser ces résultats à l’aide de la fonctionnalité [lien d’assurance qualité](/help/main/c-activities/c-activity-qa/activity-qa.md) de [!DNL Adobe Target]. Des liens d’assurance qualité sont disponibles dans la section [!UICONTROL Activity Location] de la page d’aperçu de la [!UICONTROL Activity] :

>[!NOTE]
>
>Par défaut, [!DNL Target] vous ajoute automatiquement à l’audience requise pour le lien d’assurance qualité. Si ce paramètre est désactivé et que votre activité comporte des règles de ciblage, votre profil utilisateur doit respecter ces règles de ciblage pour voir l’expérience contenant des recommandations.

À l’aide d’un lien QA , vous pouvez prévisualiser les recommandations sur votre page :

![Produits présentés](/help/main/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>* Le mode d’assurance qualité cible est « sticky » et enregistré dans un cookie. Si vous ne quittez pas le mode assurance qualité, vous continuerez à voir les résultats de l’assurance qualité sur l’ensemble du site. Pour quitter le mode assurance qualité, utilisez le [signet](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md).
>
>* En mode assurance qualité, la navigation sur le site n’affecte pas le [!UICONTROL Recently Viewed Items] ou le [!UICONTROL Recently Purchased Items] de votre profil. Ce comportement est prévu pour éviter la pollution involontaire des données comportementales de production. Pour prévisualiser les résultats d’un critère de [!UICONTROL Recently Viewed Items] ou de [!UICONTROL User-Based Recommendations], parcourez d’abord le site en dehors du mode AQ, puis utilisez la même session pour ouvrir un lien de mode AQ.

## Utilisation du téléchargement d’un fichier CSV pour prévisualiser les recommandations

Dans certains cas, il se peut que vous souhaitiez auditer les éléments spécifiques recommandés. Cela s’avère particulièrement utile lors de l’utilisation d’algorithmes tels que [!UICONTROL People Who Viewed This, Viewed That], où un ensemble d’éléments différent est recommandé en fonction de l’élément que l’utilisateur consulte actuellement et où vous pouvez avoir des milliers ou des millions d’éléments différents dans votre catalogue.

Les résultats ne peuvent pas être téléchargés tant qu’un statut de [!UICONTROL Results Ready] n’est pas affiché pour au moins un algorithme de l’activité.

Pour télécharger les résultats pour la prévisualisation, cliquez sur l’icône de menu dans le coin supérieur droit de la page d’aperçu des activités, puis cliquez sur **[!UICONTROL Download data]**.

![Option Télécharger les données](/help/main/c-recommendations/t-create-recs-activity/assets/download-data.png)

Un fichier CSV est téléchargé. Ouvrez-le pour afficher les éléments recommandés :

![Fichier CSV d’éléments recommandés](/help/main/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

De gauche à droite se trouve une liste des éléments recommandés, dans ce cas les plus consultés. Les recommandations sont séparées par environnement. Dans ce cas, seul l’environnement de production dispose de recommandations.

Si un astérisque (*) est la première valeur d’une ligne, il indique [&#x200B; éléments de sauvegarde &#x200B;](/help/main/c-recommendations/c-algorithms/backup-recs.md). Les éléments de sauvegarde s&#39;affichent si tous les emplacements d&#39;une conception ne peuvent pas être remplis par les éléments recommandés de l&#39;algorithme (critères).

Pour d’autres types d’algorithmes basés sur une valeur de clé, tels que [!UICONTROL People Who Viewed This, Viewed That], les valeurs de clé (c’est-à-dire les éléments « This ») sont répertoriées dans la colonne la plus à gauche et les éléments recommandés (c’est-à-dire les éléments « That ») sont répertoriés de gauche à droite dans les colonnes Recommendation_X.

>[!NOTE]
>
>Les téléchargements de résultats ne sont pas disponibles pour les activités contenant un algorithme de [!UICONTROL User-Based Recommendations]. Les résultats téléchargés ne sont pas disponibles pour les critères utilisant la logique de recommandation [!UICONTROL Recently-Viewed Items].

## Activation de votre activité Recommendations

Dans l’onglet [!UICONTROL Activity Overview] , cliquez sur la flèche déroulante Statut , puis sélectionnez **[!UICONTROL Activate]**.

Si votre activité de [!UICONTROL Recommendations] est actuellement à l’état [!UICONTROL Inactive], la liste déroulante est intitulée [!UICONTROL Inactive].

Au bout de quelques secondes à quelques minutes, le statut passe à [!UICONTROL Live].

Vous pouvez également désactiver ou archiver l’activité à l’aide de la même liste déroulante.

## Éviter les perturbations lors de la modification des paramètres de Recommendations

La modification des collections de [!DNL Recommendations], des critères, des promotions ou des paramètres de conception dans une activité active peut entraîner l’invalidation des résultats de l’algorithme et le passage à l’état [!UICONTROL Results Not Ready] d’un algorithme.

Pour éviter de perturber une activité active, nous vous recommandons d’adopter l’approche suivante lors de la modification d’une activité active :

1. Dupliquez l’activité d’origine (activité 1) et les critères que vous souhaitez modifier pour créer une nouvelle activité (activité 2).
1. Apportez des modifications à l’activité dupliquée (activité 2) et aux critères, puis attendez que l’algorithme génère des résultats.
1. Prévisualisez la nouvelle activité modifiée (activité 2) et confirmez que les résultats sont corrects.
1. Activer la nouvelle activité (activité 2).
1. Désactivez l’activité d’origine (activité 1).

Si vous devez conserver les résultats des rapports historiques dans la même activité, une autre approche est possible, ce qui peut entraîner une interruption temporaire de la disponibilité des recommandations :

1. Dupliquez l’activité d’origine (activité 1) et les critères que vous souhaitez modifier pour créer une nouvelle activité (activité 2).
1. Apportez des modifications à l’activité dupliquée (activité 2) et aux critères, puis attendez que l’algorithme génère des résultats.
1. Prévisualisez la nouvelle activité modifiée (activité 2) et confirmez que les résultats sont corrects.
1. Mettez en pause la nouvelle activité modifiée (activité 2) et remplacez les paramètres/critères par l’activité originale (activité 1).
1. Prévisualisez l’activité d’origine (activité 1) et confirmez que les résultats sont ceux souhaités.
1. Réactivez l’activité originale (activité 1).
