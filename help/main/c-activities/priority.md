---
keywords: paramètres, priorité
description: Découvrez comment  [!DNL Adobe Target] détermine différemment l’activité (ou les activités) à diffuser sur une page en fonction de l’interface  [!DNL Target] et de la fonction de création d’activité que vous utilisez.
title: Comment  [!DNL Target] Attribue-t-il la priorité à différentes activités ?
feature: Activities
exl-id: c32f1699-e564-40dd-8ff1-7c75a672c6ef
source-git-commit: be6e45ff301f549eb5be24a65b05c4a9c1cd6089
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 39%

---

# Priorité

[!DNL Adobe Target] détermine différemment l’activité (ou les activités) à diffuser sur une page en fonction de l’interface [!DNL Target] et de la fonction de création d’activité ([[!UICONTROL Visual Experience Composer (VEC)]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) ou [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md)) que vous utilisez.

## [!UICONTROL Visual Experience Composer] uniquement ou [!UICONTROL Form-Based Experience Composer] utilisant une requête [!DNL Target] globale uniquement {#section_4A0A317DFED345649B58B0CB5B410C8B}

Si votre entreprise utilise le compositeur d’expérience visuelle exclusivement, le contenu de plusieurs activités peut être renvoyé pour le même appel. Les activités sont diffusées en suivant le flux décisionnel suivant :

1. L’appel au serveur [!DNL Target] renvoie à [!DNL Target] avec des informations sur l’URL.
1. [!DNL Target] récupère chaque activité s’exécutant sur cette URL.
1. [!DNL Target] tente de faire correspondre le visiteur à des activités.

   Si le visiteur se trouve déjà dans une activité [!UICONTROL A/B Test] ou [!UICONTROL Multivariate Test], il fait correspondre cette activité jusqu’à ce qu’il effectue une conversion. S’ils se trouvaient auparavant dans une activité [!UICONTROL Experience Targeting], ils doivent y faire à nouveau correspondre. S’il respecte les règles de l’audience, alors le visiteur est dirigé vers ces activités et dans des expériences spécifiques.

1. Le contenu de toutes les activités et expériences auxquelles le visiteur correspond est envoyé sur la page.
1. Si le contenu de chaque activité fait référence à différents [sélecteurs CSS](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337), tout le contenu s’affiche.

   En cas de chevauchement ou de duplication d’un sélecteur CSS, le contenu de l’activité avec la priorité la plus élevée est affiché. Les résultats de toutes les activités qui s’exécutent sur la page sont comptabilisés et reflétés dans les rapports.

   >[!IMPORTANT]
   >
   >[!DNL Target] renvoie le contenu de toutes les activités de la page, en commençant par le contenu de priorité la plus faible, qui est ensuite remplacé par chaque activité, de la priorité la plus faible à la plus élevée. En règle générale, le contenu ayant la priorité la plus élevée s’affiche. Cependant, si une activité de priorité inférieure modifie la structure du DOM pour la page, il est possible que l’activité de priorité supérieure ne reconnaisse pas la structure de la page. Le contenu de priorité inférieure s’affiche donc. Les résultats de toutes les activités qui s’exécutent sur la page sont comptabilisés et reflétés dans les rapports.

1. Si plusieurs activités partagent un niveau de priorité, il existe deux brise-glace :

   * Si une seule activité utilise le ciblage d’audience, alors l’activité est affichée.
   * Si tout ou aucun ciblage est effectué, l’activité qui a été approuvée en premier s’affiche.

## [!UICONTROL Form-Based Experience Composer] et [!UICONTROL Visual Experience Composer] {#section_4620253E1CE942DD830724C7822B175F}

Si votre entreprise utilise le VEC [!UICONTROL Form-Based Experience Composer] *et*, le contenu de plusieurs activités [!UICONTROL Form-Based Experience Composer] et du VEC peut être diffusé. Auparavant, une seule activité du workflow basé sur les formulaires pouvait être diffusée. Il n’existe plus de limite au nombre d’activités basées sur les formulaires pouvant être diffusées.

La diffusion des activités est déterminée selon le flux décisionnel suivant :

1. [!DNL Target] l’appel au serveur renvoie à [!DNL Target] avec des informations sur la requête [!DNL Target] et l’URL.
1. [!DNL Target] extrait chaque activité s’exécutant dans cette requête [!DNL Target].
1. [!DNL Target] tente de faire correspondre le visiteur à des activités.

   Si le visiteur se trouve déjà dans une activité [!UICONTROL A/B Test] ou [!UICONTROL Multivariate Test], il effectue une correspondance dans ce test jusqu’à sa conversion. S’ils se trouvaient auparavant dans une activité [!UICONTROL Experience Targeting], ils doivent y faire à nouveau correspondre. S’il respecte les règles de l’audience, alors le visiteur est dirigé vers ces activités et dans des expériences spécifiques.

1. Si une activité basée sur des formulaires est la priorité la plus élevée, le contenu de cette activité est renvoyé avec tout le contenu de l’activité correspondant provenant des activités du compositeur d’expérience visuelle.
1. Si une activité du compositeur d’expérience visuelle est la priorité la plus élevée, le contenu de toutes les activités du compositeur d’expérience visuelle correspondantes est renvoyé, mais aucun contenu d’activité d’après les formulaires n’est renvoyé.

   Les résultats de toutes les activités qui s’exécutent sur la page sont comptabilisés et reflétés dans les rapports.

**Exemple**

Si vous avez deux activités, l’une ciblant le mot-clé de recherche de marque &quot;Nike&quot; et l’autre ciblant le mot-clé sans marque &quot;baskets&quot;, les priorités des deux activités sont vérifiées. Si l’activité Nike a une priorité plus élevée, son contenu s’affiche. Si l’activité portant sur les chaussures de sport sans marque a la priorité la plus élevée, son contenu s’affiche.

Si les deux activités ciblées ont la même priorité, l’activité qui a été consultée le plus récemment s’affiche. Si le visiteur est nouveau sur la page, l’activité qui a été activée le plus récemment s’affiche.

## [!UICONTROL Form-Based Experience Composer] avec des requêtes [!DNL Target] non globales {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

Si votre entreprise utilise des requêtes [!DNL Target] autres que la requête [!DNL Target] globale dans le compositeur d’après les formulaires, le contenu d’une seule activité peut être renvoyé par appel. La diffusion des activités est déterminée selon le flux décisionnel suivant :

1. L’appel au serveur [!DNL Target] renvoie à [!DNL Target] avec des informations sur la requête [!DNL Target] et l’URL.
1. [!DNL Target] extrait chaque activité s’exécutant dans cette requête [!DNL Target].
1. [!DNL Target] tente de faire correspondre le visiteur à l’activité de priorité la plus élevée.

   Si le visiteur se trouve déjà dans une activité [!UICONTROL A/B Test] ou [!UICONTROL Multivariate Test], il fait correspondre cette activité jusqu’à ce qu’il effectue une conversion. S’ils se trouvaient auparavant dans une activité [!UICONTROL Experience Targeting], ils doivent y faire à nouveau correspondre. S’il respecte les règles de l’audience, alors le visiteur est dirigé vers ces activités et dans des expériences spécifiques.

1. Si plusieurs activités partagent un niveau de priorité, il existe deux brise-glace :

   * Si une seule activité utilise le ciblage d’audience, alors l’activité est affichée.
   * Si tout ou aucun ciblage est effectué, l’activité qui a été approuvée en premier s’affiche.

## Exemples {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>Les valeurs de priorité varient en fonction de vos paramètres. Vous pouvez utiliser les paramètres hérités de [!UICONTROL Low], [!UICONTROL Medium] ou [!UICONTROL High], ou vous pouvez activer les priorités affinées de 0 à 999. Pour plus d’informations, voir [Paramètres d’activité](/help/main/c-activities/activity-settings.md#task_C6B2FF8374724933BE79A83549B9CD02).

Réponse : offer1

**Deux activités utilisent uniquement les offres créées dans [!UICONTROL Visual Experience Composer] pour différents sélecteurs**

* Activité 1 : target-global-mbox, selector1, visualExpCompOffer1, priorité faible
* Activité 2 : target-global-mbox, selector2, visualExpCompOffer2, priorité haute

Réponse : visualExpCompOffer1, visualExpCompOffer2

**Deux activités utilisent uniquement les offres créées dans [!UICONTROL Visual Experience Composer] pour le même sélecteur**

* Activité 1 : target-global-mbox, selector1, visualExpCompOffer1, priorité faible
* Activité 2 : target-global-mbox, selector1, visualExpCompOffer2, priorité haute

Réponse : visualExpCompOffer1, visualExpCompOffer2

## Vidéo de formation : Paramètres d’activité (3:02)

Cette vidéo comporte des informations sur les paramètres d’activité.

* Spécifier un objectif pour votre activité
* Définir le niveau de priorité de vos activités
* Planifier les heures de début et de fin de l’activité
* Ajouter des audiences pour la création de rapport afin de créer des filtres de rapport
* Saisir des notes pour vos activités

>[!VIDEO](https://video.tv.adobe.com/v/17381)
