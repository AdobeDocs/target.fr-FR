---
keywords: audience;sélection de l’audience;choix de l’audience;sélecteurs
description: L’audience détermine les visiteurs du site qui sont entrés dans votre Adobe. [!DNL Target] activité.
title: Comment sélectionner une audience dans une [!DNL Target] Activité A/B ?
feature: A/B Tests
exl-id: 281ae227-c593-4b71-ad12-865430b332be
source-git-commit: 676350453268e4ffc04df83dcda0525842ca8b07
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 70%

---

# Sélection de l’audience

L’audience détermine les visiteurs du site qui sont entrés dans votre [!DNL Adobe Target] activité.

>[!NOTE]
>
>En plus de sélectionner une audience existante, vous pouvez combiner plusieurs audiences pour créer des audiences combinées ad hoc plutôt que d’en créer une nouvelle. Pour plus d’informations, voir [Combinaison de plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Dans le [!UICONTROL Audience] , cliquez sur le bouton **[!UICONTROL Modifier]** (points de suspension verticaux), puis cliquez sur **[!UICONTROL Remplacer l’audience]**.

   ![Option de remplacement d’une audience](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/replace-audience.png)

   Par défaut, tous les visiteurs constituent votre audience. Vous pouvez toutefois modifier l’audience. Les audiences sont sélectionnées depuis la bibliothèque d’audiences, ou vous pouvez créer une audience d’activité unique. La bibliothèque d’audiences contient les audiences qui ont été précédemment définies ainsi que les audiences courantes préconfigurées dans [!DNL Target].

1. Sélectionnez ou créez l’audience souhaitée :

   * Sélection d’une audience dans la bibliothèque
   * [Combinaison de plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)
   * [Créer une nouvelle audience](/help/main/c-target/c-audiences/create-audience.md#task_1D507519D3AD4390B507F188BD294DC1)
   * [Créer une audience d’activité unique](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483).

   Pour un test A/B sans ciblage d’audience spécifique, choisissez la valeur par défaut, [!UICONTROL Tous les visiteurs].

   Vous pouvez également modifier ou copier une audience en survolant l’audience souhaitée dans la variable [!UICONTROL Ajouter une audience] , comme illustré ci-dessous.

   La copie d’une audience s’avère utile si vous souhaitez créer une audience similaire à une audience existante. Vous pouvez faire une copie de l’audience, y apporter des modifications, puis les enregistrer en tant que nouvelle audience. Cette fonctionnalité de survol existe également dans d’autres types d’activité.

   ![Survol d’audience](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audience_picker_hover-new.png)

   Lors de la création d’une audience, vous pouvez sélectionner un emplacement (mbox) et préciser les paramètres de ce dernier. Sous [!UICONTROL Paramètres personnalisés], sélectionnez la mbox, puis spécifiez les paramètres souhaités.

   >[!NOTE]
   >
   >Les audiences sont automatiquement importées en arrière-plan lorsque vous ouvrez la liste d’audiences et que les audiences ont été importées il y a plus de 10 minutes.

1. (Conditionnel) Indiquez le pourcentage de visiteurs admissibles à inclure dans l’activité.

   Vous pouvez par exemple décider d’inclure 50 % de tous les visiteurs.

   ![Pourcentage d’audience](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Vous pouvez également choisir de laisser Target [affecter le trafic automatiquement](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

## Vidéos de formation

Les vidéos suivantes contiennent davantage d’informations sur les concepts abordés dans cet article.

### Utilisation des audiences dans Adobe Target (6:21) ![Badge d’aperçu](/help/main/assets/overview.png)

Cette vidéo explique de quelle façon utiliser les audiences dans [!DNL Target Standard/Premium].

* Explication du terme « audience »
* Explication des deux façons d’utiliser les audiences pour l’optimisation
* Recherche d’audiences dans la liste des audiences
* Ciblage d’une activité sur une audience
* Utilisation d’audiences à des fins de création passive de rapports dans une activité

>[!VIDEO](https://video.tv.adobe.com/v/17398)

### Workflow d’activité - Ciblage (2:14) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo comprend des informations sur la configuration des audiences.

* Affecter une audience à votre activité
* Augmenter ou ralentir le trafic
* Sélectionner votre méthode d’affectation du trafic
* Affecter du trafic entre différentes expériences

>[!VIDEO](https://video.tv.adobe.com/v/17385)

Pour plus d’informations, voir [Audiences](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271).
