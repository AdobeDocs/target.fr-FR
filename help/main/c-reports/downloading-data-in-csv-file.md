---
keywords: rapports;télécharger les rapports;csv;mesure de succès;détails de commande
description: Découvrez comment télécharger des données depuis Adobe [!DNL Target] activités au format CVS pour une importation rapide dans Excel, Access ou d’autres programmes d’analyse des données.
title: Comment Télécharger Des Données De Rapport Dans Un Fichier CSV ?
feature: Reports
exl-id: b4387184-8730-4367-8bc3-52d8fbe2583e
source-git-commit: 493ecd762b5228d33377ac8263b90a0f9c73127e
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 83%

---

# Téléchargement des données dans un fichier CSV

Téléchargez les données au format .csv afin de pouvoir les importer rapidement dans Excel, Access ou d’autres programmes d’analyse des données.

Pour télécharger les données dans un fichier CSV, procédez comme suit :

1. Cliquez sur **[!UICONTROL Activités]**, puis sélectionnez l’activité souhaitée dans la liste.

   Si vous avez beaucoup d’activités, vous pouvez filtrer la liste en sélectionnant des options dans les listes déroulantes [!UICONTROL Type], [!UICONTROL État], [!UICONTROL Source de rapports], [!UICONTROL Compositeur d’expérience], [!UICONTROL Type de mesure] et [!UICONTROL Source d’activité].

1. Cliquez sur l’onglet **[!UICONTROL Rapports]**.
1. Cliquez sur l’icône **[!UICONTROL Télécharger]**, puis sélectionnez un type de rapport à télécharger pour une analyse dans Excel et d’autres outils.

   * [!UICONTROL Exportation de rapports au format CSV]
   * [!UICONTROL Exportation des détails des commandes au format CSV]

   ![Options de téléchargement](/help/main/c-reports/assets/download-options.png)

## Exportation du rapport au format CSV {#section_38BD9743EB254453B5F4A0A6F2720CD3}

Le rapport Mesures de succès contient des renseignements sur les mesures de succès, ainsi que les mesures suivantes, absentes de l’interface utilisateur de Target :

* Temps moyen avant conversion en heures, afin que vous sachiez en combien de temps le visiteur moyen parvient au point de conversion.
* Somme des recettes, quadratique, pour le calcul de fiabilité statistique hors ligne.

Les données sont enregistrées jusqu’au terme de l’activité.

>[!NOTE]
>
>Le rapport CSV comprend uniquement des données brutes. Il ne tient pas compte des mesures calculées (recettes par visiteur, effet élévateur ou degré de confiance, par exemple) utilisées dans les tests A/B. Pour calculer ces mesures calculées, téléchargez le [Calculateur de confiance complet](/help/main/assets/complete_confidence_calculator.xlsx) Fichier Excel pour saisir la valeur de l’activité ou revoir [Calculs statistiques dans les tests A/B](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## Exportation des détails des commandes au format CSV {#section_96B3F578F91F4CA3AFE38BACA2A0F11E}

Le rapport Détails de la commande présente des informations sur vos commandes, notamment :

* Date et heure de la commande
* Montant de la commande (si vous avez inséré une mbox Passer une commande)

   Le rapport Détails de la commande fonctionne seulement s’il y a des commandes.

* Indicateur de commande (commandes en double ou extrêmes)

   Une commande est considérée comme extrême lorsqu’elle présente un écart de +/- 3 par rapport à la valeur de commande moyenne en utilisant le dernier mois de données (jusqu’au moment auquel le calcul a été effectué). Les commandes extrêmes d’une activité sont exclues une fois que celle-ci a été exécutée pendant une heure ou après 15 commandes, selon le critère qui survient en premier. Pour plus d’informations, voir [Exclusion des commandes extrêmes](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA).

* ID de produit

   Les identifiants de produit, concaténés avec les virgules, ne peuvent pas comprendre plus de 255 caractères au total ; sinon, ils ne s’afficheront pas correctement dans le rapport. Si, par exemple, votre commande comprend des produits avec les identifiants « aa, bb », alors la longueur totale est « aa,bb » = 5.

* Expérience

   Dans le rapport [!UICONTROL Détails de la commande] concernant les [!UICONTROL tests A/B], le [!UICONTROL ciblage d’expérience] (XT) et les [!UICONTROL tests multivariés] (MVT), la colonne [!UICONTROL Expérience] contient l’expérience `localId`. Il s’agit de la valeur de sortie de `$campaign.recipe.id` dans les jetons de l’offre.

   Il n’existe pas de colonne [!UICONTROL Expérience] pour les activités d’[!UICONTROL Automated Personalization]. La colonne [!UICONTROL Nom de l’algorithme] actuelle a été remplacée par la terminologie « Contrôle » contre « Ciblé », tel qu’indiqué à un autre emplacement de [!DNL Target].

   Cela n’a aucun impact sur les activités de [!UICONTROL Recommandations].

>[!NOTE]
>
>* Le rapport de commande comprend quatre semaines de données pour l’environnement par défaut (groupe d’hôtes) et deux semaines de données pour tous les autres environnements qui ne sont pas des environnements par défaut.
>* Les mesures Recettes définies sur « Incrémenter le décompte et laisser l’utilisateur dans l’activité » enregistrent les détails des commandes seulement pour la première commande effectuée par le même visiteur. Toutes les commandes ultérieures augmentent le nombre de conversions, mais n’apportent pas de recettes aux recettes par visite (RPV)/à la valeur de commande moyenne (AOV)/aux ventes et ne sont pas incluses dans le rapport Détails de la commande.


## Bonnes pratiques

* Pour enregistrer un rapport de commande, le paramètre `orderTotal` doit être transmis.
* Les valeurs transmises par l’intermédiaire du paramètre de mbox `ProductPurchasedId` sont désormais répertoriées dans le rapport Détails de la commande.
* Outre le paramètre `orderID`, la bonne pratique consiste à inclure également un paramètre `orderTotal`. Ainsi, les commandes en double seront automatiquement ignorées.

## Avertissements {#section_49B9590904A645B18E694B4EFFFC1DEF}

Les informations suivantes s’appliquent à l’option de téléchargement :

* Vous pouvez télécharger les deux rapports pour les activités de test A/B, Automated Personalization, de ciblage d’expérience et multivariées. Vous ne pouvez pas télécharger le rapport Mesures de succès pour les activités de recommandation.
* L’option de téléchargement n’est pas disponible pour les activités A/B et de ciblage d’expérience créées avant Target version 15.7.1 (juillet 2015).
* Les expériences auxquelles aucune donnée n’est associée ne sont pas enregistrées dans le rapport téléchargé.
* Les audiences appliquées dans l’interface utilisateur de création de rapports Target ne sont pas transférées dans le rapport de téléchargement.
