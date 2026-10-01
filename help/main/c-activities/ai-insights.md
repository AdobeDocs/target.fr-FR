---
keywords: Informations sur l’IA;Experimentation Accelerator;opportunités;présentation des activités
description: Découvrez comment utiliser les informations et les opportunités d’optimisation générées par l’IA depuis Experimentation Accelerator dans la présentation des activités Adobe Target.
title: Informations sur l’IA dans la présentation de l’activité
feature: Activities
badge: label="Beta" type="Informative"
source-git-commit: 88a811c3ae521b94ceb6350ba44aa2d40afda2b6
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 31%
---
# Informations sur l’IA

>[!AVAILABILITY]
>
>La fonctionnalité d’informations sur l’IA est actuellement disponible en version bêta.
></br>
>La section **[!UICONTROL Informations sur l’IA]** est disponible uniquement pour les activités **[!UICONTROL Test A/B]** avec affectation du trafic **[!UICONTROL Manuel]**.

Le menu **[!UICONTROL Informations sur l’IA]** de votre **[!UICONTROL Présentation des activités]** permet d’accéder aux informations et aux opportunités d’optimisation. Utilisez cet onglet pour passer en revue les enseignements tirés des expériences, comparer des traitements et identifier les modifications susceptibles d’améliorer les taux de conversion.

## Configuration pour les informations et les opportunités de l’IA

>[!CONTEXTUALHELP]
>id="target_ai_insights"
>title="Statistiques"
>abstract="Les informations sur les expériences sont les enseignements trouvés par l’IA lorsque les données des expériences ont atteint leur signification statistique."

>[!CONTEXTUALHELP]
>id="target_ai_insights_primary_metric"
>title="Mesure principale"
>abstract="La mesure principale est automatiquement extraite des paramètres de création de rapports. Pour apporter des modifications, modifiez la mesure d’objectif sous Objectifs et paramètres."

>[!CONTEXTUALHELP]
>id="target_ai_insights_hypothesis"
>title="Hypothèse"
>abstract="L’hypothèse est une instruction que vous définissez et qui explique le résultat attendu de l’expérience. Incluez une description de ce qui est modifié et où, puis indiquez quelle mesure vous prévoyez de modifier et comment."

>[!CONTEXTUALHELP]
>id="target_ai_insights_treatment_details"
>title="Détails de l’expérience"
>abstract="Les détails de l’expérience affichent des images de ce à quoi ressemble une expérience lorsqu’un utilisateur ou une utilisatrice y est admissible. Vous pouvez consulter ces images pour toutes les expériences. Certaines expériences peuvent vous demander de confirmer l’image ou de la remplacer si nécessaire."

>[!CONTEXTUALHELP]
>id="target_ai_insights_primary_metric"
>title="Mesure principale"
>abstract="La mesure principale est automatiquement extraite des paramètres de création de rapports. Pour apporter des modifications, modifiez la mesure d’objectif sous Objectifs et paramètres."

>[!CONTEXTUALHELP]
>id="target_ai_insights_hypothesis"
>title="Hypothèse"
>abstract="L’hypothèse est une instruction que vous définissez et qui explique le résultat attendu de l’expérience. Incluez une description de ce qui est modifié et où, puis indiquez quelle mesure vous prévoyez de modifier et comment."

>[!CONTEXTUALHELP]
>id="target_ai_insights_opportunities"
>title="Opportunités"
>abstract="Les opportunités d’expérience sont des idées de traitement suggérées par l’IA basées sur des modèles que l’IA trouve dans vos captures d’écran et résultats d’expérience."

>[!CONTEXTUALHELP]
>id="target_ai_insights_treatment_details"
>title="Détails du traitement"
>abstract="Les détails du traitement montrent à quoi ressemble celui-ci lorsqu’un utilisateur ou une utilisatrice y est éligible. Vous pouvez consulter ces images pour toutes les expériences. Certaines expériences peuvent vous demander de confirmer l’image ou de la remplacer si nécessaire."

Avant de pouvoir accéder aux informations et aux opportunités générées par l’IA, vous devez d’abord configurer votre activité en confirmant les captures d’écran des mesures, hypothèses et expériences principales.

La mesure principale est automatiquement extraite des paramètres de création de rapports et dépend de la manière dont vous avez configuré vos objectifs et paramètres. Vous devez créer l’hypothèse dans le panneau Informations sur l’IA . [En savoir plus](../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)

1. Ouvrez votre activité dans [!DNL Adobe Target].

1. Sélectionnez le menu **[!UICONTROL Informations sur l’IA]** pour ouvrir le panneau de configuration.

1. Cliquez sur ![](assets/do-not-localize/Smock_Edit_18_N.svg) pour créer une hypothèse pour votre expérience.

   ![](assets/ai-insights-7.png)

1. Saisissez votre hypothèse en décrivant les modifications apportées et la manière dont elles auront un impact sur la mesure principale.

   Cliquez sur **[!UICONTROL Enregistrer]**.

1. Sous **[!UICONTROL Détails de l’expérience]**, cliquez sur une carte pour ajouter une capture d’écran à vos expériences.

   >[!NOTE]
   >Certaines images peuvent déjà être capturées automatiquement. Si tel est le cas, confirmez la capture d’écran en cliquant sur **[!UICONTROL Confirmer]**.

   ![](assets/ai-insights-1.png)

1. Sélectionnez **[!UICONTROL Télécharger l’image]** pour télécharger une capture d’écran préférée à partir de vos fichiers locaux pour chaque expérience.

   ![](assets/ai-insights-2.png)

1. Copiez le lien d’aperçu ou ouvrez-le directement pour prévisualiser l’expérience.

1. Une fois que chaque expérience comporte une capture d’écran, passez en revue les détails et cliquez sur **[!UICONTROL Confirmer]** pour terminer la configuration.

Une fois la configuration terminée, votre activité est prête à générer des opportunités. Les informations sont disponibles une fois que l’expérience dispose de données suffisantes pour la validation statistique et que les détails requis de l’expérience ont été confirmés.

## Statistiques {#insights}

>[!CONTEXTUALHELP]
>id="target_ai_insights_insights"
>title="Statistiques"
>abstract="Les informations sur les expériences sont les enseignements trouvés par l’IA lorsque les données des expériences ont atteint leur signification statistique."

Les informations d’expérience sont des apprentissages générés par l’IA provenant de cette expérience. Ces informations sont disponibles une fois que l’expérience a atteint sa signification statistique et fournissent un contexte sur ce qui a contribué à son succès. Ils mettent en évidence les attributs clés présents dans l’expérience gagnante qui sont distincts du contrôle et ont probablement influencé le résultat.

1. Cliquez sur la carte pour accéder au menu **[!UICONTROL Insights]**.

   ![](assets/ai-insights-3.png)

1. Parcourez vos informations générées par l’IA pour passer en revue l’apprentissage de l’expérience et comparer l’expérience gagnante au contrôle.

   ![](assets/ai-insights-4.png)

1. Dans **[!UICONTROL Qu’est-ce qui a fait gagner cette expérience ?]**, passez en revue les détails expliquant pourquoi cette expérience a surpassé le contrôle.

## Opportunités

>[!CONTEXTUALHELP]
>id="target_ai_insights_opportunities"
>title="Opportunités"
>abstract="Les opportunités d’expérience sont des idées d’expérience suggérées par l’IA basées sur des modèles que l’IA trouve dans vos captures d’écran et résultats d’expérience."

Le panneau **[!UICONTROL Opportunités]** affiche des recommandations générées par l’IA conçues pour améliorer les performances des tests et s’aligner sur les objectifs commerciaux et les KPI plus généraux.

1. Parcourez les opportunités suggérées et sélectionnez celle que vous souhaitez examiner.

   ![](assets/ai-insights-5.png)

1. Sélectionnez une opportunité pour ouvrir la fenêtre Détails de l’opportunité , qui décrit une expérience ou une variation spécifique. Cette vue comprend :

   * Image de l’expérience actuelle utilisée pour générer l’opportunité.

   * Hypothèse générée par l’IA qui explique le résultat attendu de l’expérience suggérée et pourquoi elle peut améliorer les performances.

   * Conseils sur la manière d’implémenter la recommandation dans votre expérience et de mesurer l’effet sur la mesure sélectionnée.

   ![](assets/ai-insights-6.png)

