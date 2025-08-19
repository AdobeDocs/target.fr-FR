---
keywords: paramètres, priorité
description: Découvrez comment  [!DNL Adobe Target]  détermine différemment la ou les activités à diffuser sur une page en fonction de l’interface et de la fonction  [!DNL Target]  création d’activités que vous utilisez.
title: Comment  [!DNL Target] -t-il la priorité à différentes activités ?
feature: Activities
exl-id: c32f1699-e564-40dd-8ff1-7c75a672c6ef
source-git-commit: be6e45ff301f549eb5be24a65b05c4a9c1cd6089
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 39%

---

# Priorité

[!DNL Adobe Target] détermine la ou les activités à diffuser sur une page différemment selon l’interface [!DNL Target] et la fonction de création d’activité ([[!UICONTROL Visual Experience Composer (VEC)]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) ou [compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md)) que vous utilisez.

## [!UICONTROL Visual Experience Composer] uniquement ou [!UICONTROL Form-Based Experience Composer] à l’aide d’une requête [!DNL Target] globale uniquement {#section_4A0A317DFED345649B58B0CB5B410C8B}

Si votre société utilise exclusivement le compositeur d’expérience visuelle, le contenu de plusieurs activités peut être renvoyé pour le même appel. Les activités sont diffusées en suivant le flux décisionnel suivant :

1. L’appel au serveur [!DNL Target] vient en [!DNL Target] avec des informations sur l’URL.
1. [!DNL Target] extrait toutes les activités exécutées sur cette URL.
1. [!DNL Target] tente de faire correspondre le visiteur à des activités.

   Si le visiteur participe déjà à une activité [!UICONTROL A/B Test] ou [!UICONTROL Multivariate Test], il ou elle correspondra à cette activité jusqu’à la conversion. Si elles se trouvaient auparavant dans une activité [!UICONTROL Experience Targeting], elles doivent y correspondre à nouveau. S’il respecte les règles de l’audience, alors le visiteur est dirigé vers ces activités et dans des expériences spécifiques.

1. Le contenu de toutes les activités et expériences auxquelles le visiteur correspond est envoyé sur la page.
1. Si le contenu de chaque activité fait référence à différents [sélecteurs CSS](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337), tout le contenu est affiché.

   En cas de chevauchement ou de duplication d’un sélecteur CSS, le contenu de l’activité avec la priorité la plus élevée est affiché. Les résultats de toutes les activités qui s’exécutent sur la page sont comptabilisés et reflétés dans les rapports.

   >[!IMPORTANT]
   >
   >[!DNL Target] renvoie le contenu de toutes les activités de la page, en commençant par le contenu dont la priorité est la plus faible, qui est ensuite remplacé par chaque activité, de la plus faible à la plus élevée. En règle générale, le contenu le plus prioritaire s’affiche. Cependant, si une activité de priorité inférieure modifie la structure du DOM pour la page, il est possible que l’activité de priorité supérieure ne reconnaisse pas la structure de la page, de sorte que le contenu de priorité inférieure s’affiche. Les résultats de toutes les activités qui s’exécutent sur la page sont comptabilisés et reflétés dans les rapports.

1. Si plusieurs activités partagent le même niveau de priorité, il existe deux pare-temps :

   * Si une seule activité utilise le ciblage d’audience, alors l’activité est affichée.
   * Si le ciblage est appliqué à tous les éléments ou à aucun, l’activité qui a été approuvée en premier s’affiche.

## [!UICONTROL Form-Based Experience Composer] et [!UICONTROL Visual Experience Composer] {#section_4620253E1CE942DD830724C7822B175F}

Si votre société utilise le [!UICONTROL Form-Based Experience Composer] *et* le compositeur d’expérience visuelle, le contenu de plusieurs [!UICONTROL Form-Based Experience Composer] et activités de compositeur d’expérience visuelle peut être diffusé. Auparavant, une seule activité du workflow basé sur les formulaires pouvait être diffusée. Il n’existe plus de limite au nombre d’activités basées sur les formulaires pouvant être diffusées.

La diffusion des activités est déterminée selon le flux décisionnel suivant :

1. [!DNL Target] appel au serveur [!DNL Target] fournit des informations sur la requête [!DNL Target] et l’URL.
1. [!DNL Target] extrait toutes les activités exécutées dans cette requête de [!DNL Target].
1. [!DNL Target] tente de faire correspondre le visiteur à des activités.

   Si le visiteur participe déjà à une activité [!UICONTROL A/B Test] ou [!UICONTROL Multivariate Test], il ou elle correspondra à ce test jusqu’à sa conversion. Si elles se trouvaient auparavant dans une activité [!UICONTROL Experience Targeting], elles doivent y correspondre à nouveau. S’il respecte les règles de l’audience, alors le visiteur est dirigé vers ces activités et dans des expériences spécifiques.

1. Si une activité basée sur des formulaires est la priorité la plus élevée, ce contenu d’activité est renvoyé avec tout le contenu d’activité correspondant des activités du compositeur d’expérience visuelle.
1. Si une activité du compositeur d’expérience visuelle est la priorité la plus élevée, le contenu de toutes les activités du compositeur d’expérience visuelle correspondantes est renvoyé, mais aucun contenu d’activité basé sur des formulaires n’est renvoyé.

   Les résultats de toutes les activités qui s’exécutent sur la page sont comptabilisés et reflétés dans les rapports.

**Exemple**

Si vous disposez de deux activités, l’une ciblant le mot-clé de recherche de marque « Nike » et l’autre ciblant le mot-clé sans marque « baskets », les priorités des deux activités sont vérifiées. Si l’activité Nike a une priorité plus élevée, son contenu s’affiche. Si l’activité portant sur les chaussures de sport sans marque a la priorité la plus élevée, son contenu s’affiche.

Si les deux activités ciblées ont la même priorité, l’activité qui a été consultée le plus récemment s’affiche. Si le visiteur est nouveau sur la page, l’activité qui a été activée le plus récemment s’affiche.

## [!UICONTROL Form-Based Experience Composer] avec des requêtes [!DNL Target] non globales {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

Si votre société utilise des requêtes [!DNL Target] autres que la requête [!DNL Target] globale dans le compositeur basé sur les formulaires, le contenu d’une seule activité peut être renvoyé par appel. La diffusion des activités est déterminée selon le flux décisionnel suivant :

1. L’appel au serveur [!DNL Target] vient en [!DNL Target] avec des informations sur la requête [!DNL Target] et l’URL.
1. [!DNL Target] extrait toutes les activités exécutées dans cette requête de [!DNL Target].
1. [!DNL Target] tente de faire correspondre le visiteur à l’activité dont la priorité est la plus élevée.

   Si le visiteur participe déjà à une activité [!UICONTROL A/B Test] ou [!UICONTROL Multivariate Test], il ou elle correspondra à cette activité jusqu’à la conversion. Si elles se trouvaient auparavant dans une activité [!UICONTROL Experience Targeting], elles doivent y correspondre à nouveau. S’il respecte les règles de l’audience, alors le visiteur est dirigé vers ces activités et dans des expériences spécifiques.

1. Si plusieurs activités partagent le même niveau de priorité, il existe deux pare-temps :

   * Si une seule activité utilise le ciblage d’audience, alors l’activité est affichée.
   * Si le ciblage est appliqué à tous les éléments ou à aucun, l’activité qui a été approuvée en premier s’affiche.

## Exemples {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>Les valeurs de priorité varient en fonction de vos paramètres. Vous pouvez utiliser les paramètres hérités de [!UICONTROL Low], [!UICONTROL Medium] ou [!UICONTROL High], ou activer les priorités affinées de 0 à 999. Pour plus d’informations, voir [ Paramètres d’activité ](/help/main/c-activities/activity-settings.md#task_C6B2FF8374724933BE79A83549B9CD02).

Réponse : offer1

**Deux activités utilisent uniquement les offres créées dans le [!UICONTROL Visual Experience Composer] pour différents sélecteurs**

* Activité 1 : target-global-mbox, selector1, visualExpCompOffer1, priorité faible
* Activité 2 : target-global-mbox, selector2, visualExpCompOffer2, priorité haute

Réponse : visualExpCompOffer1, visualExpCompOffer2

**Deux activités utilisent uniquement les offres créées dans le [!UICONTROL Visual Experience Composer] pour le même sélecteur**

* Activité 1 : target-global-mbox, selector1, visualExpCompOffer1, priorité faible
* Activité 2 : target-global-mbox, selector1, visualExpCompOffer2, priorité haute

Réponse : visualExpCompOffer1, visualExpCompOffer2

## Vidéo de formation : Paramètres des activités (3:02)

Cette vidéo comporte des informations sur les paramètres d’activité.

* Spécifier un objectif pour votre activité
* Définir le niveau de priorité de vos activités
* Planifier les heures de début et de fin de l’activité
* Ajouter des audiences pour la création de rapport afin de créer des filtres de rapport
* Saisir des notes pour vos activités

>[!VIDEO](https://video.tv.adobe.com/v/17381)
