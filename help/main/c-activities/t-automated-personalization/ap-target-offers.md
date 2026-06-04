---
keywords: automated personalization;offres;cible;audience;règles de ciblage;ciblage
description: Découvrez comment cibler des offres individuelles sur des audiences spécifiques à l’aide d’activités  (AP).
title: Comment Cibler Les Offres  ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
TQID: https://experienceleague.adobe.com/AVqyD-Von-gzuVXC09N9qHY5hEe1QLQwSavCE0mp7Ok
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 409
ht-degree: 18%

---

# Cibler [!UICONTROL les offres &#x200B;]

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

1. Créez ou modifiez une activité [&#128279;](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) contenant les offres que vous souhaitez cibler.
1. Une fois les offres de l’activité configurées dans le [!UICONTROL compositeur d’expérience visuelle], cliquez sur l’icône **[!UICONTROL Gérer le contenu]** ( ![icône Gérer le contenu](/help/main/assets/icons/Experience.svg) ).

   La boîte de dialogue [!UICONTROL Gérer le contenu] s’affiche.

1. Cliquez sur l’onglet **[!UICONTROL Offres]**.

1. Sélectionnez les offres souhaitées, puis choisissez les audiences que vous souhaitez qualifier pour voir cette offre.

   Pour configurer le ciblage d’une seule offre, cliquez sur l’icône Plus d’informations ( ![icône Plus d’informations](/help/main/assets/icons/MoreSmallList.svg) ) en regard de l’offre souhaitée, puis cliquez sur **[!UICONTROL Cibler l’audience]** pour afficher la boîte de dialogue [!UICONTROL Ajouter des audiences].

   Pour configurer le ciblage de plusieurs offres, cochez les cases des offres souhaitées, puis cliquez sur le lien **[!UICONTROL Audience cible]** qui s’affiche en bas de la liste.

1. Dans la boîte de dialogue [!UICONTROL Ajouter des audiences], sélectionnez les audiences souhaitées pour les offres, puis cliquez sur **[!UICONTROL Attribuer une audience]** pour revenir à la boîte de dialogue [!UICONTROL Gérer le contenu].

   >[!NOTE]
   >
   >Outre la sélection d’une audience existante, vous pouvez combiner plusieurs audiences pour créer des audiences combinées à la demande plutôt que de créer une nouvelle audience. Pour plus d’informations, voir [Combinaison de plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Cliquez sur **[!UICONTROL Done]** (Terminé).

>[!NOTE]
>
>Vous pouvez configurer jusqu’à 50 emplacements et 250 offres par emplacement.
