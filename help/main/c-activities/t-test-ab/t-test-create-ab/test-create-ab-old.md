---
keywords: Créer A/B;test A/B;activité A/B;nouvelle activité a/b;créer une activité a/b
description: Découvrez comment utiliser le compositeur d’expérience visuelle (VEC) d’Adobe  [!DNL Target]  créer votre activité de test A/B directement sur une page compatible avec a [!DNL Target].
title: Comment créer un test A/B ?
feature: A/B Tests
exl-id: 76002873-0b7c-44a8-8e89-8ad28b63eccb
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 36%

---

# Création d’un test A/B

Utilisez le [!UICONTROL compositeur d’expérience visuelle] (VEC) dans [!DNL Adobe Target] pour créer votre activité de [!UICONTROL test A/B] directement sur une page compatible [!DNL Target] et pour modifier des parties de la page dans [!DNL Target].

>[!NOTE]
>
>Outre l’activité Manuel (par défaut) [!UICONTROL Test A/B] (traitée dans cet article), [!DNL Target] fournit deux types supplémentaires d’activités [!UICONTROL Test A/B] : [!UICONTROL Affectation automatique] et [!UICONTROL Ciblage automatique].
>
>Voir [Types d’activités de test A/B](/help/main/c-activities/t-test-ab/test-ab.md#types) dans la présentation des tests A/B **.

Pour créer une activité manuelle [!UICONTROL Test A/B] :

1. Dans la liste **[!UICONTROL Activités]**, cliquez sur **[!UICONTROL Créer une activité]** > **[!UICONTROL Test A/B]**.

   ![Liste déroulante Créer une activité](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >Les types d’activité disponibles dépendent de votre [!DNL Target] compte. Certains types d’activité peuvent ne pas apparaître dans votre liste. Par exemple, [!UICONTROL Recommendations] est une fonctionnalité de [Target Premium](/help/main/c-intro/intro.md#premium).
   >
   >Pour plus d’informations sur les différents types d’activité, voir [Activités](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03) et le [Target activities guide (Guide des activités Target)](/help/main/c-activities/target-activities-guide.md).

1. Dans la boîte de dialogue Créer une activité de test A/B , sélectionnez **[!UICONTROL Visuel (par défaut)]** si nécessaire.

   Si vous préférez utiliser le [!UICONTROL Compositeur d’expérience d’après les formulaires], sélectionnez [!UICONTROL Formulaire]. Reportez-vous à la section [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) pour plus d’informations.

   >[!NOTE]
   >
   >Outre le compositeur d’expérience visuelle et le [!UICONTROL compositeur d’expérience d’après les formulaires], [!DNL Target] propose le compositeur d’expérience visuelle d’application d’une seule page. Pour plus d’informations sur les divers compositeurs, voir [Offres et expériences](/help/main/c-experiences/experiences.md).
   >
   >Pour plus d’informations sur la résolution de problèmes liés au compositeur d’expérience visuelle, veuillez consulter [Dépannage du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Conditionnel) Si vous êtes un client [](/help/main/c-intro/intro.md#premium), dans la liste déroulante **[!UICONTROL Choisir Workspace]**, choisissez un [espace de travail](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

   L’option [[!UICONTROL Choisir le lieu de travail]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) dans l’illustration précédente est une fonctionnalité de [Target Premium](/help/main/c-intro/intro.md) qui peut ne pas s’afficher si votre entreprise dispose d’une licence [!UICONTROL Target Standard].

1. Dans la zone **[!UICONTROL Saisir l’URL de l’activité]**, spécifiez votre [URL de l’activité](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md), puis cliquez sur **[!UICONTROL Créer]**.

   Si votre compte est [configuré avec une URL par défaut](/help/main/administrating-target/visual-experience-composer-set-up.md), cette URL apparaît par défaut. Si nécessaire, vous pouvez remplacer l’URL par défaut par une autre URL.

   Le [!UICONTROL compositeur d’expérience visuelle] s’ouvre, affichant la page indiquée dans l’URL.

1. Cliquez sur **[!UICONTROL Activité sans titre]** dans la partie supérieure du VEC, puis spécifiez un nom pour l’activité dans l’espace prévu à cet effet.

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

1. Créez de nouvelles expériences en modifiant les éléments sur la page.

   Le [!UICONTROL compositeur d’expérience visuelle] affiche deux onglets sur le côté gauche dès lors qu’une activité est créée : Expérience A et Expérience B. Expérience A correspond à l’expérience de contrôle. Vous vous concentrez sur l’onglet Expérience B, que vous pouvez modifier selon vos besoins. L’expérience B est l’autre expérience que vous pouvez ajouter à votre test. Plusieurs expériences peuvent être ajoutées au test. Vous pouvez également supprimer l’Expérience A de l’activité si vous ne souhaitez pas que l’expérience de site par défaut soit une option possible.

   Pour plus d’informations sur l’ajout et la modification d’expériences dans le [!UICONTROL compositeur d’expérience visuelle], voir [Ajouter une expérience](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00). Pour modifier l’Expérience B, commencez à l’étape 2.

1. Cliquez sur **[!UICONTROL Ciblage]** en haut du [!UICONTROL Compositeur d’expérience visuelle] pour passer à l’étape suivante du workflow guidé en trois étapes.

   Le diagramme de flux s’ouvre.

   ![Étape Ciblage des tests A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   Le diagramme de flux vous guide tout au long des étapes permettant le choix de l’audience pour l’activité et la configuration des expériences.

1. Dans la zone **[!UICONTROL Audience]**, cliquez sur l’icône de modification (les points de suspension verticaux), cliquez sur **[!UICONTROL Remplacer l’audience]**, puis [sélectionnez l’audience](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) pour votre activité.

   Par défaut, l’audience est définie sur [!UICONTROL  Tous les visiteurs ].

1. Sélectionnez le pourcentage de visiteurs admissibles qui doivent entrer dans l’activité.

   ![Pourcentage d’audience](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Vous pouvez par exemple limiter les entrées à 50 % de tous les visiteurs ou à 45 % pour l’audience « Parisiens ».

1. Configurez l’affectation de votre trafic.

   Vous pouvez proposer plusieurs expériences à une même audience. Un diagramme affiche l’audience sélectionnée et les expériences que vous avez ajoutées à l’activité.

   Choisissez la méthode d’affectation du trafic souhaitée :

   * **[!UICONTROL Manuel (par défaut)]** : indiquez le pourcentage de participants qui doivent voir chaque expérience. Vous pouvez fractionner les pourcentages de manière uniforme entre tous les contenus ou spécifier des pourcentages supérieurs ou inférieurs pour chaque contenu. Le total de toutes les expériences doit être égal à 100 %.

   * **[!UICONTROL Affectation automatique à la meilleure expérience]** : la plupart des participants à une activité sont automatiquement redirigés vers des expériences plus performantes. Certains visiteurs sont affectés à toutes les expériences afin de garantir l’exploration des expériences et de reconnaître les changements dans les tendances des performances. Pour plus d’informations, consultez la présentation de l’[[!UICONTROL affectation automatique] ](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   * **[!UICONTROL Ciblage automatique pour les expériences personnalisées]** : [!DNL Target] utilise le machine learning avancé pour personnaliser le contenu et générer des conversions en identifiant plusieurs expériences hautement performantes définies par des spécialistes marketing, puis en proposant l’expérience la plus personnalisée aux visiteurs selon leur profil client individuel et le comportement antérieur de visiteurs similaires. Pour plus d’informations, voir [Présentation du ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

   Vous pouvez également cliquer sur **[!UICONTROL Ajouter]** pour ajouter une autre expérience à l’activité.

1. Lorsque vous êtes satisfait de votre audience, de vos choix d’expérience et de vos choix d’affectation du trafic, cliquez sur **[!UICONTROL Suivant]** pour passer à la troisième étape du workflow guidé en trois étapes.

1. Spécifiez les [objectifs et paramètres](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) pour l’activité.

1. Cliquez sur **[!UICONTROL Enregistrer et fermer]** ou **[!UICONTROL Enregistrer]**.

Après avoir créé l’activité, l’onglet [!UICONTROL Aperçu] affiche des informations sur l’activité, y compris un diagramme de votre activité.

## Vidéo de formation : Création de tests A/B (8:36) ![Badge de tutoriel](/help/main/assets/tutorial.png)

Cette vidéo explique comment créer un test A/B à l’aide du processus assisté en trois étapes de [!DNL Target].

* Créez une activité [!UICONTROL Test A/B] dans [!DNL Adobe Target]
* Affecter du trafic à l’aide d’un fractionnement manuel ou de l’affectation automatique du trafic

>[!VIDEO](https://video.tv.adobe.com/v/17391)
