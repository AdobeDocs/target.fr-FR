---
keywords: automated personalization;offers
description: Dans une activité d’Automated Personalization, vous pouvez cibler des offres vers des audiences spécifiques.
title: Offres Target Automated Personalization
feature: ap
solution: Target,Analytics
translation-type: tm+mt
source-git-commit: a4b510308394110bb267665ca39d54e2ea781f3d
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 100%

---


# Offres de personnalisation automatisée ![PREMIUM](/help/assets/premium.png) Target{#target-automated-personalization-offers}

Dans une activité d’Automated Personalization (AP), vous pouvez cibler des offres vers des audiences spécifiques.

Utiliser cette fonctionnalité réduit le nombre d’offres qu’un visiteur spécifique est autorisé à voir. Prenons par exemple une activité AP comportant trois offres. L’offre 1 présente une règle de ciblage qui limite son exposition à l’audience A uniquement. Deux visiteurs ont vu cette activité.

|  | Visiteur 1 | Visiteur 2 |
|--- |--- |--- |
| Qualification d’audience | Audience A | Audience B |
| Note du modèle de personnalisation de la cible de l’offre 1 | 90 | 90 |
| Note du modèle de personnalisation de la cible de l’offre 2 | 50 | 70 |
| Note du modèle de personnalisation de la cible de l’offre 3 | 80 | 60 |

Dans ce cas de figure, le visiteur 1 voit l’offre 1 (parce qu’il fait partie de l’audience A), laquelle correspond au score le plus élevé de ce visiteur. Toutefois, le visiteur 2 verrait l’offre 2 même si son score le plus élevé correspond à l’offre 1, car il ne fait pas partie de l’audience A. Cet exemple montre pourquoi les règles de ciblage doivent être utilisées avec modération pour répondre aux besoins de l’entreprise. L’ajout de ces règles peut réduire l’efficacité des modèles de personnalisation Target.

## Paramétrage des règles de ciblage

1. Créez une [activité d’Automated Personalization](/help/c-activities/t-automated-personalization/create-ap-activity.md) contenant les offres que vous souhaitez cibler.
1. Une fois que vous avez configuré les offres pour l’activité dans le compositeur d’expérience visuelle, cliquez sur **[!UICONTROL Gérer le contenu]**.

   ![Gestion du contenu](/help/c-activities/t-automated-personalization/assets/manage-content.png)

   La boîte de dialogue de gestion du contenu s’ouvre.

1. Cliquez sur l’onglet Offres.

   ![Page Offres](/help/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. Sélectionnez les offres souhaitées et choisissez les audiences que vous souhaitez remplir pour afficher cette offre.

   Pour configurer le ciblage pour une offre unique, passez la souris sur l’offre souhaitée, puis cliquez sur l’icône **[!UICONTROL Ciblage]**.

   Pour configurer le ciblage pour plusieurs offres, cochez les cases correspondant aux offres souhaitées, puis cliquez sur l’icône **[!UICONTROL Ciblage] qui s’affiche en haut à droite de la liste.

1. Dans la boîte de dialogue [!UICONTROL Choisir l’audience], sélectionnez les audiences de votre choix pour les offres, puis cliquez sur **[!UICONTROL Terminé]** pour revenir à la boîte de dialogue [!UICONTROL Gestion du contenu].

   >[!NOTE]
   >
   >En plus de sélectionner une audience existante, vous pouvez combiner plusieurs audiences pour créer des audiences combinées ad hoc plutôt que d’en créer une nouvelle. Pour plus d’informations, voir [Combinaison de plusieurs audiences](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Cliquez sur **[!UICONTROL Terminé]**.

>[!NOTE]
>
>Vous pouvez configurer jusqu’à 50 emplacements et 250 offres par emplacement.
