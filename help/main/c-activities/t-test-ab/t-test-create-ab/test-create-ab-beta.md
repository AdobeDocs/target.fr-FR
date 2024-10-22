---
keywords: Créer A/B;test A/B;activité A/B;nouvelle activité a/b;créer a/b
description: Principal de [!UICONTROL Visual Experience Composer] (VEC) pour créer des activités de test A/B directement sur une page compatible avec  [!DNL Target].
title: Comment créer un test A/B ?
feature: A/B Tests
hide: true
hidefromtoc: true
source-git-commit: 5fc18c6d3b493ea0a58048cc20ce3a6c2ffb7d14
workflow-type: tm+mt
source-wordcount: '885'
ht-degree: 17%

---

# Créer une activité de test A/B

Tirez parti de [!UICONTROL Visual Experience Composer] (VEC) dans [!DNL Adobe Target] pour créer des activités [!UICONTROL A/B Test] directement sur une page [!DNL Target] et pour modifier les sections de page dans [!DNL Target].

>[!NOTE]
>
>Outre l&#39;activité [!UICONTROL Manual] (par défaut) [!UICONTROL A/B Test] (discutée dans cet article), [!DNL Target] fournit deux types supplémentaires d&#39;activités [!UICONTROL A/B Test] : [!UICONTROL Auto-Allocate] et [!UICONTROL Auto-Target].
>
>Voir [Types des activités de test A/B](/help/main/c-activities/t-test-ab/test-ab.md#types) dans la *présentation des tests A/B*.

Pour créer une activité [!UICONTROL A/B Test] manuelle :

1. Dans la liste **[!UICONTROL Activities]**, cliquez sur **[!UICONTROL Create Activity]** > **[!UICONTROL A/B Test]**.

1. Dans la boîte de dialogue [!UICONTROL Create A/B Test Activity], sélectionnez **[!UICONTROL Visual]**, si nécessaire.

   Si vous préférez utiliser le [!UICONTROL Form-Based Experience Composer], sélectionnez [!UICONTROL Form]. Reportez-vous à la section [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) pour plus d’informations.

   >[!NOTE]
   >
   >Outre le VEC et [!UICONTROL Form-Based Experience Composer], [!DNL Target] offre le VEC [!UICONTROL Single Page Application]. Pour plus d’informations sur les divers compositeurs, voir [Offres et expériences](/help/main/c-experiences/experiences.md).
   >
   >Pour obtenir des informations de dépannage sur le compositeur d’expérience visuelle, voir [Dépannage du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Conditionnel) Si vous êtes un [client Target Premium](/help/main/c-intro/intro.md#premium), sélectionnez un [espace de travail](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) dans la liste déroulante **[!UICONTROL Choose Workspace]**.

   L&#39;option [[!UICONTROL Choose Workplace]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) est une fonction [Target Premium](/help/main/c-intro/intro.md) et peut ne pas s&#39;afficher si votre entreprise dispose d&#39;une licence [!UICONTROL Target Standard].

1. Dans la zone **[!UICONTROL Enter Activity URL]**, spécifiez votre [URL d&#39;activité](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md).

   Si votre compte est [configuré avec une URL par défaut](/help/main/administrating-target/visual-experience-composer-set-up.md), cette URL apparaît par défaut. Si nécessaire, vous pouvez passer de la valeur par défaut à une autre URL.

1. Cliquez sur **[!UICONTROL Create]**.

   [!UICONTROL Visual Experience Composer] s’ouvre, affichant la page spécifiée dans l’URL.

1. Cliquez sur **[!UICONTROL Untitled Activity]** en haut du VEC, puis spécifiez un nom pour l’activité dans l’espace fourni.

   Le nom de l’activité ne peut pas commencer par les caractères suivants :

   | Caractère | Description |
   |--- |--- |
   | `=` | Égal |
   | `+` | Plus |
   | `-` | Moins |
   | `@` | Arobase |

   Le nom de l’activité ne peut pas contenir l’une des séquences de caractères suivantes :

   | Séquence de caractères | Description |
   |--- |--- |
   | ;= | Point-virgule, égal à |
   | ;+ | Point-virgule, plus |
   | ; - | Point-virgule, moins |
   | ;@ | Point-virgule, signe At |
   | ,= | Virgule, Égal à |
   | ,+ | Virgule, Plus |
   | ,- | Virgule, Moins |
   | ,@ | Virgule, signe At |
   | `[`&quot; | Crochets droits ouverts, guillemets doubles |
   | &quot;`]` | Guillemets doubles, crochet fermant |

1. Créez de nouvelles expériences en modifiant les éléments sur la page.

   Le [!UICONTROL Visual Experience Composer] affiche deux onglets sur le côté gauche après la création d’une activité : Expérience A et Expérience B. L’Expérience A est l’expérience de contrôle. Vous vous concentrez sur l’onglet Expérience B, que vous pouvez modifier selon vos besoins. L’expérience B est l’autre expérience que vous pouvez ajouter à votre test. Vous pouvez ajouter plusieurs expériences au test en cliquant sur l’icône [!UICONTROL Add] ( ![Ajouter une icône](/help/main/assets/icons/Add.svg) ) en haut du volet [!UICONTROL Experiences]. Vous pouvez également supprimer l’Expérience A de l’activité si vous ne souhaitez pas que l’expérience de site par défaut soit une option possible.

   Pour plus d’informations sur l’ajout et la modification d’expériences dans [!UICONTROL Visual Experience Composer], voir [Ajout d’une expérience](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00). Pour modifier l’Expérience B, commencez à l’étape 2.

1. Cliquez sur **[!UICONTROL Targeting]** dans la partie supérieure de [!UICONTROL Visual Experience Composer] pour passer à l’étape suivante du processus assisté en trois étapes.

   Le diagramme de flux s’ouvre.

   ![Étape Ciblage des tests A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

   Le diagramme de flux vous guide tout au long des étapes permettant d’affecter une audience et son pourcentage de trafic, de sélectionner la méthode d’affectation du trafic et de spécifier l’affectation du trafic pour chaque expérience de l’activité.

1. (Conditionnel) Cliquez sur le contrôle **[!UICONTROL All Visitors]** pour sélectionner une autre audience pour l’activité.

   L’audience [!UICONTROL All Visitors] est définie par défaut. Si vous sélectionnez une autre audience, son nom s’affiche dans le contrôle le plus à gauche.

   Le cadre de droite s’affiche, ce qui vous permet d’ajouter ou de supprimer une audience et d’attribuer le pourcentage du visiteur pour l’activité.

   1. Pour modifier l’audience, cliquez sur l’icône **[!UICONTROL Replace]** ( ![Icône Remplacer](/help/main/assets/icons/Retweet.svg) ) dans le cadre de droite.
   1. Dans la boîte de dialogue [!UICONTROL Add Audience], [sélectionnez l’audience souhaitée](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md), puis cliquez sur **[!UICONTROL Assign Audience]**.

      Vous pouvez cliquer sur **Combiner les audiences** pour [créer une audience qui combine plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md).

      Si vous devez créer une audience qui ne figure pas encore dans le [!UICONTROL Audience Library], cliquez sur **Créer une audience**. Au cours du [processus de création d’audience](/help/main/c-target/c-audiences/audiences.md), vous pouvez choisir parmi les options suivantes :

      * Créez une audience à la demande enregistrée dans le [!UICONTROL Audience Library] qui peut être réutilisée dans d’autres activités.
      * Créez une [audience spécifique à une activité](/help/main/c-target/creating-activity-only-audience.md) qui n’est pas enregistrée dans le [!UICONTROL Audience Library] et qui ne peut être utilisée que dans l’activité active.

   1. Cliquez sur **[!UICONTROL Visitor Percentage]** dans le cadre de droite, puis sélectionnez le pourcentage de visiteurs admissibles qui doivent entrer dans l’activité.

   Vous pouvez par exemple limiter les entrées à 50 % de tous les visiteurs ou à 45 % pour l’audience « Parisiens ».

1. Cliquez sur le contrôle **[!UICONTROL Traffic Allocation]**, puis sélectionnez la méthode d’affectation du trafic souhaitée dans le volet de droite, comme illustré ci-dessous :

   ![ Paramètres de méthode d’affectation du trafic ](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method-new.png)

   Choisissez la méthode d’affectation du trafic souhaitée :

   * **[!UICONTROL Manual (Default)]** : spécifiez le pourcentage de participants qui doivent voir chaque expérience. Vous pouvez fractionner les pourcentages de manière uniforme entre tous les contenus ou spécifier des pourcentages supérieurs ou inférieurs pour chaque contenu. Le total de toutes les expériences doit être égal à 100 %.

   * **[!UICONTROL Auto-Allocate to best experience]** : La plupart des participants à l’activité sont automatiquement dirigés vers des expériences hautement performantes. Certains visiteurs sont affectés à toutes les expériences afin de garantir l’exploration des expériences et de reconnaître les changements dans les tendances des performances. Pour plus d’informations, voir [[!UICONTROL Auto-Allocate] - Aperçu](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   * **[!UICONTROL Auto-Target for personalized experiences]** : [!DNL Target] utilise l’apprentissage automatique avancé pour personnaliser le contenu et générer des conversions en identifiant plusieurs expériences hautement performantes définies par des responsables du marketing, puis en diffusant l’expérience la plus personnalisée aux visiteurs en fonction de leurs profils client individuels et des comportements antérieurs de visiteurs similaires. Pour plus d’informations, voir [Présentation du ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

1. Cliquez sur **[!UICONTROL Experiences]** dans le volet de droite, puis spécifiez l’affectation de trafic souhaitée pour chaque expérience.

1. Lorsque vous êtes satisfait de votre audience, de vos choix d’expérience et de vos choix d’affectation du trafic, cliquez sur **[!UICONTROL Next]** pour passer à la troisième étape du processus assisté en trois étapes.

1. Spécifiez les [objectifs et paramètres](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) pour l’activité.

1. Cliquez sur **[!UICONTROL Save & Close]** ou **[!UICONTROL Save]**.

Une fois que vous avez créé l’activité, l’onglet [!UICONTROL Overview] affiche des informations sur l’activité, y compris un diagramme de votre activité.