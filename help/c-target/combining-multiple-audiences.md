---
description: Combinaison de plusieurs audiences (y compris des audiences Adobe Experience Cloud et Target) à la volée pour créer des audiences ad hoc. Vous pouvez également créer des règles d’exclusion et exclure des audiences d’une règle.
keywords: audience;règles d’audience;combiner des audiences;exclusion;ajouter une exclusion;exclure;combinaison d’audiences;audience adhoc;audience ad hoc
seo-description: Combinaison de plusieurs audiences (y compris des audiences Adobe Experience Cloud et Target) à la volée pour créer des audiences ad hoc. Vous pouvez également créer des règles d’exclusion et exclure des audiences d’une règle.
seo-title: Combinaison de plusieurs audiences dans Adobe Target
solution: Target
title: Combinaison de plusieurs audiences
topic: Advanced,Standard,Classic
uuid: aec09341-9b54-400c-a438-60058c52ac2a
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Combinaison de plusieurs audiences{#combine-multiple-audiences}

Combinaison de plusieurs audiences (y compris des audiences Adobe Experience Cloud et Target) à la volée pour créer des audiences ad hoc. Vous pouvez également créer des règles d’exclusion et exclure des audiences d’une règle.

Supposons que vous ayez une audience « Nouveaux visiteurs » et une audience « Utilisateurs Chrome ». Pour une activité spécifique, vous pouvez combiner ces audiences existantes aux nouveaux visiteurs Target utilisant un navigateur Chrome. Au lieu de créer une troisième audience et de la stocker dans la bibliothèque [!UICONTROL Audiences], vous pouvez combiner ces deux audiences lors de la création d’une nouvelle activité ou de la modification d’une activité existante.

Prenons un autre exemple. Vous pouvez cibler tous les clients fidèles en incluant un segment [!DNL Audience Manager] spécifique pour le statut de fidélité et le combiner à un segment [!DNL Target] constitué des personnes qui ont signé votre programme de fidélité pour la session en cours, au lieu de créer une troisième audience permanente.

Vous pouvez combiner jusqu’à dix audiences en utilisant les opérateurs ET et OU.

Vous pouvez créer et utiliser des audiences combinées à différents endroits dans l’interface utilisateur [!DNL Target]. 

## Create a combined audience while creating an activity {#section_2F1CE9434CC04174B4BA2BFC89B85D77}

Vous pouvez créer une audience combinée ad hoc sur la page [!UICONTROL Target] de l’activité au cours du processus assisté en trois étapes.

1. While creating an [activity](../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), on the **[!UICONTROL Target]** page, click the three vertical ellipses, then click **[!UICONTROL Replace Audience]**.

   ![Résultat d’étape](assets/edit_audience.png)

1. Dans la page [!UICONTROL Choisir le public], activez les cases à cocher des audiences que vous souhaitez utiliser comme blocs élémentaires pour votre audience combinée.

   ![Résultat d’étape](assets/combine_multiple_audiences1.png)

1. Cliquez sur **[!UICONTROL Combiner plusieurs audiences]** dans le coin supérieur droit.

   ![Résultat d’étape](assets/combine_multiple_audiences2.png)

1. (Facultatif) Modifiez la nouvelle audience combinée à votre gré.

   Dans la boîte de dialogue [!UICONTROL Modifier l’audience], vous pouvez faire glisser-déplacer des blocs de création d’audience supplémentaires depuis le côté gauche vers la nouvelle audience combinée, et ajouter des règles d’exclusion ou exclure des audiences.

   1. Vous pouvez utiliser la fonction glisser-déplacer pour ajouter des audiences dans une section existante comme bloc élémentaire de niveau 2. Pour ajouter un bloc élémentaire de niveau 1, activez la case à cocher en regard de l’audience souhaitée, puis cliquez sur **[!UICONTROL Ajouter aux règles]**.

      Supposons, par exemple, que dans l&#39;exemple précédent, vous souhaitiez inclure les utilisateurs Safari dans l&#39;audience combinée. Recherchez l&#39;audience « Navigateur Safari » et faites-la glisser dans la zone « Navigateur Firefox » sur le côté droit, comme dans l&#39;exemple suivant :

      ![](assets/combine_multiple_audiences3.png)

      Notez que l’opérateur entre les deux audiences de type navigateur est « ET ». Sélectionnez la liste déroulante ET et remplacez-la par « OR » pour créer une audience combinée pour les nouveaux visiteurs utilisant Firefox ou Safari. Veillez à ne pas créer de règles qui excluent tous les membres potentiels de l’audience. Par exemple, il n&#39;est pas possible d&#39;accéder simultanément à une page à l&#39;aide de Firefox et Safari.

      >[!NOTE]
      >
      >L’opérateur (ET ou OU) doit rester identique lorsque vous combinez des audiences. Vous ne pouvez pas mélanger les opérateurs.

   1. Pour ajouter une exclusion à une règle, cliquez sur **[!UICONTROL Exclusion]** &gt; **[!UICONTROL Ajouter une exclusion]**.

      ![](assets/combine_multiple_audiences3a.png)

      Faites glisser-déplacez une audience dans la zone :

      ![](assets/combine_multiple_audiences3b.png)

      Par exemple, pour exclure les visiteurs Etats-Unis des nouveaux visiteurs, vous pouvez faire glisser le marché : Public Etats-Unis dans la zone, comme illustré ci-dessous :

      ![](assets/combine_multiple_audiences3b2.png)

      Cette audience combinée comprend tous les nouveaux visiteurs sur votre site (à l’exclusion de ceux de San Francisco) utilisant Safari ou Firefox.

   1. Pour exclure une audience d’une règle, cliquez sur **[!UICONTROL Exclusion]** &gt; **[!UICONTROL Exclure cette audience]**.

      Vous pouvez par exemple créer une audience combinée qui comprend tous les nouveaux visiteurs sur votre site, à l’exclusion de ceux qui utilisent Firefox. Il est plus facile et plus rapide d’exclure les visiteurs utilisant Firefox que de créer une audience combinée qui inclut explicitement plusieurs navigateurs (Safari, Chrome et Internet Explorer), mais pas Firefox.

1. Saisissez un nom explicite pour l’audience combinée, puis cliquez sur **[!UICONTROL Enregistrer]**.

## Create a combined audience for use in metric targeting {#section_A42E795AFCBD4575809C5942039910F0}

Vous pouvez créer une audience combinée ad hoc dans la page [!UICONTROL Objectifs et paramètres] de l’activité à utiliser dans le ciblage des mesures. Par exemple pour créer un ciblage basé sur la conversion avec une audience combinée :

1. Lorsque vous modifiez ou créez une [activité](../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), dans la page **[!UICONTROL Objectifs et paramètres]**, sélectionnez **[!UICONTROL Conversion]** pour la mesure de succès, puis **[!UICONTROL Visionner une Mbox]** en tant qu’action.
1. Sélectionnez la mbox souhaitée dans le champ **[!UICONTROL Rechercher une mbox].**

   ![](assets/combine_multiple_audiences4.png)

1. Cliquez sur l’engrenage, puis sur **[!UICONTROL Ajouter le ciblage d’audience]**.
1. Cliquez sur le lien **[!UICONTROL Ajouter la condition de ciblage/audience]** pour afficher la boîte de dialogue [!UICONTROL Choisir l’audience].

   ![](assets/combine_multiple_audiences5.png)

1. Passez à l’[étape 2](../c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77) de la section Créer une audience combinée lors de la création d’une activité afin de créer l’audience combinée.

## Créer une audience combinée à utiliser dans les rapports {#section_4682D342EFBB43C38E54B99B3A1E14CD}

Vous pouvez créer une audience combinée ad hoc dans la page [!UICONTROL Objectifs et paramètres] de l’activité à utiliser dans les rapports.

1. Lors de la modification ou de la création d’une [activité](../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), dans la page **[!UICONTROL Objectifs et paramètres]**, cliquez sur l’icône **[!UICONTROL Ajouter une audience]** sous [!UICONTROL Audiences pour les rapports] pour afficher la page [!UICONTROL Choisir le public].

   ![](assets/combine_multiple_audiences6.png)

1. Passez à l’[étape 2](../c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77) de la section Créer une audience combinée lors de la création d’une activité afin de créer l’audience combinée.

## Create a combined audience while editing an activity {#section_364A12CE96E04B61B7C18113AA586C2C}

Vous pouvez créer une audience combinée ad hoc lors de la modification d’une activité existante.

1. Dans la page [!UICONTROL Activités], passez la souris sur l’activité souhaitée, puis cliquez sur l’icône **[!UICONTROL Modifier.]**

   OU

   Cliquez sur l’activité souhaitée pour l’ouvrir, puis cliquez sur **[!UICONTROL Modifier l’activité]**.

1. Click the **[!UICONTROL Configure]** &gt; **[!UICONTROL Audiences]** &gt; **[!UICONTROL Multiple Audiences]**.

   ![Configurer &gt; Audiences &gt; Audiences multiples](/help/c-target/assets/combine_multiple_audiences7.png)

1. Cliquez sur l’icône d’options supplémentaires (trois points alignés verticalement) en regard de l’audience actuelle de l’activité, puis cliquez sur **[!UICONTROL Changer d’audience]**.

   ![Changer l’audience](/help/c-target/assets/combine_multiple_audiences8.png)

1. Passez à l’[étape 2](../c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77) de la section Créer une audience combinée lors de la création d’une activité afin de créer l’audience combinée.