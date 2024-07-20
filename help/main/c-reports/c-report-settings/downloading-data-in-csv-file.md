---
keywords: rapports;télécharger les rapports;csv;mesure de succès;détails de commande
description: Découvrez comment télécharger des données à partir des activités Adobe [!DNL Target] au format CVS pour une importation rapide dans Excel, Access ou d’autres programmes d’analyse des données.
title: Comment Télécharger Des Données De Rapport Dans Un Fichier CSV ?
feature: Reports
exl-id: b4387184-8730-4367-8bc3-52d8fbe2583e
source-git-commit: fc1dcc2b6de1248c35191c1ecd7b36aeb891fd3f
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 37%

---

# Téléchargement des données dans un fichier CSV

Téléchargez les données au format .csv afin de pouvoir les importer rapidement dans Excel, Access ou d’autres programmes d’analyse des données.

Pour télécharger les données dans un fichier CSV, procédez comme suit :

1. Cliquez sur **[!UICONTROL Activities]**, puis sélectionnez l’activité souhaitée dans la liste.

   Si vous avez de nombreuses activités, vous pouvez filtrer la liste en sélectionnant des options dans les listes déroulantes [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type] et [!UICONTROL Activity Source].

1. Cliquez sur l’onglet **[!UICONTROL Reports]** .
1. Cliquez sur l’icône **[!UICONTROL Download]**, puis sélectionnez un type de rapport à télécharger pour l’analyse dans Excel et d’autres outils.

   * [!UICONTROL Export Reports to CSV]
   * [!UICONTROL Export Order Details to CSV]

   ![Options de téléchargement](/help/main/c-reports/assets/download-options.png)

## [!UICONTROL Export Report to CSV] {#section_38BD9743EB254453B5F4A0A6F2720CD3}

Le rapport [!UICONTROL Success Metrics] vous présente des informations sur vos mesures de succès, ainsi que les mesures suivantes, qui ne sont pas disponibles dans l’interface utilisateur de [!DNL Target] :

* Temps moyen avant conversion en heures, afin que vous sachiez en combien de temps le visiteur moyen parvient au point de conversion.
* Somme des recettes, quadratique, pour le calcul de fiabilité statistique hors ligne.

Les données sont enregistrées jusqu’au terme de l’activité.

>[!NOTE]
>
>Le rapport CSV comprend uniquement des données brutes. Il ne tient pas compte des mesures calculées (recettes par visiteur, effet élévateur ou degré de confiance, par exemple) utilisées dans les tests A/B. Pour calculer ces mesures calculées, téléchargez le fichier Excel [!DNL Target] [Complete Confidence Calculator](/help/main/assets/complete_confidence_calculator.xlsx) pour saisir la valeur de l’activité, ou consultez la section [Calculs statistiques dans les tests A/B](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## [!UICONTROL Export Order Details to CSV] {#section_96B3F578F91F4CA3AFE38BACA2A0F11E}

Le rapport [!UICONTROL Order Details] présente des informations sur vos commandes, notamment :

* Date et heure de la commande
* Montant de la commande (si vous avez inséré une mbox Passer une commande)

  Le rapport [!UICONTROL Order Details] ne fonctionne que si vous avez des commandes.

* Indicateur de commande (commandes en double ou extrêmes)

  Une commande est désignée comme extrême si elle présente un écart de +/- 3 par rapport à la valeur de commande moyenne. Ce calcul utilise le dernier mois de données (jusqu’au moment auquel le calcul a été effectué). Les commandes extrêmes d’une activité sont exclues une fois que celle-ci a été exécutée pendant une heure ou après 15 commandes, selon le critère qui survient en premier. Pour plus d’informations, voir [Exclusion des commandes extrêmes](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA).

* ID de produit

  La longueur totale des identifiants de produit, concaténés avec des virgules, ne doit pas dépasser 255 caractères ou ils ne s’affichent pas correctement dans le rapport. Si, par exemple, votre commande comprend des produits avec les identifiants « aa, bb », alors la longueur totale est « aa,bb » = 5.

* Expérience

  Dans le rapport [!UICONTROL Order Details] pour les activités [!UICONTROL A/B Test], [!UICONTROL Experience Targeting] (XT) et [!UICONTROL Multivariate Test] (MVT), la colonne [!UICONTROL Experience] contient l’expérience `localId`. Il s’agit de la valeur de sortie de `$campaign.recipe.id` dans les jetons de l’offre.

  Il n’existe pas de colonne [!UICONTROL Experience] pour les activités [!UICONTROL Automated Personalization] (AP). La colonne [!UICONTROL Algorithm Name] actuelle a été remplacée par la terminologie &quot;Contrôle&quot; et &quot;Ciblé&quot;, comme indiqué ailleurs dans [!DNL Target].

  Aucun impact sur les activités [!UICONTROL Recommendations].

>[!NOTE]
>
>* Le rapport de commande comprend quatre semaines de données pour l’environnement par défaut (groupe d’hôtes) et deux semaines de données pour tous les autres environnements qui ne sont pas des environnements par défaut.
>* Les mesures de recettes définies sur &quot;[!UICONTROL Increment count and keep the user in the activity]&quot; consignent les détails de la commande uniquement pour la première commande effectuée par le même visiteur. Toutes les commandes suivantes augmentent le nombre de conversions, mais n’ajoutent pas de recettes aux recettes par visiteur/valeur de commande moyenne/ventes et ne sont pas incluses dans le rapport [!UICONTROL Order Details].

## Bonnes pratiques

* Pour enregistrer un enregistrement de commande, le paramètre `orderTotal` doit être transmis.
* Les valeurs transmises par l’intermédiaire du paramètre de mbox `ProductPurchasedId` sont répertoriées dans le rapport [!UICONTROL Order Details].
* La bonne pratique consiste à inclure un `orderID` et un `orderTotal`. Ainsi, les commandes en double seront automatiquement ignorées.

## Avertissements {#section_49B9590904A645B18E694B4EFFFC1DEF}

Les informations suivantes s’appliquent à l’option [!UICONTROL Download] :

* Vous pouvez télécharger les deux rapports pour les activités [!UICONTROL A/B Test], [!UICONTROL Automated Personalization], [!UICONTROL Experience Targeting] et [!UICONTROL Multivariate]. Vous ne pouvez pas télécharger le rapport [!UICONTROL Success Metrics] pour les activités [!UICONTROL Recommendations].
* L’option [!UICONTROL Download] n’est pas disponible pour les activités [!UICONTROL A/B Test] et [!UICONTROL Experience Targeting] créées avant [!DNL Target] version 15.7.1 (juillet 2015).
* Les expériences auxquelles aucune donnée n’est associée ne sont pas enregistrées dans le rapport téléchargé.
* Les audiences appliquées dans l’interface utilisateur de création de rapports [!DNL Target] ne sont pas transférées vers le rapport de téléchargement.
* Les rapports générés pour le téléchargement de fichiers .csv sont incohérents si l’activité utilise plusieurs mesures. Le rapport téléchargeable est généré en fonction des paramètres du rapport uniquement et prend en compte la même valeur pour toute autre mesure utilisée. La source de vérité est toujours le rapport affiché dans l’interface utilisateur de [!DNL Target].
