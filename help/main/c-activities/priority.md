---
keywords: paramètres, priorité
description: Découvrez comment [!DNL Adobe Target] détermine différemment l’activité (ou les activités) à diffuser sur une page en fonction du [!DNL Target] et la fonction de création d’activité que vous utilisez.
title: Comment [!DNL Target] Attribuer la priorité aux différentes activités ?
feature: Activities
exl-id: c32f1699-e564-40dd-8ff1-7c75a672c6ef
source-git-commit: 18765a82b5dca94654a412e2012a3f6c1a7b5128
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 40%

---

# Priorité

[!DNL Adobe Target] détermine différemment l’activité (ou les activités) à diffuser sur une page en fonction du [!DNL Target] l’interface et la fonction de création d’activité ([[!UICONTROL Compositeur d’expérience visuelle]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) ou [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md)) que vous utilisez.

## [!DNL Target Standard/Premium] [!UICONTROL Compositeur d’expérience visuelle] uniquement ou [!UICONTROL Compositeur d’expérience d’après les formulaires] à l’aide d’une [!DNL Target] requête uniquement {#section_4A0A317DFED345649B58B0CB5B410C8B}

Si votre entreprise utilise [!DNL Target Standard/Premium] et la variable [!UICONTROL Compositeur d’expérience visuelle] seul, le contenu de plusieurs activités peut être renvoyé pour le même appel. Les activités sont diffusées en suivant le flux décisionnel suivant :

1. La variable [!DNL Target] l’appel au serveur arrive à [!DNL Target] avec des informations sur l’URL.
1. [!DNL Target] répertorie chaque activité s’exécutant sur cette URL.
1. [!DNL Target] tente d’associer le visiteur à des activités.

   Si le visiteur fait déjà partie d’un [!UICONTROL Test A/B] ou [!UICONTROL Test multivarié] , elles correspondent à cette activité jusqu’à ce qu’elles soient converties. S’ils étaient auparavant dans un [!UICONTROL Ciblage d’expérience] , ils doivent y faire à nouveau correspondre. S’il respecte les règles de l’audience, alors le visiteur est dirigé vers ces activités et dans des expériences spécifiques.

1. Le contenu de toutes les activités et expériences auxquelles le visiteur correspond est envoyé sur la page.
1. Si le contenu de chaque activité fait référence à différents [sélecteurs CSS](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337), tout le contenu est affiché.

   En cas de chevauchement ou de duplication d’un sélecteur CSS, le contenu de l’activité avec la priorité la plus élevée est affiché. Les résultats de toutes les activités qui s’exécutent sur la page sont comptabilisés et reflétés dans les rapports.

   >[!IMPORTANT]
   >
   >[!DNL Target] renvoie le contenu de toutes les activités de la page, en commençant par le contenu de priorité la plus faible, qui est alors remplacé par chaque activité, de la priorité la plus faible à la plus élevée. En règle générale, le contenu ayant la priorité la plus élevée s’affiche. Cependant, si une activité de priorité inférieure modifie la structure du DOM pour la page, il est possible que l’activité de priorité supérieure ne reconnaisse pas la structure de la page. Le contenu de priorité inférieure s’affiche donc. Les résultats de toutes les activités qui s’exécutent sur la page sont comptabilisés et reflétés dans les rapports.

1. Si plusieurs activités partagent un niveau de priorité, il existe deux brise-glace :

   * Si une seule activité utilise le ciblage d’audience, alors l’activité est affichée.
   * Si tout ou aucun ciblage est effectué, l’activité qui a été approuvée en premier s’affiche.

## [!DNL Target Standard/Premium] [!UICONTROL Compositeur d’expérience d’après les formulaires] et [!DNL Target Standard/Premium] [!UICONTROL Compositeur d’expérience visuelle] {#section_4620253E1CE942DD830724C7822B175F}

>[!NOTE]
>
>Ces informations s’appliquent également aux campagnes en cours d’exécution qui ont été créées dans [!DNL Target Classic].

Si votre entreprise utilise la variable [!UICONTROL Compositeur d’expérience d’après les formulaires] in [!DNL Target Standard/Premium] et la variable [!DNL Target Standard/Premium] [!UICONTROL Compositeur d’expérience visuelle], puis du contenu de plusieurs [!UICONTROL Compositeur d’expérience visuelle] les activités peuvent être diffusées, mais une seule activité du workflow basé sur les formulaires. La diffusion des activités est déterminée selon le flux décisionnel suivant :

1. [!DNL Target] l’appel au serveur arrive à [!DNL Target] avec des informations sur la variable [!DNL Target] requête et URL.
1. [!DNL Target Classic] et [!DNL Target Standard/Premium] extraire toutes les activités qui s’exécutent ; [!DNL Target] requête.
1. [!DNL Target] tente d’associer le visiteur à des activités.

   Si le visiteur fait déjà partie d’un [!UICONTROL Test A/B] ou [!UICONTROL Test multivarié] , ils correspondent à ce test jusqu’à ce qu’ils se convertissent. S’ils étaient auparavant dans un [!UICONTROL Ciblage d’expérience] , ils doivent y faire à nouveau correspondre. S’il respecte les règles de l’audience, alors le visiteur est dirigé vers ces activités et dans des expériences spécifiques.

1. Si une activité d’après les formulaires a la priorité la plus élevée, le contenu de cette activité est renvoyé avec tout le contenu de l’activité correspondant provenant de [!UICONTROL Compositeur d’expérience visuelle] activités.
1. Si une [!UICONTROL Compositeur d’expérience visuelle] l’activité est la priorité la plus élevée, puis le contenu de toutes les activités correspondantes [!UICONTROL Compositeur d’expérience visuelle] Les activités sont renvoyées, mais pas [!DNL Target Classic] ou le contenu de l’activité d’après les formulaires est renvoyé.

   Les résultats de toutes les activités qui s’exécutent sur la page sont comptabilisés et reflétés dans les rapports.

**Exemple**

Si vous avez deux activités, l’une ciblant le mot-clé de recherche de marque &quot;Nike&quot; et l’autre ciblant le mot-clé sans marque &quot;baskets&quot;, les priorités des deux activités sont vérifiées. Si l’activité Nike a une priorité plus élevée, son contenu s’affiche. Si l’activité portant sur les chaussures de sport sans marque a la priorité la plus élevée, son contenu s’affiche.

Si les deux activités ciblées ont la même priorité, l’activité qui a été consultée le plus récemment s’affiche. Si le visiteur est nouveau sur la page, l’activité qui a été activée le plus récemment s’affiche.

## [!DNL Target Standard/Premium] [!UICONTROL Compositeur d’expérience d’après les formulaires] avec non global [!DNL Target] requests {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

>[!NOTE]
>
>Ces informations s’appliquent également aux activités en cours d’exécution créées dans [!DNL Target Classic].

Si votre entreprise utilise [!DNL Target] demandes autres que la demande globale [!DNL Target] dans le compositeur d’après les formulaires, le contenu d’une seule activité peut être renvoyé par appel. La diffusion des activités est déterminée selon le flux décisionnel suivant :

1. La variable [!DNL Target] l’appel au serveur arrive à [!DNL Target] avec des informations sur la variable [!DNL Target] requête et URL.
1. [!DNL Target] extrait toutes les activités s’exécutant dans [!DNL Target] requête.
1. [!DNL Target] tente de faire correspondre le visiteur à l’activité de priorité la plus élevée.

   Si le visiteur fait déjà partie d’un [!UICONTROL Test A/B] ou [!UICONTROL Test multivarié] , elles correspondent à cette activité jusqu’à ce qu’elles soient converties. S’ils étaient auparavant dans un [!UICONTROL Ciblage d’expérience] , ils doivent y faire à nouveau correspondre. S’il respecte les règles de l’audience, alors le visiteur est dirigé vers ces activités et dans des expériences spécifiques.

1. Si plusieurs activités partagent un niveau de priorité, il existe deux brise-glace :

   * Si une seule activité utilise le ciblage d’audience, alors l’activité est affichée.
   * Si tout ou aucun ciblage est effectué, l’activité qui a été approuvée en premier s’affiche.

## Exemples {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>Les valeurs de priorité varient en fonction de vos paramètres. Vous pouvez utiliser les paramètres hérités de [!UICONTROL Faible], [!UICONTROL Volume moyen], ou [!UICONTROL Élevée]ou vous pouvez activer les priorités affinées de 0 à 999. Pour plus d’informations, voir [Paramètres d’activité](/help/main/c-activities/activity-settings.md#task_C6B2FF8374724933BE79A83549B9CD02).

**Deux [!DNL Target Classic] Les activités utilisent des activités non globales [!DNL Target] requests**

* Activité 1 : homePageHero, offer1, priorité élevée
* Activité 2 : homePageHero, offer2, priorité faible

Réponse : offer1

**Deux activités n’utilisent que les offres créées dans le compositeur d’expérience visuelle pour différents sélecteurs**

* Activité 1 : target-global-mbox, selector1, visualExpCompOffer1, priorité faible
* Activité 2 : target-global-mbox, selector2, visualExpCompOffer2, priorité haute

Réponse : visualExpCompOffer1, visualExpCompOffer2

**Deux activités n’utilisent que les offres créées dans le compositeur d’expérience visuelle pour le même sélecteur**

* Activité 1 : target-global-mbox, selector1, visualExpCompOffer1, priorité faible
* Activité 2 : target-global-mbox, selector1, visualExpCompOffer2, priorité haute

Réponse : visualExpCompOffer1, visualExpCompOffer2

>[!NOTE]
>
>Il s’agit de la même réponse que dans le deuxième cas d’utilisation ci-dessus car [!DNL Target Classic] ne gérait pas les collisions de sélecteurs. [!DNL Target Standard/Premium] capture ce comportement et d’autres cas d’utilisation lorsque les sélecteurs peuvent entrer en collision à la fois dans le modèle DOM et visuellement (généralement au niveau de l’éditeur d’expérience ou en mode simulation d’activité).

**Deux activités utilisent les offres créées dans la variable [!UICONTROL Compositeur d’expérience visuelle] et deux [!DNL Target Classic] activités**

* Activité 1 : cible-mbox-globale, selector1, visualExpCompOffer1, priorité moyenne à élevée
* Activité 2 : cible-mbox-globale, selector2, visualExpCompOffer2, priorité faible
* Activité 1 : target-global-mbox, offer1, priorité élevée
* Activité 2 : target-global-mbox, offer2, priorité faible

Réponse : offer1, visualExpCompOffer2, visualExpCompOffer1

>[!NOTE]
>
>L&#39;ordre des réponses combinées est le suivant : [!DNL Target Classic] le contenu vient en premier. Un seul [!DNL Target Classic] la réponse est traitée comme dans le cas d’utilisation 1, puis [!UICONTROL Compositeur d’expérience visuelle] réponses d’offre classées par priorité inversée.

## Vidéo de formation : Paramètres d’activité (3:02)

Cette vidéo comporte des informations sur les paramètres d’activité.

* Spécifier un objectif pour votre activité
* Définir le niveau de priorité de vos activités
* Planifier les heures de début et de fin de l’activité
* Ajouter des audiences pour la création de rapport afin de créer des filtres de rapport
* Saisir des notes pour vos activités

>[!VIDEO](https://video.tv.adobe.com/v/17381)
