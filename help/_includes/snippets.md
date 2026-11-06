---
source-git-commit: 87c0d2aa67d54dcbc2963be63d2d7ad9c02b6aa9
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 5%
---
# Extraits

## Fonctionnalités de Target Premium {#premium-note}

>[!NOTE]
>
>Cette fonctionnalité est disponible dans le cadre de la licence [Target Premium](/help/main/c-intro/intro.md#premium). Cette fonctionnalité n’est pas disponible dans [!DNL Target Standard].

## Mise à jour des autorisations Target {#permissions-update}

>[!IMPORTANT]
>
>[!DNL Target] utilisateurs disposant de droits [!UICONTROL Administrateur de produit] et [!UICONTROL Administrateur système] peuvent modifier tous les paramètres des pages [!UICONTROL Administration], quel que soit leur rôle dans [!DNL Target]. Les utilisateurs ne disposant pas de ces autorisations ont accès en lecture seule à ces paramètres.

## Interface utilisateur de Target mise à jour {#updated-ui}

>[!NOTE]
>
>Nouveau en 2025, [!DNL Target] a introduit une interface utilisateur et un [!UICONTROL compositeur d’expérience visuelle] (VEC) mis à jour. Pour en savoir plus, cliquez sur les liens suivants :
>
>* [[!DNL Target Standard/Premium] Notes de mise à jour de la version 25.2.1 (17 février 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2) : fournit un résumé des principales modifications apportées à l’interface utilisateur de [!DNL Target] pour [!UICONTROL Activités], [!UICONTROL Recommandations] et le [!UICONTROL Compositeur d’expérience visuelle] (VEC).
>
>* Notes de mise à jour de la version [[!DNL Target Standard/Premium] 25.1.1 (9 janvier 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1) : fournit un résumé des principales modifications apportées à l’interface utilisateur dans [!DNL Target] pour la bibliothèque [!UICONTROL Offres].
>
>* [Présentation de l [!DNL Target] interface utilisateur ](/help/main/c-intro/understand-the-target-ui.md) : fournit un bref aperçu pour vous familiariser avec les [!DNL Target] et fournit des liens vers des informations plus détaillées et des instructions détaillées.
>
>* [[!UICONTROL Compositeur d’expérience visuelle] modifications ](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md) : la version [!DNL Adobe Target Standard/Premium] 25.2.1 (17 février 2015) introduit une mise à jour du [!UICONTROL Compositeur d’expérience visuelle] (VEC). Cet article explique les différences entre les versions héritées et mises à jour du compositeur d’expérience visuelle.
>
>* [[!UICONTROL Compositeur d’expérience visuelle] options](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md) : cet article explique l’interface utilisateur du compositeur d’expérience visuelle mise à jour et ses options.
>
>* [[!DNL Target] FAQ sur la mise à jour de l’interface utilisateur](/help/main/c-intro/updated-ui-faq.md) : cette FAQ aborde les questions courantes sur la nouvelle interface utilisateur [!DNL Target] et le [!UICONTROL compositeur d’expérience visuelle] (VEC), notamment les modifications apportées à la navigation, l’emplacement des fonctionnalités et l’obsolescence du bouton (bascule) de version temporaire de l’interface utilisateur. Que vous soyez spécialiste du marketing, développeur ou administrateur, cette FAQ vous aide à effectuer une transition en douceur et à tirer le meilleur parti de l’interface utilisateur mise à jour.

## Règles de nom des activités {#activity-name-rules}

Le nom de l’activité ne peut pas commencer par `=`, `+`, `-` ou `@`. Le nom de l’activité ne peut pas non plus contenir les séquences de caractères suivantes : `;=`, `;+`, `;-`, `;@`, `,=`, `,+`, `,-`, `,@`, `["` ou `"]`.

## Sélectionner une audience à l’étape Ciblage {#audience-selection-steps}

1. Pour modifier l’audience, cliquez sur l’icône **[!UICONTROL Remplacer]** ( ![icône Remplacer](/help/main/assets/icons/Retweet.svg) ) dans le cadre de droite.

1. Dans la boîte de dialogue **[!UICONTROL Ajouter une audience]**, [sélectionnez l’audience souhaitée](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) puis cliquez sur **[!UICONTROL Attribuer l’audience]**.

   Pour créer une audience qui combine plusieurs audiences, cliquez sur **[!UICONTROL Combiner les audiences]**. Pour plus d’informations, voir [Combinaison de plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md).

   Pour créer une audience qui ne figure pas encore dans la [!UICONTROL Bibliothèque d’audiences], cliquez sur **[!UICONTROL Créer une audience]**. Dans le [workflow de création d’audience](/help/main/c-target/c-audiences/audiences.md), choisissez l’une des options suivantes :

   * **[!UICONTROL Bibliothèque d’audiences]** : créez une audience à la demande qui est enregistrée dans la [!UICONTROL Bibliothèque d’audiences] et peut être réutilisée dans d’autres activités.
   * **[!UICONTROL Cette activité uniquement]** : créez une [audience spécifique à une activité](/help/main/c-target/creating-activity-only-audience.md) qui n’est pas enregistrée dans la [!UICONTROL bibliothèque d’audiences] et qui ne peut être utilisée que dans l’activité en cours.

1. Cliquez sur **[!UICONTROL Pourcentage de visiteurs]** dans le cadre de droite, puis choisissez le pourcentage de visiteurs qualifiés qui doivent rejoindre l’activité.


