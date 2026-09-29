---
keywords: automated personalization;offres;cible;audience;règles de ciblage;ciblage
description: Découvrez comment cibler des offres individuelles vers des audiences spécifiques à l’aide d’une activité [!UICONTROL ] (AP) dans [!DNL Adobe Target].
title: Comment Cibler Les Offres [!UICONTROL ] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 26%
---
# Cibler [!UICONTROL les offres ]

Dans une activité [!DNL Adobe Target] [!DNL Automated Personalization] (AP), vous pouvez cibler des offres vers des audiences spécifiques.

Utiliser cette fonctionnalité réduit le nombre d’offres qu’un visiteur spécifique est autorisé à voir. Prenons l’exemple d’une activité  qui comporte trois offres. L’offre 1 comporte une règle de ciblage qui limite son exposition à l’audience A. Deux visiteurs ont vu cette activité.

| | Visiteur 1 | Visiteur 2 |
|--- |--- |--- |
| Qualification d’audience | Audience A | Audience B |
| Note du modèle de personnalisation de la cible de l’offre 1 | 90 | 90 |
| Note du modèle de personnalisation de la cible de l’offre 2 | 50 | 70 |
| Note du modèle de personnalisation de la cible de l’offre 3 | 80 | 60 |

Dans ce scénario, le visiteur 1 voit l’offre 1 (car ce visiteur se qualifie comme faisant partie de l’audience A), qui correspond au score le plus élevé de ce visiteur. Cependant, le visiteur 2 voit l’offre 2 même si le score le plus élevé est pour l’offre 1, car le visiteur 2 ne fait pas partie de l’audience A. Cet exemple montre pourquoi les règles de ciblage doivent être utilisées avec parcimonie pour répondre aux besoins de l’entreprise. L’ajout de ces règles peut réduire l’efficacité des modèles de personnalisation [!DNL Target].

## Paramétrage des règles de ciblage

1. Créez une [activité ](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) contenant les offres que vous souhaitez cibler.
1. Une fois les offres de l’activité configurées dans le [!UICONTROL Compositeur d’expérience visuelle], cliquez sur **[!UICONTROL Gérer le contenu]**.

   ![Gestion du contenu](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   La boîte de dialogue [!UICONTROL Gérer le contenu] s’affiche.

1. Cliquez sur l’onglet **[!UICONTROL Offres]**.

   ![Page Offres](/help/main/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. Sélectionnez les offres souhaitées, puis choisissez les audiences que vous souhaitez qualifier pour voir cette offre.

   Pour configurer le ciblage d’une seule offre, survolez-la avec la souris, puis cliquez sur l’icône **[!UICONTROL Ciblage]**.

   Pour configurer le ciblage de plusieurs offres, cochez les cases des offres souhaitées, puis cliquez sur l’icône **[!UICONTROL Ciblage]** qui s’affiche en haut à droite de la liste.

1. Dans la boîte de dialogue [!UICONTROL Choisir l’audience], sélectionnez les audiences souhaitées pour les offres, puis cliquez sur **[!UICONTROL Terminé]** pour revenir à la boîte de dialogue [!UICONTROL Gérer le contenu].

   >[!NOTE]
   >
   >En plus de sélectionner une audience existante, vous pouvez combiner plusieurs audiences pour créer des audiences combinées ad hoc plutôt que d’en créer une nouvelle. Pour plus d’informations, voir [Combinaison de plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Cliquez sur **[!UICONTROL Done]** (Terminé).

>[!NOTE]
>
>Vous pouvez configurer jusqu’à 50 emplacements et 250 offres par emplacement.
