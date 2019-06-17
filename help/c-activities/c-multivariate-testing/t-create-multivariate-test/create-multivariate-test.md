---
description: Le compositeur d’expérience visuelle de Target facilite la création correcte de votre test sur une page activée pour Target et la modification de parties de la page dans Target.
keywords: mvt;test multivarié;créer un test multivarié;création de test multivarié;créer un mvt;création de mvt;comment mvt;comment test multivarié
seo-description: Le compositeur d’expérience visuelle de Target facilite la création correcte de votre test sur une page activée pour Target et la modification de parties de la page dans Target.
seo-title: Création d’un test multivarié
solution: Target
title: Création d’un test multivarié
uuid: 876441bd-d841-4974-b1ec-3ad7cb6ef3ee
translation-type: tm+mt
source-git-commit: f689812658d45342f958629d02b74c252c7f0369

---


# Création d’un test multivarié{#create-a-multivariate-test}

Le compositeur d&#39;expérience [!UICONTROL visuelle (VEC)] permet [!DNL Target] de créer facilement votre test sur une page compatible Target et de modifier des parties de la page dans [!DNL Target].

L’éditeur convivial de Target permet de sélectionner n’importe quel emplacement et d’ajouter plusieurs offres.

Le test [!UICONTROL multivarié] prend un rapport de page premier. En d’autres termes, le test s’exécute sur une URL spécifique, avec des expériences que vous concevez pour cette page.

1. Cliquez sur **[!UICONTROL Créer une activité]** &gt; **[!UICONTROL Test multivarié]**.

   ![Créer un test multivarié](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/create-multivariate.png)

   >[!NOTE]
   >
   >Les types d’activité disponibles dépendent de votre compte Target. Certains types d’activité peuvent ne pas apparaître dans votre liste. Par exemple, [!UICONTROL la personnalisation automatisée] est une fonctionnalité [Target Premium](/help/c-intro/intro.md#premium).
   >
   >Pour plus d&#39;informations sur les différents types d&#39;activité disponibles [!DNL Target] et leurs différences, voir [Activités](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Pour [plus d&#39;informations, reportez-vous à la](/help/c-activities/target-activities-guide.md) section Types d&#39;activité Target pour déterminer les types d&#39;activité qui conviennent le mieux à vos besoins.

1. Si nécessaire, sélectionnez **[!UICONTROL Visual (]** Valeur par défaut).

   ![Boîte de dialogue Créer une activité de ciblage d&#39;expérience](/help/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   Si vous préférez utiliser le compositeur d’expérience d’après les formulaires, sélectionnez l’option [!UICONTROL Formulaire]. Voir [Compositeur d&#39;expérience d&#39;après les formulaires](/help/c-experiences/form-experience-composer.md) pour en savoir plus.

   >[!NOTE]
   >
   >Outre le compositeur d&#39;expérience visuelle et le compositeur d&#39;expérience d&#39;après les formulaires, Target propose le compositeur d&#39;expérience visuelle d&#39;une seule page et le compositeur d&#39;expérience visuelle pour les applications mobiles. Pour plus d&#39;informations sur les divers compositeurs, voir [Expériences et offres](/help/c-experiences/experiences.md).
   >
   >Pour plus d’informations sur la résolution de problèmes liés au compositeur d’expérience visuelle, veuillez consulter [Dépannage du compositeur d’expérience visuelle](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >L&#39;option [!UICONTROL Choisir le lieu de travail] de l&#39;illustration précédente est une [fonction Target Premium](/help/c-intro/intro.md) . Votre entreprise dispose d&#39;une licence Target Standard si vous ne voyez pas cette option.]

1. (Conditionnel) Si vous êtes client Target Premium, [choisissez un espace de travail](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. [Indiquez l&#39;URL](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/url.md#concept_C12E4A85FF3B4E518E3110F6CF1AF9C0) de la page à tester, puis cliquez sur **[!UICONTROL Suivant]**.

   >[!NOTE]
   >
   >Utilisez une URL complète, y compris le HTTP ou HTTPS au début.

   Si un message s’affiche vous demandant d’activer votre navigateur pour le contenu mixte, suivez les instructions du message. Après avoir activé votre navigateur pour le contenu mixte, recommencez à l’étape 1.

   Le compositeur d’expérience visuelle s’ouvre.

1. Entrez le nom de l’activité.

   ![Champ Nom de l&#39;activité](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/activityname.png)

   Le nom de l’activité ne peut pas contenir les caractères suivants :

   | Caractère | Description |
   |--- |--- |
   | / | Barre oblique |
   | ? | Point d’interrogation |
   | # | Croisillon |
   | : | Deux-points |
   | = | Égal |
   | + | Plus |
   | - | Moins |
   | @ | Arobase |

1. [Créez les offres à chaque emplacement](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/add-offers.md#concept_DCE6B45C30F7419B8EC17AFDEE8D8AA6).

   ![Boîte de dialogue Modifier le texte/HTML](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/editoffers.png)

   Vous pouvez ajouter les types d’offres suivants :

   * HTML
   * Image
   * Texte

1. Cliquez **[!UICONTROL sur Aperçu]** pour [prévisualiser vos expériences](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/preview-experiences.md).

   ![Aperçu des expériences](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt.png)

   Vous pouvez afficher chaque expérience et exclure toute expérience que vous ne souhaitez pas inclure dans votre test. Pour exclure une ou plusieurs expériences, cochez les cases de votre choix, puis cliquez **[!UICONTROL sur Exclure]** .

   ![Exclusion d&#39;expériences](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/preview-mvt-exclude.png)

1. [Utilisez l’estimateur de trafic](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) afin de tester la faisabilité de votre plan de test.

   ![Indicateur de trafic](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-traffic-indicator.png)

   L&#39;illustration suivante indique que le trafic de l&#39;activité n&#39;est pas suffisant.

   ![](assets/estimator.png)

   L&#39;illustration suivante indique que le trafic de l&#39;activité n&#39;est pas suffisant.

   ![](assets/estimator2.png)

1. Cliquez **[!UICONTROL sur Suivant]** pour accéder à [!UICONTROL la page Ciblage] .]

1. Sélectionnez l’audience et le pourcentage des visiteurs admissibles qui doivent entrer dans l’activité.

   ![Page de ciblage dans l&#39;activité MVT](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt_audperc.png)

   Vous pouvez par exemple limiter les entrées à 50 % de tous les visiteurs ou à 45 % pour l’audience « Parisiens ».

   >[!NOTE]
   >
   >En plus de sélectionner une audience existante, vous pouvez combiner plusieurs audiences pour créer des audiences combinées ad hoc plutôt que d’en créer une nouvelle. Pour plus d’informations, voir [Combinaison de plusieurs audiences](../../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. [Révisez le résumé du test](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/test-summary.md#reference_971AB225963A4DC18EEB5B0E20F0A4A7) et apportez toute modification souhaitée, puis cliquez sur **[!UICONTROL Continuer]**.

1. [Spécifiez les objectifs et paramètres](../../../c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) pour le test.

1. Cliquez sur **[!UICONTROL Enregistrer et fermer]** afin de créer l’activité.

## Vidéo de formation : Création de tests multivariés (9:25)

Cette vidéo explique comment planifier et créer un test multivarié à l’aide du flux de travaux Target à trois étapes.

* Définir et créer un test multivarié
* Création d’un test multivarié

>[!VIDEO](https://video.tv.adobe.com/v/17395?captions=fre_fr)
