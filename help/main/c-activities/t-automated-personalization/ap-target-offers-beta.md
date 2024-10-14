---
keywords: personnalisation automatisée;offres;cible;audience;règles de ciblage;ciblage
description: Découvrez comment cibler des offres individuelles sur des audiences spécifiques à l’aide d’activités [!UICONTROL Automated Personalization] (AP).
title: Comment Puis-Je Cibler Des Offres [!UICONTROL Automated Personalization] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez ce qui est inclus dans Target Premium."
feature: Automated Personalization
solution: Target,Analytics
hide: true
hidefromtoc: true
source-git-commit: 2eb99fb0c108b600d098fc14036b678c50e689b3
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 19%

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

Dans ce scénario, le visiteur 1 voit l’offre 1 (car ce visiteur est admissible dans le cadre de l’audience A), qui est le score le plus élevé de ce visiteur. Cependant, le visiteur 2 voit l’offre 2 même si le score le plus élevé est pour l’offre 1, car le visiteur 2 ne fait pas partie de l’audience A. Cet exemple montre pourquoi les règles de ciblage doivent être utilisées avec modération pour répondre aux besoins de l’entreprise. L’ajout de ces règles peut réduire l’efficacité des modèles de personnalisation [!DNL Target].

## Paramétrage des règles de ciblage

1. Créez une [activité Automated Personalization](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) contenant les offres que vous souhaitez cibler.
1. Après avoir configuré les offres pour l’activité dans [!UICONTROL Visual Experience Composer], cliquez sur l’icône **[!UICONTROL Manage Content]** ( ![Icône Gérer le contenu](/help/main/assets/icons/Experience.svg) ).

   La boîte de dialogue [!UICONTROL Manage Content] s’affiche.

1. Cliquez sur l’onglet **[!UICONTROL Offers]** .

1. Sélectionnez les offres souhaitées, puis les audiences que vous souhaitez qualifier pour voir cette offre.

   Pour configurer le ciblage d’une seule offre, cliquez sur l’icône Plus d’infos ( ![Icône Plus d’infos](/help/main/assets/icons/MoreSmallList.svg) ) en regard de l’offre souhaitée, puis cliquez sur **[!UICONTROL Target Audience]** pour afficher la boîte de dialogue [!UICONTROL Add Audiences].

   Pour configurer le ciblage pour plusieurs offres, cochez les cases correspondant aux offres souhaitées, puis cliquez sur le lien **[!UICONTROL Target Audience]** qui s’affiche au bas de la liste.

1. Dans la boîte de dialogue [!UICONTROL Add Audiences], sélectionnez les audiences de votre choix pour les offres, puis cliquez sur **[!UICONTROL Assign Audience]** pour revenir à la boîte de dialogue [!UICONTROL Manage Content].

   >[!NOTE]
   >
   >En plus de sélectionner une audience existante, vous pouvez combiner plusieurs audiences pour créer des audiences combinées à la demande plutôt que d’en créer une nouvelle. Pour plus d’informations, voir [Combinaison de plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Cliquez sur **[!UICONTROL Done]**.

>[!NOTE]
>
>Vous pouvez configurer jusqu’à 50 emplacements et 250 offres par emplacement.