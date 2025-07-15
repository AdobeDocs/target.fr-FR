---
keywords: activités;activité;types d’activité;modifier l’activité;modifier;copier
description: Découvrez les différentes manières de modifier une activité existante.
title: Comment modifier une activité ?
feature: Activities
exl-id: 5f2a930a-9950-430e-a898-50af1f917ec1
source-git-commit: cf7bc0f9ce72d5a170db76f5a932b196d4e1ddb0
workflow-type: tm+mt
source-wordcount: '890'
ht-degree: 28%

---

# Modification d’une activité

Découvrez comment modifier les activités existantes dans [!DNL Adobe Target]. Cet article couvre les différentes méthodes disponibles dans l’interface [!DNL Target] pour modifier les activités. Que vous mettiez à jour des expériences, ajustiez des règles de ciblage ou configuriez des objectifs, [!DNL Target] vous assure que vos modifications sont enregistrées en toute sécurité avant l’activation.

[!DNL Target] propose différents emplacements dans l’interface utilisateur où vous pouvez modifier des activités existantes. Le processus varie en fonction de la méthode choisie.

## Modifiez une activité à l’aide de l’icône [!UICONTROL More Actions] de survol de la page Activités {#section_29EE2ECA6B88473A8F9AC5600FFBB174}

1. Sur la page **[!UICONTROL Activities]**, cliquez sur l’icône **[!UICONTROL More Actions]** ( ![icône Autres actions](/help/main/assets/icons/MoreSmall.svg) ) en regard de l’activité à modifier, puis cliquez sur [!UICONTROL **Modifier**].

   Target ouvre l’activité dans le [!UICONTROL Visual Experience Composer] (VEC) et la page [!UICONTROL Experiences] s’affiche (première étape du workflow guidé en trois étapes).

1. Modifiez l’activité selon vos besoins à l’aide des [options du VEC](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

1. Cliquez sur le **[!UICONTROL Next]** pour passer à l’étape suivante, puis apportez les modifications nécessaires.

1. Lorsque vous accédez à la page **Objectifs et paramètres**, les options suivantes s’offrent à vous :

   * **[!UICONTROL Save & Close]:** Cliquez sur **[!UICONTROL Save and Close]** pour enregistrer vos modifications et afficher la page de [!UICONTROL Overview] de l’activité.
   * **Enregistrer :** cliquez sur l’icône **[!UICONTROL More Actions]** ( ![icône Plus d’actions](/help/main/assets/icons/MoreSmallListVert.svg) ), puis sélectionnez **[!UICONTROL Save]** pour enregistrer vos modifications et rester dans le VEC où vous pouvez continuer à apporter des modifications. Attendez que l’enregistrement soit terminé pour apporter des modifications supplémentaires. Le compositeur d’expérience visuelle se recharge avec les modifications actualisées une fois l’enregistrement terminé.

## Modifiez une activité en cliquant sur son nom dans la page [!UICONTROL Activities] {#section_176180DAD17E40CEA441903F39E0AA1C}

1. Pour éviter d’avoir à exécuter plusieurs étapes du workflow, cliquez sur l’activité souhaitée dans la page de [!UICONTROL Activities] pour l’ouvrir, sélectionnez une option dans la liste déroulante **[!UICONTROL Edit Activity]**, puis sélectionnez l’option souhaitée.

   * **Modifier les expériences :** vous permet d’accéder directement à la page [!UICONTROL Experiences] (première étape du workflow guidé en trois étapes).
   * **Modifier le ciblage** : permet d’accéder directement à la page [!UICONTROL Targeting] (deuxième étape du workflow guidé en trois étapes).
   * **[!UICONTROL Goals & Settings]** : permet d’accéder directement à la page [!UICONTROL Goals & Settings] (troisième étape du workflow guidé en trois étapes).

1. Apportez les modifications souhaitées, puis enregistrez l’activité.

   * **[!UICONTROL Save & Close]:** Cliquez sur **[!UICONTROL Save and Close]** pour enregistrer vos modifications et afficher la page de [!UICONTROL Overview] de l’activité.
   * **Enregistrer :** cliquez sur l’icône **[!UICONTROL More Actions]** ( ![icône Plus d’actions](/help/main/assets/icons/MoreSmallListVert.svg) ), puis sélectionnez **[!UICONTROL Save]** pour enregistrer vos modifications et rester dans le VEC où vous pouvez continuer à apporter des modifications. Attendez que l’enregistrement soit terminé pour apporter des modifications supplémentaires. Le compositeur d’expérience visuelle se recharge avec les modifications actualisées une fois l’enregistrement terminé.

## Utiliser les activités héritées créées dans [!DNL Recommendations Classic] {#classic}

La liste [!UICONTROL Activities] affiche les activités créées dans diverses sources, y compris les [!DNL Recommendations Classic]. Les actions suivantes sont disponibles lorsque vous utilisez des activités existantes créées dans [!DNL Recommendations Classic] :

* [!UICONTROL Activate]
* [!UICONTROL Deactivate]
* [!UICONTROL Archive]
* [!UICONTROL Copy]
* [!UICONTROL Delete]

Vous ne pouvez pas modifier directement une activité de [!DNL Recommendations]. Si vous souhaitez la modifier, vous devez en créer une copie à l’aide de [!DNL Target Premium], puis enregistrer l’activité nouvellement créée. Cette nouvelle activité peut ensuite être modifiée, si nécessaire.

## Enregistrer une activité dans un brouillon de formulaire {#section_968CD7A63027432EBD8FAE3A0F7404C3}

La fonction Enregistrer en tant que brouillon n’est plus disponible. Pour plus d’informations, voir *[!UICONTROL Status]* sous [Appliquer des filtres à la liste des activités](/help/main/c-activities/activities.md#filters).

## Copier/modifier une activité lors de l’utilisation d’espaces de travail {#section_45A92E1DD3934523B07E71EF90C4F8B6}

Avec un espace de travail, une organisation peut allouer un groupe d’utilisateurs spécifique à un groupe de propriétés spécifique. Un espace de travail peut être comparé à une suite de rapports dans [!DNL Adobe Analytics].

>[!NOTE]
>
>Les espaces de travail font partie de la fonctionnalité Propriétés et autorisations disponibles dans le cadre de la solution [!DNL Target Premium]. Elle n’est pas disponible dans [!DNL Target Standard] sans une licence [!DNL Target Premium].

Si vous êtes membre d’une organisation internationale, vous pouvez avoir un espace de travail dédié à vos pages web, propriétés ou sites européens et un autre espace de travail dédié à vos pages web, propriétés ou sites américains. Si vous faites partie d’une organisation multimarque, vous disposez peut-être d’un espace de travail distinct pour chacune de vos marques.

Pour plus d’informations sur les espaces de travail et la fonctionnalité Autorisations des utilisateurs d’Enterprise, voir [Autorisations des utilisateurs d’Enterprise](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#concept_E396B16FA2024ADBA27BC056138F9838).

Si des autorisations des utilisateurs Enterprise sont activées dans votre environnement, vous pouvez copier les activités dans le même espace de travail ou dans un espace de travail différent. Vous ne pouvez pas, pour le moment, déplacer une activité d’un espace de travail à un autre. Pour copier une activité dans un autre espace de travail, à partir de la page [!UICONTROL Activities], cliquez sur l’icône **[!UICONTROL More Actions]** ( ![icône Plus d’actions](/help/main/assets/icons/MoreSmall.svg) ) en regard de l’activité à copier, puis cliquez sur [!UICONTROL **Copier**] ou **[!UICONTROL Edit]**.

Tenez compte des informations suivantes lors de l’utilisation de la fonctionnalité de copie ou d’édition avec les espaces de travail :

* Si vous copiez une activité dans le même espace de travail ou depuis l’espace de travail par défaut vers un espace de travail autre que celui par défaut, l’Assistant Activité s’ouvre automatiquement. Dans les copies entre espaces de travail, il se peut que vous deviez uniquement mettre à jour les propriétés de l’activité.
* Lorsqu’une activité est copiée d’un espace de travail non par défaut vers un autre espace de travail (par défaut ou non), l’Assistant Activité s’ouvre et une saisie manuelle est nécessaire pour terminer la configuration :
   * **[!UICONTROL Properties]** : les propriétés peuvent différer selon les espaces de travail. Cette situation peut déclencher un avertissement :

      * Dans l’[!UICONTROL Form-Based Experience Composer], les avertissements s’affichent directement dans l’interface utilisateur pour une visibilité immédiate.

        ![Avertissement relatif à l’espace de travail basé sur les formulaires](/help/main/c-activities/assets/form-based-warning.png)

      * Dans le compositeur d’expérience visuelle, des avertissements s’affichent lorsque vous cliquez sur [!UICONTROL Configure] > [!UICONTROL Properties].

        ![vec-warning](/help/main/c-activities/assets/vec-warning.png)

        Pour résoudre ce problème, cliquez sur [!UICONTROL Add/Remove] afin que seules les propriétés disponibles dans l’espace de travail de destination s’affichent pour la sélection.

   * **Audiences et offres** : toutes les audiences et offres de l’espace de travail d’origine doivent être remplacées. Vous pouvez également les copier à partir des pages [!UICONTROL Audiences] ou [!UICONTROL Offers], puis sélectionner les éléments appropriés dans la liste correspondante de l’activité.

   * **Modifications manuelles requises** : toutes les modifications manuelles requises sont résumées dans l’étape finale ([!UICONTROL Save & Close]). Une fenêtre contextuelle affiche une liste des entités qui nécessitent des mises à jour, ce qui permet de s’assurer que tous les ajustements nécessaires sont effectués avant de terminer la configuration de l’activité.

     ![Avertissement de validation de Workspace](/help/main/c-activities/assets/work-space-validation.png)

Si la fonctionnalité [!UICONTROL Enterprise User Permissions] n’est pas activée pour votre environnement, toutes les activités s’ouvrent en mode d’édition avant d’être copiées.