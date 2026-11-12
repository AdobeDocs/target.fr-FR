---
keywords: Créer un ciblage automatique;test A/B;activité de ciblage automatique;nouvelle activité a/b;ciblage automatique;ciblage automatique pour les expériences personnalisées;personnalisé;optimisation
description: Découvrez comment utiliser le [!UICONTROL compositeur d’expérience visuelle] (VEC) pour créer une activité de test A/B de [!UICONTROL ciblage automatique].
title: Comment créer une activité de [!UICONTROL ciblage automatique] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Auto-Target
exl-id: 5521740c-eee2-4ba2-8931-cf56d56a4561
TQID: 'https://experienceleague.adobe.com/qbt-h-4C4uVz6r6xmwKmSeU-RuBdWikmtDQq40dBq9k'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: db15a02f-03cd-46fe-a53e-02064cdeadfa
    internal-label: Auto target
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
    internal-label: Customer profiles
source-git-commit: 9f1aaf5c0b172b4bbe89266800708881306e4592
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 12%
---
# Créer une activité de [!UICONTROL ciblage automatique] {#create-auto-target-activity}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment créer une activité de **[!UICONTROL ciblage automatique]** dans le **[!UICONTROL compositeur d’expérience visuelle]** (VEC). Vous créez vos expériences, définissez le ciblage et choisissez la méthode d’affectation de trafic de ciblage automatique , puis configurez les objectifs et les paramètres.

>[!ENDSHADEBOX]

Utilisez le **[!UICONTROL compositeur d’expérience visuelle]** (VEC) dans [!DNL Adobe Target] pour créer votre activité de **[!UICONTROL ciblage automatique]** **[!UICONTROL test A/B]** directement sur une page compatible avec [!DNL Target] et pour modifier des parties de la page dans [!DNL Target].

>[!NOTE]
>
>Le **[!UICONTROL ciblage automatique]** est disponible dans le cadre de la solution [!DNL Target Premium]. Cette fonctionnalité n’est pas disponible dans [!DNL Target Standard] sans une licence [!DNL Target Premium]. Pour plus d’informations sur les fonctionnalités avancées de cette licence, voir [Target Premium](/help/main/c-intro/intro.md).

L’activité suit le workflow guidé en trois étapes dans le compositeur d’expérience visuelle :

1. [Création d’expériences](#build-experiences)
1. [Définition du ciblage et de l’affectation du trafic](#set-targeting)
1. [Configurer les objectifs et les paramètres](#configure-goals-and-settings)

## Étape 1 : création d’expériences {#build-experiences}

Créez l’activité, puis concevez les autres expériences que vous souhaitez tester par rapport au contrôle.

### Création de l’activité {#create-activity}

Ouvrez la page que vous souhaitez tester dans le **[!UICONTROL Compositeur d’expérience visuelle]** et attribuez un nom à l’activité.

1. Dans la liste **[!UICONTROL Activités]**, cliquez sur **[!UICONTROL Créer une activité]** > **[!UICONTROL Test A/B]**.

   ![](../assets/create-ab-1.png)

1. Dans la boîte de dialogue **[!UICONTROL Créer une activité de test A/B]**, choisissez votre compositeur d’expérience :

   * **[!UICONTROL Visuel]**.
   * **[!UICONTROL Compositeur d’expérience d’après les formulaires]**, voir [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) pour plus d’informations.

   >[!NOTE]
   >
   >Outre le compositeur d’expérience visuelle et le **[!UICONTROL compositeur d’expérience d’après les formulaires]**, [!DNL Target] propose le compositeur d’expérience visuelle **[!UICONTROL Application sur une seule page]**. Pour plus d’informations sur les divers compositeurs, voir [Offres et expériences](/help/main/c-experiences/experiences.md).
   >
   >Pour obtenir des informations de dépannage sur le VEC, voir [Dépannage du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Sous condition) Si vous êtes un [client Target Premium](/help/main/c-intro/intro.md#premium), dans la liste déroulante **[!UICONTROL Choisir Workspace]**, choisissez un [espace de travail](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Dans la zone **[!UICONTROL Saisir l’URL d’activité]**, spécifiez votre [URL d’activité](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md).

   Si votre compte est [configuré avec une URL par défaut](/help/main/administrating-target/visual-experience-composer-set-up.md), cette URL apparaît par défaut. Si nécessaire, vous pouvez remplacer l’URL par défaut par une autre URL.

1. Cliquez sur **[!UICONTROL Créer]**. Le **[!UICONTROL compositeur d’expérience visuelle]** s’ouvre, affichant la page indiquée dans l’URL.

1. Pour nommer l’activité, cliquez sur l’icône **[!UICONTROL Modifier]** ( ![Icône Modifier](/help/main/assets/icons/Edit.svg) ) et spécifiez un nom explicite pour l’activité, puis cliquez sur **[!UICONTROL Enregistrer]**.

   {{activity-name-rules}}

   ![](../assets/create-ab-2.png)

### Concevoir les expériences {#design-experiences}

Créez de nouvelles expériences en modifiant les éléments de la page.

Après avoir créé une activité, le **[!UICONTROL compositeur d’expérience visuelle]** affiche deux onglets sur le côté gauche : Expérience A et Expérience B.

* **Expérience A** est l’expérience de contrôle. Vous pouvez la supprimer si vous ne souhaitez pas inclure une expérience de site par défaut comme option.
* **Expérience B** est l’expérience alternative que vous ajoutez à votre test. L’accent est mis sur cet onglet, que vous pouvez modifier selon vos besoins.

Pour ajouter d’autres expériences au test, cliquez sur l’icône **[!UICONTROL Ajouter]** ( ![Ajouter une icône](/help/main/assets/icons/Add.svg) ).

![](../assets/create-ab-3.png)

Pour plus d’informations sur l’ajout et la modification d’expériences dans le **[!UICONTROL compositeur d’expérience visuelle]**, voir [Ajouter une expérience](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#ab-add-experience).

## Étape 2 : définition du ciblage et de l’affectation du trafic {#set-targeting}

Après avoir accédé au menu **[!UICONTROL Ciblage]**, le diagramme de flux s’ouvre.

![Étape Ciblage des tests A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

Le diagramme de flux vous guide tout au long de l’attribution d’une audience et de son pourcentage de trafic, de la sélection de la méthode d’affectation du trafic et de la spécification de l’affectation du trafic pour chaque expérience de l’activité.

1. (Conditionnel) Cliquez sur la commande **[!UICONTROL Tous les visiteurs]** pour sélectionner une autre audience pour l’activité.

   L’audience **[!UICONTROL Tous les visiteurs]** est définie comme audience par défaut. Si vous sélectionnez une autre audience, son nom s’affiche dans le contrôle le plus à gauche. Vous pouvez par exemple limiter les entrées à 50 % de tous les visiteurs ou à 45 % pour l’audience « Parisiens ».

   +++ Procédure de sélection d’une autre audience

   Le cadre de droite s’affiche, ce qui vous permet d’ajouter ou de supprimer une audience et d’attribuer le pourcentage de visiteur ou de visiteuse à l’activité.

   1. Pour modifier l’audience, cliquez sur l’icône **[!UICONTROL Remplacer]** ( ![Icône Remplacer](/help/main/assets/icons/Retweet.svg) ) dans le cadre de droite.
   1. Dans la boîte de dialogue **[!UICONTROL Ajouter une audience]**, [sélectionnez l’audience souhaitée](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md), puis cliquez sur **[!UICONTROL Attribuer l’audience]**.

      Pour créer une audience qui combine plusieurs audiences, cliquez sur **[!UICONTROL Combiner des audiences]**. Pour plus d’informations, consultez [Combinaison de plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md).

      Pour créer une audience qui ne figure pas encore dans la **[!UICONTROL Bibliothèque d’audiences]**, cliquez sur **[!UICONTROL Créer une audience]**. Dans le workflow [créer une audience](/help/main/c-target/c-audiences/audiences.md), choisissez l’une des options suivantes :

      * **[!UICONTROL Bibliothèque d’audiences]** : créez une audience à la demande qui est enregistrée dans la **[!UICONTROL Bibliothèque d’audiences]** et peut être réutilisée dans d’autres activités.
      * **[!UICONTROL Cette activité uniquement]** : créez une [audience spécifique à l’activité](/help/main/c-target/creating-activity-only-audience.md) qui n’est pas enregistrée dans la **[!UICONTROL bibliothèque d’audiences]** et qui ne peut être utilisée que dans l’activité actuelle.

   1. Cliquez sur **[!UICONTROL Pourcentage de visiteurs]** dans le cadre de droite, puis choisissez le pourcentage de visiteurs qualifiés qui souhaitent rejoindre l’activité.

   +++

1. Cliquez sur la commande **[!UICONTROL Affectation du trafic]**, puis choisissez la méthode d&#39;affectation du trafic souhaitée dans le volet de droite. Dans ce scénario, cliquez sur **[!UICONTROL Ciblage automatique pour des expériences personnalisées]**.

   ![Paramètres de la méthode d&#39;affectation du trafic](/help/main/c-activities/assets/auto-target.png)

   +++ Méthodes d’affectation du trafic

   | Méthode | Ce qu&#39;il fait |
   |---|---|
   | **[!UICONTROL Manuel (Par Défaut)]** | Indiquez le pourcentage de participants qui doivent voir chaque expérience. Vous pouvez fractionner les pourcentages de manière uniforme entre tous les contenus ou spécifier des pourcentages supérieurs ou inférieurs pour chaque contenu. Le total de toutes les expériences doit être égal à 100 %. |
   | **[!UICONTROL Affectation automatique à la meilleure expérience]** | La plupart des participants aux activités sont automatiquement redirigés vers des expériences plus performantes. Certains visiteurs sont affectés à toutes les expériences afin de garantir l’exploration des expériences et de reconnaître les changements dans les tendances des performances. Pour plus d’informations, consultez [**[!UICONTROL Aperçu de l’affectation automatique &#x200B;]**](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4). |
   | **[!UICONTROL Ciblage automatique pour les expériences personnalisées]** | [!DNL Target] utilise le machine learning avancé pour personnaliser le contenu et générer des conversions en identifiant plusieurs expériences hautement performantes définies par des spécialistes marketing, puis en offrant l’expérience la plus personnalisée aux visiteurs selon leurs profils clients individuels et les comportements passés de visiteurs similaires. Pour plus d’informations, consultez [Aperçu du ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md). |

   +++

1. Cliquez sur **[!UICONTROL Expériences]** dans le volet de droite, puis spécifiez l’affectation du trafic souhaitée pour chaque expérience.

1. Lorsque vous êtes satisfait de votre audience, de vos choix d’expérience et de vos choix d’affectation du trafic, cliquez sur **[!UICONTROL Suivant]** pour passer à la troisième étape du workflow guidé en trois étapes.

## Étape 3 : configurer les objectifs et les paramètres {#configure-goals-and-settings}

Sur la page **[!UICONTROL Objectifs et paramètres]**, indiquez à [!DNL Target] comment mesurer l’activité. Les paramètres disponibles varient selon que vous utilisez [!DNL Target] ou [Analytics comme source de création de rapports](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

1. Spécifiez les [objectifs et paramètres](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) pour l’activité. Consultez les sections de la page et définissez ce dont vous avez besoin.

   | Section | Ce que vous avez défini |
   |---|---|
   | **[!UICONTROL Paramètres d’activité]** | Un objectif facultatif, la **[!UICONTROL Priorité]** (utilisée lorsque plusieurs activités partagent un emplacement et une audience) et la **[!UICONTROL Durée]** (dates de début et de fin). |
   | **[!UICONTROL Paramètres de création de rapports]** | La source de création de rapports, la mesure d’objectif (par exemple, une mesure **[!UICONTROL Conversion]**), les mesures supplémentaires, les audiences pour la création de rapports et la méthodologie statistique. |
   | **[!UICONTROL Paramètres avancés]** | Dépendances entre les mesures de succès, ce qui se passe lorsqu’un visiteur atteint la mesure d’objectif et la manière dont le nombre est incrémenté. |
   | **[!UICONTROL Autres métadonnées]** | Notes sur l’activité qui sont utiles pour vous ou pour les autres membres de l’équipe. |

   >[!NOTE]
   >
   >Si vous souhaitez utiliser [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) avec cette activité, consultez les informations importantes de la section Prise en charge de [A4T pour les activités d’affectation automatique et de ciblage automatique](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

1. Cliquez sur **[!UICONTROL Enregistrer et fermer]** ou **[!UICONTROL Enregistrer]**.

Après avoir créé l’activité, l’onglet **[!UICONTROL Aperçu]** affiche des informations sur l’activité, y compris un diagramme de votre activité.
