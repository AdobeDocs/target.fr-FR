---
keywords: Target;reports;report settings;preset;target preset;metric;audience;date range;settings;download;table view;graph view;average lift;lift;lift bound;confidence interval;confidence;location contribution;running average;counting methodology
description: Informations destinées à vous aider à définir les éléments que vous souhaitez voir apparaître dans votre rapport. Les paramètres des rapports peuvent être enregistrés en vue d’une utilisation ultérieure.
title: Paramètres des rapports
feature: report settings
uuid: c3463f0d-8f09-4be2-9c85-f933578cce50
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '1878'
ht-degree: 83%

---


# Paramètres des rapports{#report-settings}

Informations destinées à vous aider à définir les éléments que vous souhaitez voir apparaître dans votre rapport. Les paramètres des rapports peuvent être enregistrés en vue d’une utilisation ultérieure.

Pour afficher un rapport, cliquez sur **[!UICONTROL Activités]**, sélectionnez une activité dans la liste, puis cliquez sur l’onglet **[!UICONTROL Rapports.]**

![Interface utilisateur des rapports](/help/c-reports/c-report-settings/assets/report_ui-new.png)

## Paramètre prédéfini Target {#section_51F67341465045BEB4F1A2FB638A8EB1}

Vous pouvez enregistrer jusqu’à dix paramètres prédéfinis différents du rapport d’une activité spécifique après l’avoir configuré selon vos souhaits (mesures, plages de dates, audiences, paramètres avancés, etc.). Tous les utilisateurs de Target peuvent afficher, modifier et supprimer les divers paramètres prédéfinis, quel qu’en soit l’auteur.

Vous pouvez également configurer le rapport d’une activité spécifique selon vos souhaits puis enregistrer cette configuration comme votre paramètre prédéfini par défaut/favori. Voici la vue qui s’affiche chaque fois que vous affichez par la suite le rapport de cette activité.

### Création d’un paramètre prédéfini ou d’un paramètre prédéfini par défaut

1. Configurez le rapport activité selon vos besoins.

   Les paramètres disponibles, notamment les mesures, les plages de dates, les audiences, les paramètres avancés, etc., sont expliqués ci-dessous.

1. Cliquez sur l’icône représentant trois points alignés verticalement > **[!UICONTROL Enregistrer comme nouveau]**, à côté de **[!UICONTROL Paramètre prédéfini Target]**.

   ![Paramètre prédéfini de rapport](/help/c-reports/c-report-settings/assets/report_preset-new.png)

   La boîte de dialogue Nouveau paramètre prédéfini s’affiche :

   ![Boîte de dialogue Nouveaux paramètres prédéfinis](/help/c-reports/c-report-settings/assets/report_preset_dialog-new.png)

1. Vérifiez les informations des sections Filtres et Paramètres pour vous assurer que le rapport est configuré comme souhaité, puis spécifiez le **[!UICONTROL Nom de paramètre prédéfini]** (jusqu’à 50 caractères).
1. (Conditionnel) Si vous souhaitez que ce paramètre prédéfini soit votre vue de rapport par défaut/favorite, faites glisser la bascule **[!UICONTROL Définir comme paramètre prédéfini par défaut]** sur la position Activé.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

### Sélectionner un autre paramètre prédéfini

Sélectionnez le paramètre prédéfini voulu dans la liste déroulante **[!UICONTROL Paramètre prédéfini Target]**.

![Liste déroulante Paramètres prédéfinis](/help/c-reports/c-report-settings/assets/report_preset_drop-down-new.png)

### Modifier un paramètre prédéfini

1. Sélectionnez le paramètre prédéfini à modifier.
1. Modifiez la configuration du rapport comme vous le souhaitez (mesures, plages de dates, audiences, paramètres avancés, etc.).

   Lorsque vous cliquez sur [!UICONTROL Enregistrer] après avoir modifié la configuration du rapport, un astérisque ( * ) s’affiche après le nom du paramètre prédéfini pour indiquer que le paramètre prédéfini a changé, comme illustré ci-dessous :

   ![Paramètre prédéfini de rapport avec astérisque](/help/c-reports/c-report-settings/assets/report_preset_asterisk-new.png)

1. Cliquez sur l’icône représentant trois points alignés verticalement > **[!UICONTROL Enregistrer comme nouveau]** pour créer un nouveau paramètre prédéfini.

   OU

   Cliquez sur l’icône représentant trois points alignés verticalement > **[!UICONTROL Mettre à jour]**, pour mettre à jour le paramètre prédéfini actuel.

   ![Mise à jour du rapport par défaut](/help/c-reports/c-report-settings/assets/report_preset_update-new.png)

### Suppression d’un paramètre prédéfini

1. Sélectionnez le paramètre prédéfini à supprimer.
1. Cliquez sur l’icône représentant trois points alignés verticalement > **[!UICONTROL Supprimer]**.

   ![Suppression du rapport par défaut](/help/c-reports/c-report-settings/assets/report_preset_delete-new.png)

1. Cliquez de nouveau sur **[!UICONTROL Supprimer]** pour confirmer la suppression.

### Gestion des erreurs prédéfinies

Les alertes et les messages figurant dans les rapports vous permettent de savoir si un paramètre prédéfini n’est plus valide. L’alerte ou le message vous indique de choisir une audience, une mesure, un groupe d’hôtes ou une expérience différents pour rendre un paramètre prédéfini valide.

La liste suivante décrit certaines des situations dans lesquelles un paramètre prédéfini est susceptible de ne plus être valide :

* Une audience de rapport a été supprimée de l’activité mais est référencée dans la définition de paramètre prédéfini.
* Une ou plusieurs mesures ont été supprimées mais sont référencées dans la définition de paramètre prédéfini. Par exemple, vous pouvez supprimer une ou plusieurs mesures de l’activité, puis ajouter de nouvelles mesures.
* Un ou plusieurs groupes d’hôtes (environnement) n’existent pas mais sont référencés dans la définition de paramètre prédéfini.
* Une ou plusieurs expériences ont été supprimées après la création du paramètre prédéfini, mais sont référencées dans la définition de paramètre prédéfini.
* Un paramètre prédéfini n’est sémantiquement pas valide, car les entités référencées existent encore mais ont été mises à jour de manière telle que la définition de paramètre prédéfini a sémantiquement changé. Par exemple, supposons que vous créez un paramètre prédéfini nommé « Revenu sur Chrome ». Vous mettez par la suite l’activité à jour pour mesurer la mesure Conversion au lieu de Revenu. Cette mise à jour de la définition d’activité invalide la définition prédéfinie sémantiquement.

## Mesure du rapport {#section_894ABD7148244806B7CE556EBBA2AD62}

Cliquez sur la liste déroulante **[!UICONTROL Mesure du rapport]** afin de sélectionner une autre [mesure de succès](../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) ou plusieurs mesures à afficher dans le graphique et le tableau.

Par défaut, la mesure principale est définie dans la configuration des mesures de succès lors de la création de l’activité. Si vous modifiez la configuration et que vous réenregistrez l’activité, la mesure principale des rapports est mise à jour.

Pour plus d’informations sur la sélection de plusieurs mesures à afficher dans les rapports, voir [Affichage de plusieurs mesures dans un rapport](../../c-reports/c-report-settings/view-multiple-metrics.md#concept_9E3C3F6F3EC1412FAF252975AC0720B7).

## Public {#section_70926EB4618945D9AFF2B0564FF3717B}

Cliquez sur la liste déroulante [!UICONTROL Audience] afin de modifier l’audience affichée pour le rapport.

Pour plus d’informations, voir [Audiences](../../c-target/target.md#concept_A782F8481A5041EBA75103CB26376522).

## Période {#section_A410A768403C4E01891F95CB357E63ED}

La zone Période affiche la plage de dates actuelle du rapport. Cliquez sur l’icône déroulante pour afficher un calendrier vous permettant de changer la période du rapport.

![Calendrier](/help/c-reports/c-report-settings/assets/date_range-new.png)

Sélectionnez de nouvelles dates de **[!UICONTROL Début]** et de **[!UICONTROL Fin]** pour le rapport. Vous pouvez également utiliser les cases à cocher **[!UICONTROL Du début de l’activité]** et **[!UICONTROL À la fin de l’activité]**.

Cliquez sur **[!UICONTROL Dates personnalisées]** pour sélectionner des plages de dates prédéfinies : 7 derniers jours, 15 derniers jours ou 30 derniers jours. Ces périodes prédéfinies sont des périodes flottantes. Si la date de début est inférieure au nombre de jours choisi, le calendrier affichera la période disponible à partir de la date de début, mais décalera d’un jour dès que la date de début sera antérieure au nombre de jours choisi à mesure que la durée de l’activité augmente.

Les rapports comportent les restrictions de date suivantes :

* La date de début du rapport doit être comprise dans les deux dernières années.
* Les rapports quotidiens sont limités à 100 jours.
* Les rapports par heure sont limités à 15 jours.

## Paramètres {#section_D99CE462107D45CABE0960F820E1E972}

Cliquez sur l’engrenage pour configurer les paramètres des rapports, puis cliquez sur **[!UICONTROL Enregistrer les paramètres]** lorsque vous avez terminé.

L’illustration ci-après présente la boîte de dialogue Paramètres pour une activité A/B :

![Boîte de dialogue Paramètres](/help/c-reports/c-report-settings/assets/ab_settings_dialog-new.png)

Les options varient en fonction du type d’activité sélectionné :

* **Méthodologie de calcul :** sélectionnez la méthodologie souhaitée :

   * Visiteurs
   * Visites
   * Impressions d’activité

* **Contrôle** : sélectionnez l’expérience de contrôle à utiliser lors du calcul et de la comparaison de l’effet élévateur.
* **Environnement :** sélectionnez l’environnement (groupe d’hôtes) à utiliser pour le rapport. Pour plus d’informations, voir [Hôtes](../../administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).
* **Réinitialiser les données de rapports** : permet de réinitialiser les données des rapports afin de supprimer les anciennes données. Les visiteurs actuels restent dans l’activité. Seuls ceux qui détiennent des autorisations d’approbateur ont accès à cette option.

   >[!IMPORTANT]
   >
   >Cette opération est définitive et ne peut pas être annulée.

* **Exclure les valeurs extrêmes** : cette option s’applique uniquement aux activités qui ont recours aux mesures de type Recettes et Engagement. Pour plus d’informations, voir [Exclusion des commandes extrêmes](../../c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA).

## Télécharger {#section_77E65C50BAAF4AB79242DB3A8778ADEF}

Cliquez sur l’icône Télécharger pour télécharger les données de rapport au format [!DNL .csv] afin de pouvoir les importer rapidement dans Excel, Access ou autres programmes d’analyse des données. Pour plus d’informations, voir [Téléchargement de données au format CSV](../../c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75).

## Actualiser {#section_E203729F2F314DF3856D2EE67C60B370}

Cliquez sur l’icône Actualiser pour actualiser la vue tabulaire ou graphique d’un rapport sans actualiser toute la page, sa configuration ou sa plage de dates.

## More options {#section_AB1B5C695D7045A0A0AC0E2698D2E7DE}

Cliquez sur l’icône Plus d’options (trois points alignés verticalement) pour accéder aux options [!UICONTROL Modifier l’activité] et [!UICONTROL Afficher les URL d’expérience].

## Options de vue

Vous pouvez vue le rapport dans divers formats, selon le type d’activité. Sélectionnez une option.

![Icônes des options de vue](/help/c-reports/c-report-settings/assets/view-options.png)

* **Vue** de tableau : Cliquez sur l&#39;icône Vue **[!UICONTROL de]** tableau pour vue du rapport sous forme de tableau.
* **Vue** graphique : Cliquez sur l&#39;icône de Vue **** graphique pour vue du rapport sous forme de graphique.
* **Segments** automatisés : (disponibles uniquement pour les activités Automated Personalization (AP) et Cible automatique (AT).) Cliquez sur l&#39;icône **Segments automatisés pour vue du rapport [Segments](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)automatisés.
* **Attributs** importants : (Disponible uniquement pour les activités Automated Personalization (AP) et Cible automatique (AT).) Cliquez sur l&#39;icône **Attributs importants pour vue du rapport [Attributs](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md)importants.

## Effet élévateur moyen, limites de l’effet élévateur et intervalle de confiance {#section_0D87615B1D3344B3858BA494EEBC16FB}

Les rapports comprennent plusieurs points de données et représentations de visualisation qui vous aident à comprendre les limites de l’effet élévateur et le degré de confiance associé à votre activité. Vous pouvez ainsi déterminer plus précisément un gagnant.

Pour plus d’informations, voir [Effet élévateur moyen, limites de l’effet élévateur et intervalle de confiance](../../c-reports/c-report-settings/average-lift-bounds-and-confidence-interval.md#topic_AFFDC672A8A34D028B100EF6BE5D8129).

Tenez compte des points suivants :

* Disponible uniquement dans les rapports en vue Tableau.
* Cette fonctionnalité n’est pas disponible pour les activités utilisant [Analytics comme source de rapports (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md).

## Contribution des emplacements {#section_5832F126AC114AE1ABFFF4D9B904393B}

Cliquez sur l’icône **[!UICONTROL Contribution des emplacements]** pour que le rapport affiche la contribution par emplacement.

## Expériences {#section_3A450DE1FA7E43F0AAB73165EC3D1C34}

(option disponible seulement dans le rapport en vue graphique)

Sélectionnez ou désélectionnez des expériences à gauche du tableau pour afficher ou masquer les expériences correspondantes dans le tableau.

Dans l’illustration suivante, seules les expériences Défaut, Moyen-Orient et Total s’affichent dans le rapport : L’expérience Asie est masquée dans le graphique.

![Expériences](/help/c-reports/c-report-settings/assets/report_experiences-new.png)

## Moyenne cumulée {#section_59066693158C4433B87D07402C2BC6CD}

(option disponible seulement dans le rapport en vue graphique)

La &quot;Moyenne d’exécution&quot; reflète les conversions cumulées (du début de la fenêtre du rapports à la date représentée sur le graphique) divisées par les visiteurs cumulatifs.

Sélectionnez la vue graphique souhaitée :

* Moyenne cumulée
* Effet élévateur moyen cumulé
* Quotidien Contrôle
* Ciblage quotidien
* Effet élévateur quotidien

![Moyenne cumulée du rapport](/help/c-reports/c-report-settings/assets/report_running_average-new.png)

>[!NOTE]
>
>Le nom de cette liste déroulante varie en fonction de la vue sélectionnée, mais il s’agira de l’une des vues répertoriées ci-dessus.

## Méthodologie de calcul {#section_01B0ED5665C74AE1AE97259800190C3E}

(option disponible seulement dans le rapport en vue graphique)

Vous pouvez choisir la méthodologie de calcul pour les graphiques des rapports. Notez que cette fonctionnalité n’est pas prise en charge pour les activités d’Automated Personalization (AP).

Pour accéder à l’option Méthodologie de calcul lorsque vous visualisez un rapport en mode graphique, cliquez sur la liste déroulante **[!UICONTROL Mon principal objectif]**, puis sélectionnez la méthodologie de calcul.

La méthodologie de calcul sera la même que celle sélectionnée dans la boîte de dialogue [!UICONTROL Paramètres] et décrite ci-dessus.

![Méthodologie de calcul](/help/c-reports/c-report-settings/assets/counting_methodology_2-new.png)

Par défaut, le graphique est tracé en mode [!UICONTROL Quotidien].

You can change the mode by clicking the [!UICONTROL Daily] drop-down list, then selecting a cumulative option.

![Cumulé](/help/c-reports/c-report-settings/assets/counting_methodology-new.png)

>[!NOTE]
>
>Le nom de cette liste déroulante varie en fonction du mode sélectionné.

Il existe quatre modes pour les activités de ciblage automatique : Contrôle quotidien, Quotidien ciblé, Contrôle du cumul et Cumul ciblé.

L’ordre par défaut dans lequel le graphique est tracé est le suivant :

* **Tests A/B (y compris l’affectation automatique et l’Automated Personalization)**: Ordre de création de l’expérience, dans l’ordre décroissant.
* **Ciblage d’expérience (XT)**: Ordre des expériences dans l’activité.
* **Test multivarié (MVT)**: Ordre alphabétique par nom d’expérience.
* **Recommendations**: Ordre de création de l’expérience, dans l’ordre décroissant.

Lorsque vous utilisez les options de la méthodologie de calcul, prenez en compte les avertissements suivants :

* For [Auto-Target activities](/help/c-activities/auto-target-to-optimize.md), there is no option for selecting &quot;Visitors&quot; as the counting methodology. Le ciblage automatique est le seul type d’activité que vous ne pouvez pas représenter sous forme de graphique par visiteur.
* For activities that use [Analytics as the reporting source (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md), you cannot plot Visitor, Visit, or Impression cumulatively.

## Utilisation de graphiques contenant plus de 16 expériences dans l’activité

Si une activité comporte moins de 16 expériences, chaque expérience est tracée dans une couleur différente dans le graphique.

Si une activité comporte plus de 16 expériences, les lignes colorées pour les 16 premières expériences s’affichent dans le graphique. Les expériences restantes sont grisées dans le volet Expériences de gauche et aucune ligne correspondante ne s’affiche dans le graphique. Les lignes pour les 16 premières expériences peuvent être affichées à tout moment.

Si vous passez la souris sur une des expériences grisées, une nouvelle ligne grise correspondant à cette expérience s’affiche temporairement dans le graphique. Pour afficher la ligne d’une expérience grisée en couleur, vous pouvez désélectionner une expérience affichée en couleur en cliquant sur son nom, puis sélectionner l’expérience grisée souhaitée en cliquant sur son nom.

À titre d’exemple, l’illustration suivante montre le graphique d’une activité comportant 26 expériences :

![](assets/graph_1.png)

Le graphique affiche les lignes pour les 16 premières expériences (on constate quelques chevauchements qui font croire qu’il y a moins de 16 lignes). Le point coloré du volet Expériences de gauche en regard du nom de chaque expérience indique que la ligne de l’expérience s’affiche dans la couleur correspondante.

Si vous faites défiler le volet Expériences vers le bas, vous remarquerez que le nom des expériences 17 à 26 est grisé, comme illustré ci-dessous :

![](assets/graph_2.png)

Si vous passez la souris sur l’une des expériences grisées, une nouvelle ligne grise correspondant à cette expérience s’affiche temporairement dans le graphique.

Supposons que vous vouliez afficher la ligne pour l’Experience R et que vous ne vouliez pas afficher la ligne pour l’Experience P. Vous pouvez cliquer sur le nom de l’Experience P pour la désélectionner, puis cliquer sur le nom de l’Experience R pour la sélectionner, comme illustré ci-dessous :

![](assets/graph_3.png)

