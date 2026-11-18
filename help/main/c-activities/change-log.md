---
keywords: journal des modifications d’activité;journal des modifications
description: Accédez au journal des modifications d’une activité dans Adobe [!DNL Target] pour afficher un enregistrement des personnes qui ont modifié vos activités et du moment où les modifications se sont produites.
title: Comment puis-je voir un journal des modifications d’activités ?
feature: Activities
exl-id: 72a901c1-4fba-4044-b72b-393cab56b936
TQID: 'https://experienceleague.adobe.com/YmadzVwbj4Hy1bk3Q7a0hp9oZ7-lSgl12ImQaEsiDwU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: 8c6f23b495228ab930e6649aa2f9e6dae506cae2
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 10%
---
# Journal des modifications d’activité {#change-log}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment afficher les actions effectuées sur une activité, qui les a effectuées et quand.

>[!ENDSHADEBOX]

Le [!DNL Adobe Target] **[!UICONTROL journal des modifications]** enregistre les actions effectuées sur une activité, y compris les modifications apportées, l’auteur des modifications et le moment où elles se sont produites. Elle fournit un historique clair de l’activité et la page **[!UICONTROL Journal des modifications]** est renseignée pour obtenir des informations en temps réel.

Pour accéder à la page **[!UICONTROL Journal des modifications]** :

1. Cliquez sur **[!UICONTROL Activités]**, puis sur l’activité dans la liste.
1. Cliquez sur **[!UICONTROL Journal des modifications]** dans le rail de gauche.

   La page répertorie l’action effectuée, sa date et l’utilisateur ou l’utilisatrice qui l’a effectuée chaque fois qu’une activité est créée, mise à jour, activée ou désactivée. Les modifications apportées aux cibles et offres personnalisées utilisées dans l’activité sont également répertoriées.

   ![Menu du journal des modifications](assets/change_logs.png)

1. Pour répertorier les actions par ordre croissant ou décroissant, cliquez sur l’en-tête de colonne **[!UICONTROL Date]**.

1. Actualisez la page pour afficher les modifications d’états.

## API du journal d’audit Target

* [Révisions : obtenez le journal d’audit par le nom du dernier auteur et un horodatage modifié](https://developer.adobe.com/target/administer/admin-api/#tag/Revisions){target=_blank}
* [Liste du journal des modifications d&#39;activité](https://developer.adobe.com/target/administer/admin-api/#tag/Activities/operation/getChangelog){target=_blank}
