---
keywords: automated personalization;offres;cible;audience;règles de ciblage;ciblage
description: Découvrez comment cibler des offres individuelles vers des audiences spécifiques à l’aide d’[!UICONTROL Automated Personalization] (AP).
title: Comment Cibler Les Offres [!UICONTROL Automated Personalization] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
TQID: 'https://experienceleague.adobe.com/AVqyD-Von-gzuVXC09N9qHY5hEe1QLQwSavCE0mp7Ok'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 8%
---
# [!UICONTROL Offres Automated Personalization] Target {#target-ap-offers}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment cibler des offres individuelles vers des audiences spécifiques dans une activité **[!UICONTROL Automated Personalization]**.

>[!ENDSHADEBOX]

Dans une activité [!DNL Adobe Target] **[!UICONTROL Automated Personalization]** (AP), les règles de ciblage permettent de limiter une offre à des audiences spécifiques, de sorte que seuls les visiteurs appartenant à ces audiences puissent la voir. Utilisez les règles de ciblage avec parcimonie, et uniquement lorsqu’un besoin professionnel en a besoin, car elles réduisent le nombre d’offres qu’un visiteur peut voir et peuvent réduire l’efficacité des modèles de personnalisation [!DNL Target].

Prenons l’exemple d’une activité AP qui comporte trois offres. L’offre 1 comporte une règle de ciblage qui limite son exposition à l’audience A. Deux visiteurs voient cette activité.

| | Visiteur 1 | Visiteur 2 |
|--- |--- |--- |
| Qualification d’audience | Audience A | Audience B |
| Score du modèle de personnalisation de l’offre 1 [!DNL Target] | 90 | 90 |
| Score du modèle de personnalisation de l’offre 2 [!DNL Target] | 50 | 70 |
| Score du modèle de personnalisation de l’offre 3 [!DNL Target] | 80 | 60 |

Le visiteur 1 est qualifié comme faisant partie de l’audience A. Par conséquent, ce visiteur voit l’offre 1, qui a le score le plus élevé. Le visiteur 2 ne fait pas partie de l’audience A. Par conséquent, ce visiteur voit l’offre 2, même si le score le plus élevé est pour l’offre 1.

## Paramétrage des règles de ciblage {#set-up-targeting-rules}

<a id="task_F207ED7A41B84FD39BB6FCBFABF4B23E"></a>

Les règles de ciblage d’audience contrôlent quelles personnes peuvent voir chaque offre, ce qui vous permet de répondre à un besoin commercial spécifique, tel que la réservation d’une offre pour un segment client. Chaque règle réduit les choix du modèle de personnalisation. Par conséquent, appliquez les règles uniquement aux offres qui les nécessitent.

1. Créez ou modifiez une [activité Automated Personalization](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity) contenant les offres que vous souhaitez cibler.

   Vous pouvez configurer jusqu’à 50 emplacements et 250 offres par emplacement.

1. Après avoir configuré les offres pour l’activité dans le **[!UICONTROL compositeur d’expérience visuelle]**, cliquez sur l’icône **[!UICONTROL Gérer le contenu]** ( ![Icône Gérer le contenu](/help/main/assets/icons/Experience.svg) ). La boîte de dialogue **[!UICONTROL Gérer le contenu]** s&#39;affiche.

   ![Icône Gérer le contenu](../assets/ap-offers-1.png)

1. Cliquez sur l’onglet **[!UICONTROL Offres]**.

1. Choisissez les offres à cibler, puis choisissez les audiences qui remplissent les critères pour les voir.

   * Pour configurer le ciblage d’une seule offre, cliquez sur l’icône Plus d’informations ( ![icône Plus d’informations](/help/main/assets/icons/MoreSmallList.svg) ) en regard de l’offre, puis cliquez sur **[!UICONTROL Cibler l’audience]** pour afficher la boîte de dialogue **[!UICONTROL Ajouter des audiences]**.
   * Pour configurer le ciblage de plusieurs offres, cochez les cases correspondantes, puis cliquez sur le lien **[!UICONTROL Audience cible]** qui s&#39;affiche au bas de la liste.

   ![Icône Gérer le contenu](../assets/ap-offers-2.png)

1. Dans la boîte de dialogue **[!UICONTROL Ajouter des audiences]**, sélectionnez les audiences des offres, puis cliquez sur **[!UICONTROL Attribuer une audience]** pour revenir à la boîte de dialogue **[!UICONTROL Gérer le contenu]**.

   >[!NOTE]
   >
   >Au lieu de créer une nouvelle audience, vous pouvez combiner plusieurs audiences avec des audiences existantes pour créer des audiences combinées à la demande. Pour plus d’informations, voir [Combinaison de plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Cliquez sur **[!UICONTROL Done]** (Terminé).

Les règles de ciblage s’appliquent désormais aux offres sélectionnées, de sorte que seuls les visiteurs appartenant aux audiences affectées peuvent les voir.
