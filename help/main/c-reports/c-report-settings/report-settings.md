---
keywords: Target;rapports;paramètres de rapport;paramètre prédéfini;paramètre cible prédéfini;mesure;audience;période;paramètres;téléchargement;vue tabulaire;vue graphique;effet élévateur moyen;effet élévateur;limites de l’effet élévateur;intervalle de confiance;confiance;contribution des emplacements;moyenne glissante;méthodologie de calcul
description: Découvrez comment configurer les paramètres des rapports dans Adobe Target, notamment les mesures, les audiences, les plages de dates, etc.
title: Comment configurer les paramètres des rapports ?
feature: Reports
exl-id: 337579d1-c678-43b6-9e80-b5abe159c2d3
source-git-commit: 7de7bb1b3bc70a559d41edece8cae2d388cb0dda
workflow-type: tm+mt
source-wordcount: '1892'
ht-degree: 55%

---

# Paramètres des rapports

Informations pour vous aider à définir les éléments que vous souhaitez afficher dans votre rapport dans [!DNL Adobe Target]. Les paramètres des rapports peuvent être enregistrés en vue d’une utilisation ultérieure.

Pour afficher un rapport :

1. Cliquez sur **[!UICONTROL Activities]**, puis sélectionnez l’activité souhaitée dans la liste.
1. Cliquez sur l’onglet **[!UICONTROL Reports]** .

   ![Interface utilisateur des rapports](/help/main/c-reports/c-report-settings/assets/report_ui-new.png)

## Paramètre prédéfini Target {#section_51F67341465045BEB4F1A2FB638A8EB1}

Vous pouvez enregistrer jusqu’à dix paramètres prédéfinis différents du rapport d’une activité spécifique après l’avoir configuré selon vos souhaits (mesures, périodes, audiences, paramètres avancés, etc.). Tous les utilisateurs de [!DNL Target] peuvent afficher, modifier et supprimer les différents paramètres prédéfinis, quelle que soit la personne qui les a créés.

Vous pouvez également configurer le rapport d’une activité spécifique selon vos souhaits puis enregistrer cette configuration comme votre paramètre prédéfini par défaut/favori. Voici la vue qui s’affiche chaque fois que vous affichez par la suite le rapport de cette activité.

### Créer un paramètre prédéfini ou un paramètre prédéfini par défaut

1. Configurez le rapport de l’activité selon vos besoins.

   Les paramètres disponibles, notamment les mesures, les plages de dates, les audiences, les paramètres avancés, etc., sont expliqués ci-dessous.

1. En regard de **[!UICONTROL Target Preset]**, cliquez sur l’icône représentant trois points alignés verticalement > **[!UICONTROL Save as New]**.

   ![Paramètre prédéfini de rapport](/help/main/c-reports/c-report-settings/assets/report_preset-new.png)

   La boîte de dialogue Nouveau paramètre prédéfini s’affiche :

   ![Boîte de dialogue Nouveaux paramètres prédéfinis](/help/main/c-reports/c-report-settings/assets/report_preset_dialog-new.png)

1. Vérifiez les informations des sections **[!UICONTROL Filters]** et **[!UICONTROL Settings]** pour vous assurer que le rapport est configuré comme vous le souhaitez, puis spécifiez le **[!UICONTROL Preset Name]** (jusqu&#39;à 50 caractères).
1. (Conditionnel) Si vous souhaitez que ce rapport soit votre vue de rapport par défaut/favorite, faites glisser le bouton **[!UICONTROL Set as default preset]** sur la position Activé.
1. Cliquez sur **[!UICONTROL Save]**.

### Sélectionner un autre paramètre prédéfini

Sélectionnez un paramètre prédéfini dans la liste déroulante **[!UICONTROL Target Preset]**.

![Liste déroulante Paramètres prédéfinis](/help/main/c-reports/c-report-settings/assets/report_preset_drop-down-new.png)

### Modification d’un paramètre prédéfini

1. Sélectionnez le paramètre prédéfini à modifier.
1. Modifiez la configuration du rapport comme vous le souhaitez (mesures, plages de dates, audiences, paramètres avancés, etc.).

   Après avoir cliqué sur [!UICONTROL Save] après avoir modifié la configuration du rapport, un astérisque ( &#42; ) s’affiche après le nom du paramètre prédéfini pour indiquer que le paramètre prédéfini a changé, comme illustré ci-dessous :

   ![Paramètre prédéfini de rapport avec astérisque](/help/main/c-reports/c-report-settings/assets/report_preset_asterisk-new.png)

1. Cliquez sur l’icône représentant trois points alignés verticalement > **[!UICONTROL Save as New]** pour créer un paramètre prédéfini.

   Ou

   Cliquez sur l’icône représentant trois points alignés verticalement > **[!UICONTROL Update]** pour mettre à jour le paramètre prédéfini actuel.

   ![Mise à jour du rapport par défaut](/help/main/c-reports/c-report-settings/assets/report_preset_update-new.png)

### Suppression d’un paramètre prédéfini

1. Sélectionnez le paramètre prédéfini à supprimer.
1. Cliquez sur l’icône représentant trois points alignés verticalement > **[!UICONTROL Delete]**.

   ![Suppression du rapport par défaut](/help/main/c-reports/c-report-settings/assets/report_preset_delete-new.png)

1. Cliquez de nouveau sur **[!UICONTROL Delete]** pour confirmer la suppression (les paramètres prédéfinis supprimés ne peuvent pas être récupérés).

### Gestion des erreurs de paramètre prédéfini

Les alertes et les messages figurant dans les rapports vous permettent de savoir si un paramètre prédéfini n’est plus valide. L’alerte ou le message vous indique de choisir une audience, une mesure, un groupe d’hôtes ou une expérience différents pour rendre un paramètre prédéfini valide.

La liste suivante décrit certaines des situations dans lesquelles un paramètre prédéfini est susceptible de ne plus être valide :

* Une audience de rapport a été supprimée de l’activité mais est référencée dans la définition de paramètre prédéfini.
* Une ou plusieurs mesures ont été supprimées mais sont référencées dans la définition de paramètre prédéfini. Par exemple, vous pouvez supprimer une ou plusieurs mesures de l’activité, puis ajouter de nouvelles mesures.
* Un ou plusieurs groupes d’hôtes (environnement) n’existent pas mais sont référencés dans la définition de paramètre prédéfini.
* Une ou plusieurs expériences ont été supprimées après la création du paramètre prédéfini, mais sont référencées dans la définition de paramètre prédéfini.
* Un paramètre prédéfini n’est sémantiquement pas valide, car les entités référencées existent encore mais ont été mises à jour de manière telle que la définition de paramètre prédéfini a sémantiquement changé. Par exemple, supposons que vous créez un paramètre prédéfini nommé « Revenu sur Chrome ». Vous mettez par la suite l’activité à jour pour mesurer la mesure Conversion au lieu de Revenu. Cette mise à jour de la définition de l’activité invalide sémantiquement la définition de paramètre prédéfini.

## Mesure du rapport {#section_894ABD7148244806B7CE556EBBA2AD62}

Cliquez sur la liste déroulante **[!UICONTROL Report Metric]** pour sélectionner une autre [mesure de succès](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) ou plusieurs mesures à afficher dans le graphique et le graphique.

Par défaut, la mesure principale est définie dans la configuration des mesures de succès lors de la création de l’activité. Si vous modifiez la configuration et que vous réenregistrez l’activité, la mesure principale des rapports est mise à jour.

Pour plus d’informations sur la sélection de plusieurs mesures à afficher dans les rapports, voir [Affichage de plusieurs mesures dans un rapport](/help/main/c-reports/c-report-settings/view-multiple-metrics.md#concept_9E3C3F6F3EC1412FAF252975AC0720B7).

## Public {#section_70926EB4618945D9AFF2B0564FF3717B}

Cliquez sur la liste déroulante [!UICONTROL Audience] pour modifier l’audience affichée pour le rapport.

Pour plus d’informations, consultez la page [Audiences](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522).

## Période {#section_A410A768403C4E01891F95CB357E63ED}

La zone Période affiche la période actuelle du rapport. Cliquez sur l’icône déroulante pour afficher un calendrier vous permettant de changer la période du rapport.

![Calendrier](/help/main/c-reports/c-report-settings/assets/date_range-new.png)

Sélectionnez les nouvelles dates **[!UICONTROL Start]** et **[!UICONTROL End]** pour le rapport. Vous pouvez également utiliser les cases à cocher **[!UICONTROL From start of Activity]** et **[!UICONTROL Till end of Activity]** .

Cliquez sur **[!UICONTROL Custom Dates]** pour sélectionner des plages de dates prédéfinies : 7 derniers jours, 15 derniers jours ou 30 derniers jours. Ces périodes prédéfinies sont des périodes flottantes. Si la date de début est inférieure au nombre de jours choisi, le calendrier affiche la plage à partir de la date de début, mais cumulée une fois que la date de début est plus vieille que le nombre de jours sélectionné à mesure que la durée de l’activité augmente.

Les rapports comportent les restrictions de date suivantes :

* La date de début du rapport doit être comprise dans les deux dernières années.
* Les rapports de groupe d’offres sont limités à 99 jours à compter d’aujourd’hui.
* Les rapports par heure sont limités à 15 jours.

## Paramètres {#section_D99CE462107D45CABE0960F820E1E972}

Pour configurer les paramètres des rapports :

1. Cliquez sur l’icône d’engrenage, apportez les modifications souhaitées (comme expliqué ci-dessous).
1. Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé.

L’illustration ci-après présente la boîte de dialogue Paramètres pour une activité A/B :

![Boîte de dialogue Paramètres](/help/main/c-reports/c-report-settings/assets/ab_settings_dialog-new.png)

Les options varient en fonction du type d’activité sélectionné :

### Méthodologie de calcul

Choisissez la méthodologie souhaitée :

* Visiteurs
* Visites
* Impressions d’activité

### Contrôle

Sélectionnez l’expérience de contrôle à utiliser pour calculer et comparer l’effet élévateur.

### Environnement {#environment}

Sélectionnez l’environnement (groupe d’hôtes) à utiliser pour le rapport. Pour plus d’informations, voir [Hôtes](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).

>[!NOTE]
>
>Si votre entreprise utilise [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html){target=_blank} (AEP) pour envoyer des données de mesure à [!DNL Target], l’environnement de la banque de données AEP doit correspondre à l’environnement défini dans vos paramètres de rapport [!DNL Target].


### Réinitialisation des données du rapport

Réinitialisez les données de rapport pour supprimer les anciennes données. Les visiteurs actuels restent dans l’activité. Cette option est disponible uniquement pour les personnes disposant d’autorisations [!UICONTROL Approver].

>[!IMPORTANT]
>
>Cette opération est définitive et ne peut pas être annulée.

### Exclusion des valeurs extrêmes

Le bouton [!UICONTROL Exclude Extreme Values] s’applique uniquement aux activités avec des mesures de types Recettes et Engagement. Pour plus d’informations, voir [Exclusion des commandes extrêmes](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA).

## Télécharger {#section_77E65C50BAAF4AB79242DB3A8778ADEF}

Cliquez sur l’icône **[!UICONTROL Download]** pour télécharger les données de rapport au format [!DNL .csv] afin de pouvoir les importer rapidement dans Excel, Access ou d’autres programmes d’analyse des données.

![Icône Télécharger](/help/main/c-reports/c-report-settings/assets/download-icon.png)

Pour plus d’informations, voir [Téléchargement de données au format CSV](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md).

## Actualiser {#section_E203729F2F314DF3856D2EE67C60B370}

Cliquez sur l’icône **[!UICONTROL Refresh]** pour actualiser la vue tabulaire et graphique d’un rapport sans actualiser la page entière, sa configuration ou sa période.

## Autres options {#section_AB1B5C695D7045A0A0AC0E2698D2E7DE}

Cliquez sur l’icône Plus d’options (trois points alignés verticalement) pour accéder aux options [!UICONTROL Edit Activity] et [!UICONTROL View Experience URLs].

## Options d’affichage

Vous pouvez visualiser le rapport dans différents formats en fonction du type d&#39;activité. Sélectionnez une option.

![ Icônes d’options d’affichage ](/help/main/c-reports/c-report-settings/assets/view-options.png)

* **Vue Tableau** : cliquez sur l’icône **[!UICONTROL Table View]** pour afficher le rapport sous forme de tableau.
* **Vue graphique** : cliquez sur l’icône **[!UICONTROL Graph View]** pour afficher le rapport sous forme de graphique.
* **Segments automatisés** : (Disponible uniquement pour les activités Automated Personalization (AP) et de ciblage automatique (AT).) Cliquez sur l’icône **[!UICONTROL Automated Segments] pour afficher le [rapport Segments automatisés](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).
* **Attributs importants** : (Disponible uniquement pour les activités Automated Personalization (AP) et de ciblage automatique (AT).) Cliquez sur l’icône **[!UICONTROL Important Attributes] pour afficher le [rapport Attributs importants](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).

## Effet élévateur moyen, limites de l’effet élévateur et intervalle de confiance {#section_0D87615B1D3344B3858BA494EEBC16FB}

Les rapports comprennent plusieurs points de données et représentations de visualisation qui vous aident à comprendre les limites de l’effet élévateur et le degré de confiance associé à votre activité. Vous pouvez ainsi déterminer plus précisément un gagnant.

Pour plus d’informations, voir [Calculs statistiques dans les tests A/B](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

Tenez compte des points suivants :

* Disponible uniquement dans les rapports en vue Tableau.
* Cette fonctionnalité n’est pas disponible pour les activités utilisant [Analytics comme source de rapports (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

## Contribution des emplacements {#section_5832F126AC114AE1ABFFF4D9B904393B}

Cliquez sur l’icône **[!UICONTROL Location Contribution]** pour que le rapport affiche la contribution par emplacement.

## Expériences {#section_3A450DE1FA7E43F0AAB73165EC3D1C34}

(option disponible seulement dans le rapport en vue graphique)

Sélectionnez ou désélectionnez des expériences à gauche du tableau pour afficher ou masquer les expériences correspondantes dans le tableau.

Dans l’illustration suivante, seules les expériences Défaut, Moyen-Orient et Total s’affichent dans le rapport : L’expérience Asie est masquée dans le graphique.

![Expériences](/help/main/c-reports/c-report-settings/assets/report_experiences-new.png)

## Moyenne cumulée {#section_59066693158C4433B87D07402C2BC6CD}

(option disponible seulement dans le rapport en vue graphique)

&quot;Moyenne cumulée&quot; reflète les conversions cumulées (du début de la fenêtre de création de rapports à la date représentée sur le graphique) divisées par les visiteurs cumulés.

Sélectionnez la vue graphique souhaitée :

* Moyenne cumulée
* Effet élévateur moyen cumulé
* Quotidien
* Effet élévateur quotidien

![Moyenne cumulée du rapport](/help/main/c-reports/c-report-settings/assets/report_running_average-new.png)

Le nom de cette liste déroulante varie en fonction de la vue sélectionnée, mais il s’agira de l’une des vues répertoriées ci-dessus.

## Méthodologie de calcul {#section_01B0ED5665C74AE1AE97259800190C3E}

(option disponible seulement dans le rapport en vue graphique)

Vous pouvez choisir la méthodologie de calcul pour les graphiques des rapports. Notez que ceci n’est pas pris en charge pour les activités [!UICONTROL Automated Personalization] (AP).

Pour accéder à l’option [!UICONTROL Counting Methodology] lors de l’affichage d’un rapport en mode graphique, cliquez sur la liste déroulante **[!UICONTROL My Primary Goal]** , puis sélectionnez la méthodologie de calcul.

La méthodologie de calcul sera la même que celle sélectionnée dans la boîte de dialogue [!UICONTROL Settings], décrite ci-dessus.

![Méthodologie de calcul](/help/main/c-reports/c-report-settings/assets/counting_methodology_2-new.png)

Par défaut, le graphique est tracé en mode [!UICONTROL Daily].

Vous pouvez modifier le mode en cliquant sur la liste déroulante [!UICONTROL Daily] , puis en sélectionnant une option cumulative.

![Cumulé](/help/main/c-reports/c-report-settings/assets/counting_methodology-new.png)

>[!NOTE]
>
>Le nom de cette liste déroulante varie en fonction du mode sélectionné.

Il existe quatre modes pour les activités de ciblage automatique : Contrôle quotidien, Quotidien ciblé, Contrôle du cumul et Cumul ciblé.

L’ordre par défaut dans lequel le graphique est tracé est le suivant :

* **Tests A/B (y compris l’affectation automatique et Automated Personalization)** : ordre de création de l’expérience, dans l’ordre décroissant.
* **Ciblage d’expérience (XT)** : Ordre des expériences dans l’activité.
* **Test multivarié (MVT)** : Alphabétique par nom d’expérience.
* **Recommendations** : ordre de création de l’expérience, dans l’ordre décroissant.

Lorsque vous utilisez les options de la méthodologie de calcul, prenez en compte les avertissements suivants :

* Pour les [activités de ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md), il n’existe pas d’option pour sélectionner &quot;Visiteurs&quot; comme méthodologie de comptage. Le ciblage automatique est le seul type d’activité que vous ne pouvez pas représenter sous forme de graphique par visiteur.
* Pour les activités qui utilisent [Analytics comme source des rapports (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md), vous ne pouvez pas tracer de manière cumulée Visiteur, Visite ou Impression.

## Utilisation de graphiques comportant plus de 16 expériences dans l’activité

Si une activité comporte moins de 16 expériences, chaque expérience est tracée dans une couleur différente dans le graphique.

Si une activité comporte plus de 16 expériences, les lignes colorées pour les 16 premières expériences s’affichent dans le graphique. Les expériences restantes sont grisées dans le volet Expériences de gauche et aucune ligne correspondante ne s’affiche dans le graphique. Les lignes pour les 16 premières expériences peuvent être affichées à tout moment.

Si vous passez la souris sur une des expériences grisées, une nouvelle ligne grise correspondant à cette expérience s’affiche temporairement dans le graphique. Pour afficher la ligne d’une expérience grisée en couleur, vous pouvez désélectionner une expérience affichée en couleur en cliquant sur son nom, puis sélectionner l’expérience grisée souhaitée en cliquant sur son nom.

À titre d’exemple, l’illustration suivante montre le graphique d’une activité comportant 26 expériences :

![Graphique_1 image](assets/graph_1.png)

Le graphique affiche les lignes pour les 16 premières expériences (on constate quelques chevauchements qui font croire qu’il y a moins de 16 lignes). Le point coloré du volet Expériences de gauche en regard du nom de chaque expérience indique que la ligne de l’expérience s’affiche dans la couleur correspondante.

Si vous faites défiler le volet Expériences vers le bas, vous remarquerez que le nom des expériences 17 à 26 est grisé, comme illustré ci-dessous :

![Graphique_2 image](assets/graph_2.png)

Si vous passez la souris sur l’une des expériences grisées, une nouvelle ligne grise correspondant à cette expérience s’affiche temporairement dans le graphique.

Supposons que vous vouliez afficher la ligne pour l’Experience R et que vous ne vouliez pas afficher la ligne pour l’Experience P. Vous pouvez cliquer sur le nom de l’Experience P pour la désélectionner, puis cliquer sur le nom de l’Experience R pour la sélectionner, comme illustré ci-dessous :

![ {graph_3 image](assets/graph_3.png)
