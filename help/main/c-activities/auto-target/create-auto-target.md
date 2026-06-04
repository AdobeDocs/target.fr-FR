---
keywords: Créer un ciblage automatique;test A/B;activité de ciblage automatique;nouvelle activité a/b;ciblage automatique;ciblage automatique pour les expériences personnalisées;personnalisé;optimisation
description: Découvrez comment utiliser le [!UICONTROL compositeur d’expérience visuelle] (VEC) pour créer une activité de test A/B de [!UICONTROL ciblage automatique].
title: Comment créer une activité de [!UICONTROL ciblage automatique] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Auto-Target
exl-id: 5521740c-eee2-4ba2-8931-cf56d56a4561
TQID: https://experienceleague.adobe.com/qbt-h-4C4uVz6r6xmwKmSeU-RuBdWikmtDQq40dBq9k
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: eb30f47f-d87a-400f-8f78-63ce7979ff56id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1062
ht-degree: 17%

---

# Création d’une activité de [!UICONTROL ciblage automatique]

Utilisez le [!UICONTROL compositeur d’expérience visuelle] (VEC) dans [!DNL Adobe Target] pour créer votre activité [!UICONTROL ciblage automatique] [!UICONTROL test A/B] directement sur une page [!DNL Target] et pour modifier des parties de la page dans [!DNL Target].

>[!NOTE]
>
>Le [!UICONTROL ciblage automatique] est disponible dans le cadre de la solution [!DNL Target Premium]. Cette fonctionnalité n’est pas disponible dans [!DNL Target Standard] sans une licence [!DNL Target Premium]. Pour plus d’informations sur les fonctionnalités avancées de cette licence, voir [Target Premium](/help/main/c-intro/intro.md).

Pour créer une activité de [!UICONTROL ciblage automatique] :

1. Dans la liste **[!UICONTROL Activités]**, cliquez sur **[!UICONTROL Créer une activité]** > **[!UICONTROL Test A/B]**.

1. Dans la boîte de dialogue [!UICONTROL Créer une activité de test A/B], sélectionnez **[!UICONTROL Visuel]**, si nécessaire.

   Si vous préférez utiliser le [!UICONTROL Compositeur d’expérience d’après les formulaires], sélectionnez [!UICONTROL Formulaire]. Reportez-vous à la section [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) pour plus d’informations.

   >[!NOTE]
   >
   >Outre le compositeur d’expérience visuelle et le [!UICONTROL compositeur d’expérience d’après les formulaires], [!DNL Target] propose le compositeur d’expérience visuelle [!UICONTROL application d’une seule page]. Pour plus d’informations sur les divers compositeurs, voir [Offres et expériences](/help/main/c-experiences/experiences.md).
   >
   >Pour obtenir des informations de dépannage sur le VEC, voir [Dépannage du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Conditionnel) Si vous êtes un client [](/help/main/c-intro/intro.md#premium), dans la liste déroulante **[!UICONTROL Choisir Workspace]**, choisissez un [espace de travail](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

   L’option [[!UICONTROL  Choisir un lieu de travail ]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) est une fonctionnalité de [Target Premium](/help/main/c-intro/intro.md) qui peut ne pas s’afficher si votre entreprise dispose d’une licence [!UICONTROL Target Standard].

1. Dans la zone **[!UICONTROL Saisir l’URL de l’activité]**, spécifiez votre [URL de l’activité](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md).

   Si votre compte est [configuré avec une URL par défaut](/help/main/administrating-target/visual-experience-composer-set-up.md), cette URL apparaît par défaut. Si nécessaire, vous pouvez remplacer l’URL par défaut par une autre URL.

1. Cliquez sur **[!UICONTROL Créer]**.

   Le [!UICONTROL compositeur d’expérience visuelle] s’ouvre, affichant la page indiquée dans l’URL.

1. Cliquez sur l’icône **[!UICONTROL Renommer]** ( ![Icône Renommer](/help/main/assets/icons/MoreSmallListVert.svg) ), cliquez sur **[!UICONTROL Renommer]**, attribuez un nom à l’activité, puis cliquez sur **[!UICONTROL Enregistrer]**.

   Le nom de l’activité ne peut pas commencer par l’un des caractères suivants :

   | Caractère | Description |
   |--- |--- |
   | `=` | Égal |
   | `+` | Plus |
   | `-` | Moins |
   | `@` | Arobase |

   Le nom de l’activité ne peut pas contenir l’une des séquences de caractères suivantes :

   | Séquence De Caractères | Description |
   |--- |--- |
   | ;= | Point-virgule, égal à |
   | ;+ | Point-virgule plus |
   | ;- | Point-virgule, moins |
   | ;@ | Point-virgule, signe At |
   | ,= | Virgule, est égal à |
   | ,+ | Virgule, Plus |
   | ,- | Virgule, Moins |
   | ,@ | Virgule, Au signe |
   | `[`&quot; | Crochet ouvert, guillemets doubles |
   | &quot;`]` | Guillemets doubles, crochet fermant |

1. Créez de nouvelles expériences en modifiant les éléments de la page.

   Le [!UICONTROL compositeur d’expérience visuelle] affiche deux onglets sur le côté gauche après la création d’une activité : [!UICONTROL expérience A] et [!UICONTROL expérience B]. [!UICONTROL expérience A] est l’expérience de contrôle. Vous vous concentrez sur l’onglet [!UICONTROL Expérience B], que vous pouvez modifier selon vos besoins. [!UICONTROL Expérience B] est l’autre expérience que vous pouvez ajouter à votre test. Vous pouvez ajouter plusieurs expériences au test en cliquant sur l’icône [!UICONTROL Ajouter] ( ![Ajouter une icône](/help/main/assets/icons/Add.svg) ) en haut du volet [!UICONTROL Expériences]. Vous pouvez également supprimer l’Expérience A de l’activité si vous ne souhaitez pas que l’expérience de site par défaut soit une option possible.

   Pour plus d’informations sur l’ajout et la modification d’expériences dans le [!UICONTROL compositeur d’expérience visuelle], voir [Ajouter une expérience](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00). Pour modifier l’Expérience B, commencez à l’étape 2.

1. Cliquez sur **[!UICONTROL Ciblage]** en haut du [!UICONTROL Compositeur d’expérience visuelle] pour passer à l’étape suivante du workflow guidé en trois étapes.

   Le diagramme de flux s’ouvre.

   ![Étape Ciblage des tests A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

   Le diagramme de flux vous guide tout au long des étapes d’affectation d’une audience et de son pourcentage de trafic, de sélection de la méthode d’affectation du trafic et de spécification de l’affectation du trafic pour chaque expérience de l’activité.

1. (Conditionnel) Cliquez sur la commande **[!UICONTROL Tous les visiteurs]** pour sélectionner une autre audience pour l’activité.

   L’audience [!UICONTROL Tous les visiteurs] est définie par défaut. Si vous sélectionnez une autre audience, son nom s’affiche dans le contrôle le plus à gauche.

   Le cadre de droite s’affiche, ce qui vous permet d’ajouter ou de supprimer une audience et d’attribuer le pourcentage de visiteur ou de visiteuse à l’activité.

   1. Pour modifier l’audience, cliquez sur l’icône **[!UICONTROL Remplacer]** ( ![Icône Remplacer](/help/main/assets/icons/Retweet.svg) ) dans le cadre de droite.
   1. Dans la boîte de dialogue [!UICONTROL Ajouter une audience], [sélectionnez l’audience souhaitée](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) puis cliquez sur **[!UICONTROL Attribuer l’audience]**.

      Vous pouvez cliquer sur **Combiner les audiences** pour [créer une audience qui combine plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md).

      Si vous devez créer une nouvelle audience qui ne figure pas encore dans la [!UICONTROL Bibliothèque d’audiences], cliquez sur **Créer une audience**. Au cours du workflow [création d’audience](/help/main/c-target/c-audiences/audiences.md) vous pouvez choisir parmi les options suivantes :

      * **[!UICONTROL Bibliothèque d’audiences]** : créez une audience à la demande enregistrée dans la [!UICONTROL Bibliothèque d’audiences] qui peut être réutilisée dans d’autres activités
      * **[!UICONTROL Cette activité uniquement]** : créez une [audience spécifique à une activité](/help/main/c-target/creating-activity-only-audience.md) qui n’est pas enregistrée dans la [!UICONTROL bibliothèque d’audiences] et qui ne peut être utilisée que dans l’activité en cours

   1. Cliquez sur **[!UICONTROL Pourcentage de visiteurs]** dans le cadre de droite, puis choisissez le pourcentage de visiteurs qualifiés qui doivent rejoindre l’activité.

   Vous pouvez par exemple limiter les entrées à 50 % de tous les visiteurs ou à 45 % pour l’audience « Parisiens ».

1. Cliquez sur le contrôle **[!UICONTROL Allocation du trafic]**, puis choisissez la méthode d’affectation du trafic souhaitée dans le volet de droite. Dans ce scénario, cliquez sur **[!UICONTROL Ciblage automatique pour les expériences personnalisées]**.

   ![Paramètres de la méthode d’affectation du trafic](/help/main/c-activities/assets/auto-target.png)

   Les méthodes d’affectation du trafic disponibles sont les suivantes :

   * **[!UICONTROL Manuel (par défaut)]** : indiquez le pourcentage de participants qui doivent voir chaque expérience. Vous pouvez fractionner les pourcentages de manière uniforme entre tous les contenus ou spécifier des pourcentages supérieurs ou inférieurs pour chaque contenu. Le total de toutes les expériences doit être égal à 100 %.

   * **[!UICONTROL Affectation automatique à la meilleure expérience]** : la plupart des personnes participant à l’activité sont automatiquement redirigées vers des expériences plus performantes. Certains visiteurs sont affectés à toutes les expériences afin de garantir l’exploration des expériences et de reconnaître les changements dans les tendances des performances. Pour plus d’informations, consultez la présentation de l’[[!UICONTROL affectation automatique] ](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   * **[!UICONTROL Ciblage automatique pour les expériences personnalisées]** : [!DNL Target] utilise le machine learning avancé pour personnaliser le contenu et générer des conversions en identifiant plusieurs expériences hautement performantes définies par des spécialistes marketing, puis en proposant l’expérience la plus personnalisée aux visiteurs selon leur profil client individuel et le comportement antérieur de visiteurs similaires. Pour plus d’informations, voir [Présentation du ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

1. Cliquez sur **[!UICONTROL Expériences]** dans le volet de droite, puis spécifiez l’affectation du trafic souhaitée pour chaque expérience.

1. Lorsque vous êtes satisfait de votre audience, de vos choix d’expérience et de vos choix d’affectation du trafic, cliquez sur **[!UICONTROL Suivant]** pour passer à la troisième étape du workflow guidé en trois étapes.

1. Spécifiez les [objectifs et paramètres](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) pour l’activité.

   >[!NOTE]
   >
   >Si vous souhaitez utiliser [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) avec cette activité, reportez-vous à la section informations importantes dans Prise en charge d’[A4T pour les activités d’affectation automatique et de ciblage automatique](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

1. Cliquez sur **[!UICONTROL Enregistrer et fermer]** ou **[!UICONTROL Enregistrer]**.

Après avoir créé l’activité, l’onglet [!UICONTROL Aperçu] affiche des informations sur l’activité, y compris un diagramme de votre activité.
