---
keywords: audience;règles d’audience;créer une audience;création d’audience
description: Découvrez comment créer des audiences personnalisées et les enregistrer dans la bibliothèque  [!DNL Adobe Target] [!UICONTROL Audiences] pour les utiliser dans des activités.
title: Comment créer des audiences ?
feature: Audiences
exl-id: 59057461-d958-4d38-9725-53aacbe1f7eb
source-git-commit: a185edee86f6d07b488cf5dd3fe7e5dc3f4e87b3
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 58%

---

# Création d’audiences dans [!DNL Target]

Vous pouvez créer des audiences personnalisées et les enregistrer dans la bibliothèque [!DNL Adobe Target] [!UICONTROL Audiences] pour les utiliser dans vos activités. Vous pouvez également copier une audience existante que vous pourrez ensuite modifier pour créer une audience similaire et combiner plusieurs audiences.

## Présentation de l’audience

Les audiences sont définies par des règles qui déterminent qui est inclus ou exclu d’une activité [!DNL Target]. Une définition d’audience peut contenir plusieurs règles. De plus, chaque règle peut inclure plusieurs paramètres. Les définitions d’audience complexes utilisent les opérateurs booléens ET et OU pour associer les règles et les paramètres afin que vous puissiez contrôler avec précision quels visiteurs sont comptabilisés comme participants à l’activité.

Lorsque vous combinez des règles ou des paramètres à l’aide de l’opérateur AND, tout membre potentiel de l’audience doit satisfaire *toutes* conditions définies pour être inclus comme participant. Par exemple, si vous définissez une règle de système d’exploitation ET une règle de navigateur, seuls les visiteurs qui utilisent le système d’exploitation défini *et* le navigateur défini sont inclus dans l’activité.

Lorsque vous associez des règles ou des paramètres à l’aide de l’opérateur OU, les membres potentiels de l’audience ne doivent respecter qu’une des conditions définies pour être inclus comme participants. Par exemple, si vous définissez plusieurs règles mobiles liées par OU, les visiteurs qui respectent *un* des critères définis sont inclus dans l’activité.

Vous pouvez mélanger les deux opérateurs booléens pour créer des règles complexes. Les opérateurs à un même niveau de règle doivent toutefois correspondre. L’interface utilisateur applique automatiquement l’opérateur correct.

Par exemple, la règle suivante cible les visiteurs qui utilisent Chrome *ou* Firefox sur un ordinateur Windows :

![Création d’une audience](assets/audience_create.png)

>[!NOTE]
>
>Veillez à ne pas créer de règles qui excluent tous les membres potentiels de l’audience. Par exemple, il n’est pas possible de visiter une page en utilisant simultanément Chrome *et* Firefox.

## Création d’une audience

1. Cliquez sur **[!UICONTROL Audiences]** dans la barre de menu supérieure.

   ![image de liste_audiences](assets/audiences_list.png)

1. Dans la liste [!UICONTROL Audiences], cliquez sur **[!UICONTROL Create Audience]**.

   Ou

   Pour copier une audience existante, dans la liste [!UICONTROL Audiences], cliquez sur l’icône **[!UICONTROL More Actions]** (icône représentant des points de suspension), puis sur **[!UICONTROL Duplicate]**. Vous pouvez ensuite modifier l’audience pour créer une audience similaire.

1. Saisissez un nom d’audience descriptif et unique, ainsi qu’une description facultative.

   Les noms d’audience ne peuvent pas commencer par les caractères suivants :

   `=  +  -  !  @`

   Les noms d’audience ne peuvent pas contenir l’une des séquences de caractères suivantes :

   `;=  ;+  ;-  ;@  ,=  ,+  ,-  ,@  ["  "]  ['  ]'`

1. Faites glisser les attributs de votre choix depuis la liste **[!UICONTROL Attributes]** située à droite du volet du créateur d’audiences.

   ![Faire glisser et déposer des attributs](assets/drag-attribute.png)

   Chaque type de règle possède ses propres paramètres. Voir [Catégories d’audiences](/help/main/c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D) pour plus d’informations sur la configuration de chaque type de règle d’audience.

1. Définissez les paramètres des règles.

   Par exemple, l’audience suivante cible les visiteurs en provenance de l’Utah à l’aide du système d’exploitation Macintosh.

   ![Audience Utah/Macintosh](assets/adience-builder.png)

1. (Conditionnel) Continuez à ajouter et à définir les attributs souhaités.

   Pour créer un autre conteneur, cliquez sur **[!UICONTROL Add container]** ou faites glisser un autre attribut dans le volet Audience Builder. Vous pouvez ensuite ajuster l’opérateur (ET ou OU) à l’aide de la liste déroulante.

1. Cliquez sur **[!UICONTROL Done]**.

   Les audiences nouvellement créées s’affichent dans la liste après un délai de traitement de quelques secondes. Si l’audience ne s’affiche pas immédiatement dans la liste, recherchez-la ou actualisez la liste.

## Vidéo de formation : création d’audiences ![Badge d’aperçu](/help/main/assets/overview.png)

Cette vidéo comprend des informations sur la création des audiences.

* Créer des audiences
* Définir des catégories d’audiences

>[!VIDEO](https://video.tv.adobe.com/v/17392)
