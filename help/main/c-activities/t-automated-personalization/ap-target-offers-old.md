---
keywords: automated personalization;offres;cible;audience;règles de ciblage;ciblage
description: Découvrez comment cibler des offres individuelles sur des audiences spécifiques à l’aide d’une activité [!UICONTROL Automated Personalization] (AP) dans  [!DNL Adobe Target].
title: Comment Cibler [!UICONTROL Automated Personalization] Offres ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 27%

---

# Offres Target [!UICONTROL Automated Personalization]

Dans une activité [!DNL Adobe Target] [!DNL Automated Personalization] (AP), vous pouvez cibler des offres vers des audiences spécifiques.

Utiliser cette fonctionnalité réduit le nombre d’offres qu’un visiteur spécifique est autorisé à voir. Prenons l’exemple d’une activité [!UICONTROL Automated Personalization] comportant trois offres. L’offre 1 comporte une règle de ciblage qui limite son exposition à l’audience A. Deux visiteurs ont vu cette activité.

| | Visiteur 1 | Visiteur 2 |
|--- |--- |--- |
| Qualification de l’audience | Audience A | Audience B |
| Note du modèle de personnalisation de la cible de l’offre 1 | 90 | 90 |
| Note du modèle de personnalisation de la cible de l’offre 2 | 50 | 70 |
| Note du modèle de personnalisation de la cible de l’offre 3 | 80 | 60 |

Dans ce scénario, le visiteur 1 voit l’offre 1 (car ce visiteur se qualifie comme faisant partie de l’audience A), qui correspond au score le plus élevé de ce visiteur. Cependant, le visiteur 2 voit l’offre 2 même si le score le plus élevé est pour l’offre 1, car le visiteur 2 ne fait pas partie de l’audience A. Cet exemple montre pourquoi les règles de ciblage doivent être utilisées avec parcimonie pour répondre aux besoins de l’entreprise. L’ajout de ces règles peut réduire l’efficacité des modèles de personnalisation [!DNL Target].

## Paramétrage des règles de ciblage

1. Créez une [activité Automated Personalization](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) contenant les offres que vous souhaitez cibler.
1. Après avoir configuré les offres de l’activité dans la [!UICONTROL Visual Experience Composer], cliquez sur **[!UICONTROL Manage Content]**.

   ![Gestion du contenu](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   La boîte de dialogue [!UICONTROL Manage Content] s’affiche.

1. Cliquez sur l’onglet **[!UICONTROL Offers]** .

   ![Page Offres](/help/main/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. Sélectionnez les offres souhaitées, puis choisissez les audiences que vous souhaitez qualifier pour voir cette offre.

   Pour configurer le ciblage d’une seule offre, placez le pointeur de la souris sur l’offre souhaitée, puis cliquez sur l’icône **[!UICONTROL Targeting]** .

   Pour configurer le ciblage de plusieurs offres, cochez les cases des offres souhaitées, puis cliquez sur l’icône **[!UICONTROL Targeting]** qui s’affiche en haut à droite de la liste.

1. Dans la boîte de dialogue [!UICONTROL Choose Audience], sélectionnez les audiences souhaitées pour les offres, puis cliquez sur **[!UICONTROL Done]** pour revenir à la boîte de dialogue [!UICONTROL Manage Content].

   >[!NOTE]
   >
   >En plus de sélectionner une audience existante, vous pouvez combiner plusieurs audiences pour créer des audiences combinées ad hoc plutôt que d’en créer une nouvelle. Pour plus d’informations, voir [Combinaison de plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Cliquez sur **[!UICONTROL Done]**.

>[!NOTE]
>
>Vous pouvez configurer jusqu’à 50 emplacements et 250 offres par emplacement.
