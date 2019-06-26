---
description: Dans une activité d’Automated Personalization, vous pouvez cibler des offres vers des audiences spécifiques.
seo-description: Dans une activité d’Automated Personalization, vous pouvez cibler des offres vers des audiences spécifiques.
seo-title: Offres Target Automated Personalization
solution: Target,Analytics
title: Offres Target Automated Personalization
title-outputclass: Premium
uuid: 4ee30e1a-bfda-4b20-9313-99e32dcf60ac
badge: Premium
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Offres de personnalisation automatisée ![PREMIUM](/help/assets/premium.png) Target{#target-automated-personalization-offers}

Dans une activité de personnalisation automatisée, vous pouvez cibler des offres sur des audiences spécifiques.

Utiliser cette fonctionnalité réduit le nombre d’offres qu’un visiteur spécifique est autorisé à voir. Prenons l&#39;exemple d&#39;une activité AP qui comporte trois offres. L&#39;offre 1 possède une règle de ciblage qui limite son exposition à l&#39;audience A. Deux visiteurs ont vu cette activité AP.

|  | Visiteur 1 | Visiteur 2 |
|--- |--- |--- |
| Qualification d’audience | Audience A | Audience B |
| Note du modèle de personnalisation de la cible de l’offre 1 | 90 | 90 |
| Note du modèle de personnalisation de la cible de l’offre 2 | 50 | 70 |
| Note du modèle de personnalisation de la cible de l’offre 3 | 80 | 60 |

Dans ce cas de figure, le visiteur 1 voit l’offre 1 (parce qu’il fait partie de l’audience A), laquelle correspond au score le plus élevé de ce visiteur. Toutefois, le visiteur 2 verrait l’offre 2 même si son score le plus élevé correspond à l’offre 1, car il ne fait pas partie de l’audience A. Cet exemple montre pourquoi les règles de ciblage doivent être utilisées avec modération pour répondre aux besoins de l’entreprise. L’ajout de ces règles peut réduire l’efficacité des modèles de personnalisation Target.

## Configuration des règles de ciblage

1. Create an [Automated Personalization activity](/help/c-activities/t-automated-personalization/create-ap-activity.md) containing the offers you want to target.
1. After setting up the offers for the activity in the Visual Experience Composer, click **[!UICONTROL Manage Content]**.

   ![Gestion du contenu](/help/c-activities/t-automated-personalization/assets/manage-content.png)

   La boîte de dialogue de gestion du contenu s’ouvre.

1. Cliquez sur l&#39;onglet Offres.

   ![Page Offres](/help/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. Sélectionnez les offres souhaitées et choisissez les audiences que vous souhaitez remplir pour afficher cette offre.

   To set up targeting for a single offer, hover over the desired offer, then click the **[!UICONTORL Targeting]** icon.

   To set up targeting for multiple offers, select the checkboxes for the desired offers, then click the **[!UICONTROL Targeting] icon that displays at the top right of the list.

1. In the [!UICONTROL Choose Audience] dialog box, select the desired audience(s) for the offer(s), then click **[!UICONTROL Done]** to return to the [!UICONTROL Manage Content] dialog box.

   >[!NOTE]
   >
   >En plus de sélectionner une audience existante, vous pouvez combiner plusieurs audiences pour créer des audiences combinées ad hoc plutôt que d’en créer une nouvelle. Pour plus d’informations, voir [Combinaison de plusieurs audiences](../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Cliquez sur **[!UICONTROL Terminé]**.

>[!NOTE]
>
>Vous pouvez configurer jusqu’à 50 emplacements et 250 offres par emplacement.
