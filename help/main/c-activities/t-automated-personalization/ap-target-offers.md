---
keywords: personnalisation automatisée;offres;cible;audience;règles de ciblage;ciblage
description: Découvrez comment cibler des offres individuelles vers des audiences spécifiques à l’aide d’une [!UICONTROL Automated Personalization] (AP) dans [!DNL Adobe Target].
title: Comment Cibler [!UICONTROL Automated Personalization] Offres ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
source-git-commit: eacee6f353aa685d17b781ac82d3f79574384dfe
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 29%

---

# Cible [!UICONTROL Automated Personalization] offres

Dans un [!DNL Adobe Target] [!DNL Automated Personalization] (AP), vous pouvez cibler des offres vers des audiences spécifiques.

Utiliser cette fonctionnalité réduit le nombre d’offres qu’un visiteur spécifique est autorisé à voir. Par exemple, envisagez une [!UICONTROL Automated Personalization] activité comportant trois offres. L’offre 1 comporte une règle de ciblage qui limite son exposition à l’audience A. Deux visiteurs ont vu cette activité.

| | Visiteur 1 | Visiteur 2 |
|--- |--- |--- |
| Qualification de l’audience | Audience A | Audience B |
| Note du modèle de personnalisation de la cible de l’offre 1 | 90 | 90 |
| Note du modèle de personnalisation de la cible de l’offre 2 | 50 | 70 |
| Note du modèle de personnalisation de la cible de l’offre 3 | 80 | 60 |

Dans ce scénario, le visiteur 1 voit l’offre 1 (car ce visiteur est admissible dans le cadre de l’audience A), qui est le score le plus élevé de ce visiteur. Cependant, le visiteur 2 voit l’offre 2 même si le score le plus élevé est pour l’offre 1, car le visiteur 2 ne fait pas partie de l’audience A. Cet exemple montre pourquoi les règles de ciblage doivent être utilisées avec modération pour répondre aux besoins de l’entreprise. L’ajout de ces règles peut réduire l’efficacité de la variable [!DNL Target] modèles de personnalisation.

## Paramétrage des règles de ciblage

1. Créez un [Activité Automated Personalization](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) contenant les offres à cibler.
1. Après avoir configuré les offres pour l’activité dans la variable [!UICONTROL Compositeur d’expérience visuelle], cliquez sur **[!UICONTROL Gestion du contenu]**.

   ![Gestion du contenu](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   La variable [!UICONTROL Gestion du contenu] s’affiche.

1. Cliquez sur le bouton **[!UICONTROL Offres]** .

   ![Page Offres](/help/main/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. Sélectionnez les offres souhaitées, puis les audiences que vous souhaitez qualifier pour voir cette offre.

   Pour configurer le ciblage pour une offre unique, passez la souris sur l’offre souhaitée, puis cliquez sur l’icône **[!UICONTROL Ciblage]**.

   Pour configurer le ciblage pour plusieurs offres, cochez les cases correspondant aux offres souhaitées, puis cliquez sur le bouton **[!UICONTROL Ciblage]** qui s’affiche en haut à droite de la liste.

1. Dans le [!UICONTROL Choisir le public] , sélectionnez les audiences de votre choix pour les offres, puis cliquez sur **[!UICONTROL Terminé]** pour revenir au [!UICONTROL Gestion du contenu] de la boîte de dialogue

   >[!NOTE]
   >
   >En plus de sélectionner une audience existante, vous pouvez combiner plusieurs audiences pour créer des audiences combinées ad hoc plutôt que d’en créer une nouvelle. Pour plus d’informations, voir [Combinaison de plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Cliquez sur **[!UICONTROL Terminé]**.

>[!NOTE]
>
>Vous pouvez configurer jusqu’à 50 emplacements et 250 offres par emplacement.
