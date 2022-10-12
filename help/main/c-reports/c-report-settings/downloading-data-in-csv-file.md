---
keywords: rapports;télécharger les rapports;csv;mesure de succès;détails de commande
description: Découvrez comment télécharger des données depuis Adobe [!DNL Target] activités au format CVS pour une importation rapide dans Excel, Access ou d’autres programmes d’analyse des données.
title: Comment Télécharger Des Données De Rapport Dans Un Fichier CSV ?
feature: Reports
exl-id: b4387184-8730-4367-8bc3-52d8fbe2583e
source-git-commit: fc1dcc2b6de1248c35191c1ecd7b36aeb891fd3f
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 54%

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

## [!UICONTROL Exportation du rapport au format CSV] {#section_38BD9743EB254453B5F4A0A6F2720CD3}

Le [!UICONTROL Mesures de succès] Ce rapport présente des informations sur vos mesures de succès, ainsi que les mesures suivantes, qui ne sont pas disponibles dans la variable [!DNL Target] Interface utilisateur :

* Temps moyen avant conversion en heures, afin que vous sachiez en combien de temps le visiteur moyen parvient au point de conversion.
* Somme des recettes, quadratique, pour le calcul de fiabilité statistique hors ligne.

Les données sont enregistrées jusqu’au terme de l’activité.

>[!NOTE]
>
>Le rapport CSV comprend uniquement des données brutes. Il ne tient pas compte des mesures calculées (recettes par visiteur, effet élévateur ou degré de confiance, par exemple) utilisées dans les tests A/B. Pour calculer ces mesures calculées, téléchargez le [!DNL Target] [Calculateur de confiance complet](/help/main/assets/complete_confidence_calculator.xlsx) Fichier Excel pour saisir la valeur de l’activité ou revoir [Calculs statistiques dans les tests A/B](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## [!UICONTROL Exportation des détails des commandes au format CSV] {#section_96B3F578F91F4CA3AFE38BACA2A0F11E}

Le [!UICONTROL Détails de la commande] Ce rapport présente des informations sur vos commandes, notamment :

* Date et heure de la commande
* Montant de la commande (si vous avez inséré une mbox Passer une commande)

   Le [!UICONTROL Détails de la commande] fonctionne uniquement si vous avez des commandes.

* Indicateur de commande (commandes en double ou extrêmes)

   Une commande est désignée comme extrême si elle présente un écart de +/- 3 par rapport à la valeur de commande moyenne. Ce calcul utilise le dernier mois de données (jusqu’au moment auquel le calcul a été effectué). Les commandes extrêmes d’une activité sont exclues une fois que celle-ci a été exécutée pendant une heure ou après 15 commandes, selon le critère qui survient en premier. Pour plus d’informations, voir [Exclusion des commandes extrêmes](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA).

* ID de produit

   La longueur totale des identifiants de produit, concaténés avec des virgules, ne doit pas dépasser 255 caractères ou ils ne s’affichent pas correctement dans le rapport. Si, par exemple, votre commande comprend des produits avec les identifiants « aa, bb », alors la longueur totale est « aa,bb » = 5.

* Expérience

   Dans le rapport [!UICONTROL Détails de la commande] concernant les [!UICONTROL tests A/B], le [!UICONTROL ciblage d’expérience] (XT) et les [!UICONTROL tests multivariés] (MVT), la colonne [!UICONTROL Expérience] contient l’expérience `localId`. Il s’agit de la valeur de sortie de `$campaign.recipe.id` dans les jetons de l’offre.

   Il n’existe pas de colonne [!UICONTROL Expérience] pour les activités d’[!UICONTROL Automated Personalization]. La colonne [!UICONTROL Nom de l’algorithme] actuelle a été remplacée par la terminologie « Contrôle » contre « Ciblé », tel qu’indiqué à un autre emplacement de [!DNL Target].

   Cela n’a aucun impact sur les activités de [!UICONTROL Recommandations].

>[!NOTE]
>
>* Le rapport de commande comprend quatre semaines de données pour l’environnement par défaut (groupe d’hôtes) et deux semaines de données pour tous les autres environnements qui ne sont pas des environnements par défaut.
>* Mesures de recettes définies sur &quot;[!UICONTROL Incrémenter le décompte et laisser l’utilisateur dans l’activité]&quot; consigne les détails de la commande uniquement pour la première commande effectuée par le même visiteur. Toutes les commandes suivantes augmentent le nombre de conversions, mais n’ajoutent pas de recettes aux recettes par visiteur/valeur de commande moyenne/ventes et ne sont pas incluses dans la variable [!UICONTROL Détails de la commande] rapport.


## Bonnes pratiques

* Pour enregistrer un enregistrement de commande, la variable `orderTotal` doit être transmis.
* Les valeurs transmises par l’intermédiaire du paramètre de mbox `ProductPurchasedId` sont désormais répertoriées dans le rapport Détails de la commande.
* La bonne pratique consiste à inclure une `orderID` et un `orderTotal`. Ainsi, les commandes en double seront automatiquement ignorées.

## Avertissements {#section_49B9590904A645B18E694B4EFFFC1DEF}

Les informations suivantes s’appliquent à la variable [!UICONTROL Télécharger] option :

* Vous pouvez télécharger les deux rapports pour [!UICONTROL Test A/B], [!UICONTROL Automated Personalization], [!UICONTROL Ciblage d’expérience], et [!UICONTROL Multivariate] activités. Vous ne pouvez pas télécharger le fichier [!UICONTROL Mesures de succès] rapport pour [!UICONTROL Recommendations] activités.
* Le [!UICONTROL Télécharger] n’est pas disponible pour [!UICONTROL Test A/B] et [!UICONTROL Ciblage d’expérience] activités créées avant [!DNL Target] version 15.7.1 (juillet 2015).
* Les expériences auxquelles aucune donnée n’est associée ne sont pas enregistrées dans le rapport téléchargé.
* Audiences appliquées dans [!DNL Target] l’interface utilisateur de création de rapports n’est pas transférée vers le rapport de téléchargement.
* Les rapports générés pour le téléchargement de fichiers .csv sont incohérents si l’activité utilise plusieurs mesures. Le rapport téléchargeable n’est généré qu’en fonction des paramètres du rapport et prend en compte la même valeur pour toute autre mesure utilisée. La source de vérité est toujours le rapport affiché dans l’interface utilisateur de [!DNL Target].
