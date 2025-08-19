---
keywords: Target;rapports;paramètres de rapport;paramètre prédéfini;paramètre cible prédéfini;mesure;audience;période;paramètres;téléchargement;vue tabulaire;vue graphique;effet élévateur moyen;effet élévateur;limites de l’effet élévateur;intervalle de confiance;confiance;contribution des emplacements;moyenne glissante;méthodologie de calcul
description: Découvrez comment configurer les paramètres des rapports dans Adobe Target, notamment les mesures, les audiences, les périodes, etc.
title: Comment Configurer Les Paramètres Des Rapports ?
feature: Reports
exl-id: 337579d1-c678-43b6-9e80-b5abe159c2d3
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '1778'
ht-degree: 48%

---

# Paramètres des rapports

Informations destinées à vous aider à définir les éléments qui doivent apparaître dans votre rapport en [!DNL Adobe Target]. Les paramètres des rapports peuvent être enregistrés en vue d’une utilisation ultérieure.

Pour afficher un rapport :

1. Cliquez sur **[!UICONTROL Activities]**, puis sélectionnez l’activité souhaitée dans la liste.
1. Cliquez sur l’onglet **[!UICONTROL Reports]** .

   ![Interface utilisateur des rapports](/help/main/c-reports/c-report-settings/assets/report-ui-refresh.png)

## Paramètre prédéfini Target {#section_51F67341465045BEB4F1A2FB638A8EB1}

Vous pouvez enregistrer jusqu’à dix paramètres prédéfinis différents du rapport d’une activité spécifique après l’avoir configuré selon vos souhaits (mesures, périodes, audiences, paramètres avancés, etc.). Tous les utilisateurs d’[!DNL Target] peuvent afficher, modifier et supprimer les différents paramètres prédéfinis, quelle que soit la personne qui les a créés.

Vous pouvez également configurer le rapport d’une activité spécifique selon vos souhaits puis enregistrer cette configuration comme votre paramètre prédéfini par défaut/favori. Voici la vue qui s’affiche chaque fois que vous affichez par la suite le rapport de cette activité.

### Création d’un paramètre prédéfini ou d’un paramètre prédéfini par défaut

1. Configurez le rapport d’activité selon vos besoins.

   Les paramètres disponibles, notamment les mesures, les périodes, les audiences, les paramètres avancés, etc., sont expliqués ci-dessous.

1. En regard de **[!UICONTROL Target Preset]**, cliquez sur l’icône **[!UICONTROL More Options]** ( ![icône Plus d’options](/help/main/assets/icons/MoreSmallListVert.svg) ) > **[!UICONTROL Save as New]**.

   La boîte de dialogue [!UICONTROL Create Preset] s’affiche.

   ![Boîte de dialogue Nouveaux paramètres prédéfinis](/help/main/c-reports/c-report-settings/assets/report_preset_dialog-new.png)

1. Passez en revue les informations des sections **[!UICONTROL Filters]** pour vous assurer que le rapport est configuré comme vous le souhaitez, puis spécifiez le **[!UICONTROL Preset Name]** (50 caractères maximum).
1. (Conditionnel) Si vous souhaitez qu’il s’agisse de l’affichage de rapport par défaut/favori, faites glisser le bouton **[!UICONTROL Set as default preset]** sur la position Activé .
1. Cliquez sur **[!UICONTROL Create]**.

### Sélectionner un autre paramètre prédéfini

Sélectionnez le paramètre prédéfini de votre choix dans la liste déroulante **[!UICONTROL Target Preset]** .

### Modification d’un paramètre prédéfini

1. Sélectionnez le paramètre prédéfini à modifier.
1. Modifiez la configuration du rapport comme vous le souhaitez (mesures, plages de dates, audiences, paramètres avancés, etc.).

   Après avoir cliqué sur [!UICONTROL Save] après modification de la configuration du rapport, un astérisque ( &#42; ) s’affiche après le nom du paramètre prédéfini pour indiquer que celui-ci a été modifié.

1. Cliquez sur l’icône **[!UICONTROL More Options]** ( ![icône Plus d’options](/help/main/assets/icons/MoreSmallListVert.svg) ) > **[!UICONTROL Save as New]** pour créer un paramètre prédéfini.

### Suppression d’un paramètre prédéfini

1. Sélectionnez le paramètre prédéfini à supprimer.
1. Cliquez sur l’icône **[!UICONTROL More Options]** ( ![icône Plus d’options](/help/main/assets/icons/MoreSmallListVert.svg) ) > **[!UICONTROL Delete]**.

1. Cliquez à nouveau sur **[!UICONTROL Delete]** pour confirmer votre suppression (les préréglages supprimés ne peuvent pas être récupérés).

### Gestion des erreurs de préréglage

Les alertes et les messages figurant dans les rapports vous permettent de savoir si un paramètre prédéfini n’est plus valide. L’alerte ou le message vous indique de choisir une audience, une mesure, un groupe d’hôtes ou une expérience différents pour rendre un paramètre prédéfini valide.

La liste suivante décrit certaines des situations dans lesquelles un paramètre prédéfini est susceptible de ne plus être valide :

* Une audience de rapport a été supprimée de l’activité mais est référencée dans la définition de paramètre prédéfini.
* Une ou plusieurs mesures ont été supprimées mais sont référencées dans la définition de paramètre prédéfini. Par exemple, vous pouvez supprimer une ou plusieurs mesures de l’activité, puis ajouter de nouvelles mesures.
* Un ou plusieurs groupes d’hôtes (environnement) n’existent pas mais sont référencés dans la définition de paramètre prédéfini.
* Une ou plusieurs expériences ont été supprimées après la création du paramètre prédéfini, mais sont référencées dans la définition de paramètre prédéfini.
* Un paramètre prédéfini n’est sémantiquement pas valide, car les entités référencées existent encore mais ont été mises à jour de manière telle que la définition de paramètre prédéfini a sémantiquement changé. Par exemple, supposons que vous créez un paramètre prédéfini nommé « Revenu sur Chrome ». Vous mettez par la suite l’activité à jour pour mesurer la mesure Conversion au lieu de Revenu. Cette mise à jour de la définition de l’activité invalide sémantiquement la définition du préréglage.

## [!UICONTROL Report Metric] {#section_894ABD7148244806B7CE556EBBA2AD62}

Cliquez sur la liste déroulante **[!UICONTROL Report Metric]** pour sélectionner une ou plusieurs mesures de [succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) à afficher dans le graphique et le graphique.

Par défaut, la mesure principale est définie dans la configuration des mesures de succès lors de la création de l’activité. Si vous modifiez la configuration et que vous réenregistrez l’activité, la mesure principale des rapports est mise à jour.

Pour plus d’informations sur la sélection de plusieurs mesures à afficher dans les rapports, voir [Affichage de plusieurs mesures dans un rapport](/help/main/c-reports/c-report-settings/view-multiple-metrics.md#concept_9E3C3F6F3EC1412FAF252975AC0720B7).

## [!UICONTROL Audience] {#section_70926EB4618945D9AFF2B0564FF3717B}

Cliquez sur la liste déroulante **[!UICONTROL Audience]** pour modifier l’audience affichée pour le rapport.

Pour plus d’informations, consultez la page [Audiences](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522).

## [!UICONTROL Preset Date Range]

Cliquez sur la liste déroulante **[!UICONTROL Preset Date Range]** pour effectuer votre choix parmi des périodes prédéfinies.

Sélectionnez de nouvelles **[!UICONTROL Start]** et dates de **[!UICONTROL End]** pour le rapport. Vous pouvez également utiliser les plages de **[!UICONTROL Start of Activity]** et de **[!UICONTROL Start of activity - End of Activity]**.

Les périodes prédéfinies sont les suivantes : 7 derniers jours, 15 derniers jours ou 30 derniers jours. Ces périodes prédéfinies sont des périodes flottantes. Si la date de début est inférieure au nombre de jours choisi, le calendrier affiche la plage à partir de la date de début, mais continue une fois que la date de début est antérieure au nombre de jours choisi à mesure que la durée de l&#39;activité augmente.

Les rapports comportent les restrictions de date suivantes :

* La date de début du rapport doit être comprise dans les deux dernières années.
* Les rapports de groupe d’offres sont limités à 99 jours à compter de ce jour.
* Les rapports par heure sont limités à 15 jours.

## Période {#section_A410A768403C4E01891F95CB357E63ED}

La zone de [!UICONTROL Date Range] affiche la période actuelle du rapport. Cliquez sur l’icône **[!UICONTROL Calendar]** ( ![icône Calendrier](/help/main/assets/icons/Calendar.svg) ) pour afficher un calendrier qui vous permet de modifier la période du rapport.

## Paramètres {#section_D99CE462107D45CABE0960F820E1E972}

Pour configurer les paramètres de rapport :

1. Cliquez sur l’icône **[!UICONTROL Report Settings]** ( ![icône Paramètres de rapport](/help/main/assets/icons/Setting.svg) ), apportez les modifications souhaitées (comme expliqué ci-dessous).
1. Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé.

Les options varient en fonction du type d’activité sélectionné :

### Méthodologie de calcul

Sélectionnez la méthodologie souhaitée :

* Visiteurs
* Visites
* Impressions d’activité

### Contrôle

Sélectionnez l’expérience de contrôle à utiliser lors du calcul et de la comparaison de l’effet élévateur.

### Environnement {#environment}

Sélectionnez l’environnement (groupe d’hôtes) à utiliser pour le rapport. Pour plus d’informations, voir [Hôtes](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).

>[!NOTE]
>
>Si votre organisation utilise [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html){target=_blank} (AEP) pour envoyer des données de mesures à [!DNL Target], l’environnement du flux de données AEP doit correspondre à l’environnement dans les paramètres de votre rapport [!DNL Target].

### Réinitialisation des données du rapport

Cliquez sur [!UICONTROL Reset Report Data]. Réinitialisez les données de rapport pour supprimer les anciennes données. Les visiteurs actuels restent dans l’activité.  Cette option n’est disponible que pour les personnes disposant d’autorisations [!UICONTROL Approver].

>[!IMPORTANT]
>
>Cette opération est définitive et ne peut pas être annulée.

Exclusion des valeurs extrêmes

Le bouton [!UICONTROL Exclude Extreme Values] s’applique uniquement aux activités avec les types de mesures Revenu et Engagement . Pour plus d’informations, voir [Exclusion des commandes extrêmes](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA).

## Télécharger {#section_77E65C50BAAF4AB79242DB3A8778ADEF}

Cliquez sur l’icône **[!UICONTROL Download]** ( ![icône Télécharger](/help/main/assets/icons/Download.svg) ) pour télécharger les données de rapport dans un format [!DNL .csv] en vue d’un import rapide dans Excel, Access ou d’autres programmes d’analyse de données.

Pour plus d’informations, voir [Téléchargement de données au format CSV](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md).

## Actualiser {#section_E203729F2F314DF3856D2EE67C60B370}

Cliquez sur l’icône **[!UICONTROL Refresh]** ( ![icône Actualiser](/help/main/assets/icons/Refresh.svg) ) pour actualiser la vue tableau et graphique d’un rapport sans actualiser la page entière, sa configuration ou sa période.

## Plus d’options {#section_AB1B5C695D7045A0A0AC0E2698D2E7DE}

Cliquez sur l’icône **[!UICONTROL More Options]** ( ![icône Plus d’options](/help/main/assets/icons/MoreSmallListVert.svg) ) pour accéder aux options [!UICONTROL Save as New] et [!UICONTROL Delete].

## Afficher les options

Vous pouvez afficher le rapport dans différents formats en fonction du type d’activité. Sélectionnez l’option souhaitée.

* **Vue Tableau** : cliquez sur l’icône **[!UICONTROL Table View]** ( ![icône Vue Tableau](/help/main/assets/icons/Table.svg) ) pour afficher le rapport sous la forme d’un tableau.
* **Vue Graphique** : cliquez sur l’icône **[!UICONTROL Graph View]** ( ![icône Vue Graphique](/help/main/assets/icons/GraphTrend.svg) ) pour afficher le rapport sous forme de graphique.
* **Segments automatisés** : (disponible uniquement pour les activités [!UICONTROL Automated Personalization] (AP) et [!UICONTROL Auto-Target] (AT).) Cliquez sur l’icône **[!UICONTROL Automated Segments] ( ![icône Segments automatisés](/help/main/assets/icons/AutomatedSegment.svg) ) pour afficher le rapport [Segments automatisés](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).
* **Attributs importants** : (disponible uniquement pour les activités [!DNL Automated Personalization] (AP) et [!UICONTROL Auto-Target] (AT).) Cliquez sur l’icône **[!UICONTROL Important Attributes]** ( ![icône Attributs importants](/help/main/assets/icons/ViewList.svg) ) pour afficher le rapport [Attributs importants](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).

## Effet élévateur moyen, limites de l’effet élévateur et intervalle de confiance {#section_0D87615B1D3344B3858BA494EEBC16FB}

Les rapports comprennent plusieurs points de données et représentations de visualisation qui vous aident à comprendre les limites de l’effet élévateur et le degré de confiance associé à votre activité. Vous pouvez ainsi déterminer plus précisément un gagnant.

Pour plus d’informations, voir [Calculs statistiques dans les tests A/B](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

Tenez compte des points suivants :

* Disponible uniquement lors de l’affichage de rapports dans [!UICONTROL Table View].
* Cette fonctionnalité n’est pas disponible pour les activités utilisant [Analytics comme source de rapports (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

## Contribution des emplacements {#section_5832F126AC114AE1ABFFF4D9B904393B}

Cliquez sur l’icône [[!UICONTROL Location Contribution]](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) ( ![icône Contribution des emplacements](/help/main/assets/icons/LocationContribution.svg) ) pour changer le rapport et afficher la contribution par emplacement pour les activités de test multivarié (MVT).

## Expériences {#section_3A450DE1FA7E43F0AAB73165EC3D1C34}

Disponible uniquement lors de l’affichage du rapport dans [!UICONTROL Graph View].

Sélectionnez ou désélectionnez des expériences à gauche du tableau pour afficher ou masquer les expériences correspondantes dans le tableau.

## Moyenne cumulée {#section_59066693158C4433B87D07402C2BC6CD}

Disponible uniquement lors de l’affichage du rapport dans [!UICONTROL Graph View].

« Moyenne glissante » reflète les conversions cumulées (du début de la fenêtre de création de rapports à la date représentée sur le graphique) divisées par les visiteurs cumulés.

Sélectionnez la vue graphique souhaitée :

* Moyenne cumulée
* Effet élévateur moyen cumulé
* Quotidien
* Effet élévateur quotidien

Le nom de cette liste déroulante varie en fonction de la vue sélectionnée, mais il s’agira de l’une des vues répertoriées ci-dessus.

## Méthodologie de calcul {#section_01B0ED5665C74AE1AE97259800190C3E}

Disponible uniquement lors de l’affichage du rapport dans [!UICONTROL Graph View].

Vous pouvez choisir la méthodologie de calcul pour les graphiques des rapports. Notez que cela n’est pas pris en charge pour les activités [!UICONTROL Automated Personalization] (AP).

Pour accéder à l&#39;option [!UICONTROL Counting Methodology], lorsque vous affichez un rapport en mode graphique, cliquez sur la liste déroulante **[!UICONTROL My Primary Goal]**, puis sélectionnez la méthodologie de comptage.

La méthode de comptage sera la même que celle sélectionnée dans la boîte de dialogue [!UICONTROL Settings], décrite ci-dessus.

Par défaut, le graphique est tracé en mode [!UICONTROL Daily].

Vous pouvez changer de mode en cliquant sur la liste déroulante [!UICONTROL Daily] , puis en sélectionnant une option de cumul.

>[!NOTE]
>
>Le nom de cette liste déroulante varie en fonction du mode sélectionné.

Il existe quatre modes pour [!UICONTROL Auto-Target] activités : [!UICONTROL Daily Control], [!UICONTROL Daily Targeted], [!UICONTROL Cumulative Control] et [!UICONTROL Cumulative Targeted].

L’ordre par défaut dans lequel le graphique est tracé est le suivant :

* **[!UICONTROL A/B Test](y compris [!UICONTROL Auto-Allocate] et [!UICONTROL Automated Personalization])** : ordre de création de l’expérience, par ordre décroissant.
* **[!UICONTROL Experience Targeting](XT)** : ordre des expériences dans l’activité.
* **[!UICONTROL Multivariate Test](MVT)** : Alphabétique par nom d’expérience.
* **[!UICONTROL Recommendations]** : ordre de création de l’expérience, par ordre décroissant.

Lorsque vous utilisez les options de [!UICONTROL Counting Methodology], tenez compte des avertissements suivants :

* Pour [[!UICONTROL Auto-Target] activités](/help/main/c-activities/auto-target/auto-target-to-optimize.md) il n’est pas possible de sélectionner « Visiteurs » comme méthode de comptage. [!UICONTROL Auto-Target] est le seul type d’activité que vous ne pouvez pas tracer pour les visiteurs.
* Pour les activités qui utilisent [Analytics comme source de création de rapports (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md), vous ne pouvez pas tracer de manière cumulative Visiteur, Visite ou Impression.

## Utiliser des graphiques comportant plus de 16 expériences dans l’activité

Si une activité comporte moins de 16 expériences, chaque expérience est tracée dans une couleur différente dans le graphique.

Si une activité comporte plus de 16 expériences, les lignes colorées pour les 16 premières expériences s’affichent dans le graphique. Les expériences restantes sont grisées dans le volet Expériences de gauche et aucune ligne correspondante ne s’affiche dans le graphique. Les lignes pour les 16 premières expériences peuvent être affichées à tout moment.

Si vous passez la souris sur une des expériences grisées, une nouvelle ligne grise correspondant à cette expérience s’affiche temporairement dans le graphique. Pour afficher la ligne d’une expérience grisée en couleur, vous pouvez désélectionner une expérience affichée en couleur en cliquant sur son nom, puis sélectionner l’expérience grisée souhaitée en cliquant sur son nom.

Le graphique affiche les lignes pour les 16 premières expériences (on constate quelques chevauchements qui font croire qu’il y a moins de 16 lignes). Le point coloré du volet Expériences de gauche en regard du nom de chaque expérience indique que la ligne de l’expérience s’affiche dans la couleur correspondante.

Si vous faites défiler le volet Expériences vers le bas, vous remarquerez que le nom des expériences 17 à 26 est grisé, comme illustré ci-dessous :

Si vous passez la souris sur l’une des expériences grisées, une nouvelle ligne grise correspondant à cette expérience s’affiche temporairement dans le graphique.

Supposons que vous vouliez afficher la ligne pour l’Experience R et que vous ne vouliez pas afficher la ligne pour l’Experience P. Vous pouvez cliquer sur le nom de l’Experience P pour la désélectionner, puis cliquer sur le nom de l’Experience R pour la sélectionner, comme illustré ci-dessous :
