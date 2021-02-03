---
keywords: audience;propension;attribut de profil;comparer;comparaison;créer une audience;création d’audience
description: Définition d’une audience afin de comparer deux attributs de profil pour votre bibliothèque d’audiences Target ou dans une audience d’activité unique. À l’aide d’opérateurs (par exemple, supérieur, inférieur ou égal à), définissez une audience pour comparer dynamiquement les valeurs de deux attributs de profil différents.
title: Création d’une audience de comparaison d’attributs de profil
feature: Audiences
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 99%

---


# Création d’une audience de comparaison d’attributs de profil{#create-a-profile-attribute-comparison-audience}

Définition d’une audience afin de comparer deux attributs de profil pour votre [bibliothèque d’audiences](/help/c-target/c-audiences/audiences.md) ou dans une [audience d’activité unique](/help/c-target/creating-activity-only-audience.md). À l’aide d’opérateurs (par exemple, supérieur, inférieur ou égal à), définissez une audience pour comparer dynamiquement les valeurs de deux attributs de profil différents.

>[!NOTE]
>
>Cette fonctionnalité est disponible uniquement pour la catégorie [Profil du visiteur](/help/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E).

## Aperçu {#section_303CBC78194D49A2A004945D425441E1}

Les audiences sont définies par des règles qui déterminent qui est inclus ou exclu d’une activité Target. Une définition d’audience peut inclure de multiples règles, et chaque règle peut inclure des paramètres multiples. Si l’une des règles que vous incluez utilise la catégorie Profil du visiteur, vous pouvez définir une règle en fonction de la valeur spécifique d’un attribut de profil visiteur ou comparer la valeur de cet attribut à un autre attribut de profil de visiteur.

Par exemple, supposons que vous travailliez pour un fabricant de meubles et que vous avez chargé deux scores de propension de client dans Target :

* Probabilité d’acheter du mobilier de salle à manger dans les 90 prochains jours
* Probabilité d’acheter du mobilier de salon dans les 90 prochains jours

Vous pourriez créer une audience définie par le fait de présenter une propension à acheter du mobilier de salle à manger supérieure à la propension à acheter du mobilier de salon. Target comparerait alors de manière dynamique les scores de propension de la salle à manger et du salon pour un visiteur spécifique afin de déterminer si ce visiteur est admissible dans cette audience.

Pour plus d’informations, voir [Méthodes pour obtenir des données dans Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17).

## Création d’une audience de comparaison d’attributs de profil {#section_7A62FD47D5C74C3EBC3417ACDBB85013}

1. Cliquez sur **[!UICONTROL Audiences]** > **[!UICONTROL Créer une audience]** > **[!UICONTROL Ajouter une règle]** > **[!UICONTROL Profil de visiteur]**.
1. Dans la liste déroulante **[!UICONTROL Profil de visiteur]**, choisissez un attribut :

   ![Score de propension 1](assets/propensity_score_1.png)

1. Choisissez votre évaluateur :

   ![Score de propension 2](assets/propensity_score_2.png)

1. Dans la liste déroulante **[!UICONTROL Choisir un type de comparaison]**, choisissez **[!UICONTROL Attribut]**.

   Le type de comparaison « valeur statique » vous permet de comparer l’attribut de profil de votre visiteur à une ou plusieurs valeurs spécifiques.

   ![Score de propension 3](assets/propensity_score_3.png)

   >[!NOTE]
   >
   >Si vous utilisez l’une des catégories de profil de visiteur par défaut dans l’étape 1 (par exemple, Nouveau visiteur ou Visiteur récurrent), vous ne pouvez sélectionner que l’option de valeur statique. Les options de comparaison dynamique ne sont pas disponibles pour les catégories par défaut. Les autres exemples où les options de comparaison dynamique ne sont pas disponibles incluent « Première page de la session », « Pas dans d’autres tests », « Pas la première page de la session » et « Affinité catégorielle ».

1. Sélectionnez l’attribut supplémentaire à comparer à votre attribut initial.

   ![](assets/propensity_score_4.png)

## Vidéo de formation ![badge Aperçu](/help/assets/overview.png) {#section_3BB8DBF3418F4520B3E274B6F40AF8F3}

Pour plus d’informations et obtenir un scénario dans lequel vous pourriez utiliser cette fonction, regardez la vidéo suivante :

>[!VIDEO](https://video.tv.adobe.com/v/23218/)