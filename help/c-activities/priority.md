---
description: Target détermine différemment l’activité (ou les activités) à diffuser sur une page en fonction de l’interface Target et de la fonction de création d’activités (compositeur d’expérience visuelle ou compositeur basé sur un formulaire) que vous utilisez.
keywords: paramètres, priorité
seo-description: Target détermine différemment l’activité (ou les activités) à diffuser sur une page en fonction de l’interface Target et de la fonction de création d’activités (compositeur d’expérience visuelle ou compositeur basé sur un formulaire) que vous utilisez.
seo-title: Priorité
solution: Target
title: Priorité
topic: Standard
uuid: 114cd625-2716-4c4c-983b-a7f677717b07
translation-type: tm+mt
source-git-commit: 5405e95cf516f973b69834ac114a1e351cd3040a

---


# Priorité{#priority}

Target détermine différemment l’activité (ou les activités) à diffuser sur une page en fonction de l’interface Target et de la fonction de création d’activités (compositeur d’expérience visuelle ou compositeur basé sur un formulaire) que vous utilisez.

## Compositeur d’expérience visuelle Target Standard/Premium seulement ou compositeur basé sur un formulaire utilisant une mbox globale seulement {#section_4A0A317DFED345649B58B0CB5B410C8B}

Si votre société utilise exclusivement Target Standard/Premium et le compositeur d’expérience visuelle, le contenu de plusieurs activités peut être envoyé pour le même appel. Les activités sont diffusées en suivant le flux décisionnel suivant :

1. L’appel au serveur Target fournit des informations sur l’URL à Target.
1. Target répertorie chaque activité s’exécutant sur cette URL.
1. Target tente d’associer le visiteur à des activités.

   Si le visiteur participe déjà à un test A/B ou à un test multivarié, il sera associé à ce test jusqu’à ce qu’il effectue une conversion. S’il participait précédemment à une activité de ciblage d’expérience, il doit y être associé à nouveau. S’il respecte les règles de l’audience, alors le visiteur est dirigé vers ces activités et dans des expériences spécifiques.

1. Le contenu de toutes les activités et expériences auxquelles le visiteur correspond est envoyé sur la page.
1. Si le contenu de chaque activité fait référence à différents  [sélecteurs CSS](../c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337), tout le contenu est affiché.

   En cas de chevauchement ou de duplication d’un sélecteur CSS, le contenu de l’activité avec la priorité la plus élevée est affiché. Les résultats de toutes les activités qui s’exécutent sur la page sont comptabilisés et reflétés dans les rapports.

   >[!IMPORTANT]
   >
   >Target renvoie le contenu de toutes les activités de la page, en commençant par le contenu de priorité la plus faible, qui est alors remplacé par chaque activité, de la priorité la plus faible à la plus élevée. Dans la plupart des cas, cela provoque l’affichage du contenu de priorité la plus élevée. Néanmoins, si une activité de priorité plus faible modifie la structure du DOM pour la page, il est possible que l’activité de priorité plus élevée ne reconnaisse pas la structure de la page. De ce fait, le contenu de priorité plus faible s’affiche. Les résultats de toutes les activités qui s’exécutent sur la page sont comptabilisés et reflétés dans les rapports.

1. Si plusieurs activités partagent le même niveau de priorité, il y a deux façons de les départager :

   * Si une seule activité utilise le ciblage d’audience, alors l’activité est affichée.
   * Si toutes les activités utilisent le ciblage ou qu’aucune ne l’utilise, l’activité approuvée en premier s’affiche.

## Compositeur d’après les formulaires Target Standard/Premium et compositeur d’expérience visuelle de Target Standard/Premium  {#section_4620253E1CE942DD830724C7822B175F}

>[!NOTE]
>
>Ces informations s’appliquent également aux campagnes en cours d’exécution qui ont été créées dans [!DNL Target Classic].

Si votre société utilise le compositeur d’après les formulaires dans Target Standard/Premium et le compositeur d’expérience visuelle de Target Standard/Premium, le contenu des nombreuses activités du compositeur d’expérience visuelle peut être diffusé, mais seulement une activité du processus d’après les formulaires peut être diffusée. La diffusion des activités est déterminée selon le flux décisionnel suivant :

1. L’appel au serveur Target fournit des informations sur la mbox et l’URL à Target.
1. Target Classic et Standard répertorient toutes les activités qui s’exécutent dans cette mbox.
1. Target tente d’associer le visiteur à des activités.

   Si le visiteur participe déjà à un test A/B ou à un test multivarié, il sera associé à ce test jusqu’à ce qu’il effectue une conversion. S’il participait précédemment à une activité de ciblage d’expérience, il doit y être associé à nouveau. S’il respecte les règles de l’audience, alors le visiteur est dirigé vers ces activités et dans des expériences spécifiques.

1. Si une activité d’après les formulaires a la priorité la plus élevée, le contenu de l’activité est envoyé avec le contenu des activités correspondantes provenant des activités du compositeur d’expérience visuelle.
1. Si une activité du compositeur d’expérience visuelle a la priorité la plus élevée, le contenu des activités du compositeur d’expérience visuelle correspondantes est envoyé, mais aucun contenu des activités Target Classic ou d’après les formulaires n’est envoyé.

   Les résultats de toutes les activités qui s’exécutent sur la page sont comptabilisés et reflétés dans les rapports.

**Exemple**

Si vous avez deux activités, la première ciblant la marque Nike et la seconde les chaussures de sport sans marque, les priorités des deux activités sont vérifiées. Si l’activité Nike a une priorité plus élevée, son contenu s’affiche. Si l’activité portant sur les chaussures de sport sans marque a la priorité la plus élevée, son contenu s’affiche.

Si les deux activités ciblées ont la même priorité, l’activité qui a été consultée le plus récemment s’affiche. Si le visiteur est nouveau sur la page, l’activité qui a été activée le plus récemment s’affiche.

## Compositeur d’après les formulaires de Target Standard/Premium avec mbox non globales  {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

>[!NOTE]
>
>Ces informations s’appliquent également aux campagnes en cours d’exécution qui ont été créées dans Target Classic.

Si votre société utilise d’autres mbox que la mbox globale dans le compositeur d’après les formulaires, le contenu d’une seule activité peut être renvoyé par appel. La diffusion des activités est déterminée selon le flux décisionnel suivant :

1. L’appel au serveur Target fournit des informations sur la mbox et l’URL à Target.
1. Target répertorie toutes les activités qui s’exécutent dans cette mbox.
1. Target tente d’associer le visiteur à l’activité avec la priorité la plus élevée.

   Si le visiteur participe déjà à un test A/B ou à un test multivarié, il sera associé à ce test jusqu’à ce qu’il effectue une conversion. S’il participait précédemment à une activité de ciblage d’expérience, il doit y être associé à nouveau. S’il respecte les règles de l’audience, alors le visiteur est dirigé vers ces activités et dans des expériences spécifiques.

1. Si plusieurs activités partagent le même niveau de priorité, il y a deux façons de les départager :

   * Si une seule activité utilise le ciblage d’audience, alors l’activité est affichée.
   * Si toutes les activités utilisent le ciblage ou qu’aucune ne l’utilise, l’activité approuvée en premier s’affiche.

## Exemples {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>Les valeurs de priorité varient en fonction de vos paramètres. Vous pouvez utiliser les anciens paramètres (Faible, Moyen ou Élevé) ou vous pouvez activer les priorités affinées de 0 à 999. Pour plus d’informations, voir [Paramètres des activités](../c-activities/activity-settings.md#task_C6B2FF8374724933BE79A83549B9CD02).

**Deux campagnes Target Classic utilisent des mbox non globales **

* Campagne 1 : homePageHero, offer1, priorité élevée
* Campagne 2 : homePageHero, offer2, priorité faible

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
>Il s’agit de la même réponse que pour le second cas d’utilisation ci-dessus car Target Classic ne prend pas en charge les collisions de sélecteurs. Target Standard adopte un tel comportement et celui des autres cas d’utilisation quand les sélecteurs peuvent mener à une collision à la fois dans le DOM et visuellement (survenant généralement au niveau de l’éditeur d’expérience ou en mode simulation de campagne).

**Deux activités utilisent les offres créées dans le compositeur d’expérience visuelle et deux campagnes Target Classic**

* Activité 1 : cible-mbox-globale, selector1, visualExpCompOffer1, priorité moyenne à élevée
* Activité 2 : cible-mbox-globale, selector2, visualExpCompOffer2, priorité faible
* Campagne 1 : target-global-mbox, offer1, priorité élevée
* Campagne 2 : target-global-mbox, offer2, priorité faible

Réponse : offer1, visualExpCompOffer2, visualExpCompOffer1

>[!NOTE]
>
>L’ordre des réponses combinées est tel que le contenu classique apparaît en premier (seule une réponse classique sera proposée comme dans le cas d’utilisation n° 1) et que les réponses de l’offre du compositeur d’expérience visuelle sont triées par priorité inversée.

## Vidéo de formation : paramètres d’activité (3:02)

Cette vidéo comporte des informations sur les paramètres d’activité.

* Spécifier un objectif pour votre activité
* Définir le niveau de priorité de vos activités
* Planifier les heures de début et de fin de l’activité
* Ajouter des audiences pour la création de rapport afin de créer des filtres de rapport
* Saisir des notes pour vos activités

>[!VIDEO](https://video.tv.adobe.com/v/17381)