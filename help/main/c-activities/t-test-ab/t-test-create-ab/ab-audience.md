---
keywords: audience;sélection de l’audience;choix de l’audience;sélecteurs
description: Définissez les visiteurs et visiteuses du site qui rejoignent votre activité  [!DNL Target] en fonction des critères d’audience.
title: Comment sélectionner une audience dans une activité a [!DNL Target] A/B ?
feature: A/B Tests
exl-id: 281ae227-c593-4b71-ad12-865430b332be
TQID: https://experienceleague.adobe.com/7W8BrRxk4mKlYlgGb-GSOuc0kRMRWBvSochz9STYrTs
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 575
ht-degree: 10%

---

# Sélection de l’audience

L’audience détermine les visiteurs qualifiés qui sont entrés dans votre activité [!DNL Adobe Target].

L’étape [!UICONTROL Ciblage] du workflow en trois parties lors de la [création d’une activité](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) affiche un diagramme de flux qui vous guide tout au long des étapes d’attribution d’une audience et de son pourcentage de trafic, de sélection de la méthode d’attribution du trafic et de spécification de l’attribution du trafic pour chaque expérience de l’activité.

![Étape Ciblage des tests A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

Pour plus d’informations sur toutes les options du diagramme de flux, voir [Création d’une activité de test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

## Sélectionner une audience pour l’activité

1. Cliquez sur le contrôle **[!UICONTROL Tous les visiteurs]** pour sélectionner une autre audience pour l’activité.

   L’audience [!UICONTROL Tous les visiteurs] est définie par défaut. Si vous sélectionnez une autre audience, son nom s’affiche dans le contrôle le plus à gauche.

   Pour un test A/B sans ciblage d’audience spécifique, choisissez la valeur par défaut [!UICONTROL Tous les visiteurs].

   Le cadre de droite s’affiche, ce qui vous permet d’ajouter ou de supprimer une audience et d’attribuer le pourcentage de visiteur ou de visiteuse à l’activité.

1. Pour modifier l’audience, cliquez sur l’icône **[!UICONTROL Remplacer]** ( ![Icône Remplacer](/help/main/assets/icons/Retweet.svg) ) dans le cadre de droite.

1. Dans la boîte de dialogue [!UICONTROL Ajouter une audience], [sélectionnez l’audience souhaitée](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) puis cliquez sur **[!UICONTROL Attribuer l’audience]**.

   Par défaut, tous les visiteurs constituent votre audience. Vous pouvez toutefois modifier l’audience. Les audiences sont sélectionnées à partir de la [!UICONTROL Bibliothèque d’audiences] ou vous pouvez créer une audience d’activité uniquement. La [!UICONTROL bibliothèque d’audiences] contient des audiences qui ont été définies précédemment, y compris certaines audiences courantes qui sont préconfigurées dans le cadre de [!DNL Target].

1. (Conditionnel) Cliquez sur **Combiner les audiences** pour [créer une audience qui combine plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md).

1. (Conditionnel) Pour créer une nouvelle audience qui ne figure pas encore dans la [!UICONTROL Bibliothèque d’audiences], cliquez sur **Créer une audience**, définissez l’audience, puis cliquez sur **[!UICONTROL Terminé]**.

   Au cours du [workflow de création d’audience](/help/main/c-target/c-audiences/audiences.md), vous pouvez choisir parmi les options suivantes :

   * **[!UICONTROL Bibliothèque d’audiences]** : créez une audience à la demande enregistrée dans la [!UICONTROL Bibliothèque d’audiences] qui peut être réutilisée dans d’autres activités.
   * **[!UICONTROL Cette activité uniquement]** : créez une [audience spécifique à une activité](/help/main/c-target/creating-activity-only-audience.md) qui n’est pas enregistrée dans la [!UICONTROL bibliothèque d’audiences] et qui ne peut être utilisée que dans l’activité en cours.

1. Cliquez sur **[!UICONTROL Pourcentage de visiteurs]** dans le volet de droite, puis spécifiez le pourcentage de visiteurs qualifiés à inclure dans l’activité.

1. Lorsque vous êtes satisfait(e) de votre audience, cliquez sur **[!UICONTROL Suivant]** pour passer à la troisième étape du workflow guidé en trois étapes.

>[!NOTE]
>
>Les audiences sont automatiquement importées en arrière-plan lorsque vous ouvrez la liste [!UICONTROL Audience] et que les audiences importées datent de plus de 10 minutes.

## Afficher les informations d’une audience

1. Dans la boîte de dialogue [!UICONTROL Ajouter des audiences], cliquez sur l’icône **[!UICONTROL Informations]** ( ![icône Infos](/help/main/assets/icons/InfoOutline.svg) ) à côté d’une audience pour afficher les détails la concernant, y compris sa source et ses attributs.

1. Cliquez sur **[!UICONTROL Afficher tous les détails]** pour afficher des détails supplémentaires sur l’audience. Les détails incluent les attributs de l’audience, sa description, son espace de travail, son type et sa source, ainsi qu’une liste des activités qui y font référence. Vous pouvez afficher des informations sur chaque audience, notamment le nom de l’activité, le statut, l’espace de travail, ainsi que la date de la dernière modification de l’audience et la personne qui l’a effectuée.

## Modifier ou copier une audience

Vous pouvez modifier ou copier une audience en cliquant sur l’icône [!UICONTROL Plus d’actions] ( ![icône Plus d’actions](/help/main/assets/icons/More.svg) ) à côté de l’audience souhaitée dans la boîte de dialogue [!UICONTROL Ajouter une audience], puis en cliquant sur [!UICONTROL Modifier] ou [!UICONTROL Copier].

La copie d’une audience s’avère utile si vous souhaitez créer une audience similaire à une audience existante. Vous pouvez faire une copie de l’audience, y apporter des modifications, puis les enregistrer en tant que nouvelle audience.
