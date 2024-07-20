---
keywords: audience;propension;attribut de profil;comparer;comparaison;créer une audience;création d’audience
description: Découvrez comment définir une audience pour comparer deux attributs de profil.
title: Puis-je comparer deux attributs de profil à utiliser dans les audiences ?
feature: Audiences
exl-id: 033e90f1-5a05-4fce-a520-68826860a908
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 49%

---

# Création d’une audience de comparaison d’attributs de profil

Définissez une audience dans [!DNL Adobe Target] pour comparer deux attributs de profil pour votre [bibliothèque d’audiences](/help/main/c-target/c-audiences/audiences.md) ou dans une [audience d’activité unique](/help/main/c-target/creating-activity-only-audience.md). À l’aide d’opérateurs (par exemple, supérieur, inférieur ou égal à), définissez une audience pour comparer dynamiquement les valeurs de deux attributs de profil différents.

>[!NOTE]
>
>Cette fonctionnalité est disponible uniquement pour la catégorie [[!UICONTROL Visitor Profile]](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E).

## Aperçu {#section_303CBC78194D49A2A004945D425441E1}

Les audiences sont définies par des règles qui déterminent qui est inclus ou exclu d’une activité [!DNL Target]. Une définition d’audience peut inclure de multiples règles, et chaque règle peut inclure des paramètres multiples. Si l’une des règles que vous incluez utilise la catégorie [!UICONTROL Visitor Profile], vous pouvez définir une règle basée sur la valeur spécifique d’un attribut de profil du visiteur ou comparer la valeur de cet attribut à un autre attribut de profil du visiteur.

Supposons, par exemple, que vous travailliez pour une société de meubles et que vous ayez téléchargé deux scores de propension des clients dans [!DNL Target] :

* Probabilité d’acheter du mobilier de salle à manger dans les 90 prochains jours
* Probabilité d’acheter du mobilier de salon dans les 90 prochains jours

Vous pourriez créer une audience définie par le fait de présenter une propension à acheter du mobilier de salle à manger supérieure à la propension à acheter du mobilier de salon. [!DNL Target] comparerait alors dynamiquement les scores de propension de la salle à manger et du salon pour un visiteur spécifique afin de déterminer si ce visiteur est admissible pour cette audience.

Pour plus d’informations, voir [Méthodes de transfert de données dans Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=fr){target=_blank}.

## Création d’une audience de comparaison d’attributs de profil {#section_7A62FD47D5C74C3EBC3417ACDBB85013}

1. Cliquez sur **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Nommez l’audience et ajoutez une description facultative.
1. Faites glisser **[!UICONTROL Visitor Profile]** dans le volet du créateur d’audiences.
1. Dans la liste déroulante **[!UICONTROL Visitor Profile]** , choisissez un attribut :

   ![Score de propension 1](assets/propensity_score_1.png)

1. Choisissez votre évaluateur :

   ![Score de propension 2](assets/propensity_score_2.png)

1. Dans la liste déroulante **[!UICONTROL Choose Comparison Type]**, choisissez **[!UICONTROL Attribute]**.

   Le type de comparaison &quot;valeur statique&quot; permet de comparer l’attribut de profil du visiteur à des valeurs spécifiques.

   ![Score de propension 3](assets/propensity_score_3.png)

   >[!NOTE]
   >
   >Si vous utilisez l’une des catégories de profils du visiteur par défaut (par exemple, Nouveau visiteur ou Visiteur récurrent), vous ne pouvez choisir que l’option de valeur statique. Les options de comparaison dynamique ne sont pas disponibles pour les catégories par défaut. Les autres exemples où les options de comparaison dynamique ne sont pas disponibles incluent « Première page de la session », « Pas dans d’autres tests », « Pas la première page de la session » et « Affinité catégorielle ».

1. Sélectionnez l’attribut supplémentaire à comparer à votre attribut initial.

   ![propension_score_4 image](assets/propensity_score_4.png)

1. Cliquez sur **[!UICONTROL Done]**.

## Vidéo de formation ![Badge de présentation](/help/main/assets/overview.png) {#section_3BB8DBF3418F4520B3E274B6F40AF8F3}

Pour plus d’informations et obtenir un scénario dans lequel vous pourriez utiliser cette fonction, regardez la vidéo suivante :

>[!VIDEO](https://video.tv.adobe.com/v/23218/)
