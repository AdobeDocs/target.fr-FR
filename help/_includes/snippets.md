---
source-git-commit: 8c6f23b495228ab930e6649aa2f9e6dae506cae2
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 6%
---
# Extraits

## Fonctionnalités de Target Premium {#premium-note}

>[!NOTE]
>
>Cette fonctionnalité est disponible dans le cadre de la licence [Target Premium](/help/main/c-intro/intro.md#premium). Cette fonctionnalité n’est pas disponible dans [!DNL Target Standard].

## Mise à jour des autorisations Target {#permissions-update}

>[!IMPORTANT]
>
>Les utilisateurs [!DNL Target] disposant des droits [!UICONTROL Administrateur de produit] et [!UICONTROL Administrateur système] peuvent modifier tous les paramètres des pages [!UICONTROL Administration], quel que soit leur rôle dans [!DNL Target]. Les utilisateurs ne disposant pas de ces autorisations ont accès en lecture seule à ces paramètres.

## Interface utilisateur de Target mise à jour {#updated-ui}

>[!NOTE]
>
>Nouveau en 2025, [!DNL Target] a introduit une interface utilisateur mise à jour et [!UICONTROL le compositeur d’expérience visuelle] (VEC). Pour en savoir plus, cliquez sur les liens suivants :
>
>* [[!DNL Target Standard/Premium] 25.2.1 (17 février 2025) notes de mise à jour](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2) : fournit un résumé des principales modifications de l’interface utilisateur dans [!DNL Target] pour [!UICONTROL les activités], [!UICONTROL les recommandations] et le [!UICONTROL compositeur d’expérience visuelle] (VEC).
>
>* [[!DNL Target Standard/Premium] 25.1.1 (9 janvier 2025) notes de mise à jour](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1) : fournit un résumé des principales modifications apportées à l’interface utilisateur dans [!DNL Target] pour la [!UICONTROL bibliothèque des offres].
>
>* [Comprendre l [!DNL Target] interface utilisateur](/help/main/c-intro/understand-the-target-ui.md) : fournit un bref aperçu pour vous familiariser avec [!DNL Target] ainsi que des liens vers des informations plus détaillées et des instructions détaillées.
>
>* [[!UICONTROL Modifications du compositeur d’expérience visuelle]](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md) : la version [!DNL Adobe Target Standard/Premium] 25.2.1 (17 février 2015) introduit un [!UICONTROL compositeur d’expérience visuelle] (VEC) mis à jour. Cet article explique les différences entre les versions héritées et mises à jour du compositeur d’expérience visuelle.
>
>* [[!UICONTROL Options du compositeur d’expérience visuelle]](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md) : cet article explique l’interface utilisateur du compositeur d’expérience visuelle mise à jour et ses options.
>
>* [[!DNL Target] FAQ sur la mise à jour de l’interface utilisateur](/help/main/c-intro/updated-ui-faq.md) : cette FAQ répond aux questions courantes sur la nouvelle interface utilisateur [!DNL Target] et le [!UICONTROL compositeur d’expérience visuelle] (VEC), y compris les modifications de navigation, l’emplacement des fonctionnalités et l’obsolescence du bouton (bascule) de la version temporaire de l’interface utilisateur. Que vous soyez spécialiste du marketing, développeur ou administrateur, cette FAQ vous aide à effectuer une transition en douceur et à tirer le meilleur parti de l’interface utilisateur mise à jour.

## Règles de nom des activités {#activity-name-rules}

Le nom de l’activité ne peut pas commencer par `=`, `+`, `-` ou `@`. Le nom de l’activité ne peut pas non plus contenir les séquences de caractères suivantes : `;=`, `;+`, `;-`, `;@`, `,=`, `,+`, `,-`, `,@`, `["` ou `"]`.

## Correspondance des visiteurs dans les activités {#visitor-matching}

Un visiteur qui est déjà dans une activité de **[!UICONTROL test A/B]** ou de **[!UICONTROL test multivarié]** correspond à cette activité jusqu’à ce qu’il soit converti. Un visiteur qui se trouvait précédemment dans une activité de **[!UICONTROL ciblage d’expérience]** doit y correspondre à nouveau. Si le visiteur répond aux règles d’audience, il appartient à ces activités et à des expériences spécifiques.
