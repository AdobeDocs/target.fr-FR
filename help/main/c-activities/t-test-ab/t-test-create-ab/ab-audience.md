---
keywords: audience;sélection de l’audience;choix de l’audience;sélecteurs
description: Définissez les visiteurs et visiteuses du site qui rejoignent votre Adobe  [!DNL Target] activité en fonction des critères d’audience.
title: Comment sélectionner une audience dans une activité a [!DNL Target] A/B ?
feature: A/B Tests
exl-id: 281ae227-c593-4b71-ad12-865430b332be
source-git-commit: f6845756f9d4220214b0d9131cd5f27db2ae94a9
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 8%

---

# Sélection de l’audience

L’audience détermine les visiteurs qualifiés qui sont entrés dans votre activité [!DNL Adobe Target].

L’étape [!UICONTROL Targeting] du workflow guidé en trois parties lors de la [création d’une activité](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) affiche un diagramme de flux qui vous guide tout au long des étapes suivantes : attribution d’une audience et de son pourcentage de trafic, sélection de la méthode d’affectation du trafic et spécification de l’affectation du trafic pour chaque expérience de l’activité.

![Étape Ciblage des tests A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

Pour plus d’informations sur toutes les options du diagramme de flux, voir [Création d’une activité de test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

## Sélectionner une audience pour l’activité

1. Cliquez sur le contrôle **[!UICONTROL All Visitors]** pour sélectionner une autre audience pour l’activité.

   L’audience [!UICONTROL All Visitors] est définie comme audience par défaut. Si vous sélectionnez une autre audience, son nom s’affiche dans le contrôle le plus à gauche.

   Pour un test A/B sans ciblage d’audience spécifique, choisissez la valeur par défaut, [!UICONTROL All Visitors].

   Le cadre de droite s’affiche, ce qui vous permet d’ajouter ou de supprimer une audience et d’attribuer le pourcentage de visiteur ou de visiteuse à l’activité.

1. Pour modifier l’audience, cliquez sur l’icône **[!UICONTROL Replace]** ( ![icône Remplacer](/help/main/assets/icons/Retweet.svg) ) dans le cadre de droite.

1. Dans la boîte de dialogue [!UICONTROL Add Audience], [sélectionnez l’audience souhaitée](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) puis cliquez sur **[!UICONTROL Assign Audience]**.

   Par défaut, tous les visiteurs constituent votre audience. Vous pouvez toutefois modifier l’audience. Les audiences sont sélectionnées dans la [!UICONTROL Audience Library] ou vous pouvez créer une audience d’activité unique. Le [!UICONTROL Audience Library] contient des audiences qui ont été précédemment définies, y compris certaines audiences courantes qui sont préconfigurées dans le cadre de [!DNL Target].

1. (Conditionnel) Cliquez sur **Combiner les audiences** pour [créer une audience qui combine plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md).

1. (Conditionnel) Pour créer une nouvelle audience qui n’est pas encore dans la [!UICONTROL Audience Library], cliquez sur **Créer une audience**, définissez l’audience, puis cliquez sur **[!UICONTROL Done]**.

   Au cours du [workflow de création d’audience](/help/main/c-target/c-audiences/audiences.md), vous pouvez choisir parmi les options suivantes :

   * **[!UICONTROL Audience Library]** : créez une audience à la demande qui est enregistrée dans le [!UICONTROL Audience Library] et qui peut être réutilisée dans d’autres activités.
   * **[!UICONTROL This activity only]** : créez une [audience spécifique à l’activité](/help/main/c-target/creating-activity-only-audience.md) qui n’est pas enregistrée dans le [!UICONTROL Audience Library] et qui ne peut être utilisée que dans l’activité actuelle.

1. Cliquez sur **[!UICONTROL Visitor Percentage]** dans le volet de droite, puis spécifiez le pourcentage de visiteurs qualifiés à inclure dans l’activité.

1. Lorsque vous êtes satisfait(e) de votre audience, cliquez sur **[!UICONTROL Next]** pour passer à la troisième étape du workflow guidé en trois étapes.

>[!NOTE]
>
>Les audiences importées sont automatiquement importées en arrière-plan lorsque vous ouvrez la liste [!UICONTROL Audience] et qu’elles datent de plus de 10 minutes.

## Afficher les informations d’une audience

1. Dans la boîte de dialogue [!UICONTROL Add Audiences], cliquez sur l’icône **[!UICONTROL Information]** ( ![icône Infos](/help/main/assets/icons/InfoOutline.svg) ) à côté d’une audience pour afficher les détails la concernant, y compris sa source et ses attributs.

1. Cliquez sur **[!UICONTROL View Full Details]** pour afficher des détails supplémentaires sur l’audience. Les détails incluent les attributs de l’audience, sa description, son espace de travail, son type et sa source, ainsi qu’une liste des activités qui y font référence. Vous pouvez afficher des informations sur chaque audience, notamment le nom de l’activité, le statut, l’espace de travail, ainsi que la date de la dernière modification de l’audience et la personne qui l’a effectuée.

## Modifier ou copier une audience

Vous pouvez modifier ou copier une audience en cliquant sur l’icône [!UICONTROL More Actions] ( ![icône Autres actions](/help/main/assets/icons/More.svg) ) à côté de l’audience souhaitée dans la boîte de dialogue [!UICONTROL Add Audience], puis en cliquant sur [!UICONTROL Edit] ou [!UICONTROL Copy].

La copie d’une audience s’avère utile si vous souhaitez créer une audience similaire à une audience existante. Vous pouvez faire une copie de l’audience, apporter vos modifications, puis l’enregistrer en tant que nouvelle audience.
