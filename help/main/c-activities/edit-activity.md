---
keywords: activités;activité;types d’activité;modifier l’activité;modifier;copier
description: Découvrez les différentes manières de modifier une activité existante.
title: Comment modifier une activité ?
feature: Activities
exl-id: 5f2a930a-9950-430e-a898-50af1f917ec1
TQID: 'https://experienceleague.adobe.com/joqYeCK6Zy6Xz27eRKodA4M1kfPMi-AJu84wNXsGgQA'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 8c6f23b495228ab930e6649aa2f9e6dae506cae2
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 14%
---
# Modification d’une activité {#edit-activity}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment modifier une activité existante à partir de la page **[!UICONTROL Activités]**, comment copier une activité lorsque des espaces de travail sont utilisés et quelles actions s’appliquent aux activités héritées.

>[!ENDSHADEBOX]

Les activités existantes peuvent être modifiées à plusieurs endroits de l’interface [!DNL Adobe Target], de sorte que les modifications apportées aux expériences, aux règles de ciblage ou aux objectifs n’exigent pas de recréer l’activité. Les étapes varient en fonction de la méthode choisie. La fonctionnalité **[!UICONTROL Enregistrer en tant que brouillon]** n&#39;est plus disponible. Pour plus d’informations, voir **[!UICONTROL État]** sous [Appliquer des filtres à la liste des activités](/help/main/c-activities/activities.md#filters).

## Modifier à partir de l’icône [!UICONTROL Plus d’actions] {#section_29EE2ECA6B88473A8F9AC5600FFBB174}

Pour modifier une activité en suivant les étapes du workflow guidé en trois étapes :

1. Sur la page **[!UICONTROL Activités]**, cliquez sur l’icône **[!UICONTROL Plus d’actions]** ( ![Icône Plus d’actions](/help/main/assets/icons/MoreSmall.svg) ) en regard de l’activité, puis cliquez sur **[!UICONTROL Modifier]**.

   [!DNL Target] ouvre l’activité dans le **[!UICONTROL compositeur d’expérience visuelle]** (VEC) et affiche la page **[!UICONTROL Expériences]**, qui est la première étape du workflow.

   ![Icône Autres actions](assets/edit-activity-1.png)

1. Modifiez l’activité en utilisant les [options du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

1. Cliquez sur **[!UICONTROL Suivant]** pour passer à l’étape suivante, puis apportez les modifications nécessaires.

1. Sur la page **[!UICONTROL Objectifs et paramètres]**, enregistrez les modifications à l’aide de l’une des options suivantes :

   * **[!UICONTROL Enregistrer et fermer]:** Enregistre les modifications et affiche la page **[!UICONTROL Aperçu]** de l’activité.
   * **[!UICONTROL Enregistrer] :** Cliquez sur l’icône **[!UICONTROL Plus d’actions]** ( ![Icône Plus d’actions](/help/main/assets/icons/MoreSmallListVert.svg) ), puis sélectionnez **[!UICONTROL Enregistrer]** pour enregistrer les modifications et rester dans le compositeur d’expérience visuelle, où vous pouvez continuer à apporter des modifications. Attendez que l’enregistrement soit terminé pour apporter des modifications supplémentaires. Le compositeur d’expérience visuelle se recharge avec les modifications actualisées une fois l’enregistrement terminé.

     ![Icône Autres actions](assets/edit-activity-2.png)

## Modifier à partir du nom de l’activité {#section_176180DAD17E40CEA441903F39E0AA1C}

Pour accéder directement à l’étape qui nécessite des modifications, sans passer par le workflow :

1. Sur la page **[!UICONTROL Activités]**, cliquez sur l’activité pour l’ouvrir, puis sélectionnez l’une des options de la liste déroulante **[!UICONTROL Modifier l’activité]** :

   * **[!UICONTROL Modifier les expériences]:** Ouvre la page **[!UICONTROL Expériences]** (première étape du workflow).
   * **[!UICONTROL Modifier le ciblage]:** Ouvre la page **[!UICONTROL Ciblage]** (deuxième étape du workflow).
   * **[!UICONTROL Objectifs et paramètres]:** Ouvre la page **[!UICONTROL Objectifs et paramètres]** (troisième étape du workflow).

     ![Menu Modifier l’activité](assets/edit-activity-3.png)

1. Apportez les modifications, puis enregistrez l’activité avec **[!UICONTROL Enregistrer et fermer]** ou **[!UICONTROL Enregistrer]**, comme décrit dans la section précédente.

## Copier et modifier avec les espaces de travail {#section_45A92E1DD3934523B07E71EF90C4F8B6}

Avec un espace de travail, une organisation peut allouer un groupe d’utilisateurs spécifique à un groupe de propriétés spécifique. Un espace de travail peut être comparé à une suite de rapports dans [!DNL Adobe Analytics].

>[!NOTE]
>
>Les espaces de travail font partie des fonctionnalités **[!UICONTROL Propriétés et Autorisations]** disponibles dans le cadre de la solution [!DNL Target Premium]. Elle n’est pas disponible dans [!DNL Target Standard] sans une licence [!DNL Target Premium].

Si vous êtes membre d’une organisation internationale, vous pouvez avoir un espace de travail dédié à vos pages web, propriétés ou sites européens et un autre espace de travail dédié à vos pages web, propriétés ou sites américains. Si vous faites partie d’une organisation multimarque, vous disposez peut-être d’un espace de travail distinct pour chacune de vos marques.

Pour plus d’informations sur les espaces de travail et la fonctionnalité Autorisations des utilisateurs d’Enterprise, voir [Autorisations des utilisateurs d’Enterprise](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#concept_E396B16FA2024ADBA27BC056138F9838).

Si les **[!UICONTROL autorisations des utilisateurs d’Enterprise]** sont activées dans votre environnement, vous pouvez copier des activités dans le même espace de travail ou dans un autre. Vous ne pouvez pas, pour le moment, déplacer une activité d’un espace de travail à un autre. Pour copier une activité dans un autre espace de travail, à partir de la page **[!UICONTROL Activités]**, cliquez sur l’icône **[!UICONTROL Plus d’actions]** ( ![Icône Plus d’actions](/help/main/assets/icons/MoreSmall.svg) ) en regard de l’activité à copier, puis cliquez sur **[!UICONTROL Copier]**.

Tenez compte des informations suivantes lors de l’utilisation de la fonctionnalité de copie ou d’édition avec les espaces de travail :

* Si vous copiez une activité dans le même espace de travail ou depuis l’espace de travail par défaut vers un espace de travail autre que celui par défaut, l’Assistant Activité s’ouvre automatiquement. Dans les copies entre espaces de travail, il se peut que vous deviez uniquement mettre à jour les propriétés de l’activité.
* Lorsqu’une activité est copiée d’un espace de travail non par défaut vers un autre espace de travail (par défaut ou non), l’Assistant Activité s’ouvre et une saisie manuelle est nécessaire pour terminer la configuration :
  * **[!UICONTROL Propriétés]** : les propriétés peuvent différer entre les espaces de travail. Cette situation peut déclencher un avertissement :

    * Dans le **[!UICONTROL Compositeur d’expérience d’après les formulaires]**, des avertissements s’affichent directement dans l’interface utilisateur pour une visibilité immédiate.

      ![Avertissement relatif à l’espace de travail basé sur les formulaires](/help/main/c-activities/assets/form-based-warning.png)

    * Dans le compositeur d’expérience visuelle, des avertissements s’affichent lorsque vous cliquez sur **[!UICONTROL Configurer]** > **[!UICONTROL Propriétés]**.

      Pour résoudre ce problème, cliquez sur **[!UICONTROL Ajouter/Supprimer]** afin que seules les propriétés disponibles dans l’espace de travail de destination soient affichées pour la sélection.

  * **Audiences et offres** : lors de la copie d’une activité dans un nouvel espace de travail, toutes les [!DNL Target] audiences et offres ad hoc associées à partir de l’espace de travail d’origine sont dupliquées à l’aide du format : `<Entity Name> Copy <Date>` pour [!DNL Target] audiences et pour les offres ad hoc `<Entity Name>`.

    Détails du comportement :

    * Les audiences et offres copiées n’apparaissent pas dans les listes **[!UICONTROL Audiences]** et **[!UICONTROL Offres]** tant que l’activité n’a pas été enregistrée et rouverte.
    * Ces entités ne peuvent pas être modifiées immédiatement après la copie. Il se peut que les clients voient du contenu vide dans le VEC pour ces éléments au cours de la session de modification initiale.
    * Si nécessaire, les clients peuvent remplacer les audiences ou les offres copiées par d’autres à partir de l’espace de travail de destination.

    Ce processus garantit une duplication plus fluide des activités entre les espaces de travail tout en conservant une certaine flexibilité pour la personnalisation.

    Lors de la copie d’une activité, les audiences non ciblées et les offres qui ne sont pas enregistrées dans l’espace de travail actuel ou l’espace de travail par défaut doivent être remplacées manuellement.

    Le remplacement manuel de ces audiences et offres non cibles garantit que seules des entités accessibles valides sont utilisées dans l’activité copiée et empêche les erreurs lors de la modification ou de la diffusion.

    ![Message d&#39;avertissement](/help/main/c-activities/assets/copy.png)

>[!NOTE]
>
>Si la fonctionnalité **[!UICONTROL Autorisations des utilisateurs d’Enterprise]** n’est pas activée pour votre environnement, toutes les activités s’ouvrent en mode d’édition avant d’être copiées.

## Activités [!DNL Recommendations Classic] héritées {#classic}

La liste **[!UICONTROL Activités]** affiche les activités créées dans diverses sources, y compris [!DNL Recommendations Classic]. Les actions suivantes sont disponibles pour les activités héritées créées dans [!DNL Recommendations Classic] :

* **[!UICONTROL Activer]**
* **[!UICONTROL Désactiver]**
* **[!UICONTROL Archiver]**
* **[!UICONTROL Copier]**
* **[!UICONTROL Supprimer]**

Impossible de modifier directement une activité [!DNL Recommendations]. Pour la modifier, créez une copie de l’activité à l’aide de [!DNL Target Premium] et enregistrez la nouvelle activité, qui peut ensuite être modifiée si nécessaire.
