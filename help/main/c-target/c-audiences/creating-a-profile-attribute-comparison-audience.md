---
keywords: audience;propension;attribut de profil;comparer;comparaison;créer une audience;création d’audience
description: Découvrez comment définir une audience pour comparer deux attributs de profil.
title: Puis-je comparer deux attributs de profil à utiliser dans les audiences ?
feature: Audiences
exl-id: 033e90f1-5a05-4fce-a520-68826860a908
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 63%

---

# Création d’une audience de comparaison d’attributs de profil

Définition d’une audience dans [!DNL Adobe Target] pour comparer deux attributs de profil pour votre [Bibliothèque d’audiences](/help/main/c-target/c-audiences/audiences.md) ou dans un [audience d’activité unique](/help/main/c-target/creating-activity-only-audience.md). À l’aide d’opérateurs (par exemple, supérieur, inférieur ou égal à), définissez une audience pour comparer dynamiquement les valeurs de deux attributs de profil différents.

>[!NOTE]
>
>Cette fonctionnalité est disponible uniquement pour la catégorie [[!UICONTROL Profil du visiteur]](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E).

## Aperçu {#section_303CBC78194D49A2A004945D425441E1}

Les audiences sont définies par des règles qui déterminent qui est inclus ou exclu d’une activité [!DNL Target]. Une définition d’audience peut inclure de multiples règles, et chaque règle peut inclure des paramètres multiples. Si l’une des règles que vous incluez utilise la variable [!UICONTROL Profil du visiteur] catégorie, vous pouvez définir une règle basée sur la valeur spécifique d’un attribut de profil du visiteur ou comparer la valeur de cet attribut à un autre attribut de profil du visiteur.

Par exemple, supposons que vous travailliez pour un fabricant de meubles et que vous avez chargé deux scores de propension de client dans [!DNL Target]:

* Probabilité d’acheter du mobilier de salle à manger dans les 90 prochains jours
* Probabilité d’acheter du mobilier de salon dans les 90 prochains jours

Vous pourriez créer une audience définie par le fait de présenter une propension à acheter du mobilier de salle à manger supérieure à la propension à acheter du mobilier de salon. [!DNL Target] comparerait alors de manière dynamique les scores de propension de la salle à manger et du salon pour un visiteur spécifique afin de déterminer si ce visiteur est admissible dans cette audience.

Pour plus d’informations, voir [Méthodes de transfert de données dans Target](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/){target=_blank}.

## Création d’une audience de comparaison d’attributs de profil {#section_7A62FD47D5C74C3EBC3417ACDBB85013}

1. Cliquez sur **[!UICONTROL Audiences]** > **[!UICONTROL Création d’une audience]**.
1. Nommez l’audience et ajoutez une description facultative.
1. Glisser-déposer **[!UICONTROL Profil du visiteur]** dans le volet audience builder.
1. Dans la liste déroulante **[!UICONTROL Profil de visiteur]**, choisissez un attribut :

   ![Score de propension 1](assets/propensity_score_1.png)

1. Choisissez votre évaluateur :

   ![Score de propension 2](assets/propensity_score_2.png)

1. Dans la liste déroulante **[!UICONTROL Choisir un type de comparaison]**, choisissez **[!UICONTROL Attribut]**.

   Le type de comparaison &quot;valeur statique&quot; permet de comparer l’attribut de profil du visiteur à des valeurs spécifiques.

   ![Score de propension 3](assets/propensity_score_3.png)

   >[!NOTE]
   >
   >Si vous utilisez l’une des catégories de profils du visiteur par défaut (par exemple, Nouveau visiteur ou Visiteur récurrent), vous ne pouvez choisir que l’option de valeur statique. Les options de comparaison dynamique ne sont pas disponibles pour les catégories par défaut. Les autres exemples où les options de comparaison dynamique ne sont pas disponibles incluent « Première page de la session », « Pas dans d’autres tests », « Pas la première page de la session » et « Affinité catégorielle ».

1. Sélectionnez l’attribut supplémentaire à comparer à votre attribut initial.

   ![image propension_score_4](assets/propensity_score_4.png)

1. Cliquez sur **[!UICONTROL Terminé]**.

## Vidéo de formation ![Badge d’aperçu](/help/main/assets/overview.png) {#section_3BB8DBF3418F4520B3E274B6F40AF8F3}

Pour plus d’informations et obtenir un scénario dans lequel vous pourriez utiliser cette fonction, regardez la vidéo suivante :

>[!VIDEO](https://video.tv.adobe.com/v/23218/)
