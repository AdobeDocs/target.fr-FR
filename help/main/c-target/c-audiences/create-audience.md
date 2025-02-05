---
keywords: audience;règles d’audience;créer une audience;création d’audience
description: Découvrez comment créer des audiences personnalisées et les enregistrer dans la bibliothèque  [!DNL Adobe Target] [!UICONTROL Audiences] pour les utiliser dans des activités.
title: Comment Créer Des Audiences ?
feature: Audiences
exl-id: 59057461-d958-4d38-9725-53aacbe1f7eb
source-git-commit: 19d2b14f137fe4dbf95e9f9f9b84f80b93d1e281
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 51%

---

# Création d’audiences dans [!DNL Target]

Créez des audiences personnalisées et enregistrez-les dans la bibliothèque [!DNL Adobe Target] [!UICONTROL Audiences] pour les utiliser dans vos activités. Vous pouvez également copier une audience existante, que vous pouvez ensuite modifier, afin de créer une audience similaire et de combiner plusieurs audiences.

## Présentation de l’audience

Les audiences sont définies par des règles qui déterminent qui est inclus ou exclu d’une activité [!DNL Target]. Une définition d’audience peut contenir plusieurs règles. De plus, chaque règle peut inclure plusieurs paramètres. Les définitions d’audience complexes utilisent les opérateurs booléens ET et OU pour associer les règles et les paramètres afin que vous puissiez contrôler avec précision quels visiteurs sont comptabilisés comme participants à l’activité.

Lorsque vous combinez des règles ou des paramètres avec ET, tout membre potentiel de l’audience doit remplir les conditions définies *all* pour être inclus en tant que participant. Par exemple, si vous définissez une règle de système d’exploitation ET une règle de navigateur, seuls les visiteurs qui utilisent le système d’exploitation défini *et* le navigateur défini sont inclus dans l’activité.

Lorsque vous associez des règles ou des paramètres à l’aide de l’opérateur OU, les membres potentiels de l’audience ne doivent respecter qu’une des conditions définies pour être inclus comme participants. Par exemple, si vous définissez plusieurs règles mobiles liées par OU, les visiteurs qui respectent *un* des critères définis sont inclus dans l’activité.

Vous pouvez mélanger les deux opérateurs booléens pour créer des règles complexes. Les opérateurs à un même niveau de règle doivent toutefois correspondre. L’interface utilisateur applique automatiquement l’opérateur correct.

Par exemple, la règle suivante cible les visiteurs qui utilisent [!DNL Chrome] *ou* [!DNL Firefox] sur un ordinateur [!DNL Windows] :

![Création d’une audience](assets/audience_create.png)

>[!NOTE]
>
>Veillez à ne pas créer de règles qui excluent tous les membres potentiels de l’audience. Par exemple, il n’est pas possible pour une personne de consulter simultanément une page à l’aide de [!DNL Chrome] *et* [!DNL Firefox].

## Création d’une audience

1. Cliquez sur **[!UICONTROL Audiences]** dans la barre de menus supérieure.

   ![image audience_list](assets/audiences_list.png)

1. Dans la liste [!UICONTROL Audiences], cliquez sur **[!UICONTROL Create Audience]**.

   Ou

   Pour copier une audience existante, à partir de la liste [!UICONTROL Audiences], cliquez sur l’icône **[!UICONTROL More Actions]** ( ![icône Autres actions](/help/main/assets/icons/MoreSmallListVert.svg) ) de l’audience à copier, puis cliquez sur **[!UICONTROL Duplicate]**. Vous pouvez ensuite modifier l’audience pour créer une audience similaire.

1. Saisissez un nom d’audience unique et descriptif, ainsi qu’une description facultative.

   Les noms d’audience ne peuvent pas commencer par les caractères suivants :

   `=  +  -  !  @`

   Les noms d’audience ne peuvent pas contenir l’une des séquences de caractères suivantes :

   `;=  ;+  ;-  ;@  ,=  ,+  ,-  ,@  ["  "]  ['  ]'`

1. Faites glisser et déposez les attributs de votre choix de la liste de **[!UICONTROL Attributes]** à gauche vers le volet du créateur d’audiences.

   ![Attributs glisser-déposer](assets/drag-attribute.png)

   Chaque type de règle possède ses propres paramètres. Voir [Catégories d’audiences](/help/main/c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D) pour plus d’informations sur la configuration de chaque type de règle d’audience.

1. Définissez les paramètres des règles.

   Par exemple, l’audience suivante cible les visiteurs de l’Utah à l’aide du système d’exploitation [!DNL Macintosh].

   ![ Audience Utah/Macintosh ](assets/adience-builder.png)

1. (Conditionnel) Continuez à ajouter et à définir les attributs souhaités.

   Pour créer un autre conteneur, cliquez sur **[!UICONTROL Add container]** ou faites simplement glisser un autre attribut dans le volet du Créateur d’audience. Vous pouvez ensuite ajuster l’opérateur (ET ou OU) à l’aide de la liste déroulante.

1. Cliquez sur **[!UICONTROL Done]**.

   Les audiences nouvellement créées s’affichent dans la liste après un délai de traitement de quelques secondes. Si l’audience ne s’affiche pas immédiatement dans la liste, recherchez-la ou actualisez la liste.

## Vidéo de formation : création d’audiences ![badge d’aperçu](/help/main/assets/overview.png)

Cette vidéo comprend des informations sur la création des audiences.

* Créer des audiences
* Définir des catégories d’audiences

>[!VIDEO](https://video.tv.adobe.com/v/17392)
