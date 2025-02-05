---
keywords: rapports;télécharger les rapports;csv;mesure de succès;détails de commande
description: Découvrez comment télécharger des données d’activités d’Adobe  [!DNL Target]  format CVS pour les importer rapidement dans Excel, Access ou d’autres programmes d’analyse de données.
title: Comment Télécharger Les Données D’Un Rapport Dans Un Fichier CSV ?
feature: Reports
exl-id: b4387184-8730-4367-8bc3-52d8fbe2583e
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 34%

---

# Téléchargement des données dans un fichier CSV

Téléchargez des données au format .csv pour les importer rapidement dans des programmes d’analyse de données [!DNL Excel], [!DNL Access] ou autres.

Pour télécharger les données dans un fichier CSV, procédez comme suit :

1. Cliquez sur **[!UICONTROL Activities]**, puis sélectionnez l’activité souhaitée dans la liste.

   Si vous avez de nombreuses activités, cliquez sur l’icône Filtrer ( ![icône Filtrer](/help/main/assets/icons/Filter.svg) ) pour filtrer la liste en sélectionnant des options dans les listes déroulantes [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type] et [!UICONTROL Activity Source].

1. Cliquez sur l’onglet **[!UICONTROL Reports]** .
1. Cliquez sur l’icône **[!UICONTROL Download]** ( ![icône Télécharger](/help/main/assets/icons/Download.svg) ), puis sélectionnez un type de rapport à télécharger pour analyse dans Excel et d’autres outils.

   * [!UICONTROL Export Reports to CSV]
   * [!UICONTROL Export Order Details to CSV]

## [!UICONTROL Export Report to CSV] {#section_38BD9743EB254453B5F4A0A6F2720CD3}

Le rapport [!UICONTROL Success Metrics] vous présente des informations sur vos mesures de succès et sur les mesures suivantes, qui ne sont pas disponibles dans l’interface utilisateur de [!DNL Target] :

* Temps moyen avant conversion en heures, afin que vous sachiez en combien de temps le visiteur moyen parvient au point de conversion.
* Somme des recettes, quadratique, pour le calcul de fiabilité statistique hors ligne.

Les données sont enregistrées jusqu’au terme de l’activité.

>[!NOTE]
>
>Le rapport CSV inclut uniquement des données brutes et n’inclut pas de mesures calculées telles que les recettes par visiteur, l’effet élévateur ou le degré de confiance utilisé pour les tests A/B. Pour calculer ces mesures calculées, téléchargez le fichier Excel [!DNL Target] [Calculateur de confiance complet](/help/main/assets/complete_confidence_calculator.xlsx) pour saisir la valeur de l’activité, ou consultez [Calculs statistiques dans les tests A/B](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## [!UICONTROL Export Order Details to CSV] {#section_96B3F578F91F4CA3AFE38BACA2A0F11E}

Le rapport [!UICONTROL Order Details] affiche des informations sur vos commandes, notamment :

* Date et heure de la commande
* Montant de la commande (si vous avez inséré une mbox Passer une commande)

  Le rapport [!UICONTROL Order Details] ne fonctionne que si vous avez des commandes.

* Indicateur de commande (commandes en double ou extrêmes)

  Un ordre est marqué comme extrême s’il est supérieur à +/- 3 écarts types par rapport à la valeur d’ordre moyenne. Ce calcul utilise le dernier mois de données (jusqu’au moment où le calcul a été effectué). Les commandes extrêmes d’une activité sont exclues une fois que celle-ci a été exécutée pendant une heure ou après 15 commandes, selon le critère qui survient en premier. Pour plus d’informations, voir [Exclusion des commandes extrêmes](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA).

* ID de produit

  La longueur totale des ID de produit, concaténés avec des virgules, ne doit pas dépasser 255 caractères ou les ID ne s’affichent pas correctement dans le rapport. Si, par exemple, votre commande comprend des produits avec les identifiants « aa, bb », alors la longueur totale est « aa,bb » = 5.

* Expérience

  Dans le rapport [!UICONTROL Order Details] pour les activités [!UICONTROL A/B Test], [!UICONTROL Experience Targeting] (XT) et [!UICONTROL Multivariate Test] (MVT), la colonne [!UICONTROL Experience] contient les `localId` d’expérience. Il s’agit de la valeur de sortie de `$campaign.recipe.id` dans les jetons de l’offre.

  Il n’existe pas de colonne [!UICONTROL Experience] pour les activités [!UICONTROL Automated Personalization] (AP). La colonne [!UICONTROL Algorithm Name] actuelle a été remplacée par la terminologie « Contrôle » ou « Ciblé », comme indiqué ailleurs dans [!DNL Target].

  Il n’y a pas eu d’impact sur les activités [!UICONTROL Recommendations].

>[!NOTE]
>
>* Le rapport de commande comprend quatre semaines de données pour l’environnement par défaut (groupe d’hôtes) et deux semaines de données pour tous les autres environnements qui ne sont pas des environnements par défaut.
>* Mesures de revenus définies sur « [!UICONTROL Increment count and keep the user in the activity] » détails de commande de journal uniquement pour la première commande effectuée par le même visiteur. Toutes les commandes suivantes augmentent le nombre de conversions, mais n&#39;ajoutent pas le chiffre d&#39;affaires au RPV/AOV/Ventes et ne sont pas incluses dans l&#39;état [!UICONTROL Order Details].

## Bonnes pratiques

* Pour enregistrer un enregistrement de commande, le paramètre `orderTotal` doit être transmis.
* Les valeurs transmises par le biais du paramètre mbox `ProductPurchasedId` sont répertoriées dans le rapport [!UICONTROL Order Details].
* Il est recommandé d’inclure un `orderID` et un `orderTotal`. Ainsi, les commandes en double seront automatiquement ignorées.

## Avertissements {#section_49B9590904A645B18E694B4EFFFC1DEF}

Les informations suivantes s’appliquent à l’option [!UICONTROL Download] :

* Vous pouvez télécharger les deux rapports pour les activités [!UICONTROL A/B Test], [!UICONTROL Automated Personalization], [!UICONTROL Experience Targeting] et [!UICONTROL Multivariate]. Vous ne pouvez pas télécharger le rapport [!UICONTROL Success Metrics] pour les activités [!UICONTROL Recommendations].
* L’option [!UICONTROL Download] n’est pas disponible pour les activités [!UICONTROL A/B Test] et [!UICONTROL Experience Targeting] créées avant [!DNL Target] version 15.7.1 (juillet 2015).
* Les expériences auxquelles aucune donnée n’est associée ne sont pas enregistrées dans le rapport téléchargé.
* Les audiences appliquées dans l’interface utilisateur de création de rapports de [!DNL Target] ne sont pas transférées vers le rapport de téléchargement.
* Les rapports générés pour le téléchargement de fichiers .csv sont incohérents si l’activité utilise plusieurs mesures. Le rapport téléchargeable n’est généré qu’en fonction des paramètres du rapport et prend en compte la même valeur pour toutes les autres mesures utilisées. La source de vérité est toujours le rapport affiché dans l’interface utilisateur de [!DNL Target].
