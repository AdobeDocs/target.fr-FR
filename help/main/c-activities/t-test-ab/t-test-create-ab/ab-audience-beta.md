---
keywords: audience;sélection de l’audience;choix de l’audience;sélecteurs
description: Définissez les visiteurs du site qui rejoignent votre activité d'Adobe  [!DNL Target] en fonction des critères d'audience.
title: Comment sélectionner une audience dans une activité  [!DNL Target] A/B ?
feature: A/B Tests
hide: true
hidefromtoc: true
exl-id: 117cec36-87ef-4bd5-8a39-fb885b679d95
source-git-commit: d5bd3b0d7cdf6eb06175a6365da6b8173f76800f
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 8%

---

# Sélection de l’audience

L’audience détermine les visiteurs admissibles qui sont entrés dans votre activité [!DNL Adobe Target].

L’étape [!UICONTROL Targeting] du workflow assisté en trois parties lorsque [création d’une activité](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab-beta.md) affiche un diagramme de flux qui vous guide tout au long des étapes d’attribution d’une audience et de son pourcentage de trafic, de sélection de la méthode d’affectation du trafic et de spécification de l’affectation du trafic pour chaque expérience de l’activité.

![Étape Ciblage des tests A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

Pour plus d’informations sur toutes les options du diagramme de flux, voir [Création d’une activité de test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab-beta.md).

## Sélection de l’audience de l’activité

1. Cliquez sur le contrôle **[!UICONTROL All Visitors]** pour sélectionner une autre audience pour l’activité.

   L’audience [!UICONTROL All Visitors] est définie par défaut. Si vous sélectionnez une autre audience, son nom s’affiche dans le contrôle le plus à gauche.

   Pour un test A/B sans ciblage d’audience spécifique, choisissez la valeur par défaut, [!UICONTROL All Visitors].

   Le cadre de droite s’affiche, ce qui vous permet d’ajouter ou de supprimer une audience et d’attribuer le pourcentage du visiteur pour l’activité.

1. Pour modifier l’audience, cliquez sur l’icône **[!UICONTROL Replace]** ( ![Icône Remplacer](/help/main/assets/icons/Retweet.svg) ) dans le cadre de droite.

1. Dans la boîte de dialogue [!UICONTROL Add Audience], [sélectionnez l’audience souhaitée](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md), puis cliquez sur **[!UICONTROL Assign Audience]**.

   Par défaut, tous les visiteurs constituent votre audience. Vous pouvez toutefois modifier l’audience. Les audiences sont sélectionnées à partir de [!UICONTROL Audience Library] ou vous pouvez créer une audience d’activité unique. [!UICONTROL Audience Library] contient des audiences qui ont été précédemment définies, y compris certaines audiences courantes préconfigurées dans le cadre de [!DNL Target].

1. (Conditionnel) Cliquez sur **Combiner les audiences** à [créer une audience qui combine plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md).

1. (Conditionnel) Pour créer une audience qui ne figure pas encore dans le [!UICONTROL Audience Library], cliquez sur **Créer une audience**, définissez l’audience, puis cliquez sur **[!UICONTROL Done]**.

   Au cours du [processus de création d’audience](/help/main/c-target/c-audiences/audiences.md), vous pouvez choisir parmi les options suivantes :

   * **[!UICONTROL Audience Library]** : créez une audience à la demande qui est enregistrée dans le [!UICONTROL Audience Library] et qui peut être réutilisée dans d’autres activités.
   * **[!UICONTROL This activity only]** : créez une [audience spécifique à une activité](/help/main/c-target/creating-activity-only-audience.md) qui n’est pas enregistrée dans [!UICONTROL Audience Library] et peut être utilisée dans l’activité active uniquement.

1. Cliquez sur **[!UICONTROL Visitor Percentage]** dans le volet de droite, puis spécifiez le pourcentage de visiteurs admissibles à inclure dans l’activité.

1. Lorsque vous êtes satisfait de votre audience, cliquez sur **[!UICONTROL Next]** pour passer à la troisième étape du processus assisté en trois étapes.

>[!NOTE]
>
>Les audiences sont automatiquement importées en arrière-plan lorsque vous ouvrez la liste [!UICONTROL Audience] et que les audiences importées ont plus de 10 minutes.

## Affichage des informations d’une audience

1. Dans la boîte de dialogue [!UICONTROL Add Audiences], cliquez sur l’icône **[!UICONTROL Information]** ( ![Icône Infos](/help/main/assets/icons/InfoOutline.svg) ) en regard d’une audience pour afficher des détails sur cette audience, y compris sa source et ses attributs.

1. Cliquez sur **[!UICONTROL View Full Details]** pour afficher des détails supplémentaires sur l’audience. Les détails incluent les attributs de l’audience, la description, l’espace de travail, le type et la source de l’audience, ainsi qu’une liste des activités qui font référence à cette audience. Vous pouvez afficher des informations sur chaque audience, notamment le nom de l’activité, l’état, l’espace de travail, ainsi que la date de dernière modification de l’audience et la personne qui l’a modifiée.

## Modification ou copie d’une audience

Vous pouvez modifier ou copier une audience en cliquant sur l’icône [!UICONTROL More Actions] ( ![Icône Autres actions](/help/main/assets/icons/More.svg) ) en regard de l’audience souhaitée dans la boîte de dialogue [!UICONTROL Add Audience], puis en cliquant sur [!UICONTROL Edit] ou [!UICONTROL Copy].

La copie d’une audience s’avère utile si vous souhaitez créer une audience similaire à une audience existante. Vous pouvez faire une copie de l’audience, apporter vos modifications, puis l’enregistrer en tant que nouvelle audience.
